---
title: Collect, Clear 및 ClearCollect 함수 | Microsoft Docs
description: PowerApps의 Collect, Clear 및 ClearCollect 함수에 대한 구문과 예제를 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 86d36af00d3c5aa825b01ed873150f94738a952c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61546574"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>PowerApps의 Collect, Clear 및 ClearCollect 함수

[컬렉션](../working-with-data-sources.md#collections)을 만들고 지우고 [데이터 원본](../working-with-data-sources.md)에 [레코드](../working-with-tables.md#records)를 추가합니다.

## <a name="description"></a>설명

### <a name="collect"></a>Collect

**Collect** 함수는 데이터 원본에 레코드를 추가합니다. 추가할 수 있는 항목은 다음과 같습니다.

- 단일 값입니다. 값에 위치한 합니다 **[값](function-value.md)** 새 레코드의 필드입니다.  다른 모든 속성은 [공백](function-isblank-isempty.md)으로 둡니다.
- 레코드: 각 명명 된 속성은 새 레코드의 해당 속성에 배치 됩니다.  다른 모든 속성은 공백으로 둡니다.
- A [테이블](../working-with-tables.md): 테이블의 각 레코드는 위에서 설명한 대로 데이터 원본의 별도 레코드로 추가 됩니다. 테이블은 레코드에 중첩 테이블로 추가되지 않습니다. 이를 수행하려면 테이블을 레코드에 먼저 랩핑하십시오.

컬렉션과 함께 사용하면, 필요에 따라 추가 [열](../working-with-tables.md#columns)이 생성됩니다. 다른 데이터 원본의 열이 데이터 원본으로 고정되며 새 열은 추가할 수 없습니다.  

데이터 원본이 아직 없으면 컬렉션이 생성됩니다.

컬렉션은 전역 변수를 보관하거나 데이터 원본의 임시 복사본을 생성하는 데 사용되기도 합니다. PowerApps는 사용자가 앱과 상호 작용할 때 자동으로 다시 계산되는 수식을 기반으로 합니다. 컬렉션에는 이런 이점이 활용되지 않기 때문에 컬렉션을 사용하면 앱을 만들고 이해하기가 더 어려워질 수 있습니다. 이런 방식으로 컬렉션을 사용하기 전에 [변수 작업](../working-with-variables.md)을 참조하세요.

**[Patch](function-patch.md)** 함수를 사용하여 데이터 원본에 레코드를 생성할 수도 있습니다.

**Collect**는 수정된 데이터 원본을 테이블로 반환합니다.  **Collect**는 [동작 수식](../working-with-formulas-in-depth.md)에만 사용할 수 있습니다.

### <a name="clear"></a>지우기

**Clear** 함수는 컬렉션의 모든 레코드를 삭제합니다.  컬렉션의 열은 그대로 유지됩니다.

**Clear**는 컬렉션에서만 작동하며 다른 데이터 원본에는 작동하지 않습니다.  이런 용도에는 **[RemoveIf](function-remove-removeif.md)( *DataSource*, true )** 를 사용할 수 있습니다.  데이터 원본의 스토리지에서 모든 레코드를 제거하고 다른 사용자에게 영향을 줄 수 있으므로 주의해서 사용해야 합니다.

**[Remove](function-remove-removeif.md)** 함수를 사용하면 레코드를 선택적으로 제거할 수 있습니다.

**Clear**는 반환 값이 없습니다.  동작 수식에만 사용할 수 있습니다.

### <a name="clearcollect"></a>ClearCollect

**ClearCollect** 함수는 컬렉션에서 모든 레코드를 삭제한 다음, 동일한 컬렉션에 다른 레코드 집합을 추가합니다.  **ClearCollect**는 단일 함수로 **Clear**와 **Collect**의 조합을 제공합니다.

**ClearCollect**는 수정된 컬렉션을 테이블로 반환합니다.  **ClearCollect**는 동작 수식에만 사용할 수 있습니다.

## <a name="syntax"></a>구문

**Collect**( *DataSource*, *Item*, ... )

* *DataSource* – 필수 항목입니다. 데이터를 추가할 데이터 원본입니다.  없는 경우 새로운 컬렉션이 생성됩니다.
* *Item(s)* - 필수 항목입니다.  데이터 원본에 추가할 하나 이상의 레코드 또는 테이블입니다.  

**Clear**( *Collection* )

* *Collection* – 필수 항목입니다. 지울 컬렉션입니다.

**ClearCollect**( *Collection*, *Item*, ... )

* *Collection* – 필수 항목입니다. 지우고 데이터를 추가할 컬렉션입니다.
* *Item(s)* - 필수 항목입니다.  데이터 원본에 추가할 하나 이상의 레코드 또는 테이블입니다.  

## <a name="examples"></a>예

### <a name="clearing-and-adding-records-to-a-data-source"></a>데이터 원본 지우기 및 레코드 추가

이 예제에서는 **IceCream**이라는 컬렉션을 지우고 추가합니다. 데이터 원본은 다음 콘텐츠로 시작됩니다.

![샘플 데이터 원본](media/function-clear-collect-clearcollect/icecream.png)

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **ClearCollect( IceCream, {&nbsp;Flavor:&nbsp;"Strawberry",&nbsp;Quantity:&nbsp;300&nbsp;} )** |**IceCream** 컬렉션의 모든 데이터를 지운 다음 일정량의 Strawberry 아이스크림이 포함된 레코드를 추가합니다. |<style> img {최대 너비: none} </style> ![이상의 레코드가 있는 테이블](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>**IceCream** 데이터 원본 역시 수정되었습니다. |
| **Collect( IceCream, {&nbsp;Flavor:&nbsp;"Pistachio",&nbsp;Quantity:&nbsp;40&nbsp;}, {&nbsp;Flavor:&nbsp;"Orange",&nbsp;Quantity:&nbsp;200&nbsp;}  )** |일정량의 Pistachio 및 Orange 아이스크림이 포함된 두 개의 레코드를 **IceCream** 컬렉션에 추가합니다. |![두 개의 레코드를 사용 하 여 테이블](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>**IceCream** 데이터 원본 역시 수정되었습니다. |
| **Clear( IceCream )** |**IceCream** 컬렉션에서 모든 레코드를 제거합니다. |![빈 테이블](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>**IceCream** 데이터 원본 역시 수정되었습니다. |

컬렉션을 만드는 방법의 단계별 예제를 참조 하세요 [만들기 및 업데이트 컬렉션](../create-update-collection.md)합니다.
