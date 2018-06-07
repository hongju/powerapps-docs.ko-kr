---
title: Split 함수 | Microsoft Docs
description: PowerApps에서 Split 함수에 대한 구문과 예제를 포함한 참조 정보
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 3cb894d044a1e6ac02234bc1fa4c5b9239959015
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31830673"
---
# <a name="split-function-in-powerapps"></a>PowerApps의 Split 함수
텍스트 문자열을 하위 문자열의 테이블로 분할합니다.

## <a name="description"></a>설명
**Split** 함수는 텍스트 문자열을 하위 문자열의 테이블로 분할합니다.  **Split**을 사용하여 날짜 부분 사이에 슬래시를 사용하고 다른 경우에 잘 정의된 구분 기호가 사용되는 쉼표 구분 기호로 분리된 목록, 날짜를 분할합니다.  

텍스트 문자열을 분리하는 데 구분 기호 문자열이 사용됩니다.  구분 기호는 텍스트 문자열에서 전체로 일치되는 0개, 1개 또는 더 많은 문자일 수 있습니다.  0 길이 또는 *공백* 문자열을 사용하면 각 문자열은 개별적으로 분리됩니다.  일치하는 구분 기호 문자는 결과에 반환되지 않습니다.  일치하는 구분 기호가 없으면 전체 텍스트 문자열은 단일 결과로 반환됩니다.

**[Concat](function-concatenate.md)** 함수를 사용하여 문자열을 다시 결합합니다(구분 기호 없이).  

## <a name="syntax"></a>구문
**Split**( *Text*, *Separator* )

* *Text* - 필수 항목입니다.  분할할 텍스트입니다.
* *Separator* - 필수 항목입니다.  문자열 분할에 사용할 구분 기호입니다.  0개, 1개 또는 더 많은 문자가 될 수 있습니다.

## <a name="examples"></a>예
| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," )** |쉼표 구분 기호에 따라 다른 과일을 분할합니다.  뒤의 공백이 아닌 쉼표에 따라 분할이 수행됩니다. "&nbsp;Oranges" 및 "&nbsp;Bananas"의 앞에 공백이 생깁니다. |<style> img { max-width: none; } </style> ![](media/function-split/fruit1.png) |
| **TrimEnds( Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," ) )** |이전 예제와 동일하지만 이 경우 공백은 [**TrimEnds**](function-trim.md) 함수에 의해 제거됩니다. **Split**으로 생성되는 단일 열 테이블에서 작동합니다. 쉼표 뒤에 공백을 포함하는 **",&nbsp;"** 구분 기호를 사용할 수 있었지만 공백이 없거나 두 개의 공백이 있는 경우 제대로 작동하지 않았습니다. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| **Split( "08/28/17", "/" )** |구분 기호로 슬래시를 사용하여 날짜를 분할합니다. |<style> img { max-width: none; } </style> ![](media/function-split/date.png) |
| **Split( "Hello,&nbsp;World", "," )** |구분 기호로 쉼표를 사용하여 단어를 분할합니다.  두 번째 결과는 쉼표 바로 뒤의 문자였으므로 공백으로 시작합니다. |<style> img { max-width: none; } </style> ![](media/function-split/comma.png) |
| **Split( "Hello,&nbsp;World", "o" )** |구분 기호로 "o" 문자를 사용하여 문자열을 분할합니다. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| **Split( "Hello,&nbsp;World", "l" )** |구분 기호로 "l" 단일 문자를 사용하여 문자열을 분할합니다. **Hello**에서 두 개의 **l** 사이에 문자가 없었으므로 *공백* 값이 반환되었습니다. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| **Split( "Hello,&nbsp;World", "ll" )** |구분 기호로 "ll" 이중 문자를 사용하여 문자열을 분할합니다. |<style> img { max-width: none; } </style> ![](media/function-split/ll.png) |
| **Split( "Hello,&nbsp;World", "%" )** |구분 기호로 백분율 기호를 사용하여 문자열을 분할합니다. 이 구분 기호는 문자열에 표시되지 않으므로 전체 문자열은 하나의 결과로 반환됩니다. |<style> img { max-width: none; } </style> ![](media/function-split/percent.png) |
| **Split( "Hello,&nbsp;World", "" )** |구문 기호로 빈 문자열을 사용하여(0개의 문자) 문자열을 분할합니다. 각 문자에서 문자열을 분할합니다. |<style> img { max-width: none; } </style> ![](media/function-split/none.png) |

