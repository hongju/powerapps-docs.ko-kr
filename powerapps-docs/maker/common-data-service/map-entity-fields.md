---
title: PowerApps의 엔터티 필드 매핑 | MicrosoftDocs
description: 엔터티 필드 매핑 방법 알아보기
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 7c5aa1c3-bde9-43f1-a369-fdcdbf14dec0
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: 7e84e10a824ea218063cb2dccdc15ed7ae2340da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696644"
---
# <a name="map-entity-fields"></a>엔터티 필드 매핑
 
엔터티 관계가 있는 엔터티 간의 특성을 매핑할 수 있습니다. 이렇게 하면 다른 레코드의 컨텍스트에서 만들어진 레코드의 기본값을 설정할 수 있습니다. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>모델 기반 앱에서 새 레코드를 쉽게 만드는 방법

사람들이 특정 계정의 직원인 사람의 새 연락처 레코드를 추가하려고 한다고 가정해 봅니다. 두 가지 방법으로 이 작업을 수행할 수 있습니다.  
  
### <a name="the-hard-way"></a>어려운 방법

사람들은 앱을 탐색하여 처음부터 새로운 연락처 레코드를 만들 수 있습니다. 하지만 부모 계정을 설정하고 부모 계정과 동일한 몇 가지 정보 항목(예: 주소 및 전화 정보)을 입력해야 합니다. 이 작업은 시간이 오래 걸릴 수 있으며 오류가 발생할 수 있습니다.  
  
### <a name="the-easier-way"></a>더 쉬운 방법

보다 쉬운 방법은 계정 엔터티에서 시작하고 양식의 **연락처** 하위 그리드를 사용하여 **+** 를 선택해서 연락처를 추가합니다. 처음에는 실수로 중복 레코드를 만들지 않도록 사용자가 기존 관련 연락처를 조회하도록 안내할 것입니다. 기존 레코드를 찾을 수 없는 경우 **새로 만들기**를 선택하고 새 연락처 레코드를 만들 수 있습니다. 

새 연락처 레코드 형식에는 계정의 매핑된 특성 값(예: 주소 및 전화 정보)이 기본값으로 포함됩니다. 사용자는 레코드를 저장하기 전에 이러한 값을 편집할 수 있습니다.

## <a name="how-this-works"></a>작동 방식

1:N 엔터티 관계에 대한 엔터티 필드를 매핑하면 기본 엔터티 레코드의 특정 데이터 항목이 새 관련 엔터티 양식에 복사되어 사용자가 저장하기 전에 편집할 수 있는 기본값을 설정합니다.
 
  
> [!NOTE]
> 이러한 매핑은 저장하기 전에 기본값을 레코드로만 설정합니다. 사용자가 저장하기 전에 값을 편집할 수 있습니다. 전송되는 데이터는 해당 시점의 데이터입니다. 원본 데이터가 나중에 변경되면 동기화되지 않습니다.
>   
> 이러한 매핑은 워크플로 또는 대화 상자 프로세스를 사용하여 만든 관련 레코드에 적용되지 않습니다. 개발자가 `InitializeFrom`([InitializeFrom 함수](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) 또는 [InitializeFromRequest 클래스](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9))이라는 특수 메시지를 사용하여 사용 가능한 매핑을 통해 새 레코드를 만들 수 있지만, 코드를 사용하여 만든 새 레코드에 자동으로 적용되지 않습니다.  

## <a name="open-solution-explorer"></a>솔루션 탐색기 열기

엔터티 필드를 매핑하는 유일한 방법은 솔루션 탐색기를 사용하는 것입니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
필드 매핑은 1:N 또는 N:1 엔터티 관계의 컨텍스트에서 수행되므로 먼저 [1:N 또는 N:1 엔터티 관계 보기](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships)를 사용해야 합니다.

## <a name="view-mappable-fields"></a>매핑 가능한 필드 보기

필드 매핑은 엔터티 관계 내에서 실제로 정의되지 않지만 관계 사용자 인터페이스에 표시됩니다. 모든 1:N 엔터티 관계에 해당하는 것은 아닙니다. 엔터티에 대한 1:N(또는 N:1) 엔터티 관계의 목록을 볼 때 유형별로 표시된 관계를 필터링할 수 있습니다. **모두**, **사용자 지정**, **사용자 지정 가능** 또는 **매핑 가능** 중 하나를 선택할 수 있습니다. 매핑 가능한 엔터티 관계는 엔터티 필드 매핑을 위한 액세스를 제공합니다. 

![매핑 가능한 엔터티 관계 보기](media/mappable-entity-relationships.png) 

매핑 가능한 엔터티 관계를 열 때 왼쪽 탐색 영역에서 **매핑**을 선택합니다.

![엔터티 관계에 대한 매핑 선택](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>매핑 삭제

적용하지 않을 매핑이 있는 경우 해당 매핑을 선택하고 ![삭제 아이콘](media/delete.gif) 아이콘을 클릭합니다.

## <a name="add-new-mappings"></a>새 매핑 추가

새 매핑을 만들려면 도구 모음에서 **새로 만들기**를 클릭합니다. **필드 매핑 만들기** 대화 상자가 열립니다.

![필드 매핑 만들기 대화 상자](media/create-field-mapping-dialog.png)

하나의 원본 엔터티 필드 및 매핑할 값이 있는 대상 엔터티 필드 하나를 선택합니다. 

![필드 매핑 구성](media/configure-field-mapping.png)

그런 다음, **확인**을 선택하여 대화 상자를 닫습니다.

다음 규칙은 매핑할 수 있는 데이터의 종류를 보여줍니다.  
  
- 두 필드는 모두 유형이 동일하고 형식이 같아야 합니다.  
- 대상 필드의 길이는 원본 필드의 길이보다 크거나 같아야 합니다.  
- 대상 필드를 다른 필드에 미리 매핑할 수 없습니다.  
- 원본 필드는 양식에 표시되어야 합니다.  
- 대상 필드는 사용자가 데이터를 입력할 수 있는 필드여야 합니다.  
- 주소 ID 값을 매핑할 수 없습니다.
- 양식에 표시되지 않는 필드로 또는 필드에서 매핑하는 경우 필드가 양식에 추가될 때까지 매핑은 수행되지 않습니다.
- 필드가 옵션 집합인 경우 각 옵션의 정수 값은 동일해야 합니다.  
  
> [!NOTE]
>  옵션 집합 필드를 매핑해야 하는 경우 두 필드를 모두 동일한 글로벌 옵션 집합을 사용하도록 구성하는 것이 좋습니다. 그렇지 않으면 두 개의 개별 옵션 집합을 수동으로 동기화하는 것이 어려울 수 있습니다. 각 옵션의 정수 값이 올바르게 매핑되지 않으면 데이터에 문제가 발생할 수 있습니다. 자세한 정보: [앱용 Common Data Service에 대한 글로벌 옵션 집합 만들기 및 편집(선택 목록)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>필드 매핑이 자동으로 생성  

**추가 작업** 메뉴에서 **매핑 생성**을 선택하여 자동으로 매핑을 생성할 수도 있습니다.

시스템 엔터티에서 이 작업을 수행할 때는 주의해야 합니다. 사용자 지정 엔터티를 만들고 매핑을 활용하려는 경우 이 옵션을 사용합니다. 

> [!WARNING]
> 이렇게 하면 기존 매핑이 모두 제거되고 비슷한 이름과 데이터 형식을 가진 필드에만 기반한 제안된 매핑으로 바뀝니다. 시스템 엔터티에 이 옵션을 사용하면 일부 예상되는 매핑이 손실될 수 있습니다. 사용자 지정 엔터티의 경우 원하지 않은 매핑을 더 쉽게 삭제할 수 있고 매핑 생성 작업이 생성하지 않은 매핑을 추가할 수 있기 때문에 시간을 절약할 수 있습니다.  


## <a name="publish-customizations"></a>사용자 지정 게시 

필드 매핑은 메타데이터가 아니므로 변경 내용을 적용하기 전에 게시해야 합니다. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>참고 항목
[솔루션 탐색기를 사용하여 1:N(일대다) 또는 N:1(다대일) 엔터티 관계 만들기 및 편집](create-edit-1n-relationships-solution-explorer.md)<br />
[개발자 설명서: 엔터티 및 특성 매핑 사용자 지정](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[개발자 설명서: Web API 다른 엔터티에서 새 엔터티 만들기](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
