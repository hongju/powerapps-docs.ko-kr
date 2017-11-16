---
title: "AddColumns, DropColumns, RenameColumns 및 ShowColumns 함수 | Microsoft Docs"
description: "PowerApps에서 AddColumns, DropColumns, RenameColumns 및 ShowColumns 함수에 대한 구문과 예제를 포함한 참조 정보"
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 37261f710ffd13cb9eae4aa6aa9eb551e7964fb9
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>PowerApps에서 AddColumns, DropColumns, RenameColumns 및 ShowColumns 함수
해당 [열](../working-with-tables.md#columns)을 추가, 삭제, 이름 바꾸기 및 선택하여 [테이블](../working-with-tables.md)을 셰이프합니다.

## <a name="overview"></a>개요
이러한 함수는 해당 열을 조정하여 테이블을 셰이프합니다.

* **[Lower](function-lower-upper-proper.md)** 또는 **[Abs](function-numericals.md)**와 같은 단일 열 함수를 사용하도록 여러 열을 포함하는 테이블을 단일 열로 축소시킵니다.  
* 테이블에 계산된 열을 추가합니다(예: **Quantity**에 **Unit Price**를 곱한 결과를 표시하는 **Total Price** 열).
* 사용자에게 표시하거나 수식에서 사용할 수 있도록 열의 이름을 더 의미 있게 변경합니다.

테이블은 문자열이나 숫자처럼 PowerApps의 값입니다.  테이블을 수식의 인수로 지정할 수 있으며 함수는 테이블을 결과로 반환할 수 있습니다. 이 토픽에서 설명하는 함수는 테이블을 수정하지 않습니다. 대신 테이블을 인수로 사용하며 적용되는 변환을 통해 새 테이블을 반환합니다.  자세한 내용은 [테이블 작업](../working-with-tables.md)을 참조하세요.  

이러한 함수를 사용하여 [데이터 원본](../working-with-data-sources.md)의 열을 수정할 수는 없습니다. 데이터는 해당 원본에서 수정해야 합니다. **[Collect](function-clear-collect-clearcollect.md)** 함수를 사용하여 열을 [컬렉션](../working-with-data-sources.md#collections)에 추가할 수 있습니다.  자세한 내용은 [데이터 원본 작업](../working-with-data-sources.md)을 참조하세요.  

## <a name="description"></a>설명
**AddColumns** 함수는 열을 테이블에 추가하고, 수식은 해당 열의 값을 정의합니다. 기존 열은 수정되지 않고 유지됩니다.

수식은 각 테이블의 레코드에 대해 평가됩니다.
[!INCLUDE [record-scope](../../includes/record-scope.md)]

**DropColumns** 함수는 테이블에서 열을 제외합니다.  다른 모든 열은 수정되지 않고 유지됩니다. **DropColumns**는 열을 제외하고 **ShowColumns**는 열을 포함합니다.

**RenameColumns** 함수는 테이블 열의 이름을 변경합니다. 다른 모든 열은 원래 이름을 유지합니다.

**ShowColumns** 함수는 테이블의 열을 포함하고 다른 모든 열을 삭제합니다. **ShowColumns**를 사용하여 다중 열 테이블에서 단일 열 테이블을 만들 수 있습니다.  **ShowColumns**는 열을 포함하고 **DropColumns**는 열을 제외합니다.  

이러한 모든 함수의 경우 적용된 변환을 사용하는 새 테이블이 만들어집니다.  원래 테이블은 수정되지 않습니다.

[!INCLUDE [delegation-no](../../includes/delegation-no.md)]

## <a name="syntax"></a>구문
**AddColumns**( *Table*, *ColumnName1*, *Formula1* [, *ColumnName2*, *Formula2*, ... ] )

* *Table* - 필수 항목입니다.  연산을 수행할 테이블입니다.
* *ColumnName(s)* - 필수 항목입니다. 추가할 열의 이름입니다.  이 인수에 대해 문자열(예를 들어 큰따옴표가 포함된 **“Name”**)을 지정해야 합니다.
* *Formula(s)* - 필수 항목입니다.  각 레코드에 대해 평가할 수식입니다. 결과는 해당하는 새 열 값으로 추가됩니다. 이 수식에서 테이블의 다른 열을 참조할 수 있습니다.

**DropColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table* - 필수 항목입니다.  연산을 수행할 테이블입니다.
* *ColumnName(s)* - 필수 항목입니다. 삭제할 열의 이름입니다. 이 인수에 대해 문자열(예를 들어 큰따옴표가 포함된 **“Name”**)을 지정해야 합니다.

**RenameColumns**( *Table*, *OldColumneName*, *NewColumnName* )

* *Table* - 필수 항목입니다.  연산을 수행할 테이블입니다.
* *OldColumnName* -필수 항목입니다. 이름을 변경할 열의 이름입니다. 이 이름은 문자열(예를 들어 큰따옴표가 포함된 **“Name”**)이어야 합니다.
* *NewColumnName* - 필수 항목입니다. 교체 이름입니다. 이 인수에 대해 문자열(예를 들어 큰따옴표가 포함된 **“Customer Name”**)을 지정해야 합니다.

**ShowColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table* - 필수 항목입니다.  연산을 수행할 테이블입니다.
* *ColumnName(s)* - 필수 항목입니다. 포함할 열의 이름입니다. 이 인수에 대해 문자열(예를 들어 큰따옴표가 포함된 **“Name”**)을 지정해야 합니다.

## <a name="examples"></a>예
이 섹션의 예제에서는 다음 테이블의 데이터가 포함된 **IceCreamSales** 데이터 원본을 사용합니다.

![](media/function-table-shaping/icecream.png)

이러한 예제는 모두 **IceCreamSales** 데이터 원본을 수정하지 않습니다. 각 함수는 데이터 원본의 값을 테이블로 변환하고 결과로 해당 값을 반환합니다.

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **AddColumns( IceCreamSales, “Revenue”, UnitPrice * QuantitySold )** |**Revenue** 열을 결과에 추가합니다.  각 레코드의 경우 **UnitPrice * QuantitySold**가 평가되고 결과가 새 열에 배치됩니다. |<style> img { max-width: none; } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns( IceCreamSales, “UnitPrice” )** |**UnitPrice** 열을 결과에서 제외합니다. 이 함수를 사용하여 열을 제외하고 **ShowColumns**를 사용하여 포함합니다. |![](media/function-table-shaping/icecream-drop-price.png) |
| **ShowColumns( IceCreamSales, “Flavor” )** |**Flavor** 열만 결과에 포함합니다. 이 함수를 사용하여 열을 포함하고 **DropColumns**를 사용하여 제외합니다. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **RenameColumns( IceCreamSales, “UnitPrice”, “Price”)** |결과에서 **UnitPrice** 열 이름을 변경합니다. |![](media/function-table-shaping/icecream-rename-price.png) |
| **DropColumns(<br>RenameColumns(<br>AddColumns( IceCreamSales, “Revenue”,<br>UnitPrice * QuantitySold ),<br>“UnitPrice”, “Price” ),<br>“Quantity” )** |다음 테이블 변환을 수식의 내부부터 순서대로 수행합니다. <ol><li>**UnitPrice * Quantity**의 레코드별 계산을 기반으로 **Revenue** 열을 추가합니다.<li>**UnitPrice**의 이름을 **Price**로 변경합니다.<li>**Quantity** 열을 제외합니다.</ol>  순서는 중요합니다. 예를 들어 이름이 변경된 후에는 **UnitPrice**로 계산할 수 없습니다. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>단계별 가이드
1. [갤러리에서 텍스트 및 이미지 표시](../show-images-text-gallery-sort-filter.md)에서 설명하는 첫 번째 하위 절차에 따라 **Inventory**라는 컬렉션을 가져오거나 만듭니다.
2. 단추 하나를 추가하고 이 수식에 **[OnSelect](../controls/properties-core.md)** 속성을 설정합니다.
   
    **ClearCollect(Inventory2, RenameColumns(Inventory, “ProductName”, “JacketID”))**
3. F5 키를 누르고 방금 만든 단추를 클릭한 다음 Esc 키를 눌러서 디자인 작업 영역으로 돌아갑니다.
4. **파일** 메뉴에서 **컬렉션**을 선택합니다.
5. **Inventory2**라는 컬렉션을 만들었음을 확인합니다. 새 컬렉션은 **Inventory**의 **ProductName**라는 열이 **Inventory2**의 **JacketID**로 이름이 변경된 것 외에 **Inventory**와 동일한 정보를 포함합니다.

