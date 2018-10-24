---
title: PowerApps를 사용하여 시스템 엔터티 메시지 편집 | MicrosoftDocs
description: 시스템 엔터티 메시지를 편집하는 방법 알아보기
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 3ccbd8de-8d6f-4058-87f7-15463667cfc6
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 797d6855bea421abd90752dd9ae0ad73a9d92f38
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39694796"
---
# <a name="edit-system-entity-messages"></a>시스템 엔터티 메시지 편집

일부 시스템 엔터티의 기본 표시 이름은 앱용 Common Data Service의 사용자 인터페이스 텍스트 및 오류 메시지에서 사용됩니다. 표시 이름을 변경하는 경우 기본 표시 이름을 사용하는 모든 메시지를 업데이트해야 합니다. 예를 들어 *계정*에서 *회사*로 표시 이름을 변경하는 경우 이전 이름을 사용하는 오류 메시지를 여전히 볼 수 있습니다.  

PowerApps 포털을 사용하여 시스템 메시지를 편집할 수 없습니다. 솔루션 탐색기를 사용해야 합니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

솔루션 탐색기의 엔터티 아래에서 **메시지** 노드가 표시되는 경우 원래 엔터티 표시 이름에 대한 참조를 포함하는 특정 텍스트를 편집할 수 있습니다. 

![엔터티 메시지](../model-driven-apps/media/entity-messages.png)

이 텍스트를 편집하는 것은 간단합니다. 메시지를 두 번 클릭하여 세 개의 필드가 있는 양식을 표시합니다.  
  
|필드|설명|  
|-----------|-----------------|  
|**기본 표시 문자열**|원본 텍스트를 보여줍니다.|  
|**사용자 지정 표시 문자열**|표시 문자열을 변경하려면 이 텍스트를 편집합니다.|  
|**설명**|선택 사항입니다. 변경 내용 및 이유에 대한 설명을 포함합니다.|  
  
일부 메시지 텍스트에는 자리 표시자가 있을 수 있습니다. 이러한 자리 표시자는 양쪽에 대괄호가 있는 숫자입니다. 예: `{0}` 이러한 자리 표시자를 통해 텍스트를 메시지에 삽입할 수 있습니다. 메시지를 편집하는 경우 이러한 자리 표시자를 유지하는지 확인합니다. 

변경 내용을 저장하려면 ![저장](media/save-entity-icon-solution-explorer.png)을 선택합니다. 저장할 때 양식을 닫으려면 **저장 후 닫기**를 선택합니다.

> [!NOTE]
> 시스템 엔터티 메시지를 편집하기 위해 노출된 UI에는 엔터티 이름에 대한 여러 참조가 포함되어 있지만 모두 포함된 것은 아닙니다. 더 포괄적인 접근 방식은 [기본 언어로 지역화할 수 있는 텍스트 업데이트](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language)를 참조하세요.

## <a name="programmatically-update-entity-display-strings"></a>프로그래밍 방식으로 엔터티 표시 문자열 업데이트

코드에서 이를 사용하는 방법을 찾는 개발자의 경우 표시 문자열은 [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md) 엔터티에 저장됩니다. 

`DisplayString` 엔터티는 기본 표시 문자열을 포함하지 않습니다. 텍스트를 포함하는 이 엔터티에 대한 두 가지 특성은 [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) 및 [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString)입니다. 기본적으로 표시 문자열이 사용자 지정되고 게시되지 않는 한 이러한 특성 값은 Null입니다. `PublishedDisplayString` 값은 읽기 전용이며 현재 게시된 `CustomDisplayString`을 반영합니다.
 
## <a name="see-also"></a>참고 항목
[엔터티 편집](edit-entities.md)<br />
[모델 기반 앱의 지역화할 수 있는 텍스트 번역](../model-driven-apps/translate-localizable-text.md)
