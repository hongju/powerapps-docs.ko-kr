---
title: HashTags 함수 | Microsoft Docs
description: PowerApps HashTags 함수에 대한 구문과 예제를 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 66fad5a1afd9086bf07da88a93ac68b756dfb3d6
ms.sourcegitcommit: 521a7b8e6ae72a211045b54d153a8a8c8f59172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40021321"
---
# <a name="hashtags-function-in-powerapps"></a>PowerApps의 HashTags 함수
텍스트 문자열에서 해시태그(#strings)를 추출합니다.

## <a name="description"></a>설명
**HashTags** 함수는 문자열에서 해시태그를 검색합니다. 해시태그는 파운드 문자(#)로 시작하며 뒤에는 다음과 같은 항목의 조합이 옵니다.

* 대문자와 소문자
* 숫자
* 밑줄
* 통화 기호(예: $)

**HashTags**는 문자열에 해시태그가 포함된 단일 열 [테이블](../working-with-tables.md)을 반환합니다.  문자열에 해시태그가 없으면 이 함수는 [빈](function-isblank-isempty.md) 단일 열 테이블을 반환합니다.

## <a name="syntax"></a>구문
**HashTags**( *String* )

* *String* - 필수 항목이며,  해시태그를 검색할 문자열입니다.

## <a name="examples"></a>예
### <a name="step-by-step"></a>단계별 가이드
1. **[Text input](../controls/control-text-input.md)** 컨트롤을 추가하고 **Tweet**이라고 이름을 지정하고 다음 문장을 입력합니다.
   
    **This #app is #AMAZING and can #coUnt123 or #123abc but not #1-23 or #$\*(#\@")**
2. 세로 사용자 지정 갤러리를 추가하고 **[Items](../controls/properties-core.md)** 속성을 다음 함수로 설정합니다.
   
    **HashTags(Tweet.Text)**
3. 갤러리 템플릿에 **[Label](../controls/control-text-box.md)** 컨트롤을 추가합니다.
   
    갤러리에 다음 해시태그가 표시됩니다.
   
   * **\#app**
   * **\#AMAZING**
   * **\#coUnt123**
   * **\#123abc**
   * **\#1**

