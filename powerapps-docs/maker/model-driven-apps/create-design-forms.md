---
title: 모델 기반 앱 양식 만들기 및 설계 | MicrosoftDocs
ms.custom: ''
ms.date: 06/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 99c795e0-9165-4112-85b1-6b5e1a4aa5ec
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags:
- Links to topic not migrated
ms.openlocfilehash: ed51d04919c6316c827b0286eefaaccdf539c6ef
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697652"
---
# <a name="create-and-design-model-driven-app-forms"></a>모델 기반 앱 양식 만들기 및 설계 

PowerApps를 사용하면, 양식은 사용자가 작업을 수행하는 데 필요한 데이터와 상호 작용하는 데 사용하는 사용자 인터페이스를 제공합니다. 사용자가 사용하는 양식은 필요한 정보를 효율적으로 찾거나 입력할 수 있도록 설계되어야 합니다. 

기본 솔루션 또는 관리되지 않는 솔루션에서 양식 사용자 지정을 허용하는 모든 엔터티에 대해 새 양식을 만들거나 기존 양식을 편집할 수 있습니다. 관리되지 않는 솔루션에서 솔루션용으로 만든 관리되지 않는 사용자 지정 엔터티의 관리 속성을 편집할 수 있습니다.
관리 솔루션을 보는 경우에는 새 양식을 만들거나 엔터티에 대한 기존 양식을 편집할 수 없습니다. 그러나 관리되는 솔루션의 엔터티에 대한 관리 속성이 사용자 지정을 허용하도록 설정된 경우에는 해당 엔터티에 양식을 추가하거나 편집할 수 있습니다. 
  

<a name="BKMK_TypesOfForms"></a> 
## <a name="type-of-forms"></a>양식 유형
양식에는 여러 유형이 있으며 각 유형에는 특정 기능 또는 용도가 있습니다. 자세한 정보: [PowerApps의 양식 유형](types-forms.md)입니다.  

  
<a name="BKMK_FormDifferencesByEntity"></a>   
## <a name="updated-versus-classic-entities"></a>업데이트된 엔터티 대 클래식 엔터티  
PowerApps는 양식 디자인을 위한 많은 옵션을 제공합니다. 통합 인터페이스를 사용하면 대부분의 엔터티가 반응형 인터페이스에 더 잘 맞게 업데이트되었습니다. 업데이트된 엔터티와 고유의 사용자 지정 엔터티는 태블릿 클라이언트, 비즈니스 프로세스 흐름 및 비즈니스 규칙을 위한 Dynamics 365 대한 지원을 포함합니다. 이러한 엔터티를 사용하면 한 번 디자인하여 모든 클라이언트에 배포할 수 있습니다.  
  
여전히 이전 버전의 모양과 기능을 유지하는 엔터티(클래식 엔터티라고 함)가 많이 있습니다. 이러한 엔터티는 자주 사용되지 않습니다. 여기 나열되어 있습니다.  
  
||||||  
|-|-|-|-|-|  
|주소|문서|문서 주석|대량 삭제 작업|연결|  
|할인|할인 목록|문서 위치|이메일 첨부 파일|팔로우|  
|목표|목표 메트릭|원본 파일 가져오기|송장 제품|주문 제품|  
|가격표|큐 항목|견적 제품|롤업 필드|롤업 쿼리|  
|저장된 보기|서비스|서비스 작업|SharePoint 사이트|사이트|  
|Territory|단위|단위 그룹|||  
  
### <a name="related-topics"></a>관련 항목  
    
[양식 순서 할당](assign-form-order.md) <br />
[양식에 대한 액세스 제어](control-access-forms.md) <br />
[다른 클라이언트에서 기본 양식 표시 방법](main-form-presentations.md) <br />
