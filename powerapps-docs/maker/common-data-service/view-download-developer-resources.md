---
title: 개발자 리소스 보기 또는 다운로드 | MicrosoftDocs
description: 개발자 리소스 및 서비스 enpoint URL 찾기
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.openlocfilehash: ae93b57d9ead3a62fb538ae986eb524367259545
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696144"
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>개발자 리소스 보기 또는 다운로드

이 페이지는 개발자를 위한 리소스와 작업 중인 특정 인스턴스에 대한 정보를 제공합니다. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>사용자 환경에 대한 개발자 리소스 페이지 보기

1. PowerApps 포털에서 ![설정 단추](../../administrator/media/settings-button-nav-bar.png) 설정 단추를 선택하고 **고급 사용자 지정**을 선택합니다.

    ![고급 사용자 지정](media/advanced-customizations-menu.png)

1. **고급 사용자 지정** 패널에서 **개발자 리소스** 링크를 선택합니다.<br />![개발자 리소스 링크](media/developer-resources-link.png)

## <a name="getting-started"></a>시작하기 

이 섹션에서는 개발자가 리소스를 찾을 수 있는 링크를 제공합니다. 다음 리소스를 사용할 수 있습니다.


|링크 |설명|
|---------|---------|
|[개발자 센터](https://go.microsoft.com/fwlink/?LinkId=551006)|개발자용 설명서에 대한 주요 진입 점입니다.|
|[개발자 포럼](https://go.microsoft.com/fwlink/?LinkId=550993)|다른 개발자에게 질문하고 답변합니다.|
|[NuGet 패키지](https://go.microsoft.com/fwlink/?LinkId=550994)|프로젝트에 SDK 어셈블리를 추가하는 NuGet 패키지를 검색합니다.|
|[도구 다운로드](https://go.microsoft.com/fwlink/?LinkID=512122)|필요한 도구는 NuGet에서 다운로드할 수 있습니다. 이 페이지의 PowerShell 스크립트를 사용하여 최신 버전을 가져옵니다.|
|[샘플 코드](https://go.microsoft.com/fwlink/?LinkId=553007)|사용할 수 있는 샘플 목록입니다.|
|[개발자 개요](https://go.microsoft.com/fwlink/?LinkId=550995)|개발자를 위한 개요를 제공하는 항목에 연결합니다.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>이 앱용 Common Data Service 인스턴스에 앱 연결

이 섹션에서는 앱 인스턴스에 대한 Common Data Service에 연결하는 데 필요한 정보를 제공합니다.

### <a name="instance-web-api"></a>인스턴스 Web API

이는 인스턴스에 대한 Web API의 URL입니다. Web API는 OData v4 RESTful API입니다. 인스턴스에서 사용할 수 있는 메타데이터 및 작업을 설명하는 서비스 문서를 다운로드할 수도 있습니다. 자세한 정보: [개발자 설명서: Dynamics 365 고객 참여 Web API 사용](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>조직 서비스

인스턴스에 대한 조직 서비스의 SOAP 엔드포인트에 대한 URL입니다.
여기에서 이 서비스에 대한 WSDL을 다운로드할 수 있지만 일반적으로 CrmSvcUtil.exe 코드 생성 도구를 사용하여 .NET 프로젝트의 엔터티 클래스를 빌드합니다. 자세한 정보: 
- [개발자 설명서: 코드 생성 도구(CrmSvcUtil.exe)를 사용하여 초기 바인딩된 엔터티 클래스 만들기](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [개발자 설명서: 조직 서비스를 사용하여 데이터 또는 메타데이터 읽기 및 쓰기](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>인스턴스 참조 정보

이 정보는 인스턴스를 고유하게 설명합니다. GUID **ID** 및 **고유 이름**이 있습니다.
이 정보는 인스턴스와 함께 Azure 확장을 사용할 때 필요합니다.
자세한 정보: [개발자 설명서: Dynamics 365 고객 참여를 위한 Azure 확장](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>앱 Common Data Service 검색 서비스에 앱 연결

사람들은 앱 환경을 위해 여러 CDS에 액세스 할 수 있기 때문에 검색 서비스를 통해 사용자가 자신의 사용자 자격 증명을 기반으로 액세스할 수 있는 사용 가능한 환경을 검색할 수 있습니다.

### <a name="discovery-web-api"></a>검색 Web API

이는 인스턴스에 사용할 검색 서비스의 RESTful OData v4 버전에 대한 엔드포인트 주소입니다. 여기에서 서비스 문서를 다운로드할 수도 있습니다.
자세한 정보: [개발자 설명서: Web API를 사용하여 조직의 URL 검색](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>검색 서비스

이는 인스턴스에 사용할 검색 서비스의 SOAP 버전에 대한 엔드포인트 주소입니다. 여기에서 서비스 문서를 다운로드할 수도 있습니다.
자세한 정보: [개발자 설명서: 검색 서비스를 사용하여 조직의 URL 검색](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>자세한 정보

[개발자 설명서: 개발자 리소스 페이지](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[개발자 설명서: Dynamics 365 고객 참여 Web API 사용](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[개발자 설명서: 조직 서비스를 사용하여 데이터 또는 메타데이터 읽기 및 쓰기](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[개발자 설명서: Dynamics 365 고객 참여를 위한 Azure 확장](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[개발자 설명서: Web API를 사용하여 조직의 URL 검색](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[개발자 설명서: 검색 서비스를 사용하여 조직의 URL 검색](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  

