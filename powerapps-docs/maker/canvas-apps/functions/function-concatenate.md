---
title: Concat 및 Concatenate 함수 | Microsoft Docs
description: PowerApps의 Concat 및 Concatenate 함수에 대한 구문과 예제를 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 2ead46b4b34e2013205a412eacd86197a3c3b552
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015826"
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>PowerApps의 Concat 및 Concatenate 함수
[테이블](../working-with-tables.md)에 있는 텍스트와 문자열의 개별 문자열을 연결합니다.

## <a name="description"></a>설명
**Concat** 함수는 테이블의 모든 [레코드](../working-with-tables.md#records)에 적용된 수식의 결과를 연결하여 하나의 문자열을 생성합니다. **[Sum](function-aggregates.md)** 함수가 숫자를 요약하듯 테이블의 문자열을 요약하려면 이 함수를 사용합니다.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

문자열을 하위 문자열 테이블로 분할하려면 **[Split](function-split.md)** 함수를 사용합니다.

**Concatenate** 함수는 개별 문자열과 문자열의 단일 열 테이블을 조합하여 연결합니다. 이 함수는 개별 문자열에 사용되며 **&** [연산자](operators.md)를 사용하는 것과 같습니다. **[ShowColumns](function-table-shaping.md)** 함수를 포함하는 수식을 사용하여 여러 열이 있는 테이블에서 단일 열 테이블을 만들 수 있습니다.

## <a name="syntax"></a>구문
**Concat**( *Table*, *Formula* )

* *Table* - 필수 항목입니다.  연산을 수행할 테이블입니다.
* *Formula* - 필수 항목입니다.  테이블의 레코드 전체에 적용할 수식입니다.

**Concatenate**( *String1* [, *String2*, ...] )

* *String(s)* - 필수 항목입니다.  개별 문자열 또는 문자열의 단일 열 테이블의 조합입니다.

## <a name="examples"></a>예
#### <a name="concat"></a>Concat
1. **[단추](../controls/control-button.md)** 컨트롤을 추가하고 이 수식에 **[OnSelect](../controls/properties-core.md)** 속성을 설정합니다.
   
    **Collect(Products, {String:"Violin", Wind:"Trombone", Percussion:"Bongos"}, {String:"Cello", Wind:"Trumpet", Percussion:"Tambourine"})**
2. F5 키를 누르고 단추를 클릭한 다음 Esc 키를 눌러서 디자인 작업 영역으로 돌아갑니다.
3. **[레이블](../controls/control-text-box.md)** 컨트롤을 추가하고, **[Text](../controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.
   
    **Concat(Products, String & " ")**
   
    레이블에 **Violin Cello**로 표시됩니다.

#### <a name="concatenate"></a>Concatenate
1. **[텍스트 입력](../controls/control-text-input.md)** 컨트롤을 추가하고 **AuthorName**이라고 이름을 지정합니다.
2. **[레이블](../controls/control-text-box.md)** 컨트롤을 추가하고, **[Text](../controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.<br>
   **Concatenate("By ", AuthorName.Text)**
3. **AuthorName**에 이름을 입력합니다.
   
    레이블에 **By** 다음으로 사용자 이름이 표시됩니다.

**FirstName** 열과 **LastName** 열이 포함된 **Employees** 테이블이 있는 경우, 다음 수식은 해당 열의 각 행에 있는 데이터를 연결합니다.
<br>**Concatenate(Employees.FirstName, " ", Employees.LastName)**

