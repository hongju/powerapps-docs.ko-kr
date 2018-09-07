---
title: Blank, Coalesce, IsBlank 및 IsEmpty 함수 | Microsoft Docs
description: PowerApps의 Blank, Coalesce, IsBlank 및 IsEmpty 함수에 대한 참조 정보이며, 구문과 예제를 포함하고 있습니다.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.component: canvas
ms.date: 07/24/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e31d3689c7b61c408be90c31f1e212e4fdd9a91c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42848986"
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>PowerApps의 Blank, Coalesce, IsBlank 및 IsEmpty 함수
값이 비어 있거나 [테이블](../working-with-tables.md)에 [레코드](../working-with-tables.md#records)가 없는지 여부를 테스트하고 *공백* 값을 만드는 방법을 제공합니다.

## <a name="overview"></a>개요
*공백*은 "값 없음" 또는 "알 수 없는 값"에 대한 자리 표시자입니다. 사용자가 문자를 입력하지 않으면 **[텍스트 입력](../controls/control-text-input.md)** 컨트롤은 *공백*입니다. 사용자가 문자를 입력하는 즉시 동일한 컨트롤은 더 이상 *공백*이 아닙니다.  일부 데이터 원본에서 NULL 값을 저장하고 반환할 수 있으며, 이 값은 PowerApps에서 *공백*으로 표현됩니다.

> [!NOTE]
> *공백* 값 저장은 현재 로컬 컬렉션에만 지원됩니다. 많은 데이터 원본에서 *공백*(NULL) 값을 지원하며, 이 제한을 제거하기 위해 노력하고 있습니다.

속성 또는 계산 값은 *공백*일 수 있습니다.  예를 들어 부울 값은 일반적으로 **true** 또는 **false** 값 중 하나입니다.  하지만 이 두 가지 값 외에도 *공백*일 수도 있습니다.  이는 워크시트 셀이 공백으로 시작하지만 **TRUE** 또는 **FALSE** 값을 포함할 수 있는 Microsoft Excel과 비슷합니다. 셀의 내용은 언제든지 제거할 수 있으며, 이 경우 *공백* 상태로 돌아갑니다.

*비어 있음*은 레코드가 없는 테이블에만 해당됩니다. 테이블 구조는 [열](../working-with-tables.md#columns) 이름을 포함한 채 그대로 완벽하게 유지될 수 있지만 테이블에는 데이터가 없습니다. 테이블은 비어있는 것으로 시작하여 레코드를 가져와서 더 이상 비어 있지 않으며, 그런 다음 레코드를 제거하여 다시 비워둘 수 있습니다.

## <a name="description"></a>설명
**Blank** 함수는 *공백* 값을 반환합니다. 이 값을 지원하는 데이터 원본에 NULL 값을 저장하여 필드에서 값을 효과적으로 제거합니다.

**IsBlank** 함수는 *공백* 값을 테스트합니다. *공백* 값은 다음과 같은 상황에서 찾을 수 있습니다.

* **Blank** 함수의 반환 값입니다.
* 컨트롤 속성에 수식이 설정되어 있지 않습니다.
* 텍스트 입력 컨트롤에 입력된 값이 없거나 목록 상자에서 아무 것도 선택하지 않았습니다. **IsBlank**를 사용하여 필수 필드임을 알려주는 피드백을 제공할 수 있습니다.
* 문자가 없는 문자열에는 **[Len](function-len.md)** 의 0이 있습니다.
* 함수에서 오류가 발생했습니다. 종종 함수에 대한 인수 중 하나가 유효하지 않습니다. 인수의 값이 *공백*이면 많은 함수에서 *공백*을 반환합니다.
* 연결된 [데이터 원본](../working-with-data-sources.md)(예: SQL Server)에서 "null" 값을 사용할 수 있습니다. 이 값은 PowerApps에서 *공백*으로 표시됩니다.
* **[If](function-if.md)** 함수의 *else* 부분은 지정되지 않았으며 모든 조건이 **false**입니다.
* **[Update](function-update-updateif.md)** 함수를 사용했지만 모든 열에 대한 값을 지정하지 않았습니다. 이에 따라 지정하지 않은 열에는 값이 배치되지 않았습니다.

**Coalesce** 함수는 인수를 순서대로 평가하고 *공백*이 아닌 첫 번째 값을 반환합니다.  이 함수를 사용하여 *공백* 값을 다른 값으로 바꾸지만 *공백*이 아닌 값은 변경하지 않고 그대로 둡니다.  모든 인수가 *공백*이면 함수에서 *공백*을 반환합니다.  **Coalesce**에 대한 모든 인수는 같은 형식이어야 합니다. 예를 들어 숫자와 텍스트 문자열을 함께 사용할 수 없습니다.  **Coalesce( value1, value2 )** 는 **If( Not( IsBlank( value1 ) ), value1, value2 )** 와 동등한 간결한 구문이며, **value1**을 두 번 평가할 필요가 없습니다.  

**IsEmpty** 함수는 테이블에 레코드가 있는지 여부를 테스트합니다. **[CountRows](function-table-counts.md)** 함수를 사용하여 0을 확인하는 것과 같습니다. **IsEmpty**를 **[Errors](function-errors.md)** 함수와 결합하여 데이터 원본 오류를 확인할 수 있습니다.

**IsBlank** 및 **IsEmpty** 모두에 대한 반환 값은 **true** 또는 **false** 부울 값입니다.

## <a name="syntax"></a>구문
**Blank**()

**Coalesce**( *Value1* [, *Value2*, ... ] )

* *Value(s)* – 필수 항목이며, 테스트할 값입니다.  *공백*이 아닌 값을 찾을 때까지 각 값이 순서대로 평가됩니다.  *공백*이 아닌 값 다음의 값은 평가되지 않습니다.  

**IsBlank**( *Value* )

* *Value* – 필수 항목이며, 테스트할 값입니다.

**IsEmpty**( *Table* )

* *Table* - 필수 항목입니다. 레코드를 테스트할 테이블입니다.

## <a name="examples"></a>예
### <a name="blank"></a>비어 있음
> [!NOTE]
> 다음 예제는 현재 로컬 컬렉션에서만 작동합니다.  많은 데이터 원본에서 *공백*(NULL) 값을 지원하며, 이 제한을 제거하기 위해 노력하고 있습니다.

1. 앱을 처음부터 만들고 **단추** 컨트롤을 추가합니다.
2. 단추의 **[OnSelect](../controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.

    **ClearCollect( Cities, { Name: "Seattle", Weather: "비" } )**
3. 앱을 미리 보고, 추가한 단추를 클릭하거나 탭한 다음, 미리 보기를 닫습니다.  
4. **파일** 메뉴에서 **컬렉션**을 클릭하거나 탭합니다.

     **Cities** 컬렉션이 나타나서 "Seattle" 및 "비"가 있는 레코드 하나가 표시됩니다.

    !["비" 날씨가 있는 Seattle을 보여 주는 컬렉션](./media/function-isblank-isempty/seattle-rainy.png)
5. 기본 작업 영역으로 돌아가려면 뒤로 화살표를 클릭하거나 탭합니다.
6. **레이블** 컨트롤을 추가하고 **Text** 속성을 다음 수식으로 설정합니다.

    **IsBlank( First( Cities ).Weather )**

    **Weather** 필드에 값("비")이 있으므로 레이블에 **false**가 표시됩니다.
7. 두 번째 단추를 추가하고 **OnSelect** 속성을 다음 수식으로 설정합니다.

    **Patch( Cities, First( Cities ), { Weather: Blank() } )**
8. 앱을 미리 보고, 추가한 단추를 클릭하거나 탭한 다음, 미리 보기를 닫습니다.  

    **Cities**의 첫 번째 레코드의 **Weather** 필드는 *공백*으로 바뀌어 이전에 있었던 "비"를 제거합니다.

    ![공백인 Weather 필드가 있는 Seattle을 보여 주는 컬렉션](./media/function-isblank-isempty/seattle-blank.png)

    **Weather** 필드에 더 이상 값이 없으므로 레이블에 **true**가 표시됩니다.

### <a name="coalesce"></a>Coalesce

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **Coalesce( Blank(), 1 )** |**Blank** 함수의 반환 값을 테스트하며, 항상 *공백* 값을 반환합니다. 첫 번째 인수가 *공백*이므로 *공백*이 아닌 값을 찾을 때까지 다음 인수로 계속 평가됩니다. |**1** |
| **Coalesce( Blank(), Blank(), Blank(), Blank(), 2, 3 )** |**Coalesce**가 인수 목록의 시작 부분에서 시작하고, *공백*이 아닌 값을 찾을 때까지 각 인수를 차례로 평가합니다.  이 경우 처음 네 개의 인수에서 모두 *공백*을 반환하므로 다섯 번째 인수로 계속 평가됩니다. 다섯 번째 인수는 *공백*이 아니므로 여기서 평가를 중지합니다. 다섯 번째 인수의 값이 반환되고, 여섯 번째 인수는 평가되지 않습니다. |**2** |

### <a name="isblank"></a>IsBlank
1. 앱을 처음부터 만들고, 텍스트 입력 컨트롤을 추가하고, 이름을 **FirstName**으로 지정합니다.
2. 레이블을 추가하고 **[Text](../controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.

    **If( IsBlank( FirstName.Text ), "First Name은 필수 필드입니다." )**

    텍스트 입력 컨트롤의 **[Text](../controls/properties-core.md)** 속성은 기본적으로 **"텍스트 입력"** 으로 설정됩니다. 속성에 값이 포함되어 있으므로 공백이 아니며 레이블에 메시지가 표시되지 않습니다.
3. 텍스트 입력 컨트롤에서 모든 공백을 포함하여 모든 문자를 제거합니다.

    **[Text](../controls/properties-core.md)** 속성에 더 이상 문자가 없으므로 이 속성은 *공백*이고, **IsBlank( FirstName.Text )** 는 **true**가 됩니다. 필수 필드 메시지가 표시됩니다.

다른 도구를 사용하여 유효성 검사를 수행하는 방법에 대한 자세한 내용은 **[Validate](function-validate.md)** 함수 및 [데이터 원본 작업](../working-with-data-sources.md)을 참조하세요.  

다른 예제:

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **IsBlank( Blank() )** |**Blank** 함수의 반환 값을 테스트하며, 항상 *공백* 값을 반환합니다. |**true** |
| **IsBlank( "" )** |문자가 없는 문자열입니다. |**true** |
| **IsBlank( "Hello" )** |하나 이상의 문자가 포함된 문자열입니다. |**false** |
| **IsBlank( *AnyCollection* )** |[컬렉션](../working-with-data-sources.md#collections)이 있으므로 레코드가 없더라도 공백이 아닙니다. 빈 컬렉션을 확인하려면 **IsEmpty**를 대신 사용합니다. |**false** |
| **IsBlank( Mid( "Hello", 17, 2 ) )** |**[Mid](function-left-mid-right.md)** 에 대한 시작 문자가 문자열의 끝을 벗어납니다.  결과는 빈 문자열입니다. |**true** |
| **IsBlank( If( false, false ) )** |*ElseResult*가 없는 **[If](function-if.md)** 함수입니다.  조건이 항상 **false**이므로 이 **[If](function-if.md)** 는 항상 *공백*을 반환합니다. |**true** |

### <a name="isempty"></a>IsEmpty
1. 앱을 처음부터 만들고 **단추** 컨트롤을 추가합니다.
2. 단추의 **[OnSelect](../controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.

    **Collect( IceCream, { Flavor: "딸기", Quantity: 300 }, { Flavor: "초콜릿", Quantity: 100 } )**
3. 앱을 미리 보고, 추가한 단추를 클릭하거나 탭한 다음, 미리 보기를 닫습니다.  

    **IceCream**이라는 컬렉션이 만들어지고 다음 데이터가 포함되어 있습니다.

    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)

    이 컬렉션에는 두 개의 레코드가 있으며 비어 있지 않습니다. **IsEmpty( IceCream )** 는 **false**를 반환하고, **CountRows( IceCream )** 는 **2**를 반환합니다.
4. 두 번째 단추를 추가하고 **[OnSelect](../controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.

    **Clear( IceCream )**
5. 앱을 미리 보고, 두 번째 단추를 클릭하거나 탭한 다음, 미리 보기를 닫습니다.  

    이제 컬렉션은 다음과 같이 비어 있습니다.

    ![](media/function-isblank-isempty/icecream-clear.png)

    **[Clear](function-clear-collect-clearcollect.md)** 함수는 컬렉션에서 모든 레코드를 제거하여 빈 컬렉션을 만듭니다. **IsEmpty( IceCream )** 는 **true**를 반환하고, **CountRows( IceCream )** 는 **0**을 반환합니다.

또한 다음 예제와 같이 **IsEmpty**를 사용하여 계산된 테이블이 비어 있는지 여부를 테스트할 수 있습니다.

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1,&nbsp;2,&nbsp;3 ] )** |단일 열 테이블에는 세 개의 레코드가 있으므로 비어 있지 않습니다. |**false** |
| **IsEmpty( [&nbsp;] )** |단일 열 테이블에는 레코드가 없으며 비어 있습니다. |**true** |
| **IsEmpty( Filter( [&nbsp;1,&nbsp;2,&nbsp;3&nbsp;], Value > 5 ) )** |단일 열 테이블에는 5보다 큰 값이 없습니다.  필터의 결과에 레코드가 없으며 비어 있습니다. |**true** |

