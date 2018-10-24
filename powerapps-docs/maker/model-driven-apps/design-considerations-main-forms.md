---
title: PowerApps를 사용한 모델 기반 앱 기본 양식에 대한 디자인 고려 사항 | MicrosoftDocs
description: 기본 양식 디자인 방법 알아보기
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: a83872f4-9e36-413b-8561-41a1e5ffe5dd
caps.latest.revision: 17
ms.author: matp
manager: kvivek
ms.openlocfilehash: 68915af214b86511f7fba4bbb05ee59f598340b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697863"
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>모델 기반 앱 기본 양식에 대한 디자인 고려 사항

기본 양식은 사용자가 데이터를 보고 상호 작용하는 기본 사용자 인터페이스입니다. 기본 양식은 가장 광범위한 옵션을 제공하며 모델 기반 앱에 사용할 수 있습니다. 단, 휴대폰용 Dynamics 365는 예외입니다.  
  
 기본 양식의 주요 디자인 목표 중 하나는 한 번 디자인하여 모든 곳에 배포하는 것입니다. 모델 기반 앱 또는 Dynamics 365 고객 참여 웹 응용 프로그램용으로 디자인한 것과 동일한 기본 양식은 Outlook용 Dynamics 365 및 태블릿용 Dynamics 365에도 사용됩니다. 이 방식의 이점은 변경 내용을 여러 형식으로 통합할 필요가 없다는 것입니다. 그러나 이러한 양식을 설계할 때 고려해야 할 몇 가지 중요한 요소가 있습니다.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>다른 그룹에 대한 사용자 지정 양식  
 여러 기본 양식을 만들고 각 양식에 다른 보안 역할을 할당할 수 있으므로, 응용 프로그램 사용 방법에 최적화된 양식을 조직의 여러 그룹에 제공할 수 있습니다. 선택할 수 있는 다양한 양식을 가질 수 있도록 각 그룹에 다양한 옵션을 제공할 수도 있습니다. 자세한 정보: [양식에 대한 액세스 제어](control-access-forms.md)  
  
 관리자와 의사 결정권자는 주요 데이터 포인트에 대한 빠른 참조를 제공하기 위해 최적화된 양식을 원할 것입니다. 그들은 목록보다 많은 차트를 보고 싶어하며 많은 데이터 입력을 수행하지 않을 수 있습니다.  
  
 고객과 직접 상호 작용하는 사람들은 가장 자주 수행하는 작업에 맞는 양식이 필요할 수 있습니다. 가장 효율적인 데이터 입력을 허용하는 양식을 원할 수 있습니다.  
  
 조직의 사람들이 무엇을 원하고 필요로 하는지 찾아야 합니다. 이는 자주 입력을 수집하고, 다른 것을 시도하고, 사람들이 사용할 수 있는 양식을 만드는 반복적인 과정입니다. 다양한 도구를 사용할 수 있으며 양식 내에서 모든 작업을 수행할 필요는 없습니다. 비즈니스 규칙, 워크플로 프로세스, 대화 상자 및 비즈니스 프로세스 흐름을 양식과 함께 사용하여 조직에 적합한 솔루션을 제공합니다.  
  
 양식 관리에 소비할 시간과 균형을 이루어야 합니다. 양식 만들기 및 편집은 비교적 쉽지만 양식을 많이 만들수록 더 많은 양식을 관리해야 합니다.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>프레젠테이션 차이점  
 각 프레젠테이션에 대해 여러 양식을 관리할 필요는 없지만, 프레젠테이션의 차이점을 기본 양식에서 설명할 수 있는 방법을 고려해야 합니다. [기본 양식 프레젠테이션](main-form-presentations.md)에서는 기본 양식을 표시할 수 있는 다양한 방법을 설명합니다. 고려해야 할 주요 사항은 다음과 같습니다.  
  
- 태블릿용 Dynamics 365는 양식에 추가할 이미지, HTML 또는 Silverlight 웹 리소스를 지원하지 않습니다.  
  
-   태블릿용 Dynamics 365 양식의 레이아웃은 기본 양식에 따라 자동으로 생성됩니다. 태블릿용 Dynamics 365 양식에 대한 특별한 양식 편집기가 없습니다. 두 클라이언트 모두에서 양식 프리젠테이션이 제대로 작동하는지 확인해야 합니다.  
  
-   웹 응용 프로그램에서 DOM 요소와 상호 작용하는 지원되지 않는 스크립트가 있는 경우, 동일한 DOM 요소를 사용할 수 없기 때문에 이러한 스크립트는 태블릿용 Dynamics 365 양식에서 작동하지 않습니다.  
  
- Outlook용 Dynamics 365 읽기 창 양식은 스크립팅을 허용하지 않습니다. 양식 요소의 표시 유형은 기본 설정에 따라 달라지며 스크립트를 사용하여 런타임에 변경할 수 없습니다.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>양식 성능  
 느리게 로드되거나 신속하게 응답하지 않는 양식은 생산성 및 사용자 채택에 영향을 줍니다. [양식 성능 최적화](optimize-form-performance.md)는 양식을 설계할 때 고려해야 할 많은 권장 사항을 제공하여 사용자 지정이 양식 성능에 부정적인 영향을 미치지 않도록 합니다.  
  
### <a name="next-steps"></a>다음 단계 
 [양식 만들기 및 설계](create-design-forms.md)    
 [빠른 생성 양식 만들기 및 편집](create-edit-quick-create-forms.md)   

 
