---
title: Shuffle 함수 | Microsoft Docs
description: PowerApps의 Shuffle 함수에 대한 구문과 예제를 포함한 참조 정보
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 6d981c410b22dd9db52cdf077a00e6eaae83be75
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827370"
---
# <a name="shuffle-function-in-powerapps"></a>PowerApps의 Shuffle 함수
[테이블](../working-with-tables.md)의 [레코드](../working-with-tables.md#records)를 무작위로 다시 정렬합니다.

## <a name="description"></a>설명
**Shuffle** 함수는 테이블의 레코드 다시 정렬합니다.

**Shuffle**은 인수와 동일한 [열](../working-with-tables.md#columns) 및 동일한 수의 행을 갖는 테이블을 반환합니다.

## <a name="syntax"></a>구문
**Shuffle**( *Table* )

* *Table* - 필수 항목입니다.  순서를 섞을 테이블입니다.

## <a name="example"></a>예
카드 놀이에 대한 세부 정보를 **Deck**라는 [컬렉션](../working-with-data-sources.md#collections)에 저장한 경우, 아래 수식은 무작위로 섞은 컬렉션의 복사본을 반환합니다.

**Shuffle(Deck)**

