---
title: PowerApps로 계층적 데이터 쿼리 및 시각화 | MicrosoftDocs
description: 계층적 관련 데이터를 쿼리 및 시각화하는 방법 알아보기
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: ec45f43266c1920d05301c92bdd67838b40b7734
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691175"
---
# <a name="query-and-visualize-hierarchically-related-data"></a>계층적으로 관련된 데이터 쿼리 및 시각화

계층적으로 관련된 데이터를 시각화하여 유용한 비즈니스 통찰력을 얻을 수 있습니다. 계층적 모델링 및 시각화 기능은 다음과 같은 많은 이점을 제공합니다.  
  
-   복잡한 계층 정보를 보고 탐색합니다.  
  
-   계층 구조의 상황에 맞는 보기에서 KPI(핵심 성과 지표)를 봅니다.  
  
-   웹 및 태블릿에 걸쳐 중요한 정보를 시각적으로 분석합니다.  
  
계정 및 사용자와 같은 일부 엔터티의 경우 시각화가 기본 제공됩니다. 사용자 지정 엔터티를 포함한 다른 엔터티를 계층 구조에 사용할 수 있으며 해당 엔터티에 대한 시각화를 만들 수 있습니다. 필요에 따라 전체 계층 구조를 보여 주는 트리 보기 또는 계층 구조의 더 작은 부분을 나타내는 타일 보기 중에서 선택할 수 있습니다. 두 보기는 나란히 표시됩니다. 계층 트리를 확장 및 축소하여 계층 구조를 탐색할 수 있습니다. 시각화를 위해 동일한 계층 설정이 한 번 설정되지만 웹 클라이언트와 모바일 클라이언트 모두에 적용됩니다. 태블릿에서는 시각적 개체가 작은 폼 팩터에 적합한 수정된 형식으로 렌더링됩니다. 계층적 시각화에 필요한 사용자 지정 가능한 구성 요소는 솔루션을 인식하므로 다른 사용자 지정처럼 조직 간에 전송할 수 있습니다. 양식 편집기를 사용하여 빠른 양식을 사용자 지정하여 시각화에 표시된 속성을 구성할 수 있습니다. 코드를 작성할 필요가 없습니다.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>계층적 데이터 쿼리  
 앱용 Common Data Service를 사용하면 계층적 데이터 구조가 관련 레코드의 자기 참조 일대다(1:N) 관계로 지원됩니다. 과거에는 계층적 데이터를 보려면 관련 레코드를 반복적으로 쿼리해야 했습니다. 지금은 관련된 데이터를 계층 구조로 한 번에 쿼리할 수 있습니다. **다음에 속함** 및 **다음에 속하지 않음** 논리를 사용하여 레코드를 쿼리할 수 있습니다. 상세하게 찾기 및 워크플로 편집기에 **다음에 속함** 및 **다음에 속하지 않음** 계층적 연산자가 표시됩니다. 이러한 연산자를 사용하는 방법에 대한 자세한 내용은 [워크플로 단계 구성](/flow/configure-workflow-steps)을 참조하세요. 상세하게 찾기에 대한 자세한 내용은 [상세하게 찾기 검색 만들기, 편집 또는 저장](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)을 참조하세요.  
  
 다음 예에서는 계층 구조를 쿼리하는 다양한 시나리오를 보여 줍니다.  
  
 계정 계층 구조 쿼리  
  
 ![계정 계층 구조에서 계정 쿼리](media/query-accounts.png "계정 계층 구조에서 계정 쿼리")  
  
 관련 활동을 포함하여 계정 계층 구조 쿼리  
  
 ![계정의 관련 활동 쿼리](media/query-account-related-activities.png "계정의 관련 활동 쿼리")  
  
 관련 기회를 포함하여 계정 계층 구조 쿼리  
  
 ![계정의 관련 기회 쿼리](media/query-account-related-opportunities.png "계정의 관련 기회 쿼리")  
  
 데이터를 계층 구조로 쿼리하려면 엔터티의 일대다(1:N) 자기 참조 관계 중 하나를 계층적으로 설정해야 합니다. 계층 구조를 설정하려면  
  
1.  [솔루션 탐색기](../model-driven-apps/advanced-navigation.md#solution-explorer)를 엽니다. 
  
2.  원하는 엔터티를 선택하고 **1:N 관계**를 선택한 다음, (1:N) 관계를 선택합니다. 

3.  **관계 정의**에서 **계층적**을 **예**로 설정합니다.  
  
> [!NOTE]
> - 기본 제공(1:N) 관계 중 일부는 사용자 지정할 수 없습니다. 이렇게 하면 관계를 계층적으로 설정할 수 없습니다.  
> - 시스템 자기 참조 관계에 대해 계층적 관계를 지정할 수 있습니다. 여기에는 “contact_master_contact” 관계와 같은 시스템 유형의 1:N 자기 참조 관계가 포함됩니다.  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>계층적 데이터 시각화  
 기본 제공되어 사용 가능한 시각화가 있는 시스템 엔터티에는 `Account`, `Position`, `Product` 및 `User`가 있습니다. 이러한 엔터티의 눈금 보기에서는 레코드 이름 왼쪽에 계층 구조 차트를 나타내는 아이콘이 표시됩니다. 기본적으로 계층 구조 아이콘은 일부 레코드에 대해서만 표시됩니다. 이 아이콘은 부모 레코드, 자식 레코드 또는 둘 다가 있는 레코드에 대해 표시됩니다.  
  
 ![활성 계정](media/cust-hs-active-account.png "활성 계정")  
  
 계층 구조 아이콘을 선택하면 아래와 같이 왼쪽에는 트리 보기, 오른쪽에는 타일 보기가 있는 계층 구조를 볼 수 있습니다.  
  
 ![계정 트리 및 타일 보기](media/hierachy-security-accounts-tile-view.png "계정 트리 및 타일 보기")  
  
 계층 구조에는 몇 가지 다른 기본 제공 시스템 엔터티를 사용할 수 있습니다. 이러한 엔터티에는 `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign` 및 `Team`이 포함됩니다. 계층 구조에는 모든 사용자 지정 엔터티를 사용할 수 있습니다.  
  
> [!TIP]
>  계층 구조에 엔터티를 사용할 수 있는 경우:  
>  솔루션 탐색기에서 원하는 엔터티를 확장합니다. **계층 구조 설정**이라는 엔터티 구성 요소가 표시됩니다. 계층 구조에 사용할 수 없는 엔터티에 이 구성 요소가 없습니다(단, Dynamics 365 고객 관계 Sales Territory 엔터티를 제외). Sales Territory 엔터티에 **계층 구조 설정**이 나타나지만 계층 구조에 이 엔터티를 사용할 수는 없습니다.  
  
 시각화를 만들 때 기억해야 할 중요한 사항:  
  
-   엔터티당 하나의 (1: N) 자기 참조 관계만 계층적으로 설정할 수 있습니다. 이 관계에서 주 엔터티와 관련 엔터티는 account_parent_account 또는 new_new_widget_new_widget처럼 동일한 유형이어야 합니다.  
  
-   현재 계층 구조 또는 시각화는 하나의 엔터티만 기반으로 합니다. 계정을 여러 수준으로 표시하는 계정 계층 구조를 나타낼 수 있지만 계정 및 연락처를 동일한 계층 구조 시각화로 표시할 수는 없습니다.  
  
-   타일에 표시할 수 있는 최대 필드 수는 4입니다. 타일 보기에 사용되는 빠른 양식에 필드를 더 추가하면 처음 네 개의 필드만 표시됩니다.  
  
### <a name="visualization-example"></a>시각화 예제  
 사용자 지정 엔터티에 대한 시각화를 만드는 예제를 살펴보겠습니다. new_Widget이라는 사용자 지정 엔터티를 작성하고 여기에 표시된 대로 (1:N) 자기 참조 관계 **new_new_widget_new_widget**을 만들고 계층적으로 표시했습니다.  
  
 ![위젯 관계 정의](media/widget-relationship-definition.png "위젯 관계 정의")  
  
 다음으로 **계층 구조 설정** 표 보기에서 **new_new_widget_new_widget** 계층적 관계를 선택했습니다. 양식에서 필수 필드를 입력했습니다. (1:N) 관계를 계층적으로 아직 표시하지 않은 경우 양식의 링크를 통해 관계 정의 양식으로 돌아가 관계를 계층적으로 표시할 수 있습니다.  
  
 **빠른 보기 양식**에 대해 **위젯 계층 타일 양식**이라는 빠른 양식을 만들었습니다. 이 양식에서는 각 타일에 표시할 4개의 필드를 추가했습니다.  
  
 ![위젯에 대한 빠른 양식 만들기](media/create-quickf-orm.png "위젯에 대한 빠른 양식 만들기")  
  
 설정이 완료되면 Standard Widget과 Premium Widget이라는 두 개의 레코드가 생성됩니다. 조회 필드를 사용하여 Premium Widget을 Standard Widget의 부모로 만들면 아래와 같이 new_Widget 눈금 보기에 계층 구조 아이콘이 표시됩니다.  
  
 ![위젯의 계층 구조 눈금](media/widget-hierarchy-grid.png "위젯의 계층 눈금")  
  
> [!TIP]
>  레코드가 부모 - 자식 관계로 페어링될 때까지 계층 아이콘은 레코드 표 보기에 나타나지 않습니다.  
  
 계층 구조 아이콘을 선택하면 new_Widget 계층 구조가 왼쪽에는 트리 보기, 오른쪽에는 타일 보기 형태로 두 개의 레코드가 표시됩니다. 각 타일에는 **위젯 계층 타일 양식**에서 제공한 4개의 필드가 있습니다.  
  
 ![위젯의 트리 및 타일 보기](media/widget-tree-tiles.png "위젯의 트리 및 타일 보기")  
  
## <a name="see-also"></a>참고 항목  
 [비디오: 계층적 보안 모델링](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [비디오: 계층 구조 시각화](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
