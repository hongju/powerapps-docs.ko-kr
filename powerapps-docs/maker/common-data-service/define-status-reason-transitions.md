---
title: PowerApps를 사용하여 상태 이유 전환 정의 | MicrosoftDocs
description: 상태 이유 전환을 정의하는 방법 알아보기
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
ms.assetid: dbc4f436-0b23-42f9-8079-b0de482aaebe
caps.latest.revision: 11
ms.author: matp
manager: kvivek
ms.openlocfilehash: e21069a86d2ef21e8209fea6ea4a4b05e604cda4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39694732"
---
# <a name="define-status-reason-transitions-for-the-case-or-custom-entities"></a>사례 또는 사용자 지정 엔터티에 대한 상태 이유 전환 정의

인시던트(**사례**) 엔터티 또는 사용자 지정 엔터티에 대한 상태 이유 전환을 지정할 수 있습니다.

> [!NOTE]
> 인시던트(사례) 엔터티가 기본 앱용 Common Data Service 환경에 포함되지 않더라도 [Dynamics 365 for Customer Service](https://dynamics.microsoft.com/customer-service/)에서 사용되며 [공통 데이터 모델](https://github.com/Microsoft/CDM/blob/master/schemaDocuments/core/applicationCommon/foundationCommon/crmCommon/service/Incident.cdm.json) 내에서 정의됩니다.
  
상태 이유 전환은 각 상태 이유에 대해 변경될 수 있는 상태 이유 값을 정의하는 필터링의 선택적 추가 수준입니다. 유효한 옵션의 제한된 목록을 정의하면 유효한 상태 이유 값에 대한 조합 수가 많은 경우 사용자가 레코드에 대한 올바른 다음 상태 이유를 쉽게 선택할 수 있도록 할 수 있습니다.  
  
<a name="BKMK_StatusAndStatusReasons"></a>

## <a name="what-is-the-connection-between-status-and-status-reason-fields"></a>상태 및 상태 이유 필드 간의 연결이란?  

서로 다른 상태 값을 가질 수 있는 엔터티에는 이 데이터를 캡처하는 두 개의 필드가 있습니다.  
  
|표시 이름|설명|  
|------------------|-----------------|  
|**Status**|레코드의 상태를 나타냅니다. 일반적으로 **활성** 또는 **비활성**입니다. 새 상태 옵션을 추가할 수 없습니다.|  
|**상태 이유**|특정 상태에 연결되는 이유를 나타냅니다. 각 상태에는 가능한 상태 이유가 하나 이상 있어야 합니다. 추가 상태 이유 옵션을 추가할 수 있습니다.|  
  
필드에 대한 메타데이터는 지정된 상태에 유효한 상태 값을 정의합니다. 예를 들어 인시던트(**사례**) 엔터티의 경우 기본 상태 및 상태 이유 옵션은 다음과 같습니다.  
  
|상태|상태 이유|  
|------------|-------------------|  
|**활성**|<li>**진행 중**</li><li>**대기 중**</li><li>**세부 정보 대기 중**</li><li>**연구 중**</li>| 
|**확인됨**|<li>**문제 해결됨**</li><li>**제공된 정보**</li>|
|**취소됨**|<li>**취소됨**</li><li>**병합됨**</li>|
  
  
<a name="BKMK_EditStatusReasonTransitions"></a>   

## <a name="edit-status-reason-transitions"></a>상태 이유 전환 편집
 
사용자가 선택할 수 있는 다른 상태 이유 옵션을 정의하도록 사례 엔터티 및 사용자 지정 엔터티에 대한 상태 이유 필드 옵션을 수정할 수 있습니다. 유일한 제한은 활성 상태에 대한 각 상태 이유 옵션이 비활성 상태로 하나 이상의 경로를 허용해야 한다는 것입니다. 그렇지 않으면 사례를 해결하거나 취소할 수 없는 조건을 만들 수 있습니다.  

> [!NOTE]
> 상태 이유 전환을 편집하려면 솔루션 탐색기를 사용해야 합니다. 필드를 편집하는 방법에 대한 내용은 [PowerApps 솔루션 탐색기를 사용하여 앱용 Common Data Service의 필드 만들기 및 편집](create-edit-field-solution-explorer.md)을 참조하세요.
  
 상태 이유 필드를 편집하는 경우 **상태 이유 전환 편집** 단추가 메뉴에 있습니다. 

![상태 이유 전환 편집 명령](media/status-reason-transitions-command.png)

이 단추를 클릭하면 **상태 이유 전환** 대화 상자는 **상태 이유 전환을 활성화**하도록 선택하는 옵션을 제공합니다. 이 옵션이 선택된 경우 각 상태 이유에 대해 허용된 *다른* 상태 이유 값을 정의해야 합니다. 적용된 필터링을 제거하려면 **상태 이유 전환 활성화** 선택을 제거합니다. 정의한 전환은 유지되지만 적용되지 않습니다.  
  
아래 스크린샷에서는 다음 요구 사항을 충족하는 예제를 제공합니다. 
 
- 사례를 언제든지 병합할 수 있습니다. 상태 이유 전환이 허용하지 않는 경우 사례를 병합할 수 없습니다.  
- 활성 사례를 언제든지 취소할 수 있습니다.  
- 해결되거나 취소된 사례는 다시 활성화될 수 없습니다.  
- 모든 사례는 해결되려면 다음 단계: **진행 중** > **보류 중** > **세부 정보 대기 중** > **연구 중**을 통과해야 합니다. 이 구성을 사용하여 사례는 이전 상태로 설정될 수 없습니다.  
  > [!NOTE]
  >  이는 실제 작업에 좋은 예제가 아니지만 상태의 단계를 상태 이유 전환을 통해 적용할 수 있는 방법을 보여줍니다.  
  
 ![사례에 대한 상태 이유 전환의 예제](media/status-reason-transitions-example.PNG)  
  
### <a name="see-also"></a>참고 항목  

[PowerApps 솔루션 탐색기를 사용하여 앱용 Common Data Service의 필드 만들기 및 편집](create-edit-field-solution-explorer.md)<br />
[엔터티 메타데이터 > 엔터티 상태](/powerapps/developer/common-data-service/entity-metadata#entity-states)<br />
[사용자 지정 상태 모델 전환 정의](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions)

