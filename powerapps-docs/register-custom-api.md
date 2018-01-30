---
title: "사용자 지정 커넥터 등록 및 사용 | Microsoft Docs"
description: "OpenAPI 및 Postman을 사용하여 PowerApps에서 사용자 지정 커넥터를 등록하고 사용합니다."
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
ms.date: 05/05/2017
ms.author: mblythe
ms.openlocfilehash: 2eac422675fc8741848ab90777824a10ec9e0e1e
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="register-and-use-custom-connectors-in-powerapps"></a>PowerApps에서 사용자 지정 커넥터 등록 및 사용
PowerApps를 사용하면 기존 응용 프로그램 코드 없이 모든 기능을 갖춘 앱을 빌드할 수 있습니다. 하지만 경우에 따라 PowerApps 기능을 확장해야 하고 웹 서비스가 적합할 수 있습니다. 사용자 앱은 서비스에 연결하고, 작업을 수행하고, 데이터를 다시 가져올 수 있습니다. PowerApps를 사용하여 연결하려는 웹 서비스가 있는 경우 서비스를 사용자 지정 커넥터로 등록합니다. 이 프로세스를 사용하여 PowerApps에서 필요한 인증, 지원 작업 및 해당 작업의 매개 변수 및 출력을 비롯한 웹 API의 특성을 이해할 수 있습니다.

이 항목에서는 사용자 지정 커넥터를 등록하고 사용하는 데 필요한 단계를 살펴보고 Azure Cognitive Services [텍스트 분석 API](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api)를 예로 듭니다. 이 API는 전달한 텍스트에서 언어, 감정 및 핵심 구를 식별합니다. 다음 이미지는 서비스, 서비스에서 생성한 사용자 지정 커넥터 및 API를 호출하는 앱 간의 상호 작용을 보여줍니다.

![API, 사용자 지정 커넥터 및 앱](./media/register-custom-api/intro-graphic.png)

## <a name="prerequisites"></a>필수 조건
* [PowerApps 계정](https://powerapps.microsoft.com)
* JSON 형식의 OpenAPI 파일, OpenAPI 정의에 대한 URL 또는 API에 대한 Postman 컬렉션입니다. 이러한 항목이 하나도 없다면 사용자를 위한 지침을 제공합니다.
* 사용자 지정 커넥터에 아이콘으로 사용할 이미지입니다(선택 사항).

## <a name="steps-in-the-custom-connector-process"></a>사용자 지정 커넥터 프로세스의 단계
사용자 지정 커넥터 프로세스에는 아래에서 간략하게 설명한 여러 단계가 있습니다. 이 문서에서는 문서의 나머지 부분에서 3~6단계에 집중하도록 몇 가지 형식의 인증된 액세스 권한이 있는 RESTful API가 이미 있다고 가정합니다. 1 및 2단계의 예제는 [PowerApps에 사용자 지정 Web API 만들기](customapi-web-api-tutorial.md)를 참조하세요.

1. 선택한 언어 및 플랫폼으로 **RESTful API를 빌드**합니다. Microsoft 기술에서는 다음 중 하나를 사용하는 것이 좋습니다.
   
   * Azure 기능
   * Azure Web Apps
   * Azure API Apps
2. 다음과 같은 인증 메커니즘 중 하나를 사용하여 **API를 보호**합니다. API에 인증되지 않은 액세스를 허용할 수 있지만 권장하지 않습니다.
   
   * Azure Active Directory 자세한 내용은 [PowerApps에서 사용자 지정 커넥터로 Azure Active Directory 사용](customapi-azure-resource-manager-tutorial.md)을 참조하세요.
   * Dropbox, Facebook 및 SalesForce와 같은 특정 서비스의 경우 OAuth 2.0
   * 제네릭 OAuth 2.0
   * API 키
   * 기본 인증
3. 해당 PowerApps가 데이터베이스에 연결할 수 있도록 업계 표준의 두 가지 방법 중 하나에서 **API를 설명**합니다.
   
   * OpenAPI 파일(Swagger 파일이라고도 함) - 등록 프로세스의 일부로 4단계에서 OpenAPI 파일을 빌드할 수 있습니다.
   * Postman 컬렉션
4. PowerApps에서 마법사를 사용하여 **사용자 지정 커넥터를 등록**합니다. 여기서 API 설명, 보안 정보 및 기타 정보를 지정합니다.

5. 앱에서 **사용자 지정 커넥터를 사용**합니다. 앱에서 API에 대한 연결을 만들고 PowerApps에서 네이티브 함수를 호출하는 것처럼 API에서 제공하는 모든 작업을 호출합니다.

6. PowerApps에서 다른 데이터를 연결하는 것처럼 **사용자 지정 커넥터를 공유**합니다. 이 단계는 옵션이지만 여러 앱 작성자가 사용자 지정 커넥터를 공유하는 것이 효율적입니다.

## <a name="describe-your-api"></a>API 설명
일부 형식의 인증된 액세스 권한을 가진 API가 있다고 가정하여 PowerApps가 데이터베이스에 연결할 수 있도록 API를 설명하는 방법이 필요합니다. 그러려면 OpenAPI 파일 또는 Postman 컬렉션을 만듭니다. 여기서 다음을 비롯한 *모든* REST API 끝점을 수행할 수 있습니다.

* 공개적으로 사용할 수 있는 API입니다. 몇 가지 예로 [Spotify](https://developer.spotify.com/), [Uber](https://developer.uber.com/), [Slack](https://api.slack.com/), [Rackspace](http://docs.rackspace.com/) 등이 있습니다.
* Azure, AWS(Amazon Web Services), Heroku, Google 클라우드 등을 비롯한 클라우드 호스팅 공급자에 만들고 배포한 API입니다.
* API가 공용 인터넷에 노출되는 동안 네트워크에 배포된 사용자 지정 기간 업무 API입니다.

OpenAPI 파일 및 Postman 컬렉션은 다른 형식을 사용하지만 둘 다 API의 작업 및 매개 변수를 설명하는 언어 독립적인 머신 읽기 가능 문서입니다.

* API가 기반으로 하는 언어 및 플랫폼에 따라 다양한 도구를 사용하여 이러한 문서를 생성할 수 있습니다. OpenAPI 파일의 예제는 [텍스트 분석 API 설명서](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/export?DocumentFormat=Swagger&ApiName=Azure)를 참조하세요.
* 아직 API에 OpenAPI 파일이 없고 새로 만들지 않으려는 경우 Postman 컬렉션을 사용하여 사용자 지정 커넥터를 쉽게 만들 수 있습니다. 자세한 정보는 [Postman 컬렉션 만들기](postman-collection.md)를 참조하세요.
* PowerApps는 이면에서 궁극적으로 OpenAPI를 사용하므로 Postman 컬렉션을 구문 분석하고 OpenAPI 정의 파일로 변환합니다.

> [!NOTE]
> 파일 크기는 1MB 미만이어야 합니다.

### <a name="getting-started-with-openapi-and-postman"></a>OpenAPI 및 Postman 시작
* OpenAPI를 처음 사용하는 경우 swagger.io 사이트에서 [OpenAPI 시작](http://swagger.io/getting-started/)을 참조하세요.
* Postman을 처음 사용하는 경우 사이트에서 [Postman 앱](https://www.getpostman.com/apps)을 설치합니다.
* API가 Azure API Apps 또는 Azure Functions로 빌드된 경우 자세한 정보는 [PowerApps 및 Microsoft Flow에 Azure 호스티드 API 내보내기](https://docs.microsoft.com/azure/app-service/app-service-export-api-to-powerapps-and-flow)를 참조하세요.

## <a name="register-your-custom-connector"></a>사용자 지정 커넥터 등록
이제 OpenAPI 파일 또는 Postman 컬렉션을 사용하여 사용자 지정 커넥터를 PowerApps에 등록합니다.

1. [powerapps.com](https://web.powerapps.com)의 왼쪽 메뉴에서 **연결**을 선택합니다. 줄임표(**...**)를 선택한 다음 오른쪽 위 모서리에서 **사용자 지정 커넥터 관리**를 선택합니다.
   
     > [!TIP]
> 모바일 브라우저에서 사용자 지정 커넥터를 관리할 위치를 찾을 수 없는 경우 왼쪽 위 모서리의 메뉴 아래에 있을 수 있습니다.
   
    ![사용자 지정 커넥터 만들기](./media/register-custom-api/managecustomapi.png)  
2. **사용자 지정 커넥터 만들기**를 선택합니다.
   
    ![사용자 지정 커넥터 속성](./media/register-custom-api/newcustomapi.png)
3. **일반** 탭에서 사용자 지정 커넥터를 만드는 방법을 선택합니다.
   
   * OpenAPI 파일 업로드

   * OpenAPI URL 사용

   * Postman 컬렉션 V1 업로드
     
     ![사용자 지정 커넥터를 만드는 방법](./media/register-custom-api/choosehowtocreate.png)
     
     사용자 지정 커넥터에 아이콘 업로드 설명, 호스트 및 기본 URL 필드는 일반적으로 OpenAPI 파일의 정보로 자동으로 채워집니다. 자동으로 채워지지 않는 경우 해당 필드에 정보를 추가할 수 있습니다. **계속**을 선택합니다.
4. **보안** 탭에서 인증 속성을 입력합니다.
   
    ![인증 형식](./media/register-custom-api/authenticationtypes.png)
   
   * 인증 형식은 OpenAPI `securityDefinitions` 개체에서 정의된 내용에 따라 자동으로 채워집니다. OAuth2.0 예제는 다음과 같습니다.
     
       ```
       "securityDefinitions": {
           "AAD": {
           "type": "oauth2",
           "flow": "accessCode",
           "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
           "scopes": {}
           }
       },
       ```
   * OpenAPI 파일이 `securityDefintions` 개체를 사용하지 않는 경우 추가 값이 필요하지 않습니다.
   * Postman 컬렉션을 사용할 때 OAuth 2.0 또는 기본과 같은 지원되는 인증 형식을 사용하는 경우에만 인증 형식이 자동으로 채워집니다.
   * AAD(Azure Active Directory) 인증을 설정하는 예제는 [PowerApps에서 사용자 지정 Web API 만들기](customapi-web-api-tutorial.md#set-up-azure-active-directory-authentication)를 참조하세요.
5. **정의** 탭에서 OpenAPI 파일 또는 Postman 컬렉션에 정의된 모든 작업은 요청 및 응답 값을 사용하여 자동으로 채워집니다. 모든 필수 작업이 정의된 경우 이 화면에서 변경하지 않고 등록 프로세스의 6단계로 이동할 수 있습니다.
   
    ![정의 탭](./media/register-custom-api/definitiontab.png)
   
    기존 작업을 편집하거나 사용자 지정 커넥터에 새 작업을 추가하려는 경우 아래를 계속 읽어보세요.
   
   1. OpenAPI 파일 또는 Postman 컬렉션에 없는 새 작업을 추가하려는 경우 왼쪽 창에서 **새 작업**을 선택하고, **일반** 섹션에서 작업의 이름, 설명 및 표시 유형으로 채웁니다.
   2. **요청** 섹션의 오른쪽 위에 있는 **샘플에서 가져오기**를 선택합니다. 오른쪽의 양식에서 샘플 요청을 붙여넣습니다. 샘플 요청은 일반적으로 API 설명서에서 지원됩니다. 여기서 **동사**, **요청 URL**, **헤더** 및 **본문** 필드를 채울 정보를 가져올 수 있습니다. 예제는 [텍스트 분석 API 설명서](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6)를 참조하세요.
      
       ![샘플에서 가져오기](./media/register-custom-api/importfromsample.png)

   3. **가져오기**를 선택하여 요청 정의를 완성합니다. 비슷한 방법으로 응답을 정의합니다.
6. 모든 작업을 정의하면 **만들기**를 선택하여 사용자 지정 커넥터를 만듭니다.
7. 사용자 지정 커넥터를 만들면 **테스트** 탭으로 이동하여 API에서 정의된 작업을 테스트합니다. 연결을 선택하고 입력 매개 변수를 제공하여 작업을 테스트합니다.
   
    ![사용자 지정 커넥터 테스트](./media/register-custom-api/testcustomapi.png)
   
    호출에 성공하면 유효한 응답을 얻을 수 있습니다.
   
    ![API 응답 테스트](./media/register-custom-api/testapiresponse.png)

## <a name="use-your-custom-connector"></a>사용자 지정 커넥터 사용
이제 API를 등록했으므로 다른 데이터 원본처럼 앱에 사용자 지정 커넥터를 추가합니다. 여기에서 간단한 예를 살펴봅니다. 데이터 연결에 대한 자세한 내용은 [PowerApps에서 데이터 연결 추가](add-data-connection.md)를 참조하세요.

1. PowerApps Studio의 오른쪽 창에서 **데이터 원본 추가**를 클릭하거나 누릅니다.
   
    ![](./media/register-custom-api/data-source.png)
2. 만든 사용자 지정 커넥터를 클릭하거나 누릅니다.
   
    ![](./media/register-custom-api/connector.png)
3. 연결하려는 서비스에 로그인하는 데 필요한 모든 단계를 완료합니다. API가 OAuth 인증을 사용하는 경우 로그인 화면이 표시될 수 있습니다. API 키 인증의 경우 키 값을 입력하라는 메시지가 표시될 수 있습니다.
4. 앱에서 API를 호출합니다. 이 예제에서 Cognitive Services에 텍스트를 전송하는 앱을 만들고 앱에서 백분율로 표시하는 0에서 1 사이의 감정 점수를 가져옵니다.
   
   * 이 커넥터를 사용하여 수식 입력줄에 "Az"를 입력하기 시작하는 경우 API 및 지원되는 작업이 표시됩니다.
     
       ![](./media/register-custom-api/formula.png)
   * 전체 호출이 이렇게 표시되면 여기에서 `TextInput` 컨트롤의 텍스트를 전달하고 앱에 표시할 점수를 가져옵니다.
     
       ```
       'AzureMachineLearning-TextAnalytics'.Sentiment({documents:Table({language:"en",id:"1",text:TextInput.Text})}).documents.score)
       ```
   * 앱에서 약간 더 많은 작업을 수행하여 가져올 데이터를 처리하지만 너무 복잡하지는 않습니다.

완성된 앱은 다음 이미지처럼 표시됩니다. 간단한 앱이지만 사용자 지정 커넥터를 통해 Cognitive Services를 호출할 수 있도록 하여 강력한 기능을 사용합니다.

![](./media/register-custom-api/finished-app.png)

### <a name="quota-and-throttling"></a>할당량 및 제한
* 사용자 지정 커넥터 생성 할당량에 대한 세부 내용은 [PowerApps 가격 책정](https://powerapps.microsoft.com/pricing/) 페이지를 참조하세요. 사용자와 공유된 사용자 지정 커넥터는 이 할당량에 대해 계산되지 않습니다.
* 사용자 지정 커넥터에서 만든 각 연결의 경우 사용자는 분당 최대 500개 요청을 만들 수 있습니다.

## <a name="share-your-custom-connector"></a>사용자 지정 커넥터 공유
이제 사용자 지정 커넥터가 있으므로 조직의 다른 사용자와 공유할 수 있습니다. API를 공유하는 경우 다른 사용자도 공유하기 시작할 수 있고 사용자 지정 커넥터를 삭제하면 API에 대한 모든 연결이 삭제됩니다. 조직 외부의 사용자에게 커넥터를 제공하려는 경우 [PowerApps에서 사용자 지정 커넥터 인증 개요](api-connector-overview.md)를 참조하세요.

1. [powerapps.com](https://web.powerapps.com)의 왼쪽 메뉴에서 **연결**을 선택합니다. 줄임표(**...**)를 선택한 다음 오른쪽 위 모서리에서 **사용자 지정 커넥터 관리**를 선택합니다.
   
    ![새 연결](./media/register-custom-api/managecustomapi.png)
2. 커넥터에 대한 줄임표(**...**) 단추를 선택한 다음 **속성 보기**를 선택합니다.  
   
    ![커넥터 속성 보기](./media/register-custom-api/view-properties.png)
3. API를 선택하고, **공유**를 선택하고, API에 대한 액세스 권한을 부여하려는 사용자 또는 그룹을 입력합니다.  
   
    ![사용자 지정 커넥터 공유](./media/register-custom-api/sharecustomapi.png)
4. **저장**을 선택합니다.

## <a name="next-steps"></a>다음 단계
[Postman 컬렉션을 만드는 방법 알아보기](postman-collection.md)

[ASP.NET Web API 사용](customapi-web-api-tutorial.md)

[Azure Resource Manager API 등록](customapi-azure-resource-manager-tutorial.md)

