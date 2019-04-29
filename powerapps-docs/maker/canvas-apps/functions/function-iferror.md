---
title: IfError 함수 | Microsoft Docs
description: PowerApps의 IfError 함수에 대한 구문과 예제를 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/21/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1bf9f3cf075441dd3264b5a2f6533671d2e08654
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61562816"
---
# <a name="iferror-function-in-powerapps"></a>PowerApps의 IfError 함수
오류를 감지하고 대체 값을 제공하거나 작업을 수행합니다.

## <a name="description"></a>설명
> [!NOTE]
> 이 함수는 실험적 기능의 일부이며 변경될 수 있습니다.  여기에 설명된 동작은 수식 수준 오류 관리 기능이 설정되어 있는 경우에만 사용할 수 있습니다.  기본적으로 해제되어 있는 앱 수준 설정입니다.  이 기능을 켜려면 *파일* 탭으로 이동하고, 왼쪽 메뉴의 *앱 설정*으로 이동한 다음, *실험적 기능*으로 이동합니다.  여러분의 피드백은 매우 소중합니다. [PowerApps 커뮤니티 포럼](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To)에 의견을 남겨주세요.

**IfError** 함수는 오류 값을 찾기 위해 각 인수를 순서대로 테스트하여 오류가 아닌 첫 번째 값을 찾으면 중지합니다.  오류가 아닌 값 다음의 인수는 무시되고 평가되지 않습니다.

**IfError**를 사용하여 오류 값을 유효한 값으로 바꿉니다.  예를 들어, 사용자 입력으로 인해 0으로 나누기가 발생할 수 있는 경우, 다운스트림 계산을 진행할 수 있도록 앱에 적합한 0 또는 다른 유효한 값으로 바꿉니다.

[동작 수식](../working-with-formulas-in-depth.md)에 **IfError**를 사용하여 작업을 수행하고 오류에 대한 결과를 확인하여 필요한 경우 추가 작업을 수행하거나 [**Notify**](function-showerror.md)를 사용하여 사용자에게 오류 메시지를 표시합니다.

**IfError**에 대한 모든 인수에서 오류가 발생하면 마지막 인수의 값이 반환됩니다(이것이 오류 값이 됨). 

## <a name="syntax"></a>구문
**IfError**( *Value*, *Fallback1* [, *Fallback2*, ... ] )

* *Value* - 필수 항목입니다. 오류 값을 테스트할 수식입니다. 
* *Fallback(s)* - 필수 항목입니다. 이전 인수가 오류를 반환한 경우 평가할 수식과 반환할 값입니다.  *대체 (fallback)* 인수 오류가 아닌 값이 발견 되는 지점까지 순서 대로 평가 됩니다.

## <a name="examples"></a>예

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **IfError( 1, 2 )** |첫 번째 인수는 오류가 아닙니다.  반환되고 이후 인수는 평가되지 않습니다.   | 1 |
| **IfError( 1/0, 2 )** | 첫 번째 인수는(0으로 나누기로 인해) 오류 값을 반환합니다.  두 번째 인수는 평가되고 오류가 아닌 값이 반환됩니다. | 2 | 
| **IfError( 1/0, Notify( "내부 문제가 있었습니다.", NotificationType.Error ) )** | 첫 번째 인수는(0으로 나누기로 인해) 오류 값을 반환합니다.  두 번째 인수는 평가되고 사용자에게 메시지를 표시합니다.  **IfError**의 반환 값은 **Notify**의 반환 값이며 **IfError**(숫자)의 첫 번째 인수와 동일한 형식으로 강제 변환됩니다. | 1 |
| **IfError( 1/0, 1/0, 2, 1/0, 3 )** | 첫 번째 인수는(0으로 나누기로 인해) 오류 값을 반환합니다.  두 번째 인수는 평가되고 역시(또 다른 0으로 나누기로 인해) 오류 값이 발생합니다.  세 번째 인수가 평가되고 반환되는 오류 값에 반환되지 않습니다.  네 번째와 다섯 번째 인수는 무시됩니다.  | 2 |

### <a name="step-by-step"></a>단계별 가이드

1. **[텍스트 입력](../controls/control-text-input.md)** 컨트롤을 추가하고 기본 이름이 없는 경우 이름을 **TextInput1**로 지정합니다.

2. **[레이블](../controls/control-text-box.md)** 컨트롤을 추가하고 기본 이름이 없는 경우 이름을 **Label1**로 지정합니다.

3. **Label1**의 **Text** 속성에 대한 수식을 다음과 같이 설정합니다.

    **IfError( Value( TextInput1.Text ), -1 )**

4. **TextInput1**에 **1234**를 입력합니다.  

    Label1에 **1234** 값이 표시됩니다. 이것이 Value 함수에 대한 유효한 입력이기 때문입니다.

5. **TextInput1**에 **ToInfinity**를 입력합니다.

    Label1에 **-1** 값이 표시됩니다. 이것은 Value 함수에 대한 유효한 입력이 아니기 때문입니다.  IfError를 사용하여 Value 함수를 래핑하지 않으면 오류 값이 공백으로 처리되므로 레이블에 값이 표시되지 않습니다. 

