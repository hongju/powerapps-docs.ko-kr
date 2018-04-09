---
title: 엔터티 메타데이터 | Microsoft Docs
description: Common Data Service for Apps에서 사용되는 엔터티 메타데이터에 대해 알아봅니다.
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
ms.openlocfilehash: eb908978eee8d6473a46ca3894cee55ce4b036df
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="entity-metadata"></a>엔터티 메타데이터

각 엔터티는 구조적 데이터를 저장하는 기능을 제공합니다. 개발자의 경우 엔터티는 Common Data Servic에서 데이터로 작업할 때 사용할 클래스에 해당합니다.

## <a name="entity-names"></a>엔터티 이름
각 엔터티에는 만들어질 때 정의된 고유한 이름이 있습니다. 이 이름은 다음과 같이 여러 가지 방법으로 표시됩니다.

|이름 속성 |설명|
|---------|---------|
|`SchemaName`|일반적으로 파스칼식 대/소문자 버전의 논리적 이름입니다. 예: Account|
|`CollectionSchemaName`|복수 형태의 스키마 이름입니다. 예: Accounts|
|`LogicalName`|모두 소문자 버전의 스키마 이름입니다. 예: account|
|`LogicalCollectionName`|모두 소문자 버전의 컬렉션 스키마 이름입니다. 예: accounts|
|`EntitySetName`|Web API를 사용하여 컬렉션을 식별하는 데 사용됩니다. 기본적으로 논리적 컬렉션 이름과 동일합니다.<br />엔터티 집합 이름은 메타데이터를 프로그래밍 방식으로 업데이트하여 변경할 수 있습니다. 그러나 이 작업은 엔터티에 대한 Web API 코드를 작성하기 전에 수행해야 합니다. 자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: Web API 형식 및 작업 - 엔터티 집합 이름 변경](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations#change-the-name-of-an-entity-set)|

> [!NOTE]
> 사용자 지정 엔터티를 만들면 해당 엔터티가 만들어진 솔루션과 연결된 솔루션 게시자의 사용자 지정 접두사 값이 선택한 이름 앞에 추가됩니다. 엔터티를 만든 후에는 엔터티 집합 이름이 아닌 엔터티 이름은 변경할 수 없습니다. 솔루션의 메타데이터 항목에 대해 일관된 이름을 사용하려면, 사용할 사용자 지정 접두사가 포함된 솔루션 게시자와 연결하여 만든 솔루션의 컨텍스트에서 해당 항목을 만들어야 합니다. 자세한 정보: [솔루션 게시자 및 솔루션 만들기](introduction-solutions.md#create-a-solution-publisher-and-solution)

또한 각 엔터티에는 지역화된 값을 표시할 수 있는 세 가지 속성이 있습니다.


|이름  |설명  |
|---------|---------|
|`DisplayName`|일반적으로 스키마 이름과 동일하지만 공백을 포함할 수 있습니다. 예: Account|
|`DisplayCollectionName`|복수 형태의 표시 이름입니다. 예: Accounts|
|`Description`|엔터티를 설명하는 짧은 문장입니다. 즉 *고객 또는 잠재 고객을 나타내는 비즈니스입니다. 비즈니스 거래에서 청구되는 회사입니다.*|

이러한 값은 앱의 엔터티를 참조하는 데 사용되는 지역화할 수 있는 값입니다. 이러한 값은 언제든지 변경할 수 있습니다. 지역화된 값을 추가하거나 편집하려면 [Dynamics 365 사용자 지정 가이드: 사용자 지정된 엔터티 및 필드 텍스트를 다른 언어로 번역](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation)을 참조하세요.


## <a name="primary-key"></a>기본 키

`PrimaryIdAttribute` 속성 값은 엔터티에 대한 기본 키인 특성의 논리적 이름입니다.

기본적으로 모든 엔터티에는 단일 GUID 고유 식별자 특성이 있습니다. 대개 *&lt; 엔터티 논리 이름 &gt;*+ `Id`로 지정됩니다.

## <a name="primary-name"></a>기본 이름

`PrimaryNameAttribute` 속성 값은 엔터티 레코드를 식별하는 문자열 값을 저장하는 특성의 논리적 이름입니다. UI에서 레코드를 여는 링크에 표시되는 값입니다.

**예**: `fullname` 특성은 Contact(연락처) 엔터티에서 기본 이름 특성으로 사용합니다.

> [!NOTE]
> 모든 엔터티에 기본 이름이 있는 것은 아닙니다. 일부 엔터티는 UI에 표시되지 않습니다.

## <a name="entity-images"></a>엔터티 이미지

`PrimaryImageAttribute` 속성 값은 엔터티 레코드에 대한 이미지 데이터를 저장하는 특성의 논리적 이름입니다. 각 엔터티에는 하나의 이미지 특성만 있을 수 있으며, 해당 특성의 논리적 이름은 항상 `entityimage`입니다.

**예**: [ContactEntity](reference/entities/contact.md) [EntityImage](reference/entities/contact.md#BKMK_EntityImage) 특성은 연락처의 그림을 저장할 수 있습니다.

성능상의 이유로 명시적으로 요청하지 않는 한 엔터티 이미지는 검색 작업에 포함되지 않습니다.

엔터티 이미지를 지원하는 각 엔터티에는 세 가지 지원 특성이 있습니다.

|SchemaName|유형|설명|
|--|--|--|
|`EntityImage_Timestamp` |`BigIntType`|이미지가 마지막으로 업데이트된 시점을 나타내며, 최신 버전의 이미지가 다운로드되어 클라이언트에 캐시되도록 하는 데 사용됩니다.|
|`EntityImage_URL`|`StringType`|클라이언트에 엔터티 이미지를 표시하는 절대 URL입니다.|
|`EntityImageId`|`UniqueIdentifierType`|이미지의 고유 식별자입니다.|

자세한 정보: 
- [Dynamics 365 고객 관계 개발자 가이드: 이미지 특성](/dynamics365/customer-engagement/developer/image-attributes)
- [Dynamics 365 고객 관계 개발자 가이드: 샘플: 엔터티 이미지 설정 및 검색](/dynamics365/customer-engagement/developer/sample-set-retrieve-entity-images)

> [!NOTE]
> 이는 모델 기반 앱에서 엔터티에 대해 표시되는 아이콘과 다릅니다. `IconVectorName` 속성은 이를 설정하는 SVG 웹 리소스의 이름을 포함합니다.

## <a name="types-of-entities"></a>엔터티 형식

엔터티의 기능 및 동작은 여러 엔터티 속성에 따라 달라집니다. 이러한 속성 대부분은 비교적 간단하며 설명이 포함된 이름을 사용합니다. 추가 설명이 필요한 네 가지 속성은 *소유권*, *활동 엔터티*, *Activityparty 엔터티* 및 *자식 엔터티*입니다.

### <a name="entity-ownership"></a>엔터티 소유권

엔터티는 포함된 데이터를 소유하는 방식에 따라 분류할 수 있습니다. 이는 보안이 엔터티에 적용되는 방법과 관련된 중요한 개념입니다. 이 정보는 `OwnershipType` 속성에 있습니다. 다음 표에서는 여러 가지 소유권 유형을 설명합니다.

|소유권 유형  |설명  |
|---------|---------|
|Business|비즈니스 단위에 속한 데이터입니다. 데이터에 대한 액세스는 비즈니스 단위 수준에서 제어할 수 있습니다.|
|없음|다른 엔터티에서 소유하지 않은 데이터입니다.|
|조직|조직에 속한 데이터입니다. 데이터에 대한 액세스는 조직 수준에서 제어됩니다.|
|사용자 또는 팀|사용자 또는 팀에 속한 데이터입니다. 이러한 레코드에서 수행할 수 있는 작업은 사용자 수준에서 제어할 수 있습니다.|

새 엔터티를 만들 때는 **조직** 또는 **사용자 또는 팀** 소유권 옵션만 사용할 수 있습니다. 이 옵션을 선택하면 변경할 수 없습니다. 레코드에 대한 작업을 보거나 수행할 수 있는 사용자를 가장 세밀하게 제어하려면 **사용자 또는 팀**을 선택합니다. 이 수준의 제어가 필요하지 않은 경우 **조직**을 선택합니다. 

### <a name="activity-entities"></a>활동 엔터티

활동은 사용자가 수행하거나 수행할 작업입니다. 활동은 일정에 항목을 만들 수 있는 모든 작업입니다. 

활동은 비즈니스 데이터를 저장하는 다른 종류의 엔터티와 다르게 모델링됩니다. 활동에 대한 데이터는 자주 목록에 함께 표시되지만 각 종류의 활동에는 고유한 속성이 필요합니다. 가능한 모든 속성이 포함된 단일 활동 엔터티가 아니라 개별 종류의 활동 엔터티가 있으며, 각 엔터티는 기본 [ActivityPointer 엔터티](reference/entities/activitypointer.md)에서 속성을 상속합니다. 이러한 엔터티에는 `IsActivity` 속성이 true로 설정됩니다.


|엔터티 |설명  |
|---------|---------|
|[Appointment](reference/entities/appointment.md)|시작/종료 시간 및 시간으로 시간 간격을 나타내는 약속입니다.|
|[Email](reference/entities/email.md)|이메일 프로토콜을 사용하여 전달되는 활동입니다.|
|[Fax](reference/entities/fax.md)|팩스에 대한 통화 결과 및 페이지 수를 추적하고 필요에 따라 문서의 전자 복사본을 저장하는 활동입니다.|
|[Letter](reference/entities/letter.md)|편지 전달을 추적하는 활동입니다. 이 활동은 편지의 전자 복사본을 포함할 수 있습니다.|
|[PhoneCall](reference/entities/phonecall.md)|전화 통화를 추적하는 활동입니다.|
|[RecurringAppointmentMaster](reference/entities/recurringappointmentmaster.md)|되풀이 약속 시리즈의 마스터 약속입니다.|
|[SocialActivity](reference/entities/socialactivity.md)|내부 전용입니다.|
|[Task](reference/entities/task.md)|수행해야 할 작업을 나타내는 일반적인 활동입니다.|

이러한 종류의 활동 엔터티 레코드 중 하나를 만들 때마다 동일한 `ActivityId` 고유 식별자 특성 값을 사용하여 해당 `ActivityPointer` 엔터티 레코드가 만들어집니다. `ActivityPointer` 엔터티의 인스턴스를 생성, 업데이트 또는 삭제할 수 없지만 검색할 수는 있습니다. 이렇게 하면 모든 유형의 활동을 목록에 함께 표시할 수 있습니다.

동일한 방식으로 작동하는 사용자 지정 활동 엔터티를 만들 수 있습니다.
<!-- TODO: Add link to topic about creating an activity entity -->

### <a name="activityparty-entity"></a>ActivityParty 엔터티

이 엔터티는 다른 엔터티에 대한 참조를 포함하는 활동 엔터티 `PartyListType` 특성에 구조를 추가하는 데 사용됩니다. `Email.to` 또는 `PhoneCall.from`과 같은 활동 엔터티 특성 값을 설정할 때 이 엔터티를 사용합니다. [ActivityParty 엔터티](reference/entities/activityparty.md) 내에서 [ParticipationTypeMask](reference/entities/activityparty.md#BKMK_ParticipationTypeMask) 특성을 설정하여 참조에서 재생하는 역할을 정의합니다. 역할에는 `Sender`, `ToRecipient`, `Organizer` 등이 포함됩니다.

`ActivityParty` 엔터티를 쿼리할 수 있지만, 관련된 활동 외부의 활동 당사자를 생성, 검색, 업데이트 또는 삭제할 수는 없습니다.
자세한 정보: 
- [Dynamics 365 고객 관계 개발자 가이드: ActivityParty 엔터티](/dynamics365/customer-engagement/developer/activityparty-entity).


### <a name="child-entities"></a>자식 엔터티

`IsChildEntity` 속성이 true인 엔터티는 정의된 권한을 포함할 수 없으며 사용자 또는 팀에서 소유하지 않습니다. 자식 엔터티에 대해 수행할 수 있는 작업은 다대일 관계를 통해 연결된 엔터티에 바인딩됩니다. 사용자는 관련 엔터티에 대해 동일한 작업을 수행할 수 있는 경우에만 자식 엔터티에 대한 작업을 수행할 수 있습니다. 종속된 엔터티 레코드가 삭제되면 자식 엔터티가 자동으로 삭제됩니다.

예를 들어 `PostComment`, `PostLike` 및 `PostRole`은 각각 `Post` 엔터티의 자식 엔터티입니다.

## <a name="entity-keys"></a>엔터티 키

각 대체 키 정의는 엔터티 인스턴스를 고유하게 식별하는 하나 이상의 특성을 조합하여 설명합니다. 대체 키는 일반적으로 외부 시스템과의 통합에만 적용됩니다. 대체 키를 정의하여 레코드를 고유하게 식별할 수 있습니다. GUID 고유 식별자 키를 지원하지 않는 시스템과 데이터를 통합하는 경우에 유용합니다. 엔터티를 고유하게 식별하기 위해 단일 필드 값 또는 필드 값 조합을 정의할 수 있습니다. 대체 키를 추가하면 이러한 특성에 고유성 제약 조건이 적용됩니다. 동일한 값을 사용하도록 다른 엔터티 레코드를 만들거나 업데이트할 수 없습니다.

자세한 정보: 
 - [Dynamics 365 고객 관계 사용자 지정 가이드: Dynamics 365 레코드를 참조할 대체 키 정의](/dynamics365/customer-engagement/customize/define-alternate-keys-reference-records)
 - [Dynamics 365 고객 관계 개발자 가이드: 엔터티에 대한 대체 키 정의 및 Dynamics 365 데이터를 외부 시스템과 동기화](/dynamics365/customer-engagement/developer/synchronize-dynamics-365-data-with-external-systems)

## <a name="entity-states"></a>엔터티 상태

대부분의 엔터티에는 레코드 상태를 추적하는 두 가지 속성이 있습니다. 모델 기반 앱에서 **상태**라고 하는 `StateCode` 및 **상태 설명**이라고 하는 `StatusCode`입니다. 

두 특성은 모두 유효한 값을 표시하는 옵션 집합을 포함합니다. 특정 `StatusCode` 옵션만 지정된 `StateCode`에 대해 유효하도록 `StateCode` 및 `StatusCode` 특성 값이 연결됩니다.

이는 엔터티에 따라 다를 수 있지만 대부분의 엔터티에서 일반적인 패턴이며, 사용자 지정 엔터티에 대한 기본값은 다음과 같습니다.

|StateCode 옵션  |StatusCode 옵션  |
|---------|---------|
|0: 활성|1: 활성|
|1: 비활성|2: 비활성|

일부 엔터티에는 다른 옵션 집합이 있습니다. 

**예**: `PhoneCall` 엔터티, `StateCode` 및 `StatusCode` 옵션


|Column1  |Column2  |
|---------|---------|
|0: 시작됨|1: 시작됨|
|1: 완료됨|2: 수행함 <br />4: 받음|
|2: 취소됨|3: 취소됨|

엔터티에 대한 유효한 상태 코드 집합은 사용자 지정할 수 없지만, 상태 코드는 사용자 지정할 수 있습니다. 해당 `StateCode`에 대해 `StatusCode` 추가 옵션을 추가할 수 있습니다.

사용자 지정 엔터티의 경우 유효한 상태 간 전환에 대한 추가 조건을 정의할 수 있습니다. 자세한 정보: 
- [Dynamics 365 고객 관계 개발자 가이드: 엔터티 특성 메타데이터 사용자 지정](/dynamics365/customer-engagement/developer/customize-entity-attribute-metadata)
- [Dynamics 365 고객 관계 개발자 가이드: 사용자 지정 상태 모델 전환 정의](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions).

### <a name="see-also"></a>참고 항목

[Common Data Service for Apps 엔터티](entities.md)