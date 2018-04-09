---
title: 특성 메타데이터 | Microsoft Docs
description: Common Data Service for Apps에서 사용되는 특성 메타데이터에 대해 알아봅니다.
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
ms.openlocfilehash: efe04d9bd9c761f432d16d4c9304c52e55503aeb
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="attribute-metadata"></a>특성 메타데이터

엔터티에는 각 레코드에 포함될 수 있는 데이터를 나타내는 특성의 컬렉션이 포함됩니다. 개발자는 다양한 유형의 특성과 이를 사용하는 방법을 이해해야 합니다. 

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: 엔터티 특성 소개](/dynamics365/customer-engagement/developer/introduction-entity-attributes)

## <a name="attribute-names"></a>특성 이름

엔터티와 마찬가지로, 각 특성에는 만들어질 때 정의된 고유한 이름이 있습니다. 이 이름은 다음과 같이 여러 가지 방법으로 표시됩니다.


|이름 |설명  |
|---------|---------|
|`SchemaName`|일반적으로 파스칼식 대/소문자 버전의 논리적 이름입니다. 예: `AccountNumber`|
|`LogicalName`|모두 소문자 이름입니다. 예: `accountnumber`|

사용자 지정 특성을 만들면 해당 특성이 만들어진 솔루션과 연결된 솔루션 게시자의 사용자 지정 접두사 값이 선택한 이름 앞에 추가됩니다.

특성을 만든 후에는 특성 이름을 변경할 수 없습니다.

또한 각 특성에는 지역화된 값을 표시할 수 있는 두 가지 속성이 있습니다. 이러한 값은 앱의 특성을 참조하는 데 사용되는 값입니다.

|이름 |설명  |
|---------|---------|
|`DisplayName`|일반적으로 스키마 이름과 동일하지만 공백을 포함할 수 있습니다. 예: **계정 번호**|
|`Description`|특성을 설명하거나 사용자에게 지침을 제공하는 짧은 문장입니다. 예: *시스템 보기에서 신속하게 계정을 검색하고 식별하려면 계정에 대한 ID 번호 또는 코드를 입력합니다.*<br />모델 기반 앱의 경우 사용자가 양식에서 이 특성에 대한 필드 위를 마우스로 가리키면 이 정보가 표시됩니다.|


이러한 값은 앱의 특성을 참조하는 데 사용되는 지역화할 수 있는 값입니다. 이러한 값은 언제든지 변경할 수 있습니다. 지역화된 값을 추가하거나 편집하려면 [Dynamics 365 고객 관계 사용자 지정 가이드: 사용자 지정된 엔터티 및 필드 텍스트를 다른 언어로 번역](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation)을 참조하세요.

## <a name="attribute-types"></a>특성 유형

`AttributeTypeName` 속성은 특성 유형을 설명합니다. 이 속성에는 존재하는 다양한 유형의 각 특성에 대한 레이블을 제공하는 `AttributeTypeDisplayName` 형식의 값이 포함됩니다. 

> [!NOTE]
> `AttributeType` 속성으로 혼동하지 마세요. 이전의 이 속성 값은 `ImageType` 특성을 `Virtual`로 표시한다는 점을 제외하고는 대부분 `AttributeTypeName`에 맞춰집니다. `AttributeType` 속성 대신 `AttributeTypeName` 속성을 참조해야 합니다.

다음 표에서,

- 이러한 유형은 비교를 위해 범주별로 그룹화됩니다.
- 각 `AttributeTypeDisplayName` 값에 대해 사용할 수 있는 경우 .NET 어셈블리의 해당 [AttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.attributemetadata) 파생 클래스가 포함됩니다. 이러한 유형과 `AttributeTypeDisplayName` 레이블 간에는 일대일 관계가 없습니다.
- 사용자 지정 특성으로 만들 수 있는 특성 유형에는 UI에 표시된 해당 레이블이 포함됩니다.


|범주|AttributeTypeDisplayName/<br />AttributeMetadata 형식|생성 가능 여부/<br />레이블|설명  |
|---------|---------|---------|---------|
|분류|`BooleanType`<br />[BooleanAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.booleanattributemetadata)|예<br />**두 가지 옵션**|일반적으로 true 또는 false 값을 나타내는 두 가지 옵션에서 선택한 옵션 값을 포함합니다.<br />자세한 정보: [옵션 집합](#option-sets)|
|분류|`EntityNameType`<br />[EntityNameAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.entitynameattributemetadata)|아니요|시스템의 엔터티에 해당하는 옵션 값을 포함합니다. 내부 전용입니다.|
|분류|`MultiSelectPicklistType`<br />[MultiSelectPicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.multiselectpicklistattributemetadata)|예<br />**MultiSelect Option Set**|여러 옵션을 선택할 수 있는 여러 개의 선택된 옵션 값을 포함합니다.<br />자세한 정보: <br />[옵션 집합](#option-sets)<br />[Dynamics 365 고객 관계 개발자 가이드: 다중 선택 목록 특성](/dynamics365/customer-engagement/developer/multi-select-picklist)|
|분류|`PicklistType`<br />[PicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.picklistattributemetadata)|예<br />**옵션 집합**|한 가지 옵션을 선택할 수 있는 선택된 옵션 값을 포함합니다.<br />자세한 정보: [옵션 집합](#option-sets)|
|분류|`StateType`<br />[StateAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stateattributemetadata)|아니요|엔터티 레코드의 상태를 설명하는 옵션 값을 포함합니다.<br />자세한 정보: [옵션 집합](#option-sets)|
|분류|`StatusType`<br />[StatusAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.statusattributemetadata)|아니요|엔터티 레코드의 상태에 대한 이유를 설명하는 옵션 값을 포함합니다.<br />자세한 정보: [옵션 집합](#option-sets)|
|컬렉션|`CalendarRulesType`|아니요|`CalendarRules` 엔터티 레코드의 컬렉션을 포함합니다.<br />이 유형을 사용하는 특성은 없습니다. 프록시를 생성할 때 코드 생성 도구에서 메타데이터에 없는 두 개의 시뮬레이션된 특성을 만듭니다. 이러한 특성은 엔터티 레코드와 일대다 관계로 연결된 일정 규칙 레코드의 뷰를 나타냅니다.|
|컬렉션|`PartyListType`|아니요|`ActivityParty` 엔터티 레코드의 컬렉션을 포함합니다.<br />자세한 정보: [ActivityParty 엔터티](#activityparty-entity)|
|날짜 및 시간|`DateTimeType`<br />[DateTimeAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.datetimeattributemetadata)|예<br />**날짜 및 시간**|날짜 및 시간 값을 포함합니다.<br />모든 날짜 및 시간 특성은 1753년 1월 1일 오전 12시처럼 이른 시간 값을 지원합니다.|
|이미지|`ImageType`<br />[ImageAttributeMetadata]()|예<br />**이미지**|엔터티 레코드에 대한 이미지 데이터 검색을 지원하는 데이터를 포함합니다.<br />자세한 정보: [엔터티 이미지](entity-metadata.md#entity-images)|
|관리 속성|`ManagedPropertyType`<br />[ManagedPropertyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.imageattributemetadata)|아니요|관리형 솔루션에 포함되는 경우 엔터티 레코드에 저장된 솔루션 구성 요소를 사용자 지정할 수 있는지 여부를 나타내는 데이터를 포함합니다.<br />자세한 정보: [관리 속성](introduction-solutions.md#managed-properties)|
|수량|`BigIntType`<br />[BigIntAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.bigintattributemetadata)|아니요|`BigInt` 값을 포함합니다. 내부 전용입니다.|
|수량|`DecimalType`<br />[DecimalAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.decimalattributemetadata)|예<br />**10진수**|`Decimal` 값을 포함합니다. `Precision` 속성은 자릿수 수준을 설정합니다.|
|수량|`DoubleType`<br />[DoubleAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.doubleattributemetadata)|예<br />**부동 소수점 숫자**|`Double` 값을 포함합니다. `Precision` 속성은 자릿수 수준을 설정합니다.|
|수량|`IntegerType`<br />[IntegerAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.integerattributemetadata)|예<br />**정수**|`Int` 값을 포함합니다.|
|수량|`MoneyType`<br />[MoneyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.moneyattributemetadata)|예<br />**통화**|`Decimal` 값을 포함합니다. `PrecisionSource` 속성은 정밀도 수준이 설정되는 위치를 결정합니다.<br />0: `Precision` 속성<br />1: `Organization.PricingDecimalPrecision` 특성<br />2: 엔터티 레코드의 `TransactionCurrency.CurrencyPrecision` 특성|
|참조|`CustomerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|예<br />**고객**|계정 또는 연락처 엔터티 레코드에 대한 참조를 포함합니다.|
|참조|`LookupType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|예<br />**조회**|엔터티 레코드에 대한 참조를 포함합니다. 유효한 레코드의 논리적 이름은 일반적으로 특성의 `Targets` 속성에 저장됩니다.|
|참조|`OwnerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|아니요|사용자 또는 팀 엔터티 레코드에 대한 참조를 포함합니다.|
|문자열|`MemoType`<br />[MemoAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.memoattributemetadata)|예<br />**여러 줄 텍스트**|여러 줄 텍스트 상자에 표시할 문자열 값을 포함합니다.|
|문자열|`StringType`<br />[StringAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stringattributemetadata)|예<br />**한 줄 텍스트**|한 줄 텍스트 상자에 표시할 문자열 값을 포함합니다.|
|고유 식별자|`UniqueidentifierType`<br />[UniqueIdentifierAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.uniqueidentifierattributemetadata)|아니요|GUID 고유 식별자 값을 포함합니다.|
|가상|`VirtualType`|아니요|이러한 특성은 코드에서 사용할 수 없으며 일반적으로 무시할 수 있습니다.|


## <a name="supported-operations-and-form-usage-for-attributes"></a>특성에 대해 지원되는 작업 및 양식 사용

각 특성에는 참여할 수 있는 작업의 종류와 양식에 포함될 수 있는 방법을 설명하는 부울 속성이 포함됩니다.

|속성|설명|
|--|--|
|`IsRequiredForForm`|특성을 양식의 필드로 포함해야 하는지 여부입니다.|
|`IsValidForCreate`|특성 값을 만들기 작업에서 설정할 수 있는지 여부입니다.|
|`IsValidForForm`|특성을 양식의 필드로 포함할 수 있는지 여부입니다.|
|`IsValidForRead`|특성 값을 검색할 수 있는지 여부입니다.|
|`IsValidForUpdate`|특성 값을 업데이트 작업에서 설정할 수 있는지 여부입니다.|

해당 작업에 유효하지 않은 특성에 대한 만들기 또는 업데이트 작업에서 값을 설정하려고 하면 값이 무시됩니다.
읽기에 유효하지 않은 특성을 검색하려고 하면 null 값이 반환됩니다.


## <a name="attribute-requirement-level"></a>특성 요구 사항 수준

`RequiredLevel` 속성은 특성 값이 필요한지 여부를 설명하는 부울 관리 속성입니다.

이 속성에는 다음 값을 설정할 수 있습니다.

|이름|값|UI 레이블|설명|
|--|--|--|--|
|`None`|0|**(옵션)**|요구 사항이 지정되지 않습니다.|
|`SystemRequired`|1|**시스템 필수**|특성에 값이 있어야 합니다.|
|`ApplicationRequired`|2|**업무상 필수**|특성에 비즈니스와 관련된 값이 있어야 합니다.|
|`Recommended`|3|**업무상 권장**|특성에 값이 있는 것이 좋습니다.|

Common Data Service는 시스템에서 만든 특성에 대해서만 `SystemRequired` 옵션을 적용합니다. 사용자 지정 특성은 `SystemRequired` 옵션을 사용하도록 설정할 수 없습니다. 

모델 기반 앱은 `ApplicationRequired` 옵션을 적용하고, `Recommended` 옵션에는 다른 프레젠테이션을 사용합니다. 사용자 지정 클라이언트의 작성자는 이 정보를 사용하여 유사한 유효성 검사 또는 프레젠테이션 옵션을 요구할 수 있습니다.

이는 관리 속성이므로 관리형 솔루션의 게시자는 솔루션의 소비자가 솔루션의 특성에 대해 이러한 설정을 변경할 수 있는지 여부를 결정할 수 있습니다.

자세한 정보: [관리 속성](introduction-solutions.md#managed-properties)


## <a name="rollup-and-calculated-attributes"></a>롤업 및 계산 특성

계산 및 롤업 특성을 사용하면 사용자가 수동으로 계산을 수행하고 해당 작업에 집중할 필요가 없습니다. 시스템 관리자는 개발자와 함께 작업하지 않고도 많은 일반적인 계산 값을 포함하도록 필드를 정의할 수 있습니다. 또한 개발자는 이러한 계산을 자체 코드 내에서가 아니라 플랫폼 기능을 활용하여 수행할 수 있습니다.

자세한 정보: 
- [Dynamics 365 고객 관계 사용자 지정 가이드: 값을 집계하는 롤업 필드 정의](/dynamics365/customer-engagement/customize/define-rollup-fields)
- [Dynamics 365 고객 관계 사용자 지정 가이드: 계산 및 롤업 특성](/dynamics365/customer-engagement/customize/define-calculated-fields)
- [Dynamics 365 고객 관계 개발자 가이드: 계산 및 롤업 특성](/dynamics365/customer-engagement/developer/calculated-rollup-attributes)

## <a name="attribute-format"></a>특성 형식

특성에 대한 형식 값은 모델 기반 앱에 표시되는 방법을 제어합니다. 사용자 지정 앱 개발자는 이 정보를 사용하여 비슷한 환경을 만들 수 있습니다.

### <a name="integer-formats"></a>정수 형식

정수 특성이 있는 `Format` 속성을 사용하여 이 유형에 대한 대체 사용자 환경을 표시합니다.

|옵션|설명|
|--|--|
|`None`|숫자 값을 편집하는 텍스트 상자를 표시합니다.|
|`Duration`|시간 간격이 포함된 드롭다운 목록을 표시합니다. 사용자가 목록에서 값을 선택하거나 시간(분)을 나타내는 정수 값을 입력할 수 있습니다.|
|`TimeZone`|표준 시간대 목록이 포함된 드롭다운 목록을 표시합니다.|
|`Language`|조직에서 사용하도록 설정된 언어 목록이 포함된 드롭다운 목록을 표시합니다. 다른 언어를 사용하지 않도록 설정된 경우 기본 언어만 선택할 수 있습니다. 저장된 값은 해당 언어에 대한 LCID 값입니다.|

### <a name="string-formats"></a>문자열 형식

문자열 특성이 있는 `FormatName` 속성을 사용하여 문자열 특성의 형식을 지정하는 방법을 제어하도록 [StringFormatName 클래스](/dotnet/api/microsoft.xrm.sdk.metadata.stringformatname)의 값을 설정합니다.

|이름|설명|
|--|--|
|`Email`|양식 필드에서 텍스트 값을 이메일 주소로 확인하고 mailto 링크를 해당 필드에 만듭니다.|
|`PhoneNumber`|양식 필드에는 Skype를 사용하여 전화 통화를 시작하는 링크가 포함됩니다.|
|`PhoneticGuide`|내부 전용입니다.|
|`Text`|양식에 텍스트 상자가 표시됩니다.|
|`TextArea`|양식에 텍스트 영역 필드가 표시됩니다.|
|`TickerSymbol`|양식에 주식 시세 기호에 대한 따옴표를 표시하기 위해 열리는 링크가 표시됩니다.|
|`URL`|양식에 URL을 열 수 있는 링크가 표시됩니다.|
|`VersionNumber`|내부 전용입니다.|

### <a name="date-and-time-formats"></a>날짜 및 시간 형식

날짜 및 시간 특성에 대한 동작을 제어하는 `DateTimeBehavior` 속성입니다.
다음 세 가지 옵션이 있습니다.

|옵션|간단한 설명|
|--|--|
|`UserLocal`|날짜와 시간 값을 UTC 값으로 시스템에 저장합니다.|
|`DateOnly`|시간 값이 오전 12시(00:00:00)인 실제 날짜 값을 시스템에 저장합니다.|
|`TimeZoneIndependent`|사용자 표준 시간대와 관계없이 실제 날짜 및 시간 값을 시스템에 저장합니다.|

`Format` 속성을 사용하여 `DateTimeBehavior`와 관계없이 모델 기반 앱에서 값을 표시하는 방법을 제어합니다.

|옵션|설명|
|--|--|
|DateAndTime|전체 날짜 및 시간을 표시합니다.|
|DateOnly|날짜만 표시합니다.|

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: 날짜 및 시간 특성의 동작 및 형식](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute)

## <a name="auto-number-attributes"></a>자동 번호 매기기 특성

엔터티에 대한 자동 번호 매기기 특성을 추가할 수 있습니다. 현재 프로그래밍 방식으로 특성을 추가할 수 있습니다. 이 유형의 특성을 추가하는 사용자 인터페이스가 없습니다.
자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: 자동 번호 매기기 특성 만들기](/dynamics365/customer-engagement/developer/create-auto-number-attributes)

## <a name="option-sets"></a>옵션 집합

옵션 집합을 표시하는 특성은 특성으로 정의된 옵션 집합을 참조하거나 둘 이상의 특성에서 공유할 수 있는 별도의 옵션 집합을 참조할 수 있습니다. 이는 한 특성의 값이 다른 특성에도 적용되는 경우에 특히 유용합니다. 공통 옵션 집합을 참조하여 옵션을 한 곳에서 유지 관리할 수 있습니다. *글로벌* 옵션 집합은 공유할 수 있는 집합입니다. *로컬* 옵션 집합은 특성 내에 정의된 집합입니다.

### <a name="retrieve-options-data"></a>옵션 데이터 검색
조직 서비스는 특성에서 사용되는 옵션을 검색하는 데 사용할 수 있는 요청 클래스를 제공합니다.

#### <a name="use-the-organization-service-to-retrieve-options"></a>조직 서비스를 사용하여 옵션 검색

옵션이 있는 각 특성은 [EnumAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata)에서 상속받고 [OptionSet 속성](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata.optionset)을 포함합니다. 이 속성은 [Options 속성](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata.options) 내에 옵션이 포함된 [OptionSetMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata)를 포함합니다. 

조직 서비스를 사용하면 다음 메시지를 사용하여 옵션 집합에 대한 정보를 검색할 수 있습니다.
|요청 클래스|설명|
|--|--|
|[RetrieveAllOptionSetsRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest) |모든 *글로벌* 옵션 집합에 관한 데이터를 검색합니다|
|[RetrieveAttributeRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveattributerequest) |임의의 *로컬* 옵션 집합이 포함된 특성에 관한 데이터를 검색합니다|
|[RetrieveMetadataChangesRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievemetadatachangesrequest) |*로컬* 옵션 집합을 포함할 수 있는 쿼리에 따라 메타데이터를 검색합니다.<br />자세한 정보: [메타데이터에 대한 변경 내용 추적 및 검색](/dynamics365/customer-engagement/developer/retrieve-detect-changes-metadata)|
|[RetrieveOptionSetRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveoptionsetrequest) |하나의 *글로벌* 옵션 집합에 관한 데이터를 검색합니다.|

자세한 정보: 
- [샘플: 파일에 특성 선택 목록 메타데이터 덤프](/dynamics365/customer-engagement/developer/org-service/sample-dump-attribute-picklist-metadata-file)
- [Dynamics 365 고객 관계 개발자 가이드: 글로벌 옵션 집합 사용자 지정](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)

#### <a name="use-the-web-api-to-retrieve-options"></a>Web API를 사용하여 옵션 검색

Web API는 옵션 값을 쿼리하기 위한 RESTful 스타일을 제공합니다. 엔터티 내에서 특성을 검색하여 로컬 또는 글로벌 옵션을 검색할 수 있습니다. 다음 예제에서는 [Account](reference/entities/account.md).[AccountCategoryCode 속성](reference/entities/account.md#BKMK_AccountCategoryCode)에 포함된 옵션에 대해 [OptionSetMetadata](/dynamics365/customer-engagement/web-api/optionsetmetadata)를 반환합니다.

`GET <organization url>/api/data/v9.0/EntityDefinitions(LogicalName='account')/Attributes(LogicalName='accountcategorycode')/Microsoft.Dynamics.CRM.PicklistAttributeMetadata?$select=LogicalName&$expand=OptionSet`

또한 Web API를 사용하면 [RetrieveMetadataChanges 함수](/dynamics365/customer-engagement/web-api/retrievemetadatachanges)도 사용할 수 있습니다.

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: Web API를 사용하여 메타데이터 쿼리 - EntityMetadata 특성 쿼리](/dynamics365/customer-engagement/developer/webapi/query-metadata-web-api#querying-entitymetadata-attributes)



## <a name="attribute-mapping"></a>특성 매핑

기존 엔터티 레코드의 컨텍스트에서 새 엔터티 레코드를 만들면, 기존 엔터티 레코드의 특정 값을 새 엔터티 레코드에 대한 기본값으로 자동으로 전송할 수 있습니다. 이렇게 하면 모델 기반 앱을 사용하는 사용자에 대한 데이터 입력이 간소화됩니다. 응용 프로그램 사용자는 매핑된 값을 보고 엔터티를 저장하기 전에 편집할 수 있습니다.

사용자 지정 클라이언트를 만드는 개발자의 경우, `InitializeFrom` 메시지(조직 서비스 [InitializeFromRequest 클래스](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest) 또는 Web API [InitializeFrom 함수](/dynamics365/customer-engagement/web-api/initializefrom))를 사용하여 구성된 기본값이 설정된 엔터티 데이터를 가져옴으로써 동일한 동작을 수행할 수 있습니다.

자세한 정보 
- [Dynamics 365 고객 관계 사용자 지정 가이드: 엔터티 필드 매핑](/dynamics365/customer-engagement/customize/map-entity-fields#BKMK_mappingEntityFields)
- [Dynamics 365 고객 관계 개발자 가이드: 엔터티 및 특성 매핑 사용자 지정](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)

### <a name="see-also"></a>참고 항목

[Common Data Service for Apps 엔터티](entities.md)