---
title: 앱용 Common Data Service로 계층 구조 데이터 정의 및 쿼리 | MicrosoftDocs
description: 계층적으로 관련된 데이터를 정의하고 쿼리하는 방법 알아보기
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: 4dad7da635156350d104d68108ac4acfbb991862
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690724"
---
# <a name="define-and-query-hierarchically-related-data"></a>계층적으로 관련된 데이터 정의 및 쿼리

계층적으로 관련된 데이터를 정의하고 쿼리하여 유용한 비즈니스 인사이트를 얻을 수 있습니다. 계층적 모델링 및 시각화 기능은 다음과 같은 많은 이점을 제공합니다.  
  
- 복잡한 계층 정보를 보고 탐색합니다.  
- 계층 구조의 상황에 맞는 보기에서 KPI(핵심 성과 지표)를 봅니다.  
- 웹 및 태블릿에 걸쳐 중요한 정보를 시각적으로 분석합니다.  
  
일부 표준 엔터티에는 이미 정의된 계층 구조가 있습니다. 사용자 지정 엔터티를 포함한 다른 엔터티를 계층 구조에 사용할 수 있으며 해당 엔터티에 대한 시각화를 만들 수 있습니다. 

## <a name="define-hierarchical-data"></a>계층적 데이터 정의

앱용 Common Data Service를 사용하면 계층적 데이터 구조가 관련 레코드의 *자기 참조* 일대다(1:N) 관계로 지원됩니다. 

> [!NOTE]
> *자기 참조*란 엔터티가 엔터티 자체와 관련된 것을 의미합니다. 예를 들어 계정 엔터티에는 다른 계정 엔터티 레코드와 연결할 조회 필드가 있습니다.

자기 참조 일 대 다(1:N) 관계가 있는 경우 관계 정의에서 **계층 구조** 옵션을 **예**로 설정할 수 있습니다.

![관계 정의의 계층 구조 설정](media/self-referential-relationship-car-solution-explorer.png)

데이터를 계층 구조로 쿼리하려면 엔터티의 일대다(1:N) 자기 참조 관계 중 하나를 계층적으로 설정해야 합니다. 이 작업은 솔루션 탐색기를 통해서만 수행할 수 있습니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

계층 구조를 설정하려면  
  
1. [1:N 관계를 볼 때](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships) 편집하려는 자기 참조 관계를 선택합니다.
2. **관계 정의**에서 **계층적**을 **예**로 설정합니다.  
  
> [!NOTE]
> - 기본 제공(1:N) 관계 중 일부는 사용자 지정할 수 없습니다. 이렇게 하면 관계를 계층적으로 설정할 수 없습니다.  
> - 시스템 자기 참조 관계에 대해 계층적 관계를 지정할 수 있습니다. 여기에는 “contact_master_contact” 관계와 같은 시스템 유형의 1:N 자기 참조 관계가 포함됩니다.  

> [!IMPORTANT]
> 자기 참조 관계를 여러 개 사용할 수 있지만 엔터티당 관계를 하나만 계층 구조 관계로 정의할 수 있습니다. 적용된 설정을 변경하려면 경고가 표시됩니다.
>
> - **사용하지 않도록 설정할 경우:** 이 관계의 계층 구조 설정을 해제하면 이 계층 구조를 사용하는 모든 롤업 정의, 프로세스 및 보기가 작동하지 않습니다. 계속하시겠습니까? 
> - **사용하도록 설정할 경우:** 이 관계의 계층 구조 설정을 사용하도록 설정하면 기존 계층 구조를 사용하는 모든 롤업 정의가 유효하지 않게 됩니다. 계속하시겠습니까?
>
> 기존 계층 구조에 다른 종속성이 있는지 확실하지 않은 경우, 계속하기 전에 배포에 대한 문서를 검토하거나 다른 맞춤 제작자와 협의하여 기존 계층 구조 관계가 사용되는 방식을 파악해야 합니다.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>계층 구조 데이터 쿼리  

정의된 계층 구조 없이 계층 구조 데이터를 검색하려면 관련 레코드를 반복해서 쿼리해야 합니다. 정의된 계층 구조가 없으면 관련된 데이터를 계층 구조로 한 번에 쿼리할 수 있습니다. **다음에 속함** 및 **다음에 속하지 않음** 논리를 사용하여 레코드를 쿼리할 수 있습니다. 상세하게 찾기 및 워크플로 편집기에 **다음에 속함** 및 **다음에 속하지 않음** 계층적 연산자가 표시됩니다. 이러한 연산자를 사용하는 방법에 대한 자세한 내용은 [워크플로 단계 구성](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions)을 참조하세요. 상세하게 찾기에 대한 자세한 내용은 [상세하게 찾기 검색 만들기, 편집 또는 저장](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)을 참조하세요.  

> [!NOTE]
> 개발자는 코드에서 이러한 연산자를 사용할 수도 있습니다. 자세한 정보: [개발자 설명서: 계층 구조 데이터 쿼리](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
다음 예에서는 계층 구조를 쿼리하는 시나리오를 보여 줍니다.  
  
### <a name="query-account-hierarchy"></a>계정 계층 구조 쿼리  
  
![계정 계층 구조의 계정 쿼리](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>관련 활동을 포함하여 계정 계층 구조 쿼리  
  
![계정 관련 활동 쿼리](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>관련 기회를 포함하여 계정 계층 구조 쿼리  
  
![계정 관련 기회 쿼리](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>참고 항목 
[1:N(일 대 다) 또는 N:1(다 대 일) 엔터티 관계 만들기 및 편집](create-edit-1n-relationships.md)<br />
[솔루션 탐색기를 사용하여 1:N(일대다) 또는 N:1(다 대 일) 엔터티 관계 만들기 및 편집](create-edit-1n-relationships-solution-explorer.md)<br />
[모델 기반 앱으로 계층적 데이터 시각화](visualize-hierarchical-data.md)<br />
[비디오: 계층적 보안 모델링](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[비디오: 계층 구조 시각화](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
