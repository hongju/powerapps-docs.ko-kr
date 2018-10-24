---
title: 엔터티 형식 | MicrosoftDocs
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
- powerapps
author: Mattp123
ms.assetid: 2f3f6053-0b9e-41e7-bd94-2239351e9f4b
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 60e16ff8cb5c40a37cf0a5243b420f77c4a695bb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697807"
---
# <a name="types-of-entities"></a>엔터티 형식

앱용 Common Data Service에서 엔터티를 만들거나 편집하기 전에 다양한 형식의 엔터티가 있음을 이해해야 합니다. 사용자 지정 엔터티가 생성되면 이러한 형식을 변경할 수 없습니다. 두 가지 주요 구분은 엔터티 소유권과 엔터티 활동 엔터티인지 여부를 기반으로 합니다.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>엔터티 소유권  

엔터티 소유권에는 네 가지 유형이 있습니다. 사용자 지정 엔터티를 만들 때 유일한 옵션은 **사용자 또는 팀 소유** 또는 **조직 소유**이지만 다른 엔터티에는 다양한 소유권 유형이 있음을 인식해야 합니다.  
  
|소유권|설명|  
|---------------|-----------------|  
|**회사 소유**|이러한 엔터티의 데이터는 비즈니스 단위에 속합니다. 데이터에 대한 액세스는 비즈니스 단위 수준에서 제어할 수 있습니다.|  
|**없음**|다른 엔터티에서 소유하지 않은 데이터입니다.|  
|**조직 소유**|조직에 속한 데이터입니다. 데이터에 대한 액세스는 조직 수준에서 제어됩니다.|  
|**사용자 또는 팀 소유**|사용자 또는 팀에 속한 데이터입니다. 이러한 레코드에서 수행할 수 있는 작업은 사용자 수준에서 제어할 수 있습니다.|  
  
  
> [!IMPORTANT]
>  엔터티를 만든 후에는 소유권을 변경할 수 없습니다. 엔터티를 만들기 전에 올바른 유형의 소유권을 선택해야 합니다. 나중에 사용자 지정 엔터티가 다른 형식이어야 하는 것으로 결정되면 해당 엔터티를 삭제하고 새 엔터티를 만들어야 합니다.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>활동 엔터티

활동은 일정에 항목을 만들 수 있는 모든 작업으로 간주할 수 있습니다. 활동에는 작업이 발생했거나 발생할 시기를 결정하는 데 도움이 되는 시간 차원(시작 시간, 중지 시간, 기한 및 기간)이 있습니다. 활동에는 또한 주제 및 설명과 같이 활동이 나타내는 작업을 결정하는 데 도움이 되는 데이터가 포함되어 있습니다. 활동을 열거나 취소하거나 완료할 수 있습니다. 완료된 활동 상태에는 활동이 완료된 방법을 명확하게 하기 위해 활동과 관련된 여러 하위 상태 값이 있습니다.  
  
활동 엔터티는 사용자 또는 팀만 소유할 수 있으며 조직에서 소유할 수 없습니다.  
  
다음 표에서는 앱용 CDS 환경에서 사용할 수 있는 활동 엔터티가 나열되어 있습니다.
  
|이름|설명|활동 메뉴 표시|참조|
|----------|-----------------|----------------|---------------|  
|**Appointment**|시작/종료 시간 및 시간으로 시간 간격을 나타내는 약속입니다.|예|[Appointment](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**Email**|이메일 프로토콜을 사용하여 전달되는 활동입니다.|예|[이메일](/powerapps/developer/common-data-service/reference/entities/email)|
|**Fax**|팩스에 대한 통화 결과 및 페이지 수를 추적하고 필요에 따라 문서의 전자 복사본을 저장하는 활동입니다.|예|[Fax](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Letter**|편지 전달을 추적하는 활동입니다. 이 활동은 편지의 전자 복사본을 포함할 수 있습니다.|예|[Letter](/powerapps/developer/common-data-service/reference/entities/letter)|
|**전화 통화**|전화 통화를 추적하는 활동입니다.|예|[PhoneCall](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**되풀이 약속**|되풀이 약속 시리즈의 마스터 약속입니다.|예|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Task**|수행해야 할 작업을 나타내는 일반적인 활동입니다.|예|[Task](/powerapps/developer/common-data-service/reference/entities/task)|
  
새 사용자 지정 활동 엔터티를 만들 수 있습니다. 예를 들어 사용자 지정 활동 엔터티를 만들어 인스턴트 메시지 통신을 기록할 수 있습니다. 활동 엔터티를 만드는 것은 기본 필드를 지정하지 않으므로 비활동 엔터티를 만드는 것과 다릅니다. 모든 활동 엔터티에는 **기본 필드**가 **주체**로 설정되고 활동 엔터티에 의해 정의된 기타 일반 필드가 있습니다. 이렇게 하면 공용 필드만 표시되는 보기에 모든 유형의 활동을 표시할 수 있습니다.  

> [!NOTE]
> PowerApps 포털을 사용하여 사용자 지정 활동을 만들 수 없습니다. **고급** 단추를 사용하여 솔루션 탐색기를 열어야 합니다.
  
사용자 지정 활동 엔터티를 만들려면 **활동 엔터티로 정의**를 선택합니다. 이 옵션을 선택하면 **활동 메뉴의 표시**가 선택되어 있습니다. 이 설정을 통해 활동 메뉴에서 이 유형의 활동을 만들 수 있습니다. 일반적으로 특정 이벤트와 연관되고 코드를 사용하거나 워크플로에 의해 생성된 활동에는 선택되지 않습니다. 엔터티를 저장한 후에는 이러한 설정을 변경할 수 없습니다.  

### <a name="see-also"></a>참고 항목
[엔터티 만들기 또는 편집](create-edit-entities.md)
