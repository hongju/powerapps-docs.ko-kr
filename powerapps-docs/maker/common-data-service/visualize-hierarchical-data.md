---
title: 모델 기반 앱으로 계층적 데이터 시각화 | MicrosoftDocs
description: 계층적 관련 데이터를 쿼리 및 시각화하는 방법 알아보기
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: bed8662d7d9475215df8e92490702b68e36574e2
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696153"
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>모델 기반 앱으로 계층적 데이터 시각화

> [!NOTE]
> 계층적 데이터 시각화는 **웹** 클라이언트용으로 구성된 모델 기반 앱에서만 사용할 수 있습니다. **통합 인터페이스** 클라이언트에서는 시각화를 사용할 수 없습니다. 자세한 정보: [앱 디자이너를 사용하여 모델 기반 앱 만들기](../model-driven-apps/create-edit-app.md)

엔터티가 계층적 자체 참조 관계를 가지도록 구성되면 해당 계층을 사용하여 시각화를 구성할 수 있습니다. 자세한 정보: [계층적으로 관련된 데이터 정의 및 쿼리](../common-data-service/define-query-hierarchical-data.md)

기본적으로 시각화를 사용할 수 있는 엔터티는 [계정](/powerapps/developer/common-data-service/reference/entities/account), [위치](/powerapps/developer/common-data-service/reference/entities/position) 및 [사용자](/powerapps/developer/common-data-service/reference/entities/systemuser)가 포함됩니다. 이러한 엔터티의 그리드 보기에서는 레코드 이름 왼쪽에 계층 구조 차트를 나타내는 아이콘이 표시됩니다. 기본적으로 계층 구조 아이콘은 일부 레코드에 대해서만 표시됩니다. 계층 관계를 사용하여 관련된 레코드에 대해 아이콘이 표시됩니다.  
  
 ![계층 구조가 있는 계정](media/account-list-with-hierarchy.png)  
  
 계층 구조 아이콘을 선택하면 아래와 같이 왼쪽에는 트리 보기, 오른쪽에는 타일 보기가 있는 계층 구조를 볼 수 있습니다.  
  
 ![계정 트리 및 타일 보기](media/hierachy-security-accounts-tile-view.png)  
  
 계층 구조에 대해 몇 가지 다른 엔터티를 사용할 수 있습니다. 이러한 엔터티에는 [연락처](/powerapps/developer/common-data-service/reference/entities/contact) 및 [팀](/powerapps/developer/common-data-service/reference/entities/team)이 포함됩니다. 계층 구조에 대해 모든 사용자 지정 엔터티를 사용할 수 있습니다.  
  
시각화를 만들 때 기억해야 할 중요한 사항:  
  
- 엔터티당 하나의 (1:N) 자체 참조 관계만 계층적으로 설정할 수 있습니다. 자체 참조 관계에서 주요 엔터티와 관련된 엔터티는 동일한 형식이어야 합니다.  
- 계층 구조 또는 시각화는 하나의 엔터티만을 기반으로 합니다. 계정을 여러 수준으로 표시하는 계정 계층 구조를 나타낼 수 있지만 계정 및 연락처를 동일한 계층 구조 시각화로 표시할 수는 없습니다. 
- 타일에 표시할 수 있는 최대 필드 수는 4개입니다. 타일 보기에 사용되는 빠른 양식에 필드를 더 추가하면 처음 네 개의 필드만 표시됩니다. 

## <a name="hierarchy-settings"></a>계층 구조 설정

계층 구조에 대한 시각화를 사용하려면 계층 구조를 빠른 보기 양식에 연결해야 합니다. 이 작업은 솔루션 탐색기를 통해서만 수행할 수 있습니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

계층 구조 설정은 솔루션 탐색기의 엔터티와 연결됩니다. 

1. [엔터티 보기](../common-data-service/create-edit-entities-solution-explorer.md#view-entities) 중에 **계층 구조 설정**을 선택합니다.
2. 기존 계층 구조 설정이 있는 경우 편집할 수 있습니다. 그렇지 않으면 **새로 만들기**를 클릭하여 새로 만듭니다.
    
    > [!NOTE]
    > 계층 구조 설정이 존재하지 않는 경우 엔터티는 계층 구조를 구성할 수 없습니다.
    >하나의 계층 구조 설정만 있을 수 있습니다. 

1. 다음 필드에 데이터를 설정합니다.

|필드|설명|
|--|--|
|**Name**|*필수.* 계층 구조 설정에 대한 고유한 이름을 추가합니다. 이는 일반적으로 엔터티의 이름일 뿐입니다. 이 값에는 솔루션 게시자의 사용자 지정 접두사가 포함됩니다.|
|**기본 빠른 보기 양식**|*필수.* 기존 빠른 보기 양식에서 선택하거나 선택할 **새로 만들기**를 선택하여 빠른 보기 양식 편집기를 열고 새 양식을 만듭니다.|
|**계층적 관계**|*필수.* 엔터티에 대한 계층적 관계가 이미 정의되어 있으면 여기에 값이 설정됩니다. 값이 없는 경우에는 **계층 구조에 사용하도록 설정한 관계 표시**를 선택하여 대화 상자를 열고 사용 가능한 자체 참조 관계 중 하나를 선택합니다.|
|**설명**|시스템을 사용자 정의하는 향후 사용자가 이 작업이 수행된 이유를 이해할 수 있도록 이 계층 구조의 목적에 대한 설명을 포함시킵니다.|
    

시각화를 위해 동일한 계층적 설정이 한 번 설정되지만 웹 클라이언트와 모바일 클라이언트 모두에 적용됩니다. 태블릿에서는 시각적 개체가 작은 폼 팩터에 적합한 수정된 형식으로 렌더링됩니다. 계층적 시각화에 필요한 사용자 지정 가능한 구성 요소는 솔루션을 인식하므로 다른 사용자 지정처럼 조직 간 전송이 가능합니다. 양식 편집기를 사용하여 빠른 양식을 사용자 지정하여 시각화에 표시된 속성을 구성할 수 있습니다.
  
## <a name="visualization-walk-through"></a>시각화 연습

사용자 지정 엔터티에 대한 시각화를 만드는 예제를 살펴보겠습니다. `new_Widget`이라는 사용자 지정 엔터티를 만들고 여기에 표시된 대로 (1:N) 자체 참조 관계 `new_new_widget_new_widget`을 만들고 계층적으로 표시했습니다.  
  
![위젯 관계 정의](media/widget-relationship-definition.png)  
  
그런 다음, **계층 구조 설정** 그리드 보기에서 `new_new_widget_new_widget` 계층적 관계를 선택했습니다. 양식에서 필수 필드를 입력했습니다. (1:N) 관계를 아직 계층적으로 표시하지 않은 경우 양식의 링크를 통해 관계 정의 양식으로 돌아가 관계를 계층적으로 표시할 수 있습니다.  

> [!IMPORTANT]
> 각 엔터티는 한 번에 하나의 계층적 관계만 가질 수 있습니다. 이를 다른 자체 참조 관계로 변경하면 결과가 있을 수 있습니다. 자세한 정보: [계층적 데이터 정의](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)
  
![계층 구조 설정](media/hierarchy-settings.png)  
  
**빠른 보기 양식**에 대해 **위젯 계층 타일 양식**이라는 빠른 양식을 만들었습니다. 이 양식에서는 각 타일에 표시할 4개의 필드를 추가했습니다.  
  
![위젯에 대한 빠른 양식 만들기](media/create-quickform.png)  
  
설정이 완료되면 *Standard Widget*과 *Premium Widget*이라는 두 개의 레코드가 생성됩니다. 조회 필드를 사용하여 Premium Widget을 Standard Widget의 부모로 만들면 아래와 같이 `new_Widget` 그리드 보기에 계층 구조 아이콘이 표시됩니다.  
  
![위젯의 계층 구조 그리드](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  계층 아이콘은 계층적 관계를 사용하여 레코드가 관련될 때까지 레코드 그리드 보기에 표시되지 않습니다.  
  
계층 구조 아이콘을 선택하면 `new_Widget` 계층 구조가 왼쪽에는 트리 보기, 오른쪽에는 타일 보기 형태로 두 개의 레코드가 표시됩니다. 각 타일에는 **위젯 계층 구조 타일 양식**에서 제공한 4개의 필드가 있습니다.  
  
![위젯의 트리 및 타일 보기](media/widget-tree-tiles.png)  

필요에 따라 전체 계층 구조를 보여 주는 트리 보기 또는 계층 구조의 더 작은 부분을 나타내는 타일 보기 중에서 선택할 수 있습니다. 두 보기는 나란히 표시됩니다. 계층 트리를 확장 및 축소하여 계층 구조를 탐색할 수 있습니다. 

### <a name="see-also"></a>참고 항목 

[계층적으로 관련된 데이터 정의 및 쿼리](../common-data-service/define-query-hierarchical-data.md)<br />
[비디오: 계층 구조 시각화](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)