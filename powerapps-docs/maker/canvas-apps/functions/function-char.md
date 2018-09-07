---
title: Char 함수 | Microsoft Docs
description: PowerApps의 Char 함수에 대한 참조 정보이며, 구문과 예제를 포함하고 있습니다.
dauthor: gregli-msft
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
ms.openlocfilehash: aec27b788fff8434cfdc4e0e130487f718a42aa6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42826368"
---
# <a name="char-function-in-powerapps"></a>PowerApps의 Char 함수
문자 코드를 문자열로 변환합니다.

## <a name="description"></a>설명
**Char** 함수는 플랫폼에 적합한 ASCII 문자가 포함된 문자열을 반환합니다.

## <a name="syntax"></a>구문
**Char**( *CharacterCode* )

* *CharacterCode* - 필수 항목이며, 변환할 ASCII 문자 코드입니다.

## <a name="examples"></a>예

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **Char( 65 )** |ASCII 코드 65에 해당하는 문자를 반환합니다. |A |
| **Char( 105 )** |ASCII 코드 105에 해당하는 문자를 반환합니다. |i |
| **Char( 35 )** |ASCII 코드 35에 해당하는 문자를 반환합니다. |# |

