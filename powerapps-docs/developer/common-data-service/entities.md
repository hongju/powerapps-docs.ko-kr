---
title: Common Data Service for Apps 엔터티 | Microsoft Docs
description: 앱용 Common Data Service에서 사용 가능한 엔터티에 대해 알아봅니다.
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
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f40c05c3bdab521cb1230be15cefc5dbb58eac18
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844229"
---
# <a name="common-data-service-for-apps-entities"></a>Common Data Service for Apps 엔터티

앱용 Common Data Service의 가장 중요한 기능은 데이터에 대한 저장소를 제공하는 기능입니다. Common Data Service는 비즈니스 응용 프로그램에서 사용되는 데이터에 대한 구조를 제공하는 기본 엔터티 집합을 포함하고 있습니다. 

[Common Data Service for Apps 엔터티 참조](reference/about-entity-reference.md)에서 기본 엔터티 집합을 볼 수 있습니다.

## <a name="modify-entities"></a>엔터티 수정

여러 가지 방법을 사용하여 엔터티 메타데이터를 수정할 수 있습니다.

### <a name="use-designers"></a>디자이너 사용

디자이너를 사용하여 엔터티 메타데이터를 편집하는 여러 가지 방법이 있습니다.


|디자이너  |설명  |
|---------|---------|
|powerapps.com|스키마를 수정하는 가장 쉽고 일반적인 방법은 환경과 관련된 Common Data Service를 편집할 수 있는 [powerapps.com](https://web.powerapps.com/) 사이트를 사용하는 것입니다. 여기서 적용된 변경 내용은 비관리 Common Data Service 기본 솔루션의 컨텍스트에서 수행됩니다. <!-- TODO: Add link to topic that describes this -->|
|Common Data Service 기본 솔루션 탐색기|Common Data Service를 편집할 때 [powerapps.com](https://web.powerapps.com/) 사이트에서 사용할 수 있는 또 다른 디자이너가 있습니다. 왼쪽 하단 모서리를 보면 Common Data Service 기본 솔루션에서 솔루션 탐색기를 여는 **고급** 단추가 있습니다. |
|솔루션에 대한 솔루션 탐색기 |솔루션을 배포하려는 경우 솔루션 개발에 사용할 비관리 솔루션의 컨텍스트에서 새 엔터티, 특성 또는 관계를 만들어야 합니다. <br /> 자세한 정보: [솔루션 게시자 및 솔루션 만들기](introduction-solutions.md#create-a-solution-publisher-and-solution)|
|폼 편집기에서|엔터티의 모델 기반 앱 폼을 편집할 때 **필드 탐색기**에서 **새 필드** 단추를 클릭할 수 있습니다. 조회 필드를 만드는 경우 이를 지원하기 위한 새 엔터티 관계를 만들게 됩니다.|

### <a name="import-a-solution"></a>솔루션 가져오기

솔루션은 엔터티 메타데이터 및 기타 사용자 지정된 구성 요소를 포함할 수 있습니다. 관리 또는 비관리 솔루션을 앱용 Common Data Service 테넌트로 가져오면 해당 엔터티가 포함되거나 포함하고 있는 새 엔터티 메타데이터를 사용하여 기존 엔터티가 확장됩니다.

### <a name="from-a-data-source-using-power-query"></a>Microsoft Excel용 파워 쿼리를 사용하여 데이터 원본에서

Microsoft Excel용 파워 쿼리를 사용하여 새 엔터티를 만들고 데이터를 채울 수 있습니다. 자세한 정보: [Power Query를 사용하여 Common Data Service의 엔터티에 데이터 추가](../../maker/common-data-service/data-platform-cds-newentity-pq.md)

### <a name="use-metadata-services"></a>메타데이터 서비스 사용

Common Data Service에 노출되는 웹 서비스는 엔터티 메타데이터를 만들고 읽고 쓰고 삭제하는 기능을 포함하고 있습니다. 이러한 서비스는 런타임에 환경이 사용자 지정된 방식을 코드에 알려주는 메타데이터를 읽기 위해 가장 많이 사용됩니다.

자세한 정보: [메타데이터 서비스](use-web-services.md#metadata-services)

## <a name="entity-metadata"></a>엔터티 메타데이터

데이터 모델은 Common Data Service 내에 저장되는 메타데이터로 정의됩니다. 스키마에 대한 이 데이터를 *엔터티 메타데이터*라고 합니다. 

- [EntityMetadata 클래스](/dotnet/api/microsoft.xrm.sdk.metadata.entitymetadata)는 조직 서비스를 통해 이 데이터를 정의합니다. 
- [EntityMetadata EntityType](/dynamics365/customer-engagement/web-api/entitymetadata)은 Web API에 대해 이 데이터를 정의합니다. 

엔터티 메타데이터에는 다음 정보가 포함됩니다.


|데이터  |설명  |
|---------|---------|
|엔터티 속성|각 엔터티에는 식별 방법 및 수행 가능한 작업에 대해 설명하는 거의 100개에 가까운 속성이 있습니다.  자세한 정보: [엔터티 메타데이터](entity-metadata.md)|
|특성|엔터티 `Attributes` 속성은 특성 컬렉션입니다. 각 특성에는 식별 방법, 포함되는 데이터 형식, 서식 지정 방법, 수행 가능한 작업에 대해 설명하는 약 50개의 속성이 있습니다. 자세한 정보: [특성 메타데이터](entity-attribute-metadata.md)|
|관계|세 가지 엔터티 속성은 엔터티 간의 관계 컬렉션입니다. 이러한 컬렉션은 여러 가지 관계(다대다, 다대일, 일대다)를 포함하고 있습니다. 자세한 정보: [엔터티 관계 메타데이터](entity-relationship-metadata.md)|
|권한|엔터티 속성 중 하나는 서로 연결된 고유 식별자가 있는 엔터티에서 수행 가능한 데이터 작업의 종류를 식별하는 0~8 사이의 권한 컬렉션입니다. 이러한 작업으로는 *Append*, *AppendTo*, *Assign*, *Create*, *Delete*, *Read*, *Share* 및 *Write*가 있습니다.|
|키|기본적으로 각 엔터티에는 단일 GUID(Globally Unique Identifier) 특성이 있으며 `Keys` 속성은 빈 컬렉션입니다. 엔터티에 대체 키를 추가할 수 있습니다. 자세한 정보: [엔터티 키](entity-metadata.md#entity-keys)|

> [!TIP]
> 시스템의 엔터티 메타데이터를 깊이 이해하면 Common Data Service의 작동 방식을 파악하는 데 도움이 될 수 있습니다. 또한 모델 기반 앱에서 수행할 수 있는 작업을 제어하는 여러 속성이 있습니다. 메타데이터를 편집할 수 있는 디자이너는 메타데이터에 있는 모든 세부 정보를 표시할 수 없습니다. 메타데이터 브라우저라는 모델 기반 앱을 설치하면 시스템에 있는 숨겨진 모든 엔터티와 메타데이터 속성을 볼 수 있습니다. 자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: 조직에 대한 메타데이터 찾아보기](/dynamics365/customer-engagement/developer/browse-your-metadata)

### <a name="see-also"></a>참고 항목

[Common Data Service for Apps 개발자 개요](overview.md)


