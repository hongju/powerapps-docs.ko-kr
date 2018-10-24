---
title: 연결 역할 구성 | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.author: matp
manager: brycho
ms.openlocfilehash: 4faf195f1c751e3796267d52725c1cb753c4889d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696075"
---
# <a name="configure-connection-roles"></a>연결 역할 구성

앱용 Common Data Service를 사용하면 엔터티 관계를 만들지 않고 엔터티 레코드 간의 **연결**을 정의할 수 있습니다. 모델 기반 앱에서 사용자는 레코드 간에 명명된 링크를 설정하여 실제 엔터티 관계를 만드는 것을 정당화하지 않는 공식적인 관계를 덜 설정할 수 있습니다. 몇 가지 예로 *친구*, *형제*, *배우자*, *참석자* 및 *관련자*가 포함됩니다. 일부 연결은 *자식*과 *부모*, *남편*과 *아내* 또는 *의사*와 *환자*같은 상호 관계가 될 수도 있습니다.

사람들이 두 레코드 간의 연결을 설정하면 관계에 대한 설명과 시작 및 종료 날짜와 같은 추가 정보를 추가할 수도 있습니다. 자세한 정보: [레코드 간의 관계를 정의하고 볼 수 있는 연결 만들기](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)

**연결 역할** 엔터티에 대한 쓰기 액세스 권한이 있는 모든 사용자는 누구나 사용할 수 있는 연결을 설정할 수 있습니다.

## <a name="view-connection-roles"></a>연결 역할 보기

앱용 CDS에는 이미 구성된 여러 가지 표준 연결 역할이 있습니다. 그것을 보려면 설정 영역으로 이동해야 합니다. 

### <a name="navigate-to-the-settings-area"></a>설정 영역으로 이동

1. 모델 기반 앱을 보는 동안 URL을 편집하여 `dynamics.com` 이후의 모든 항목을 제거하고 페이지를 새로 고칩니다.
1. **설정** > **비즈니스** > **비즈니스 관리**로 이동한 다음, **연결 역할**을 선택합니다.

![비즈니스 관리 설정의 연결 역할](media/navigate-settings-connection-roles.png)

이 보기에서는 이 환경에 사용할 수 있는 모든 연결 역할을 볼 수 있으며 여기에서 편집할 수 있습니다.

> [!NOTE]
> 솔루션과 함께 연결 역할을 배포하려는 경우 배포할 솔루션에 해당 역할이 포함되어 있는지 확인하세요. 자세한 정보: [솔루션에 연결 역할 추가](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>솔루션 탐색기에서 연결 역할을 확인합니다.

역할 연결은 *솔루션 인식*으로 솔루션에 포함될 수 있음을 의미하므로 배포하는 솔루션에 연결 역할을 추가할 수도 있습니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

**설정** 영역에서 볼 수 있는 대부분의 연결 역할은 *내부* **기본 솔루션**에 정의되어 있습니다(**Common Data Services 기본 솔루션**과 혼동하지 않아야 함). 이 내부 **기본 솔루션**에는 시스템의 모든 사용자 지정이 포함되어 있습니다. **기본 솔루션**을 보려면 **모든 솔루션 - 내부** 보기를 선택합니다.

## <a name="add-connection-roles-to-a-solution"></a>솔루션에 연결 역할 추가

일반적으로 내부 **기본 솔루션**의 구성 요소는 편집하지 않는 것이 좋습니다. **Common Data Services 기본 솔루션** 또는 작업하기 위해 만든 모든 솔루션에서 **기존 항목 추가** 명령을 사용하여 기본 연결 역할을 솔루션으로 가져올 수 있습니다.

![기존 연결 역할 추가](media/add-existing-connection-role.png)

솔루션에 연결 역할을 추가하면 표시되는 모든 위치에서 편집할 수 있습니다.

## <a name="create-or-edit-connection-roles"></a>연결 역할을 만들거나 편집합니다.

> [!IMPORTANT]
> 새 연결 역할 또는 변경 내용이 포함된 솔루션을 기존 연결 역할에 배포하려면 배포할 솔루션에 추가해야 합니다. **설정** 영역을 사용하여 새 연결 역할을 편집하거나 추가하면 이러한 연결 역할이 내부 **기본 솔루션**에 추가되고, 솔루션에 먼저 추가하지 않으면 배포할 솔루션에 포함되지 않습니다. 자세한 정보 [솔루션에 연결 역할 추가](#add-connection-roles-to-a-solution)

**연결 역할** 목록에서 편집할 연결 역할 중 하나를 선택합니다.
양식에서 명확하게 호출되는 연결 역할을 정의하는 세 가지 단계가 있습니다.

![연결 역할 양식 만들기](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>연결 역할 설명

다음 필드를 설정합니다.

|필드|설명|
|--|--|
|**Name**|(필수) 연결을 설명하는 텍스트입니다.|
|**연결 역할 범주**|연결의 범주를 설명하는 그룹입니다. 자세한 정보: [연결 역할 범주 값](#connection-role-category-values)|
|**설명**|역할에 대한 정의를 제공합니다.|

#### <a name="connection-role-category-values"></a>연결 역할 범주 값

기본 **연결 역할 범주** 값은 다음과 같습니다.
- Business
- 가족
- 소셜
- 영업
- 기타
- 관련자
- 영업팀
- 서비스

**범주** 글로벌 옵션 집합을 편집하여 새 범주를 추가하거나 기존 범주를 수정할 수 있습니다. 자세한 정보: [앱용 Common Data Service에 대한 글로벌 옵션 집합 만들기 및 편집(선택 목록)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>레코드 유형 선택

연결할 수 있는 레코드 유형을 선택합니다.

> [!NOTE]
> **모두**가 기본적으로 선택되어 있지만 추가할 연결 역할에 적합한 유형을 고려해야 합니다.

### <a name="matching-connection-roles"></a>연결 역할 일치

이 선택적 단계에서는 상호 방식으로 적용되는 역할을 정의할 수 있습니다. 필수 사항은 아니지만 연결이 정의되면 더 의미가 있습니다.

예를 들어 사람들이 Glen은 Mary의 *친구*라고 설정할 수 있지만, 이것이 Mary가 Glen의 *친구*라는 것을 의미하나요? 그러길 바랍니다. 그러나 Glen이 Mary의 *아버지*인 경우 Mary가 Glen의 *아버지*임을 의미하는 것은 아닙니다. 올바른 상호 관계를 설정하려면 이 추가 단계가 필요합니다.

일치하는 연결 역할이 없는 연결 역할을 설정한 경우 해당 역할은 연결이 적용된 레코드에서 연결을 볼 때만 표시됩니다. 연결된 레코드에서 볼 때 일치하는 역할이 설정되어 있지 않으면 역할이 비어 있게 됩니다.

*친구*, *배우자*, *동료* 또는 *형제*와 같은 역할 정의의 경우 일치하는 역할을 자체에 할당하는 것이 가장 좋습니다. 일치하는 단일 연결 역할이 구성된 경우 일치하는 단일 연결 역할이 양방향으로 적용됩니다.

> [!IMPORTANT]
> 일치하는 연결 역할을 직접 설정하려면 먼저 이 일치하는 연결 역할 없이 새 연결 역할을 저장해야 합니다.

일부 연결 역할은 일치하는 연결 역할로 이미 구성되어 있습니다. *퇴사 직원*은 *전 고용주*와 일치하며 그 반대의 경우도 마찬가지입니다. 이러한 종류의 일대일 일치 연결 역할이 가장 일반적입니다.

여러 개의 일치하는 연결 역할을 구성하여 복잡한 관계를 설명할 수 있습니다. *아버지*와 같은 연결 역할을 만드는 경우 *딸* 및 *아들*과 같은 두 역할을 추가로 구성하고 두 역할을 모두 *아버지*에 일치하는 연결 역할로 적용할 수 있습니다. 결과적으로 *딸*과 *아들* 연결 역할은 모두 *아버지*와 일치해야 합니다. 물론 그런 다음, *딸* 및 *아들*과 비슷하게 일치하는 *어머니*에 대한 동일한 역할을 설정해야 합니다.

> [!TIP]
> 복잡한 연결 역할 집합을 만들기 전에 더 간단한 역할 집합으로도 충분할지 고려합니다. 예를 들어 *아버지*, *어머니*, *아들* 및 *딸*과 같이 복잡한 연결 역할 집합을 만드는 대신 단순한 *부모*와 *자식*을 사용하는 것이 효율적인지 고려합니다.

일치하는 연결 역할이 둘 이상 구성된 경우 이러한 연결 역할은 유효한 상호 역할만 나타냅니다. 첫 번째 것이 기본값으로 자동 적용됩니다. 기본값이 올바르지 않으면 수동으로 연결을 편집하고 구성에 정의된 유효한 옵션 중에서 선택해야 합니다.

### <a name="see-also"></a>참고 항목
<!-- This is in the basics guide. It needs to be migrated -->
[레코드 간의 관계를 정의하고 볼 수 있는 연결 만들기](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[앱용 Common Data Service에 대한 글로벌 옵션 집합 만들기 및 편집(선택 목록)](create-edit-global-option-sets.md)<br />
[엔터티 간의 관계 만들기 및 편집](create-edit-entity-relationships.md)


