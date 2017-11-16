---
title: "타이머 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 타이머 컨트롤에 관한 정보"
services: 
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: c84eec1bdd541429d4524640d9e1ffa649b895fd
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="timer-control-in-powerapps"></a>PowerApps의 타이머 컨트롤
일정 시간이 지난 후 앱이 응답하는 방식을 결정할 수 있는 컨트롤입니다.

## <a name="description"></a>설명
타이머는 일정 시간이 지난 후 컨트롤이 표시되는 시간이나 컨트롤의 다른 속성 변경 등을 결정할 수 있습니다.

타이머가 디자이너에서 실행되려면 앱을 미리 보아야 합니다.  이렇게 하면 사용자가 시간 제한 없이 디자이너에서 타이머를 구성할 수 있습니다.

## <a name="key-properties"></a>주요 속성
**Duration** – 타이머가 실행되는 기간입니다.

**OnTimerEnd** - 타이머 실행이 완료될 때 앱이 응답하는 방식입니다.

**Repeat** – 타이머 실행 완료 후 자동으로 다시 시작할지 여부입니다.

## <a name="additional-properties"></a>추가 속성
**[Align](properties-text.md)** - 컨트롤의 가로 가운데를 기준으로 한 텍스트의 위치입니다.

**AutoPause** – 사용자가 다른 화면으로 이동할 경우 오디오 또는 동영상 클립을 자동으로 일시 중지할지 여부를 선택합니다.

**자동 시작** - 사용자가 해당 컨트롤이 있는 화면으로 이동할 때 오디오 또는 동영상 컨트롤이 클립 재생을 자동으로 시작할지 여부를 선택합니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[DisabledColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 텍스트 색입니다.

**[DisabledFill](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 배경색입니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Font](properties-text.md)** – 텍스트가 표시되는 글꼴의 제품군 이름입니다.

**[FontWeight](properties-text.md)** - 컨트롤의 텍스트 굵기입니다. **Bold**, **Semibold**, **Normal** 또는 **Lighter**로 설정합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**[HoverColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 텍스트 색입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**[Italic](properties-text.md)** - 컨트롤의 텍스트를 기울임꼴로 설정할지 여부를 선택합니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**OnTimerStart** - 타이머가 실행을 시작했을 때 앱이 응답하는 방식입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[PressedColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 텍스트 색입니다.

**[PressedFill](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 배경색입니다.

**[Reset](properties-core.md)** – 컨트롤을 기본값으로 되돌릴지 여부를 선택합니다.

**[Size](properties-text.md)** -컨트롤에 표시되는 텍스트의 글꼴 크기입니다.

**Start** – 오디오 또는 동영상 클립의 재생 여부를 선택합니다.

**[Strikethrough](properties-text.md)** - 컨트롤에 표시되는 텍스트 중앙에 선을 표시할지 여부를 선택합니다.

**[Text](properties-core.md)** – 컨트롤에 표시되는 텍스트 또는 사용자가 컨트롤에 입력하는 텍스트입니다.

**[Tooltip](properties-core.md)** – 사용자가 컨트롤을 마우스로 가리킬 때 나타나는 설명 텍스트입니다.

**[Underline](properties-text.md)** – 컨트롤에 표시되는 텍스트 아래에 선을 표시할지 여부를 선택합니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**Refresh**( *DataSource* )](../functions/function-refresh.md)

## <a name="examples"></a>예
### <a name="show-a-countdown"></a>카운트다운 표시
1. 타이머를 추가하고 이름을 **Countdown**으로 지정합니다.
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. 타이머의 **Duration** 속성을 **10000**, **Repeat** 및 **Autostart** 속성을 **true**로 설정합니다.
3. (선택 사항) 타이머를 더 판독하기 쉽게 **[Height](properties-size-location.md)** 속성을 **160**, **[Width](properties-size-location.md)** 속성을 **600**, **[Size](properties-text.md)** 속성을 **60**으로 설정합니다.
4. 레이블을 추가하고 **[Text](properties-core.md)** 속성을 다음 수식으로 설정합니다.
   <br>**"Number of seconds remaining: " & RoundUp(10-Countdown.Value/1000, 0)**
   
    **[RoundUp](../functions/function-round.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
   
    레이블은 타이머를 다시 시작하기 전까지 남은 시간(초)을 표시합니다.
5. (선택 사항) 타이머의 **[Visible](properties-core.md)** 속성을 **false**로 설정합니다.

### <a name="animate-a-control"></a>컨트롤 애니메이션
1. 타이머를 추가하고 이름을 **FadeIn**으로 지정합니다.
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. 타이머의 **Duration** 속성을 **5000**, **Repeat** 및 **Autostart** 속성을 **true**로 설정합니다.
3. (선택 사항) 타이머를 더 판독하기 쉽게 **[Height](properties-size-location.md)** 속성을 **160**, **[Width](properties-size-location.md)** 속성을 **600**, **[Size](properties-text.md)** 속성을 **60**으로 설정합니다.
4. 레이블을 추가하고 **[Text](properties-core.md)** 속성을 **Welcome!**을 표시하도록 설정하며 **[Color](properties-color-border.md)** 속성을 다음 수식으로 설정합니다.
   <br>**ColorFade(Color.BlueViolet, FadeIn.Value/5000)**
   
    **[ColorFade](../functions/function-colors.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
   
    레이블의 텍스트가 흰색으로 흐려지며 전체 강도로 돌아가는 프로세스를 반복합니다.
5. (선택 사항) 타이머의 **[Visible](properties-core.md)** 속성을 **false**로 설정합니다.

