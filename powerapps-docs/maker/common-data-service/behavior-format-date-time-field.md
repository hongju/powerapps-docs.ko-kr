---
title: 앱용 Common Data Service의 날짜 및 시간 필드 동작 및 형식 | MicrosoftDocs
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: 73d691c7-344e-4c96-8979-c661c290bf81
caps.latest.revision: 47
ms.author: matp
manager: kvivek
ms.openlocfilehash: 2f62f2433fe959e3713df544628db186b801731e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696500"
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>날짜 및 시간 필드의 동작 및 형식

앱용 Common Data Service에서 날짜 및 시간 데이터 형식은 많은 표준 엔터티 필드에서 사용됩니다. 필드가 나타내는 날짜의 종류에 따라 **사용자 로컬**, **날짜 전용** 또는 **표준 시간대 독립**의 다른 필드 동작을 선택할 수 있습니다.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>날짜 및 시간 필드 동작 및 형식  

다음 표에는 날짜 및 시간 필드 동작 및 형식에 대한 정보가 포함되어 있습니다.  
  
|동작|서식|설명|  
|--------------|------------|-------------------------------|  
|**사용자 로컬** |**날짜 전용**<br />- 또는 -<br />**날짜 및 시간**|이는 사용자 지정 날짜 및 시간 필드의 기본 동작입니다.<br /><br />필드 값은 현재 사용자의 로컬 시간으로 표시됩니다.<br />웹 서비스에서 이러한 값은 공통 UTC 표준 시간대 형식을 사용하여 반환됩니다.<br /><br />기본 동작을 선택하면 한 번은 변경할 수 있습니다. 자세한 정보 [사용자 로컬 동작 변경](#change-user-local-behavior)|  
|**날짜 전용**|**날짜 전용**|표준 시간대 변환이 없습니다.<br /><br />값의 시간 부분은 항상 오전 12:00입니다.<br />값의 날짜 부분은 UI 및 웹 서비스에 지정된 대로 저장되고 검색됩니다.|  
|**표준 시간대 독립**|**날짜 전용**<br />- 또는 -<br />**날짜 및 시간**|표준 시간대 변환이 없습니다.<br /><br />날짜와 시간 값은 UI 및 웹 서비스에 지정된 대로 저장되고 검색됩니다.|  

## <a name="change-user-local-behavior"></a>사용자 로컬 동작 변경:

관리 솔루션의 게시자가 이를 막지 않는 한 기존 사용자 지정 날짜 필드의 동작을 **사용자 로컬**에서 **날짜 전용** 또는 **표준 시간대 독립**으로 변경할 수 있습니다. 이는 일회성 변경입니다.

필드 동작을 변경하면 필드 동작이 변경된 후 추가되거나 수정된 필드 값에 영향을 줍니다. 기존 필드 값은 UTC 표준 시간대 형식으로 데이터베이스에 남아 있습니다. 기존 필드 값의 동작을 UTC에서 날짜 전용으로 변경하려면 프로그래밍 방식으로 작업을 수행하는 개발자의 도움이 필요할 수 있습니다. 자세한 정보: [데이터베이스에서 기존 날짜 및 시간 값의 동작을 변환](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database)합니다. 

> [!WARNING]
> 기존 날짜 및 시간 필드의 동작을 변경하기 전에 비즈니스 규칙, 워크플로, 계산된 필드 또는 롤업 필드와 같은 필드의 모든 종속성을 검토하여 동작을 변경함으로써 발생하는 문제가 없는지 확인해야 합니다. 날짜 및 시간 필드의 동작을 변경한 후에 변경한 필드에 따라 각 비즈니스 규칙, 워크플로, 계산된 필드 및 롤업 필드를 열어 정보를 검토하고 저장하여 최신 날짜와 시간 필드의 동작 및 값이 사용되지는 확인합니다. 

### <a name="change-behavior-during-a-solution-import"></a>솔루션 가져오기 중 동작 변경

**로컬 사용자** 동작을 사용하여 날짜 필드가 포함된 솔루션을 가져오면, 동작을 **날짜 전용** 또는 **표준 시간대 독립**으로 변경하는 옵션이 있을 수 있습니다.  

### <a name="prevent-changing-behavior"></a>동작 변경 방지

관리 솔루션에 사용자 지정 날짜 필드를 배포하는 경우 **CanChangeDateTimeBehavior** 관리 속성을 **False**로 설정하여 솔루션을 사용하는 사용자가 동작을 변경하지 못하게 할 수 있습니다. 자세한 정보: [필드 관리 속성](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>사례 사용

**날짜 전용** 및 **표준 시간대 독립** 동작에 대해 다음 사용 사례를 고려합니다.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>날짜 전용 시나리오: 생일 및 기념일

날짜 전용 동작은 생일이나 기념일과 같은 시간 및 표준 시간대에 대한 정보가 필요하지 않은 경우에 적합합니다. 이 선택 항목을 사용하면 전 세계 모든 앱 사용자는 정확하게 동일한 날짜 값을 볼 수 있습니다.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>표준 시간대 독립 시나리오: 호텔 체크 인

호텔 체크 인 시간과 같이 표준 시간대 정보가 필요하지 않은 경우 이 동작을 사용할 수 있습니다. 이 선택 항목을 사용하면 전 세계 모든 앱 사용자는 동일한 날짜와 시간 값을 볼 수 있습니다.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>날짜 및 시간 쿼리 연산자는 날짜 전용 동작에 대해 지원되지 않습니다.  

다음 날짜 및 시간 관련 쿼리 연산자는 **날짜 전용** 동작에 대해 유효하지 않습니다. 이러한 연산자 중 하나가 쿼리에서 사용되면 잘못된 연산자 예외 오류가 발생됩니다.  
  
- X분 초과 경과  
- X시간 초과 경과  
- 마지막 X시간  
- 다음 X시간  

  
### <a name="see-also"></a>참고 항목

[필드 만들기 및 편집](create-edit-fields.md)<br />
[수동 계산을 자동화하는 계산된 필드 정의](define-calculated-fields.md)<br />
[필드 관리 속성](set-managed-properties-metadata.md#field-managed-properties)<br />
[관리 속성](solutions-overview.md#managed-properties)

