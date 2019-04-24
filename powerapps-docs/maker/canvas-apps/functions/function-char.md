---
title: Char 함수 | Microsoft Docs
description: PowerApps의 Char 함수에 대한 참조 정보이며, 구문과 예제를 포함하고 있습니다.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1b598cc863ec01bcb2a66a9510cb48ec5203e679
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559710"
---
# <a name="char-function-in-powerapps"></a>PowerApps의 Char 함수

문자 코드를 문자열로 변환합니다.

## <a name="description"></a>설명

합니다 **Char** 함수 해당 ASCII 문자로 문자열을 숫자로 변환 합니다.

## <a name="syntax"></a>구문

**Char**( *CharacterCode* )

- *CharacterCode* - 필수 항목이며, 변환할 ASCII 문자 코드입니다.

## <a name="examples"></a>예

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **Char( 65 )** |ASCII 코드 65에 해당하는 문자를 반환합니다. |"A" |
| **Char( 105 )** |ASCII 코드 105에 해당하는 문자를 반환합니다. |"i" |
| **Char( 35 )** |ASCII 코드 35에 해당하는 문자를 반환합니다. |"#" |

### <a name="display-a-character-map"></a>문자 매핑 표시

1. 태블릿 앱에서 사용 되는 빈 화면에서 추가 [ **갤러리** ](../controls/control-gallery.md) 컨트롤을 **빈 가로** 레이아웃, 이러한 속성을 설정한 후:

    - **항목**: `[0,1,2,3,4,5,6,7]`
    - **Width**: 800
    - **높이**: 500
    - **TemplateSize**: 100
    - **TemplatePadding**: 0

1. 해당 갤러리 내에서 추가 **갤러리** 컨트롤을 **빈 세로** 레이아웃, 이러한 속성을 설정한 후:

    - **항목**: `ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 )`
    - **Width**: 100
    - **높이**: 500
    - **TemplateSize**: 30
    - **TemplatePadding**: 0

    값을 **항목** 속성의 값 열을 제공한 열 수는 16을 곱합니다 합니다 **항목** 갤러리의 첫 번째 속성 (0-7에서 `ThisItem.Value`). 수식에 추가한 결과 행 번호 중 하나에 갤러리의 두 번째 (0 ~ 15 개 레코드의 범위를 합니다 [ **ForAll** ](function-forall.md) 함수는 제공).

1. 두 번째 (세로) 갤러리 내에서 추가 **레이블** 이러한 속성을 설정 합니다.

    - **텍스트**: `ThisItem.Value`
    - **Width**: 50

1. 두 번째 (세로) 갤러리 내에서 다른 항목 추가 **레이블** 이러한 속성을 설정 합니다.

    - **텍스트**: `Char( ThisItem.Value )`
    - **Width**: 50
    - **X**: 50

차트의 처음 128 개 ASCII 문자를 만들었습니다. 작은 사각형을 인쇄할 수 없는 것으로 표시 하는 문자입니다.

![먼저 128 개의 ASCII 문자](media/function-char/chart-lower.png)

확장 된 ASCII 문자를 표시 하려면 설정 합니다 **항목** 128 각 문자 값을 추가 하는 다음이 수식으로 두 번째 갤러리의 속성:

`ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 + 128)`

![확장 된 ASCII 문자](media/function-char/chart-higher.png)

다른 글꼴에서 문자를 표시 하려면 설정 합니다 **글꼴** 와 같은 값으로 두 번째 레이블의 속성 **Dancing 스크립트**합니다.

![스크립트 dancing](media/function-char/chart-higher-dancing-script.png)
