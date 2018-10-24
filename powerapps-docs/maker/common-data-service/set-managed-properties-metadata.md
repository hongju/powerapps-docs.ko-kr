---
title: 앱 메타데이터에 대한 Common Data Service에서 관리 속성 설정 | Microsoft Docs
description: 솔루션에서 메타데이터 항목에 대한 관리 속성을 설정하는 방법 알아보기
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
ms.assetid: edaa7d4a-a95f-4d66-a9d9-2ad6051332f7
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 46727f5a46e3fd518da52fac7d08a6e43992c00d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692655"
---
# <a name="set-managed-properties-in-common-data-service-for-apps-metadata"></a>앱 메타데이터에 대한 Common Data Service에서 관리 속성 설정 

관리 속성은 관리형 솔루션을 통해 메타데이터를 포함하고 다른 환경으로 가져올 경우에만 적용됩니다. 이러한 설정을 통해 솔루션 작성자는 관리형 솔루션을 설치하는 사람들에게 허용하려는 사용자 지정 수준을 어느 정도 제어할 수 있습니다. 

> [!TIP]
> 일반적으로 비즈니스 데이터를 사용하는 솔루션에서 메타데이터를 확장할 수 있도록 하는 것이 좋습니다. 이렇게 하면 표준 엔터티에 대해 할 수 있는 것과 동일한 방법으로 해당 요구에 맞게 솔루션을 조정할 수 있습니다.
>
>솔루션을 지원하기 위한 기능을 제공하지만 비즈니스 데이터를 포함하지 않은 메타데이터에서는 사용자 지정이 허용되는 것을 제한하는 것이 좋습니다.

관리 속성을 설정은 솔루션 탐색기를 사용하여 이뤄져야 합니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>엔터티 관리 속성

[엔터티를 보는](create-edit-entities-solution-explorer.md#view-entities) 동안 엔터티를 선택하고 메뉴 모음에서 **관리 속성**을 선택합니다.  이렇게 하면 **관리 속성 설정** 대화 상자가 열립니다.

![엔터티 관리 속성 설정](media/set-managed-properties.png)
  
엔터티에는 다른 유형의 솔루션 구성 요소보다 관리 속성이 많이 있습니다. 엔터티를 사용자 지정할 수 있는 경우 다음 옵션을 설정할 수 있습니다.  

|옵션|설명|
|--|--|
|**사용자 지정 가능** |다른 모든 옵션을 제어합니다. 이 옵션이 `False`이면 다른 설정이 적용되지 않습니다. 이 옵션이 `True`이면 다른 사용자 지정 옵션을 지정할 수 있습니다. 이 옵션이 `False`이면 다른 모든 옵션을 False로 설정하는 것과 같습니다.|
|**표시 이름 수정 가능**|엔터티 표시 이름을 수정할 수 있는지 여부를 결정합니다.|
|**추가 속성 변경 가능** |다른 옵션에서 다루지 않는 모든 항목에 적용됩니다.|
|**새 양식 생성 가능**|엔터티에 대한 새 양식을 만들 수 있는지 여부를 결정합니다.|
|**새 차트 생성 가능**|엔터티에 대한 새 차트를 만들 수 있는지 여부를 결정합니다.|
|**새 보기 생성 가능** |엔터티에 대한 새 보기를 만들 수 있는지 여부를 결정합니다.|
|**계층적 관계 변경 가능**|계층적 관계 설정을 변경할 수 있는지 여부를 결정합니다. 자세한 정보: [계층적으로 관련된 데이터 정의 및 쿼리](define-query-hierarchical-data.md)|
|**변경 내용 추적 사용 가능** |엔터티 **변경 내용 추적** 속성을 변경할 수 있는지 여부를 결정합니다.|
|**외부 검색 인덱스에 동기화 사용하도록 설정 가능** |관련성 검색을 사용하도록 엔터티를 구성할 수 있는지 여부를 결정합니다. 자세한 정보: [검색 결과 및 성능 향상을 위해 관련성 검색 구성](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>필드 관리 속성

필드를 편집하는 방법에 대한 내용은 [PowerApps 솔루션 탐색기를 사용하여 앱용 Common Data Service의 필드 만들기 및 편집](create-edit-field-solution-explorer.md)을 참조하세요.

[필드를 보는](create-edit-field-solution-explorer.md#view-fields) 동안 관리되지 않는 솔루션에서 사용자 지정 필드를 선택한 다음, 메뉴 모음에서 **기타 작업** >  **관리 속성**을 선택합니다.

![필드 관리 속성 보기](media/view-field-managed-properties-solution-explorer.png)  
  
이렇게 하면 **관리 속성 설정** 대화 상자가 열립니다.

![필드 관리 속성 설정](media/set-field-managed-property.png)

**사용자 지정 가능** 옵션은 다른 모든 옵션을 제어할 수 있습니다. 이 옵션이 **False**이면 다른 설정이 적용되지 않습니다. 이 옵션이 **True**이면 다른 사용자 지정 옵션을 지정할 수 있습니다.  
  
필드를 사용자 지정할 수 있는 경우 다음 옵션을 **True** 또는 **False**로 설정합니다.  
  
- **표시 이름 수정 가능**
- **요구 사항 수준 변경 가능** 
- **추가 속성 변경 가능**: 이 속성은 특정 관리 속성이 없는 다른 모든 사용자 지정을 제어합니다.

모든 개별 옵션을 **False**로 설정하면 **사용자 지정 가능** 옵션을 **False**로 설정하는 것과 같습니다.  

선택 항목을 적용하고 **설정**을 클릭하여 대화 상자를 닫습니다.

> [!NOTE]
> 이 필드가 **날짜 및 시간** 필드인 경우 **날짜 및 시간 동작 변경 가능** 속성을 추가로 사용할 수 있습니다. 자세한 정보: [날짜 및 시간 필드의 동작 및 형식](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>관계 관리 속성

엔터티 관계를 보는 동안 관리되지 않는 솔루션에서 관계를 선택한 다음, 메뉴 모음에서 **기타 작업** > **관리 속성**을 선택합니다.
  
관계를 사용하여 관리 속성만 **사용자 지정 가능**합니다. 이 단일 설정은 엔터티 관계에 대해 수행할 수 있는 모든 변경 내용을 제어합니다. 


### <a name="see-also"></a>참고 항목

[관리 속성](solutions-overview.md#managed-properties)<br />
[솔루션 탐색기를 사용하여 엔터티 만들기 및 편집](create-edit-entities-solution-explorer.md)<br />
[PowerApps 솔루션 탐색기를 사용하여 앱용 Common Data Service의 필드 만들기 및 편집](create-edit-field-solution-explorer.md)<br />
[솔루션 탐색기를 사용하여 1:N(일대다) 또는 N:1(다대일) 엔터티 관계 만들기 및 편집](create-edit-1n-relationships-solution-explorer.md)<br />
[솔루션 탐색기를 사용하여 앱용 Common Data Service에서 N:N(다대다) 엔터티 관계 만들기](create-edit-nn-relationships-solution-explorer.md)