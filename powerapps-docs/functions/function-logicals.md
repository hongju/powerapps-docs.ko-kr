---
title: "And, Or, Not 함수 | Microsoft Docs"
description: "PowerApps의 And, Or, Not 함수에 대한 구문과 예제를 포함한 참조 정보"
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
ms.openlocfilehash: ff908d29efa02a3ebed2b2fa5517da35322518b8
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="and-or-and-not-functions-in-powerapps"></a>PowerApps의 And, Or, Not 함수
일반적으로 비교 및 테스트 결과를 조작하는 데 사용되는 부울 논리 함수입니다.

## <a name="description"></a>설명
**And** 함수는 모든 인수가 **true**인 경우 **true**를 반환합니다.  **&&** [연산자](operators.md)가 **And**와 동일합니다.

**Or** 함수는 인수 중 **true**인 항목이 있으면 **true**를 반환합니다.  **||** 연산자가 **Or**과 동일합니다.

**Not** 함수는 인수가 **false**이면 **true**를 반환하고 인수가 **true**이면 **false**를 반환합니다.  **!** 연산자가 **Not**과 동일합니다.

이러한 함수는 논리 값에 작동합니다. 숫자 또는 문자열로 직접 전달할 수 없고 대신 비교 또는 테스트를 수행해야 합니다. 예를 들어 **x > 1**과 같은 비교는 **x** 가 **1**보다 크면 부울 값 **true**로 계산되는 논리식입니다. **x**가 **1**보다 작으면 수식은 **false**로 계산됩니다.

## <a name="syntax"></a>구문
**And**( *LogicalFormula1*, *LogicalFormula2* [, *LogicalFormula3*, ... ] )<br>
**Or**( *LogicalFormula1*, *LogicalFormula2* [, *LogicalFormula3*, ... ] )<br>
**Not**( *LogicalFormula* )

* *LogicalFormula(s)* - 필수 항목입니다.  계산 및 연산의 대상이 되는 논리식입니다.

## <a name="examples"></a>예
### <a name="step-by-step"></a>단계별 가이드
다음 함수를 사용하여 슬라이더의 값이 50에서 100 범위를 벗어나는지 확인합니다.

**Or(Slider1.Value < 50, Slider1.Value> 100)**

[테이블](../working-with-tables.md)에 **Dept** [열](../working-with-tables.md#columns)과 **Salary** 열이 포함된 경우 **Result** 열에 다음 함수를 사용하여 **Dept** 열의 값이 **HR**이거나 **Salary** 열의 값이 **200000**보다 큰 모든 행에 **true**를 표시할 수 있습니다.

**Or(Dept = HR, Salary >= 200000)**

또는, 이전 수식이 반환한 것과 동일한 결과를 얻으려면 || 연산자를 사용합니다.

**Slider1.Value < 50 || Slider1.Value> 100**

**Dept = "HR" || Salary > 200000**

