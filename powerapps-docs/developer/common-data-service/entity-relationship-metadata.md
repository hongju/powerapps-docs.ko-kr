---
title: 엔터티 관계 메타데이터 | Microsoft Docs
description: Common Data Service for Apps에서 사용되는 엔터티 관계 메타데이터에 대해 알아봅니다.
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
ms.date: 03/12/2018
ms.author: jdaly
ms.openlocfilehash: da8899151fdb40713d19ca1cb82444a486526549
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="entity-relationship-metadata"></a>엔터티 관계 메타데이터

솔루션 탐색기 또는 `EntityMetadata`의 세 관계 컬렉션을 살펴볼 때 세 가지 유형의 엔터티 관계가 있는 것으로 생각할 수도 있습니다. 사실은 다음 표와 같이 두 가지 유형만 있습니다.

|관계 유형|설명|
|--|--|
|일대다<br />[OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)|관련 엔터티에 대한 조회 필드 때문에 **주 엔터티**에 대한 하나의 엔터티 레코드를 여러 다른 **관련 엔터티**에 연결할 수 있는 엔터티 관계입니다.<br />주 엔터티 레코드를 볼 때 그와 연결된 관련 엔터티 레코드 목록을 볼 수 있습니다.|
|다대다<br />[ManyToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.manytomanyrelationshipmetadata)|*교차* 엔터티라고도 하는 특수한 *관계 엔터티*에 의존하는 엔터티 관계로, 한 엔터티의 여러 레코드가 다른 엔터티의 여러 레코드와 관련될 수 있습니다.<br />다대다 관계의 두 엔터티를 볼 때 해당 엔터티와 관계가 있는 다른 엔터티의 레코드 목록을 볼 수 있습니다.|

`EntityMetadata` `ManyToOneRelationships` 컬렉션은 [OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata) 형식을 포함합니다. 일대다 관계는 엔터티 간에 존재하며 서로 각 엔터티를 *주 엔터티가* 또는 *관련 엔터티*로 참조합니다. *자식 엔터티*라고도 하는 관련 엔터티는 *부모 엔터티*라고도 하는 주 엔터티의 레코드 참조를 저장할 수 있는 조회 특성을 갖고 있습니다. 다대일 관계는 관련 엔터티에서 보는 일대다 관계일 뿐입니다.

> [!NOTE]
> 관련 엔터티를 *자식 엔터티*라고 부르기도 하지만, 관련 엔터티에 보안을 적용하는 방식을 나타내는 [자식 엔터티](entity-metadata.md#child-entities)와 혼동하면 안 됩니다.

자세한 정보:
- [Dynamics 365 Customer Engagement 사용자 지정 가이드: 엔터티 간 관계 만들기 및 편집](/dynamics365/customer-engagement/customize/create-edit-entity-relationships)
- [Dynamics 365 Customer Engagement 개발자 가이드: 엔터티 관계 메타데이터 사용자 지정](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

## <a name="cascade-configuration"></a>계단식 배열 구성

일대다 엔터티 관계가 있을 때 데이터 무결성을 유지하고 비즈니스 프로세스를 자동화하도록 구성할 수 있는 계단식 배열 동작이 있습니다.

자세한 정보:

- [Dynamics 365 Customer Engagement 사용자 지정 가이드: 1:N(일대다) 또는 N:1(다대일) 관계 만들기 > 관계 동작](/dynamics365/customer-engagement/customize/create-and-edit-1n-relationships#relationship-behavior)
- [Dynamics 365 Customer Engagement 개발자 가이드: 엔터티 관계 동작](/dynamics365/customer-engagement/developer/entity-relationship-behavior)


## <a name="create-a-hierarchy-of-entities"></a>엔터티 계층 구조 만들기

자기 참조 일대다 관계 내에서 `IsHierarchical` 속성을 `true`로 설정하여 계층 구조를 설정할 수 있습니다.

모델 기반 앱을 사용하면 계층 구조를 보고 상호 작용할 수 있는 환경을 만들 수 있습니다. 

개발자의 경우 이렇게 하면 `Under` 및 `Not Under` 연산자를 사용하는 계층 구조를 기반으로 새로운 형식의 쿼리를 사용할 수 있습니다.

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: 계층적으로 관련된 데이터를 쿼리 및 시각화](/dynamics365/customer-engagement/customize/query-visualize-hierarchical-data)

### <a name="see-also"></a>참고 항목

[Common Data Service for Apps 엔터티](entities.md)