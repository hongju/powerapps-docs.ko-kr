---
title: Distinct 함수 | Microsoft Docs
description: PowerApps의 Distinct 함수에 대한 구문과 예제를 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 17a2f2cfca16c5589f74ac434b36326037146b16
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551218"
---
# <a name="distinct-function-in-powerapps"></a>PowerApps의 Distinct 함수
[테이블](../working-with-tables.md)의 [레코드](../working-with-tables.md#records)를 요약하여 중복을 제거합니다.

## <a name="description"></a>설명
**Distinct** 함수는 테이블의 각 레코드에서 수식을 계산합니다. **Distinct**는 중복 값이 제거된 결과를 포함하는 단일 열 테이블을 반환합니다.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

## <a name="syntax"></a>구문
**Distinct**( *Table*, *Formula* )

* *Table* - 필수 항목입니다.  계산 대상 테이블입니다.
* *Formula* - 필수 항목입니다.  각 레코드에 대해 계산할 수식입니다.

## <a name="example"></a>예
**Department** 열이 포함된 **Employees** 테이블이 있는 경우, 이 함수는 각 열에 이름이 나타나는 횟수와 상관없이 열에 있는 고유한 부서 이름을 나열합니다.

**Distinct(Employees, Department)**

