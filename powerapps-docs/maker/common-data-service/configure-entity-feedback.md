---
title: PowerApps를 사용하여 피드백에 대한 엔터티 구성 | Microsoft Docs
description: 엔터티에 대한 피드백을 사용하도록 설정하는 방법 알아보기
ms.custom: ''
ms.date: 05/18/2018
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
ms.assetid: 5b25cf09-d43b-4165-9eaa-7549f4855e7c
caps.latest.revision: 13
ms.author: matp
manager: kvivek
ms.openlocfilehash: efb1cf167353d5928564b42aeb7a49f43cf272d6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692884"
---
# <a name="configure-an-entity-for-feedbackratings"></a>피드백/등급에 대한 엔터티 구성

고객이나 직원이 엔터티 레코드에 대한 피드백을 작성하거나, 피드백에 대한 엔터티를 사용하여 정의된 등급 범위 내에서 엔터티 레코드의 등급을 지정할 수 있습니다.  

이 기능은 일반적으로 포털 또는 설문 조사를 통해 고객에게서 데이터를 캡처하는 시스템에서 사용됩니다. 서비스나 제품 만족도에 대한 데이터는 해당 종류의 데이터를 나타내는 엔터티를 통해 적용될 수 있습니다.

피드백은 공동 작업에 대한 피드백을 제공하기 위해 직원이 사용할 수도 있습니다.

> [!NOTE]
> 이러한 단계를 수행하려면 시스템 관리자나 시스템 사용자 지정 보안 역할 또는 동일한 권한이 있어야 합니다.
  
## <a name="enable-feedback"></a>피드백 사용하도록 설정  
  
**피드백**을 사용하도록 설정하려면 엔터티를 편집합니다. 자세한 내용: [엔터티 편집](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>엔터티 양식에 대한 피드백에 하위 그리드 추가  

기본적으로 사용자는 피드백을 추가하려는 레코드의 연결된 레코드 목록으로 이동해야 합니다. 사용자가 피드백을 쉽게 추가하게 하려면 피드백을 사용하도록 설정하는 엔터티의 양식에 피드백 하위 그리드를 추가하려 할 수 있습니다.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. -->자세한 정보: [하위 그리드 속성 개요](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>등급을 표시하려면 엔터티 양식에 롤업 필드 추가  

엔터티에 대한 등급을 계산하려는 방법에 따라 등급을 계산하는 롤업 필드를 만든 다음, 피드백에 대해 사용하도록 설정하는 엔터티 형식에 해당 필드를 추가합니다. 자세한 정보: [값을 집계하는 롤업 필드 정의](define-rollup-fields.md)
  
### <a name="see-also"></a>참고 항목  
 [Dynamics 365 레코드에 대한 피드백 또는 등급 제출](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
