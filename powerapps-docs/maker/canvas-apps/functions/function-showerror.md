---
title: ShowError 함수 | Microsoft Docs
description: PowerApps의 ShowError 함수에 대한 구문과 예제를 포함한 참조 정보
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 1191016f26192f997b8347cdbfecc7701c19cb8c
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="showerror-function-in-powerapps"></a>PowerApps의 ShowError 함수
사용자에게 오류를 표시합니다.

## <a name="description"></a>설명
**ShowError** 함수는 사용자에게 오류를 표시합니다.  앱을 제작할 때와 최종 사용자가 앱을 사용할 때 모두 메시지가 표시됩니다.

**ShowError**는 [동작 수식](../working-with-formulas-in-depth.md)에만 사용할 수 있습니다.

**ShowError**는 항상 *true*를 반환합니다.

**ShowError**는 [**IfError**](function-iferror.md) 함수와 쌍을 이루어 오류를 감지하고 사용자 지정 오류 메시지를 사용하여 오류를 보고할 수 있습니다.

## <a name="syntax"></a>구문
**ShowError**( *Message* )

* *Message* - 필수입니다.  사용자에게 표시할 메시지입니다. 

## <a name="examples"></a>예

### <a name="step-by-step"></a>단계별 가이드

1. **단추** 컨트롤을 화면에 추가합니다.

2. **단추**의 **OnSelect** 속성을 다음과 같이 설정합니다.

    **ShowError( "Hello, World" )**

3. 단추를 클릭하거나 누릅니다.  

    단추를 클릭할 때마다 **Hello, World**라는 메시지가 사용자에게 표시됩니다.

    ![제작 환경에 ShowError를 호출하는 Button.OnSelect가 표시되고 그에 따른 Hello, World 메시지가 사용자에게 빨간색 배너 메시지로 표시됩니다.](media/function-showerror/hello-world.png)
