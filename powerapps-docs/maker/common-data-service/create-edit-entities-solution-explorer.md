---
title: 솔루션 탐색기를 사용하여 엔터티 만들기 및 편집 | MicrosoftDocs
description: 솔루션 탐색기를 사용하여 엔터티를 만드는 방법 알아보기
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 48025088da85bf0685ba1a46efa4f3a989a20a58
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690292"
---
# <a name="create-and-edit-entities-using-solution-explorer"></a>솔루션 탐색기를 사용하여 엔터티 만들기 및 편집

가장 일반적인 상황에서는 PowerApps 포털을 사용하여 엔터티를 손쉽게 만들 수 있지만 모든 기능이 구현되는 것은 아닙니다. [앱용 Common Data Service for Apps에서 엔터티 만들기 및 편집](create-edit-entities.md)에 설명된 요구 사항을 충족해야 하는 경우 솔루션 탐색기를 사용하여 엔터티를 만들거나 편집하여 구현할 수 있습니다.

## <a name="open-solution-explorer"></a>솔루션 탐색기 열기

사용자가 만드는 모든 엔터티의 이름 부분은 사용자 지정 접두사입니다. 이는 작업 중인 솔루션의 솔루션 게시자를 기반으로 설정됩니다. 사용자 지정 접두사에 관심이 있는 경우 이 엔터티에 대해 원하는 사용자 지정 접두사가 있는 관리되지 않는 솔루션에서 작업하는지 확인해야 합니다. 자세한 정보: [솔루션 게시자 접두사 변경](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>엔터티 보기

솔루션 탐색기 **구성 요소** 노드에서 **엔터티** 노드를 선택합니다.

![솔루션 탐색기에서 엔터티 보기](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>엔터티 만들기

[엔터티를 볼 때](#view-entities) **새로 만들기**를 선택하여 새로운 엔터티 양식을 엽니다.

![솔루션 탐색기의 새로운 엔터티 양식](media/new-entity-form-solution-explorer.png)

새 엔터티 양식에는 두 개의 탭이 있습니다. **일반** 탭에는 엔터티 옵션이 있습니다. **기본 필드** 탭에는 조회 필드에서 엔터티를 여는 링크가 있는 경우 표시되는 텍스트를 정의하는 한 줄로 된 특수 텍스트 필드에 대한 각 엔터티의 옵션이 있습니다.

각 섹션에 대한 자세한 내용은 다음을 참조하세요.
- [기본 필드 구성](#configure-the-primary-field)
- [필수 필드 구성](#configure-required-fields)

> [!NOTE]
> 또한 엔터티를 사용자 지정 활동으로 만들 수도 있습니다. 이 옵션은 일부 기본 옵션 값을 변경합니다. 자세한 정보: [사용자 지정 활동 엔터티 만들기](#create-custom-activity-entity)

엔터티에 필요한 옵션을 설정한 후 ![명령 저장](media/save-entity-icon-solution-explorer.png) 항목을 클릭하여 사용자 지정 엔터티를 만듭니다.

### <a name="configure-the-primary-field"></a>기본 필드 구성

**기본 필드** 탭에서는 일반적으로 기본 필드에 기본값을 그대로 사용할 수 있지만 다음과 같은 옵션이 있습니다.

|필드   |설명  |
|---------|---------|
|**표시 이름**|양식 및 목록에서 이 필드에 표시되는 지역화 가능 레이블을 입력합니다. 기본값은 **이름**입니다.|
|**Name**|시스템에서 이 필드에 사용되는 이름을 설정합니다. 기본값은 `<customization prefix>_name`입니다.|
|**최대 길이**|필드 값의 최대 길이를 입력합니다. 기본값은 100입니다.|

> [!NOTE]
> 엔터티가 활동 엔터티인 경우 이러한 옵션이 적용되지 않습니다. 자세한 정보: [사용자 지정 활동 엔터티 만들기](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>필수 필드 구성

**일반** 탭에서 일부 옵션은 엔터티를 저장하기 위한 필수 옵션입니다.

|필드   |설명  |
|---------|---------|
|**표시 이름**|앱에서 표시되는 엔터티의 단수 이름입니다.<br />이는 나중에 변경할 수 있습니다.|
|**복수 이름**|앱에서 표시되는 엔터티의 복수 이름입니다.<br />이는 나중에 변경할 수 있습니다.|
|**Name**|이 필드는 사용자가 입력하는 표시 이름에 따라 미리 채워집니다. 여기에는 솔루션 게시자 사용자 지정 접두사가 포함됩니다.|
|**소유권**|사용자나 팀 소유 또는 조직 소유를 선택할 수 있습니다. 자세한 정보: [엔터티 소유권](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>엔터티 편집

[엔터티를 볼 때](#view-entities) 편집하려는 엔터티를 선택하거나 방금 저장한 새 엔터티를 계속 편집합니다.

> [!NOTE]
> 관리되는 솔루션의 일부인 표준 엔터티 또는 사용자 지정 엔터티는 적용 가능한 변경 사항에 제한이 있을 수 있습니다. 옵션이 사용 불가하거나 비활성화된 경우 변경을 수행할 수 없습니다.

#### <a name="set-once-options"></a>옵션을 한 번 설정

다음 옵션은 한 번 설정한 후에 변경할 수 없습니다. 이러한 옵션은 필요할 때만 설정하도록 주의해야 합니다.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

#### <a name="options-that-you-can-change"></a>변경할 수 있는 옵션

다음 속성은 언제든 지 변경할 수 있습니다.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)]

또한 다음과 같이 변경할 수도 있습니다.
- [앱용 Common Data Service에서 필드 만들기 및 편집](create-edit-fields.md)
- [엔터티 간의 관계 만들기 및 편집](create-edit-entity-relationships.md)
- [양식 만들기 및 설계](../model-driven-apps/create-design-forms.md)
- [프로세스를 표준화하는 비즈니스 프로세스 흐름 만들기](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>엔터티 삭제

시스템 관리자 보안 역할이 있는 사용자는 관리되는 솔루션의 일부가 아닌 사용자 지정 엔터티를 삭제할 수 있습니다.  
  
> [!IMPORTANT]
>  사용자 지정 엔터티를 삭제하면 해당 엔터티에 대한 데이터를 저장하는 데이터베이스 테이블과 여기에 포함된 모든 데이터가 사라집니다. 사용자 지정 엔터티에 대한 부모/자식 관계를 포함하는 관련 레코드도 삭제됩니다. 부모/자식 관계에 대한 자세한 내용은 [엔터티 간의 관계 만들기 및 편집](create-edit-entity-relationships.md)을 참조하세요.  
  
> [!NOTE]
> 삭제된 엔터티에서 데이터를 복구하는 유일한 방법은 엔터티가 삭제되기 이전의 시점에서 데이터베이스를 복원하는 것입니다. 자세한 정보: [인스턴스 백업 및 복원](/dynamics365/customer-engagement/admin/backup-restore-instances)

[엔터티를 볼 때](#view-entities) 도구 모음에서 ![삭제 명령](media/delete.gif)을 클릭합니다.

엔터티를 볼 때 메뉴 모음에서 삭제 명령을 사용합니다.

![삭제 명령](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> 데이터를 포함하는 엔터티를 삭제하면 모든 데이터가 제거됩니다. 이 데이터는 데이터베이스 백업으로만 검색할 수 있습니다.

> [!NOTE]
> 엔터티 종속성이 있으면 **세부 정보** 링크와 함께 **구성 요소를 삭제할 수 없음** 오류가 표시됩니다. 이 링크는 엔터티를 삭제할 수 없는 이유에 대한 정보를 확인하는 데 사용할 수 있습니다. 대부분의 경우 이 오류는 제거해야 하는 종속성으로 인해 발생합니다. 
>
> 엔터티 삭제를 차단하는 종속성이 두 개 이상 있을 수 있습니다. 이 오류 메시지에는 첫 번째 종속성만 표시될 수 있습니다. 종속성을 확인하는 다른 방법은 [엔터티 종속성 파악](#identify-entity-dependencies)을 참조하세요.



### <a name="identify-entity-dependencies"></a>엔터티 종속성 파악

엔터티가 삭제되기 전에 이를 방해하는 종속성을 파악할 수 있습니다. 

1. 솔루션 탐색기에서 엔터티를 선택한 후 명령 모음에서 **종속성 표시**를 클릭합니다.

![종속성 표시 명령](media/entity-show-dependencies.png)

2. 대화 상자 창이 열리면 목록을 오른쪽으로 스크롤하여 **종속성 유형** 열을 봅니다.

![게시된 종속성 유형](media/published-entity-dependency.png)

**게시된** 종속성은 엔터티 삭제를 차단합니다. 시스템에서 **내부** 종속성을 확인해야 합니다.  

3. 이 게시된 종속성을 제거하면 엔터티를 삭제할 수 있습니다.

 > [!NOTE]
 > 매우 일반적인 종속성은 다른 엔터티 양식에 삭제 대상 엔터티에 대한 조회 필드가 있는 경우입니다. 양식에서 조회 필드를 제거하면 종속성이 해결됩니다.

## <a name="create-custom-activity-entity"></a>사용자 지정 활동 엔터티 만들기

활동 엔터티를 만들려면 이 항목에 설명된 것 단계를 따르되, **활동 엔터티로 정의**를 선택합니다.

![활동 엔터티로 정의](media/create-activity-entity-solution-explorer.png)

활동 엔터티는 일정에 항목을 만들 수 있는 작업을 추적하는 특수한 엔터티 유형입니다. 자세한 정보: [활동 엔터티](types-of-entities.md#activity-entities).

이 옵션을 설정하면 일부 엔터티 속성이 호환되지 않습니다. 활동 엔터티는 모든 활동 엔터티가 사용하는 표준 동작을 준수해야 합니다.

기본 필드 **이름** 및 **표시 이름**은 **제목**으로 설정되며, 이는 변경할 수 없습니다.

다음 옵션이 기본적으로 설정되며 이는 변경할 수 없습니다.

 - **피드백**
 - **노트(첨부 파일 포함)**
 - **연결**
 - **큐**
 - **Outlook용 Dynamics 365의 오프라인 기능**

다음 옵션은 설정할 수 없습니다.

- **이 엔터티를 표시하는 영역**
- **활동**
- **이메일 보내기**
- **메일 병합**
- **단일 레코드 감사**
- **여러 레코드 감사**

## <a name="create-a-virtual-entity"></a>가상 엔터티 만들기

일부 옵션은 가상 엔터티를 만들 때 사용됩니다.

|옵션   |설명  |
|---------|---------|
|**가상 엔터티**|엔터티가 가상 엔터티인지 여부입니다.|
|**데이터 원본**|엔터티의 데이터 원본입니다.|

자세한 정보: [외부 데이터 원본의 데이터를 포함하는 가상 엔터티 만들기 및 편집](create-edit-virtual-entities.md)

### <a name="see-also"></a>참고 항목
[앱용 Common Data Service에서 엔터티 만들기 및 편집](create-edit-entities.md)<br />
[자습서: PowerApps에 구성 요소가 있는 사용자 지정 엔터티 만들기](/powerapps/maker/common-data-service/create-custom-entity)<br />
[솔루션 만들기](create-solution.md)