---
title: PowerApps의 모델 기반 앱 공통 필드 속성 | MicrosoftDocs
description: Dynamics 365 for Customer Engagement의 기본 양식에 대한 공통 필드 속성 이해
Keywords: Main form; Common field properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
ms.openlocfilehash: 74e67dd4299d06a54d5ec85765e4e5d03710b432
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691204"
---
# <a name="model-driven-app-common-field-properties"></a>모델 기반 앱 공통 필드 속성

 양식의 필드는 사용자가 엔터티 레코드에서 데이터를 보거나 편집하기 위해 사용하는 컨트롤을 표시합니다. 한 섹션에 최대 4개의 열이 들어가도록 필드의 서식을 지정할 수 있습니다.  

솔루션 탐색기에서 **공통 필드 속성**에 액세스할 수 있습니다. **구성 요소**에서 **엔터티** 및 원하는 엔터티를 차례로 확장한 다음, **양식**을 선택합니다. 양식 목록에서 **기본** 형식의 양식을 엽니다. 그런 다음, 공통 필드 속성을 보려는 필드 중 하나를 두 번 클릭합니다.

![common-field-properties](media/common-field-properties.png)
  
다음 표에서는 모든 필드가 포함하고 있는 속성을 설명합니다. 특정 유형의 필드에는 특수한 속성이 있습니다. 이에 대한 설명은 [특수 필드 속성](special-field-properties-legacy.md)에 나와 있습니다.  
  
|탭|속성|설명|  
|---------|--------------|-----------------|  
|**표시**|**레이블**|**필수**: 기본적으로 레이블은 필드의 표시 이름과 일치합니다. 여기에 다른 레이블을 입력하여 양식의 해당 이름을 재정의할 수 있습니다.|  
||**양식에 레이블 표시**|레이블을 아예 표시하지 않도록 선택할 수 있습니다.|  
||**필드 동작**|확인란을 사용하여 필드 수준 동작을 지정합니다.|  
||**잠금**|이렇게 하면 실수로 양식에서 필드가 제거되지 않습니다. 이렇게 하면 이벤트 처리기와 같이 필드에 적용한 구성이 필드가 제거되었을 때 지워지지 않습니다. 이 필드를 제거하려면 사용자 지정자가 이 설정을 먼저 지워야 합니다.|  
||**표시 유형**|필드 표시는 선택 사항이며 스크립트를 사용하여 제어할 수 있습니다. 자세한 정보: [표시 유형 옵션](visibility-options-legacy.md)|  
||**가용성**|휴대폰에서 탭을 사용할 수 있도록 할지 여부를 선택합니다.|
|**서식 지정**|**컨트롤이 차지하는 열 수 선택**|필드를 포함하는 섹션에 둘 이상의 열이 있다면 섹션에 있는 최대 열 수를 차지하도록 필드를 설정할 수 있습니다.|  
|**세부 정보**|**표시 이름**, **이름** 및 **설명**|이러한 읽기 전용 필드는 참조용입니다. 편집하려는 필드 정의에 편리하게 액세스하려면 **편집** 단추를 클릭합니다.<br /><br /> 양식에 있는 필드의 각 인스턴스마다 이름 속성이 있으므로 양식 스크립트에서 참조할 수 있지만 이 이름은 응용 프로그램에서 관리합니다. 필드의 첫 번째 인스턴스는 필드를 만들 때 지정한 필드의 이름입니다. 자세한 정보: [필드 만들기 및 편집](../common-data-service/create-edit-fields.md)<br /><br /> 필드가 양식에 포함될 때마다 이름 끝에 1부터 시작하는 숫자가 추가됩니다. 따라서 필드 이름이 ‘new_cost’인 경우 첫 번째 인스턴스는 ‘new_cost’이고 두 번째 인스턴스는 ‘new_cost1’이며 양식에 있는 필드의 각 인스턴스에 대해 이렇게 번호가 매겨집니다.<br /><br />**참고:** **설명** 필드 값은 사람이 커서를 올려 놓을 때 필드에 대한 도구 설명 텍스트를 제공합니다.|  
|**이벤트**|**양식 라이브러리**|필드 `OnChange` 이벤트 처리기에서 사용될 JavaScript 웹 리소스를 지정합니다.<br /><br />|  
||**이벤트 처리기**|필드 `OnChange` 이벤트에 대해 호출해야 하는 양식 라이브러리에서 함수를 구성합니다. 자세한 정보: [이벤트 처리기 구성](configure-event-handlers-legacy.md)|  
|**비즈니스 규칙**|**비즈니스 규칙**|이 필드를 참조하는 비즈니스 규칙을 보고 관리합니다. 자세한 정보: [비즈니스 규칙 및 권장 사항 만들기](create-business-rules-recommendations-apply-logic-form.md)|  
|**컨트롤**|**컨트롤**|컨트롤을 추가하고 웹, 휴대폰 및 테이블에서 사용 여부를 지정합니다.|  

## <a name="next-steps"></a>다음 단계

[기본 양식 및 해당 구성 요소 사용](use-main-form-and-components.md)
