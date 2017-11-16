---
title: "Now, Today 및 IsToday 함수 | Microsoft Docs"
description: "PowerApps의 Now, Today 및 IsToday 함수에 대한 참조 정보이며, 구문과 예제를 포함하고 있습니다."
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
ms.openlocfilehash: 483922d2c96c23d1d2672aed7e284e30d38f298a
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>PowerApps의 Now, Today 및 IsToday 함수
현재 날짜와 시간을 반환하고, 날짜/시간 값이 오늘인지 테스트합니다.

## <a name="description"></a>설명
**Now** 함수는 현재 날짜와 시간을 날짜/시간 값으로 반환합니다.

**Today** 함수는 현재 날짜를 날짜/시간 값으로 반환합니다. 시간 부분은 자정입니다. **Today**는 오늘 자정부터 내일 자정까지의 하루 동안에 동일한 값을 갖습니다.

**IsToday** 함수는 날짜/시간 값이 오늘 자정과 내일 자정 사이에 속하는지 여부를 테스트합니다. 이 함수는 **true** 또는 **false** 부울 값을 반환합니다.

이러한 함수는 모두 현재 사용자의 현지 시간으로 작동합니다.

자세한 내용은 [날짜 및 시간 작업](../show-text-dates-times.md)을 참조하세요.

## <a name="syntax"></a>구문
**Now**()

**Today**()

**IsToday**( *DateTime* )

* *DateTime* - 필수 항목이며,  테스트할 날짜/시간 값입니다.

## <a name="examples"></a>예
이 섹션의 예제에서 현재 시간은 **2015년 2월 12일** **오전 3시 59분**이며, 언어는 **ko-kr**입니다.

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **Text( Now(), "mm/dd/yyyy hh:mm:ss" )** |현재 날짜와 시간을 검색하여 문자열로 표시합니다. |"02/12/2015 03:59:00" |
| **Text( Today(), "mm/dd/yyyy hh:mm:ss" )** |시간 부분은 자정으로 유지한 채 현재 날짜만 검색하여 문자열로 표시합니다. |"02/12/2015 00:00:00" |
| **IsToday( Now() )** |현재 날짜와 시간이 오늘 자정과 내일 자정 사이에 속하는지 여부를 테스트합니다. |**true** |
| **IsToday( Today() )** |현재 날짜가 오늘 자정과 내일 자정 사이에 속하는지 여부를 테스트합니다. |**true** |
| **Text( DateAdd( Now(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |현재 날짜와 시간을 검색하고, 결과에 12일을 추가하여 이를 문자열로 표시합니다. |"02/24/2015 03:59:00" |
| **Text( DateAdd( Today(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |현재 날짜를 검색하고, 결과에 12일을 추가하여 이를 문자열로 표시합니다. |"02/24/2015 00:00:00" |
| **IsToday( DateAdd( Now(), 12 ) )** |현재 날짜와 시간에 12일을 추가한 값이 오늘 자정과 내일 자정 사이에 속하는지 여부를 테스트합니다. |**false** |
| **IsToday( DateAdd( Today(), 12 ) )** |현재 날짜에 12일을 추가한 값이 오늘 자정과 내일 자정 사이에 속하는지 여부를 테스트합니다. |**false** |

