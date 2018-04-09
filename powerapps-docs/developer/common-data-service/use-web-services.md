---
title: Common Data Service for Apps 웹 서비스 사용 | Microsoft Docs
description: 개발자가 Common Data Service for Apps 웹 서비스를 사용하는 방법을 알아봅니다.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/26/2018
ms.author: jdaly
ms.openlocfilehash: 7f89a74b37ebf322137d680e165c007cd8fa6d26
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="use-common-data-service-for-apps-web-services"></a>Common Data Service for Apps 웹 서비스 사용

Common Data Service for Apps는 데이터와 상호 작용하는 데 사용할 수 있는 두 가지 웹 서비스를 제공합니다. 요구 사항과 기술에 가장 잘 적합한 웹 서비스를 선택합니다. 자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: Dynamics 365 고객 관계에 대한 개발 스타일 선택](/dynamics365/customer-engagement/developer/choose-development-style)

## <a name="web-api"></a>Web API
Web API는 OData v4 RESTful 엔드포인트입니다. OAuth 2.0을 사용하여 HTTP 요청 및 인증을 지원하는 모든 프로그래밍 언어에 Web API를 사용합니다.

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: Dynamics 365 고객 관계 Web API 사용](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

## <a name="organization-service"></a>조직 서비스

조직 서비스는 Common Data Service for Apps 플랫폼의 핵심 부분입니다. WCF(Windows Communication Foundation) 서비스이며, 현재 SOAP 엔드포인트만 노출합니다. .NET 개발자는 SDK 어셈블리를 사용하여 데이터 작업을 수행할 수 있습니다. 플러그 인 내에서 SDK 어셈블리를 통한 조직 서비스가 유일한 옵션입니다.
> [!NOTE]
> 개발자가 .NET SDK 어셈블리를 사용하지 않고도 조직 서비스의 SOAP 엔드포인트를 사용할 수 있지만, Web API의 RESTful 특성으로 인해 훨씬 뛰어난 대안이 될 수 있습니다.

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: Dynamics 365 조직 서비스 사용](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service)

## <a name="about-the-web-services-and-the-platform"></a>웹 서비스 및 플랫폼 정보

조직 서비스가 플랫폼을 정의하는 것임을 인식하는 것이 중요합니다. Web API는 RESTful 프로그래밍 환경을 제공하지만, 궁극적으로 모든 데이터 작업은 기본 조직 서비스를 통해 수행됩니다. 

조직 서비스는 지원되는 작업을 메시지로 정의합니다. 각 메시지에는 이름이 있습니다. SDK 어셈블리 내에서 각 메시지에는 해당하는 *&lt;메시지 이름&gt;*`Request` 및 *&lt;메시지 이름&gt;*`Response` 클래스가 있습니다. `Microsoft.Xrm.Sdk.dll`의 [IOrganizationService 인터페이스](/dotnet/api/microsoft.xrm.sdk.iorganizationservice)는 메시지를 호출하는 데 사용할 수 있는 [Execute 메서드](/dotnet/api/microsoft.xrm.sdk.iorganizationservice.execute)뿐만 아니라 일반적인 CRUD 작업에 대한 몇 가지 도우미 메서드도 정의합니다. 모든 메시지는 기본 [OrganizationRequest 클래스](/dotnet/api/microsoft.xrm.sdk.organizationrequest)를 사용합니다.

Web API는 조직 서비스와 동일한 작업을 모두 제공하지만, OData v4 프로토콜을 사용하여 RESTful 스타일로 제공합니다. OData v4는 *함수* 또는 *작업*을 통해 명명된 작업을 제공합니다. 조직 서비스에서 사용할 수 있는 거의 모든 메시지는 해당 명명된 해당 함수 또는 작업으로 공개됩니다. CRUD 작업에 해당하는 메시지는 RESTful 서비스로서 GET, POST, PATCH 및 DELETE HTTP 메서드를 사용하는 구현이 있으므로 Web API에서 사용할 수 없습니다.

조직 서비스 SOAP 엔드포인트에 대한 .NET SDK 어셈블리는 [IOrganizationService 인터페이스](/dotnet/api/microsoft.xrm.sdk.iorganizationservice)를 기반으로 하는 기본 플랫폼 서비스를 자세히 모델링하도록 설계되었습니다. 그러나 이러한 어셈블리는 동일한 구성 요소가 아니며, 서로 혼동되지 않아야 합니다. 

조직 서비스에 대한 SOAP 엔드포인트는 2011년에 도입되었으며 더 이상 사용되지 않는다고 발표했습니다. 즉, 이 엔드포인트는 제거할 때까지 계속 작동하고 지원될 것입니다. 또한 SOAP 엔드포인트가 제거된 후에도 계속 작동하도록 .NET SDK 어셈블리를 업데이트할 것이라고 발표했습니다. 즉, SOAP 엔드포인트를 제거하기 전에 업데이트된 SDK 어셈블리를 사용할 수 있으며, 개발자가 이후의 특정 시점에서 이러한 새 어셈블리를 사용하도록 코드를 업데이트해야 합니다.

## <a name="discovery-services"></a>검색 서비스

각 Common Data Service for Apps 사용자는 여러 개의 Common Data Service for Apps 인스턴스에 액세스할 수도 있습니다. 검색 서비스를 사용하면 사용자가 사용하는 Microsoft 계정에 따라 연결할 수 있는 인스턴스 목록을 제공하는 코드를 작성할 수 있습니다. 각 인스턴스에는 선택한 인스턴스에 연결하는 데 사용할 수 있는 URL이 포함되어 있습니다. 

검색 서비스는 Web API 또는 조직 서비스를 통해 액세스됩니다.

- Web API의 경우: [Dynamics 365 고객 관계 개발자 가이드: Web API를 사용하여 조직에 대한 URL 검색](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api) 참조
- 조직 서비스의 경우: [Dynamics 365 고객 관계 개발자 가이드: 조직 서비스를 사용하여 조직에 대한 URL 검색](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service) 참조

## <a name="use-custom-actions"></a>사용자 지정 작업 사용

프로세스에서 사용할 수 있는 선언적 옵션 중 하나는 *사용자 지정 작업*을 만드는 것입니다. 사용자 지정 작업은 기본적으로 조직 서비스에 새 메시지를 만드는 것입니다. 사용자 지정 작업을 사용하여 작업 집합을 다시 사용할 수 있는 명명된 작업으로 결합할 수 있습니다. 예를 들어 중요한 고객에게 심각한 문제가 발생했을 때 올바른 사람에게 알리는 데 관련된 표준 작업 집합을 결합한 *new_Escalate*라는 새 메시지를 만들 수 있습니다.

사용자 지정 작업을 정의할 때 반환되는 결과에 포함될 입력 매개 변수와 속성을 정의하여 작업의 시그니처를 선택합니다. 그러면 사용자 지정 작업은 디자이너 또는 코드를 사용하여 선언적 프로세스에서 호출할 수 있습니다. 

사용자 지정 작업의 고유한 값은 다른 프로세스 또는 호출하는 코드에 영향을 주지 않고 디자이너를 사용하는 개발자가 아닌 사용자가 포함된 특정 작업을 수정할 수 있다는 것입니다.  작업의 시그니처가 변경되지 않는 경우에도 마찬가지입니다. 다른 입력 매개 변수 또는 출력 속성이 필요한 경우, 기존 작업을 사용하여 프로세스 또는 코드가 손상되지 않도록 다른 사용자 지정 작업을 새로 만들어야 합니다.

환경에 사용자 지정 작업이 정의되면 Web API를 사용하여 새 OData v4 작업을 사용할 수 있으며, 조직 서비스 내에서 [OrganizationRequest 클래스](/dotnet/api/microsoft.xrm.sdk.organizationrequest)를 직접 사용하거나 *코드 생성 도구(CrmSvcUtil.exe)*로 생성된 강력한 형식의 클래스를 사용하여 사용자 지정 작업을 호출할 수 있습니다.

자세한 정보: 
- [Dynamics 365 고객 관계 사용자 지정 가이드: 작업 개요](/dynamics365/customer-engagement/customize/actions)
- [Dynamics 365 고객 관계 개발자 가이드: 사용자 고유의 작업 만들기](/dynamics365/customer-engagement/developer/create-own-actions)
- [Dynamics 365 고객 관계 개발자 가이드: Web API 작업 사용 - 사용자 지정 작업 사용](/dynamics365/customer-engagement/developer/webapi/use-web-api-actions#use-a-custom-action)

## <a name="metadata-services"></a>메타데이터 서비스

Web API와 조직 서비스에는 모두 엔터티 스키마에서 CRUD 작업을 수행하는 기능이 포함되어 있습니다. 코드를 사용하여 이러한 작업을 수행할 수 있지만, 일반적으로 디자이너를 사용하여 사용자 지정 스키마 요소를 추가, 업데이트 또는 삭제합니다. 스키마 변경 내용을 적용하려면 관리자 권한이 있어야 하지만, 모든 사용자는 메타데이터를 읽을 수 있습니다.

메타데이터 서비스에 대한 더 일반적인 사용은 확장이 실행되는 환경에 대한 메타데이터를 검색하는 것입니다. 모든 환경이 다를 수 있으며 스키마 메타데이터에는 환경을 구성하는 방법에 대한 많은 정보가 포함되어 있으므로, 확장이 해당 환경에 적용되는 다른 사용자 지정에 적응할 수 있도록 이 정보를 검색해야 할 수도 있습니다.

몇 가지 예:
- 옵션 집합 특성에서 사용할 수 있는 옵션 수가 변경될 수 있습니다. 사용자 환경에서 값을 하드 코딩하는 대신, 다른 옵션이 있는지 여부를 고려합니다. 시스템을 쿼리하여 현재 환경에 다른 옵션이 있는지를 확인할 수 있습니다.
- 엔터티에 대한 표시 이름은 변경할 수 있습니다. 계정 엔터티에 대한 기본 표시 이름은 *Account*입니다. 이 이름을 *Company*로 변경할 수 있습니다. 사용자에게 메시지를 표시하고 엔터티의 이름을 참조하려는 경우, 이를 하드 코딩하지 않고, 대신 사용자가 보는 데 익숙한 값과 일치하는 값을 사용하고 엔터티 메타데이터에서 검색된 표시 이름을 사용합니다.

시스템의 메타데이터에 대한 효과적인 이해를 개발하면 Common Data Service for Apps 플랫폼의 작동 방식을 파악하는 데 도움이 될 수 있습니다. 메타데이터를 편집할 수 있는 디자이너는 메타데이터에 있는 모든 세부 정보를 표시할 수 없습니다. *메타데이터 브라우저*라는 모델 기반 앱을 설치하면 시스템에 있는 숨겨진 모든 엔터티와 메타데이터 속성을 볼 수 있습니다. 

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: 조직에 대한 메타데이터 찾아보기](/dynamics365/customer-engagement/developer/browse-your-metadata)

프로그래밍 방식의 메타데이터 작업에 대한 자세한 내용은 다음 항목을 참조하세요.
- [Dynamics 365 고객 관계 개발자 가이드: 메타데이터와 함께 Web API 사용](/dynamics365/customer-engagement/developer/webapi/use-web-api-metadata)
- [Dynamics 365 고객 관계 개발자 가이드: Dynamics 365 메타데이터와 함께 조직 서비스 사용](/dynamics365/customer-engagement/developer/org-service/use-organization-service-metadata)
 
### <a name="see-also"></a>참고 항목

[Common Data Service for Apps 개발자 개요](overview.md)

