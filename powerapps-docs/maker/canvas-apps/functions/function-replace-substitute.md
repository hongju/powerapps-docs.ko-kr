---
title: "Replace 및 Substitute 함수 | Microsoft Docs"
description: "PowerApps의 Replace 및 Substitute 함수에 대한 구문을 포함한 참조 정보"
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
ms.openlocfilehash: fe8f1e1cc8e54c3abf4b44bbfe46d9f96a7adfe7
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>PowerApps의 Replace 및 Substitute 함수
텍스트 문자열의 일부를 다른 문자열로 바꿉니다.

## <a name="description"></a>설명
**Replace** 함수는 시작 위치 및 길이를 통해 바꿀 텍스트를 식별합니다.  

**Substitute** 함수는 문자열을 일치시킴으로써 바꿀 텍스트를 식별합니다.  둘 이상이 일치하는 경우 어떤 항목을 바꿀지 제어할 수 있습니다.

단일 문자열을 전달하는 경우 반환 값은 수정된 문자열입니다.  문자열이 포함된 단일 열 [테이블](../working-with-tables.md)을 전달하는 경우 반환 값은 수정된 문자열의 단일 열 테이블입니다. 여러 열 테이블이 있는 경우 [테이블 작업](../working-with-tables.md)에 설명된 대로 단일 열 테이블로 만들 수 있습니다.

## <a name="syntax"></a>구문
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *String* - 필수 항목이며, 연산을 수행할 문자열입니다.
* *StartingPosition* - 필수 항목입니다.  교체를 시작할 문자 위치입니다. *String*의 첫 번째 문자는 위치 1입니다.
* *NumberOfCharacters* - 필수 항목입니다.  *String*에서 교체할 문자 수입니다.
* *NewString* - 필수 항목입니다.  대체 문자열입니다. 이 인수의 문자 수는 *NumberOfCharacters* 인수와 다를 수 있습니다.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *String* - 필수 항목이며, 연산을 수행할 문자열입니다.
* *OldString* - 필수 항목입니다.  교체할 문자열입니다.
* *NewString* - 필수 항목입니다.  대체 문자열입니다. *OldString* 및 *NewString*은 길이가 다를 수 있습니다.
* *InstanceNumber* -선택 사항입니다. 기본적으로 *OldString*의 첫 번째 인스턴스가 대체됩니다. *String*에 둘 이상의 인스턴스가 포함되어 있는 경우 교체할 인스턴스를 지정할 수 있습니다.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* - 필수 항목입니다. 연산을 수행할 문자열의 단일 열 테이블입니다.
* *StartingPosition* - 필수 항목입니다.  교체를 시작할 문자 위치입니다.  테이블에 있는 각 문자열의 첫 번째 문자는 위치 1에 있습니다.
* *NumberOfCharacters* - 필수 항목입니다.  각 문자열에서 교체할 문자 수입니다.
* *NewString* - 필수 항목입니다.  대체 문자열입니다. 이 인수의 문자 수는 *NumberOfCharacters* 인수와 다를 수 있습니다.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* - 필수 항목입니다. 연산을 수행할 문자열의 단일 열 테이블입니다.
* *OldString* - 필수 항목입니다.  교체할 문자열입니다.
* *NewString* - 필수 항목입니다.  대체 문자열입니다. *OldString* 및 *NewString*은 길이가 다를 수 있습니다.
* *InstanceNumber* -선택 사항입니다. 기본적으로 *OldString*의 첫 번째 인스턴스가 대체됩니다. 테이블에 둘 이상의 인스턴스가 포함되어 있는 경우 교체할 인스턴스를 지정할 수 있습니다.

