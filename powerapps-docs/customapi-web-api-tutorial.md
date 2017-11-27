---
title: "Web API용 사용자 지정 커넥터 빌드 | Microsoft Docs"
description: "PowerApps에서 Azure Active Directory 인증으로 ASP.NET Web API를 만드는 방법을 설명합니다."
services: 
suite: powerapps
documentationcenter: 
author: mgblythe
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: mblythe
ms.openlocfilehash: 6ec78949915c8c82a88def492c249902afef6a88
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="build-a-custom-connector-for-a-web-api-in-powerapps"></a>PowerApps에서 Web API용 사용자 지정 커넥터 빌드
이 자습서에서는 PowerApps에서 ASP.NET Web API 빌드를 시작하고, Azure Web Apps에서 호스트하고, Azure Active Directory 인증을 활성화한 다음 ASP.NET Web API를 등록하는 방법을 보여 줍니다. API를 등록한 후에 연결하고 앱에서 호출할 수 있습니다.

## <a name="prerequisites"></a>필수 조건
* [Azure 구독](https://azure.microsoft.com/en-us/free/)
* [PowerApps 계정](https://powerapps.microsoft.com)
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 이상

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>ASP.NET Web API를 만들고 Azure에 배포
1. Visual Studio에서 **파일** > **새 프로젝트**를 클릭하여 새 C# ASP.NET 웹 응용 프로그램을 만듭니다.
   
    ![새 웹앱](./media/customapi-web-api-tutorial/newwebapp.png)
2. **Web API** 템플릿을 선택합니다.  **클라우드의 호스트**를 선택한 상태로 둡니다.  **인증 변경**을 클릭합니다.
   
    ![새 웹 프로젝트 템플릿](./media/customapi-web-api-tutorial/new-web-api.png)
3. **인증 없음**을 선택한 다음 **확인**을 클릭합니다.
   
    ![인증 없음](./media/customapi-web-api-tutorial/noauth.png)
4. **새 ASP.NET 프로젝트** 대화 상자에서 **확인**을 클릭합니다.  Microsoft Azure 웹앱 구성 대화 상자가 나타납니다.
   
    ![Microsoft Azure 웹앱 구성](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Azure 계정을 선택하고, **웹앱 이름**을 입력하고(또는 기본값을 그대로 적용) Azure **구독**을 선택합니다.  **App Service 계획**을 선택하거나 만듭니다(구독 내에서 Web Apps의 컬렉션).  **리소스 그룹**을 선택하거나 만듭니다(구독 내에서 Azure 리소스의 그룹화).  웹앱이 배포되어야 할 지역을 선택합니다.  Web API에 대해 필요한 경우 Azure **데이터베이스 서버**를 만들거나 선택합니다.  마지막으로 **확인**을 클릭합니다.
5. Web API를 빌드합니다.
   
    **참고**: Web API에 대한 코드가 아직 준비되지 않은 경우 자습서 [ASP.NET Web API 2 시작(C#)](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api)을 시도하세요.
6. Web API를 PowerApps에 연결하려면 해당 작업을 설명하는 [OpenAPI](http://swagger.io/) 파일이 필요합니다.  [온라인 편집기](http://editor.swagger.io/)를 사용하여 사용자 고유의 OpenAPI를 작성할 수 있지만 이 자습서에서는 [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md)이라는 오픈 소스 도구를 사용합니다.  **도구** > **NuGet 패키지 관리자** > **패키지 관리자 콘솔**을 클릭한 다음 패키지 관리자 콘솔에서 `Install-Package Swashbuckle` 명령을 입력하여 Visual Studio 프로젝트에 Swashbuckle Nuget 패키지를 설치합니다.
   
    ![Install-Package Swashbuckle](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
    **팁**: Swashbuckle을 설치한 후 Web API 응용 프로그램을 실행할 때 이제 OpenAPI 파일이 URL `http://<your root URL>/swagger/docs/v1`에서 생성됩니다.  생성된 사용자 인터페이스는 `http://<your root URL>/swagger`에서도 제공됩니다.
7. Web API가 준비되면 Azure에 게시합니다. Visual Studio에서 게시하려면 솔루션 탐색기에서 웹 프로젝트를 마우스 오른쪽 단추로 클릭하고, **게시...**을 클릭한 다음 게시 대화 상자에 표시되는 메시지를 따릅니다.
8. `https://<azure-webapp-url>/swagger/docs/v1`로 이동하여 OpenAPI JSON을 검색합니다.  콘텐츠를 JSON 파일로 저장합니다.  브라우저에 따라 텍스트를 복사하여 빈 텍스트 파일에 붙여넣어야 할 수도 있습니다.   
   
    **중요**: 중복된 작업 ID를 사용하는 OpenAPI 문서는 유효하지 않습니다. 샘플 C# 템플릿을 사용하는 경우 작업 ID `Values_Get`은 두 번 반복됩니다. 인스턴스 하나를 `Value_Get`으로 변경하고 다시 게시하여 이를 해결할 수 있습니다. 이 자습서에서 [샘플 OpenAPI 파일](http://pwrappssamples.blob.core.windows.net/samples/webAPI.json)을 다운로드할 수도 있습니다. 사용하기 전에 메모를 제거하십시오(`//`로 시작).

## <a name="set-up-azure-active-directory-authentication"></a>Azure Active Directory 인증 설정
이제 Azure에서 두 개의 AAD(Azure Active Directory) 응용 프로그램을 만듭니다.  이 작업을 수행하는 방법의 예제는 [Azure Resource Manager 자습서](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory)를 참조하세요.

**중요** 두 앱 모두 동일한 디렉터리에 있어야 합니다.

### <a name="first-aad-application-securing-the-web-api"></a>첫 번째 AAD 응용 프로그램: Web API 보안 설정
첫 번째 AAD 응용 프로그램은 Web API 보안을 설정하는 데 사용됩니다. 이름을 **webAPI**로 지정합니다.  다음 값으로 위의 연결된 자습서 단계("Azure Active Directory에서 인증 활성화"라는 제목의 섹션)를 따릅니다.

* 로그온 URL: `https://login.windows.net`
* 회신 URL: `https://<your-root-url>/.auth/login/aad/callback`
* 클라이언트 키에 대해서는 필요하지 않습니다.
* 사용 권한을 위임할 필요가 없습니다.
* **중요**: 응용 프로그램 ID를 적어 둡니다.  나중에 필요합니다.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>두 번째 AAD 응용 프로그램: 사용자 지정 커넥터 및 위임된 액세스 보안 설정
두 번째 AAD 응용 프로그램은 사용자 지정 커넥터 등록을 보호하고 첫 번째 응용 프로그램에 의해 보호된 Web API에 대한 위임된 액세스를 획득하는 데 사용됩니다. 이 이름을 **webAPI-customAPI**로 지정합니다.

* 로그온 URL: `https://login.windows.net`
* 회신 URL: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Web API에 대한 위임된 액세스를 갖도록 권한을 추가합니다.
* 이 응용 프로그램의 응용 프로그램 ID도 나중에 필요하므로 기록합니다.
* 클라이언트 키를 생성하고 안전한 위치에 저장합니다. 이 키는 나중에 필요합니다.

## <a name="add-authentication-to-your-azure-web-app"></a>Azure 웹앱에 인증 추가
1. [Azure Portal](https://portal.azure.com)에 로그인한 다음 첫 번째 섹션에서 배포한 웹앱을 찾습니다.
2. **설정**을 클릭한 다음 **인증/권한 부여**를 선택합니다.
3. **App Service 인증**을 켠 다음 **Azure Active Directory**를 선택합니다.  다음 블레이드에서 **기본**을 선택합니다.  
4. **기존 AD 앱 선택**을 클릭하고, 앞에서 만든 **webAPI** AAD 응용 프로그램을 선택합니다.

이제 AAD를 사용하여 웹 응용 프로그램을 인증할 수 있습니다.

## <a name="add-the-custom-connector-to-powerapps"></a>PowerApps에 사용자 지정 커넥터 추가
1. OpenAPI 파일을 수정하여 웹앱에 사용되는 `securityDefintions` 개체 및 AAD 인증을 추가합니다. **host** 속성을 사용하는 OpenAPI 파일의 섹션은 다음과 같이 표시되어야 합니다.

```javascript
// File header should be above here...

"host": "<your-root-url>",
"schemes": [
    "https"         //Make sure this is https!
],
"securityDefinitions": {
    "AAD": {
        "type": "oauth2",
        "flow": "implicit",
        "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
        "scopes": {}
    }
},

// The rest of the OpenAPI document follows...
```

1. [PowerApps](https://web.powerapps.com)를 찾고 [PowerApps에서 사용자 지정 커넥터 등록 및 사용](register-custom-api.md)에 설명된 대로 사용자 지정 커넥터를 추가합니다.
2. OpenAPI 파일을 업로드하면 마법사에서 Web API에 대해 AAD 인증을 사용하고 있는지 자동 검색합니다.
3. 사용자 지정 커넥터에 대한 AAD 인증을 구성합니다.  
   
   * **클라이언트 ID**: *webAPI-CustomAPI의 클라이언트 ID*
   * **비밀**: *webAPI-CustomAPI의 클라이언트 키*
   * **로그인 URL**: `https://login.windows.net`
   * **ResourceUri**: *webAPI의 클라이언트 ID*
4. **만들기**를 클릭하고 사용자 지정 커넥터에 대한 연결을 만듭니다.

## <a name="next-steps"></a>다음 단계
[Azure Resource Manager 사용자 지정 커넥터 자습서](customapi-azure-resource-manager-tutorial.md)를 안내합니다.

