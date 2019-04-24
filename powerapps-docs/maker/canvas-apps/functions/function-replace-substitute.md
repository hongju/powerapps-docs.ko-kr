---
title: Replace 및 Substitute 함수 | Microsoft Docs
description: PowerApps의 Replace 및 Substitute 함수에 대한 구문을 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/02/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fca1953402c87ca13bc3560b827cde03a47a8e92
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551609"
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>PowerApps의 Replace 및 Substitute 함수
텍스트 문자열의 일부를 다른 문자열로 바꿉니다.

## <a name="description"></a>설명
**Replace** 함수는 시작 위치 및 길이를 통해 바꿀 텍스트를 식별합니다.  

**Substitute** 함수는 문자열을 일치시킴으로써 바꿀 텍스트를 식별합니다. 둘 이상의 일치 하는 경우에 모두 대체 수도 있고 바꾸려면 하나를 지정할 수 있습니다.

단일 문자열을 전달하는 경우 반환 값은 수정된 문자열입니다. 문자열이 포함된 단일 열 [테이블](../working-with-tables.md)을 전달하는 경우 반환 값은 수정된 문자열의 단일 열 테이블입니다. 여러 열 테이블이 있는 경우 [테이블 작업](../working-with-tables.md)에 설명된 대로 단일 열 테이블로 만들 수 있습니다.

## <a name="syntax"></a>구문
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *String* - 필수 항목이며, 연산을 수행할 문자열입니다.
* *StartingPosition* - 필수 항목입니다. 교체를 시작할 문자 위치입니다. *String*의 첫 번째 문자는 위치 1입니다.
* *NumberOfCharacters* - 필수 항목입니다. *String*에서 교체할 문자 수입니다.
* *NewString* - 필수 항목입니다. 대체 문자열입니다. 이 인수의 문자 수는 *NumberOfCharacters* 인수와 다를 수 있습니다.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *String* - 필수 항목이며, 연산을 수행할 문자열입니다.
* *OldString* - 필수 항목입니다. 교체할 문자열입니다.
* *NewString* - 필수 항목입니다. 대체 문자열입니다. *OldString* 및 *NewString*은 길이가 다를 수 있습니다.
* *InstanceNumber* -선택 사항입니다. 이 인수를 사용 하 여 인스턴스를 지정 *OldString* 경우 바꾸려면 *문자열* 둘 이상의 인스턴스를 포함 합니다. 이 인수를 지정 하지 않으면 모든 인스턴스가 바뀝니다.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* - 필수 항목입니다. 연산을 수행할 문자열의 단일 열 테이블입니다.
* *StartingPosition* - 필수 항목입니다. 교체를 시작할 문자 위치입니다.  테이블에 있는 각 문자열의 첫 번째 문자는 위치 1에 있습니다.
* *NumberOfCharacters* - 필수 항목입니다. 각 문자열에서 교체할 문자 수입니다.
* *NewString* - 필수 항목입니다.  대체 문자열입니다. 이 인수의 문자 수는 *NumberOfCharacters* 인수와 다를 수 있습니다.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* - 필수 항목입니다. 연산을 수행할 문자열의 단일 열 테이블입니다.
* *OldString* - 필수 항목입니다.  교체할 문자열입니다.
* *NewString* - 필수 항목입니다.  대체 문자열입니다. *OldString* 및 *NewString*은 길이가 다를 수 있습니다.
* *InstanceNumber* -선택 사항입니다. 이 인수를 사용 하 여 인스턴스를 지정 *OldString* 경우 바꾸려면 *문자열* 둘 이상의 인스턴스를 포함 합니다. 이 인수를 지정 하지 않으면 모든 인스턴스가 바뀝니다.

## <a name="examples"></a>예

| 수식 | 설명 | 결과 |
|---------|-------------|--------|
| **Replace( "abcdefghijk",&nbsp;6,&nbsp;5,&nbsp;"*" )** | 단일 "abcdefghijk"에서 다섯 개의 문자를 대체 "*" 문자, 여섯 번째 문자 ("f")를 사용 하 여 시작 합니다. | "abcde*k" |
| **Replace(&nbsp;"2019",&nbsp;3,&nbsp;2,&nbsp;"20"&nbsp;)** | "20"을 사용 하 여 "2019"의 마지막 두 문자를 바꿉니다. | "2020" |
| **Replace(&nbsp;"123456",&nbsp;1,&nbsp;3,&nbsp;"_"&nbsp;)** | 단일 "_" 문자를 사용 하 여 "123456"의 처음 세 문자를 바꿉니다. | "_456" | 
| **대체 (&nbsp;"매출&nbsp;데이터"를&nbsp;"Sales"&nbsp;"비용"&nbsp;)** | "Sales"에 대 한 "비용" 문자열을 대체합니다. | "비용 데이터" | 
| **Substitute( "Quarter&nbsp;1,&nbsp;2018", "1", "2", 1 )** | 때문에 "2" 인 "1"의 첫 번째 인스턴스만 대체 네 번째 인수 (*InstanceNumber*) 1을 사용 하 여 제공 됩니다. |  "Quarter 2, 2018" |
| **Substitute( "Quarter&nbsp;1,&nbsp;2011", "1", "2", 3 )** | 때문에 "2" 인 "1"의 세 번째 인스턴스만 대체 네 번째 인수 (*InstanceNumber*)는 3을 사용 하 여 제공 됩니다. | "Quarter 1, 2012" |
| **Substitute( "Quarter&nbsp;1,&nbsp;2011", "1", "2" )** | 때문에 "2" 인 "1"의 모든 인스턴스를 대체 네 번째 인수 (*InstanceNumber*) 제공 되지 않았습니다. | "Quarter 2, 2022" |
| **Replace(<br>[&nbsp;"Quarter&nbsp;1,&nbsp;2018",<br>"Quarter&nbsp;2,&nbsp;2011",<br>"Quarter&nbsp;4,&nbsp;2019" ],<br>9,  1, "3" )** | "3"을 사용 하 여 단일 열 테이블의 각 레코드의 아홉 번째 문자를 바꿉니다. | [&nbsp;"Quarter&nbsp;3,&nbsp;2018",<br>"Quarter&nbsp;3,&nbsp;2011",<br>"Quarter&nbsp;3,&nbsp;2019"&nbsp;] |
| **Substitute( <br>[&nbsp;"Qtr&nbsp;1,&nbsp;2018",<br>"Quarter&nbsp;1,&nbsp;2011",<br>"Q1,&nbsp;2019"&nbsp;],<br>"1", "3", 1 )** | 때문에 네 번째 인수 (*InstanceNumber*)에서 제공 됩니다 1의 값을 사용 하 여 "1"의 첫 번째 인스턴스만 대체 "3"을 사용 하 여 단일 열 테이블의 각 레코드입니다. | [&nbsp;"Qtr&nbsp;3,&nbsp;2018",<br>"Quarter&nbsp;3,&nbsp;2011",<br>"Q3,&nbsp;2019"&nbsp;] |
| **Substitute( <br>[&nbsp;"Qtr&nbsp;1,&nbsp;2018",<br>"Quarter&nbsp;1,&nbsp;2011",<br>"Q1,&nbsp;2019"&nbsp;],<br>"1", "3" )** | 때문에 네 번째 인수 (*InstanceNumber*) 제공 되지 않는, "1"에서 "3"을 사용 하 여 단일 열 테이블의 각 레코드의 모든 인스턴스를 대체 합니다. | [&nbsp;"Qtr&nbsp;3,&nbsp;2038",<br>"분기&nbsp;3&nbsp;2033",<br>"Q3,&nbsp;2039"&nbsp;] |  
 


