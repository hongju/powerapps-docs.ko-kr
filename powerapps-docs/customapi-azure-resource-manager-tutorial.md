---
title: "사용자 지정 커넥터로 Azure Active Directory 사용 | Microsoft Docs"
description: "Azure Active Directory 인증을 사용하여 Azure Resource Manager에 대한 사용자 지정 커넥터를 만드는 방법을 알아봅니다."
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
ms.date: 05/03/2017
ms.author: mblythe
ms.openlocfilehash: c62a927ae6a7e7b6cf6b101d84e3ba1fe15cccc5
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-powerapps"></a>PowerApps에서 사용자 지정 커넥터로 Azure Active Directory 사용
ARM(Azure Resource Manager)을 사용하여 Azure에서 데이터베이스, 가상 머신 및 웹앱과 같은 솔루션의 구성 요소를 관리할 수 있습니다. 이 자습서에서는 Azure Active Directory에서 인증을 활성화하고, 사용자 지정 커넥터로 ARM API 중 하나를 등록한 다음 PowerApps에서 연결하는 방법을 설명합니다. 이는 앱에서 직접 Azure 리소스를 관리하려는 경우에 유용합니다. ARM에 대한 자세한 내용은 [Azure Resource Manager 개요](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)를 참조하세요.

## <a name="prerequisites"></a>필수 조건
* [Azure 구독](https://azure.microsoft.com/free/)
* [PowerApps 계정](https://powerapps.microsoft.com)
* 이 자습서에서 사용되는 [샘플 OpenAPI 파일](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json)

## <a name="enable-authentication-in-azure-active-directory"></a>Azure Active Directory에서 인증 활성화
먼저 ARM API 끝점을 호출할 때 인증을 수행하는 AAD(Azure Active Directory) 응용 프로그램을 만들어야 합니다.

1. [Azure Portal](https://portal.azure.com)에 로그인합니다.  하나 이상의 Azure Active Directory 테넌트가 있는 경우 오른쪽 위 모퉁이에서 사용자 이름을 확인하여 올바른 디렉터리로 로그인하고 있는지 확인합니다.
   
    ![사용자 이름](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. 왼쪽 메뉴에서 **더 많은 서비스**를 클릭합니다.  **필터** 텍스트 상자에 **Azure Active Directory**를 입력한 다음 **Azure Active Directory**를 클릭합니다.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    Azure Active Directory 블레이드가 열립니다.   
3. Azure Active Directory 블레이드의 메뉴에서 **앱 등록**을 클릭합니다.
   
    ![앱 등록](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. 등록된 응용 프로그램의 목록에서 **추가**를 클릭합니다.
   
    ![추가 단추](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. 응용 프로그램에 대한 이름을 입력하고, **웹앱/API**를 선택된 채로 둔 다음 **로그온 URL**에 `https://login.windows.net`을 입력합니다.  **만들기**를 클릭합니다.  
   
    ![새 앱 형식](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. 목록에서 새 응용 프로그램을 클릭합니다.
   
    ![목록의 새 앱](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    등록된 앱 블레이드가 열립니다.  **응용 프로그램 ID**를 적어 둡니다.  나중에 필요합니다.
7. 설정 블레이드도 열려야 합니다.  그렇지 않은 경우 **설정** 단추를 클릭합니다.
   
    ![설정 단추](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. 설정 블레이드에서 **회신 URL**을 클릭합니다. URL의 목록에서 `https://msmanaged-na.consent.azure-apim.net/redirect`를 추가하고 **저장**을 클릭합니다.
   
    ![회신 URL](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. 다시 설정 블레이드에서 **필수 권한**을 클릭합니다.  필수 권한 블레이드에서 **추가**를 클릭합니다.
   
    ![필수 권한](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    API 액세스 추가 블레이드가 열립니다.
10. **API 선택**을 클릭합니다. 열리는 블레이드에서 Azure Service Management API에 대한 옵션을 클릭하고 **선택**을 클릭합니다.
    
    ![API 선택](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. **사용 권한 선택**을 클릭합니다.  *위임된 권한* 아래에서 **Azure Service Management에 조직 사용자로 액세스**를 클릭한 다음 **선택**을 클릭합니다.
    
    ![위임된 권한](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. API 액세스 추가 블레이드에서 **완료**를 클릭합니다.
13. 다시 설정 블레이드에서 **키**를 클릭합니다.  키 블레이드에서 키에 대한 설명을 입력하고, 만료 기간을 선택한 다음 **저장**을 클릭합니다.  새 키가 표시됩니다.  역시 나중에 필요하므로 키 값을 기록해 두십시오.  이제 Azure Portal을 닫을 수 있습니다.
    
    ![키 만들기](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-powerapps"></a>PowerApps에서 연결 추가
이제 AAD 응용 프로그램을 구성했으므로 사용자 지정 커넥터를 추가해 보겠습니다.

1. [powerapps.com](https://web.powerapps.com)의 왼쪽 메뉴에서 **연결**을 선택합니다. 줄임표(**...**)를 선택한 다음 오른쪽 위 모서리에서 **사용자 지정 커넥터 관리**를 선택합니다.
   
     **팁**: 모바일 브라우저에서 사용자 지정 커넥터를 관리할 수 있는 위치를 찾을 수 없는 경우 왼쪽 위 모서리의 메뉴 아래에 있을 수 있습니다.
   
    ![사용자 지정 커넥터 만들기](./media/customapi-azure-resource-manager-tutorial/managecustomapi.png)  
2. **사용자 지정 커넥터 만들기**를 선택합니다.
   
    ![사용자 지정 커넥터 속성](./media/customapi-azure-resource-manager-tutorial/newcustomapi.png)
3. 연결에 대한 이름을 입력한 다음 [샘플 ARM OpenAPI 파일](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json)을 업로드합니다.  **계속**을 클릭합니다.  
   
    ![새 API 끝점에 연결](./media/customapi-azure-resource-manager-tutorial/createcustom.png)
4. 다음 화면에서 OpenAPI 파일은 인증을 위해 AAD 응용 프로그램을 사용하므로 PowerApps에 응용 프로그램에 대한 일부 정보를 제공해야 합니다.  **클라이언트 ID** 아래에 앞에서 적어둔 AAD **응용 프로그램 ID**를 입력합니다.  클라이언트 비밀의 경우 **키**를 사용합니다.  마지막으로 **리소스 URL**에 `https://management.core.windows.net/`을 입력합니다.
   
    **중요**: 후행 슬래시를 포함하여 위에 쓰인 대로 리소스 URL을 정확히 포함해야 합니다.
   
    ![OAuth 설정](./media/customapi-azure-resource-manager-tutorial/oauthsettings.png)
5. 이제 사용자 지정 커넥터가 등록되었으므로 PowerApps 또는 Microsoft Flow 내에서 사용될 수 있습니다.
   
    ![추가된 사용자 지정 커넥터](./media/customapi-azure-resource-manager-tutorial/createdcustomapi.png)
   
    **참고**: 샘플 OpenAPI는 전체 ARM 작업 집합을 정의하지 않고 현재 [모든 구독 나열](https://msdn.microsoft.com/library/azure/dn790531.aspx) 작업만 포함합니다.  [온라인 OpenAPI 편집기](http://editor.swagger.io/)를 사용하여 이 OpenAPI 파일을 편집하거나 다른 OpenAPI 파일을 만들 수 있습니다. 이 프로세스는 AAD를 사용하여 인증되는 모든 RESTful API에 액세스하는 데 사용될 수 있습니다.

## <a name="next-steps"></a>다음 단계
앱을 만드는 방법에 대한 자세한 내용은 [데이터에서 앱 만들기](get-started-create-from-data.md)를 참조하세요.

앱에서 흐름을 사용하는 방법에 대한 자세한 내용은 [앱에서 흐름 시작](using-logic-flows.md)을 참조하세요.

사용자 지정 커넥터에 대한 질문을 하거나 의견을 제출하려면 [커뮤니티에 가입합니다](https://aka.ms/powerapps-community).

