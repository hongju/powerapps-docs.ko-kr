---
title: "날짜 선택기 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 날짜 선택기 컨트롤에 관한 정보"
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
ms.openlocfilehash: f2605680c7b6e8f7102fd3459230344863a93f55
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="date-picker-control-in-powerapps"></a>PowerApps의 날짜 선택기 컨트롤
사용자가 날짜를 지정하기 위해 클릭 또는 탭할 수 있는 컨트롤입니다.

## <a name="description"></a>설명
**[텍스트 입력](control-text-input.md)** 컨트롤 대신 **날짜 선택기** 컨트롤을 추가하면 사용자가 올바른 형식으로 날짜를 지정하는 데 도움이 됩니다.

## <a name="key-properties"></a>주요 속성
**DefaultDate** – 사용자가 변경하지 않을 경우 날짜 컨트롤 값의 초기 값입니다.

**SelectedDate** -날짜 컨트롤에서 현재 선택한 날짜입니다.

**Format** - 컨트롤이 날짜를 표시하고 사용자가 날짜를 지정하는 텍스트 형식입니다. 이 속성을 **ShortDate**(기본값) 또는 **LongDate**로 설정하여 이 컨트롤의 **날짜** 속성에 따라 날짜 형식을 지정할 수 있습니다. 또한, 언어와 상관없이 동일한 형식을 원하는 경우 이 속성을 표현식(예: **yyyy/mm/dd**)으로 설정할 수도 있습니다. 예:

* 이 컨트롤은 사용자가 2017의 마지막 날을 클릭하거나 누르고, **Format** 형식이 **ShortDate**로 설정되어 있고 **Language** 속성이 **en-us**로 설정되어 있는 경우 **12/31/2017**을 표시합니다.
* 이 컨트롤은 사용자가 2017의 마지막 날을 클릭하거나 누르고, **Format** 형식이 **LongDate**로 설정되어 있고 **Language** 속성이 **fr-fr**로 설정되어 있는 경우 **dimanche 31 decembre 2017**을 표시합니다.

**Language** – 월 이름을 포함하여 날짜 형식을 지정하는 데 사용하는 언어를 결정합니다. 이 속성이 지정되지 않은 경우 사용자의 장치 설정이 언어를 결정합니다.

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[FocusedBorderThickness](properties-color-border.md)** - 키보드 포커스가 있을 때 컨트롤의 테두리 두께입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(편집)하거나, 데이터만 표시(보기)하거나 사용 안 하도록(사용 안 함) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[DisabledColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 텍스트 색입니다.

**[DisabledFill](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 배경색입니다.

**EndYear** – 사용자가 날짜 선택기 컨트롤의 값을 설정할 수 있는 가장 늦은 연도입니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Font](properties-text.md)** – 텍스트가 표시되는 글꼴의 제품군 이름입니다.

**[FontWeight](properties-text.md)** - 컨트롤의 텍스트 굵기입니다. **Bold**, **Semibold**, **Normal** 또는 **Lighter**로 설정합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[Italic](properties-text.md)** - 컨트롤의 텍스트를 기울임꼴로 설정할지 여부를 선택합니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 하단 가장자리 사이의 거리입니다.

**[PaddingLeft](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 왼쪽 가장자리 사이의 거리입니다.

**[PaddingRight](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 오른쪽 가장자리 사이의 거리입니다.

**[PaddingTop](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 상단 가장자리 사이의 거리입니다.

**[Size](properties-text.md)** -컨트롤에 표시되는 텍스트의 글꼴 크기입니다.

**StartYear** – 사용자가 날짜 선택기 컨트롤의 값을 설정할 수 있는 가장 이른 연도입니다.

**[TabIndex](properties-accessibility.md)** – 0 이외의 값으로 설정된 경우 런타임 시 컨트롤의 탭 순서를 사용자 지정합니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
**[Year](../functions/function-datetime-parts.md)**( *DateTimeValue* )

## <a name="example"></a>예
1. **날짜 선택기** 컨트롤을 추가하고 이름을 **Deadline**으로 지정합니다.
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. **[Label](control-text-box.md)** 컨트롤을 추가하고 **[Text](properties-core.md)** 속성을 다음 수식으로 설정합니다.
   <br>**DateDiff(Today(), Deadline.SelectedDate) & " 남은 일수!"**
   
    **[DateDiff](../functions/function-dateadd-datediff.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
3. F5 키를 누르고 **마감일**에서 날짜를 선택한 다음, **확인**을 클릭하거나 탭합니다.
   
    **[레이블](control-text-box.md)** 컨트롤은 오늘과 사용자가 선택한 날짜 사이의 일수를 보여줍니다.
4. 기본 작업 영역으로 돌아가려면 Esc 키를 누릅니다.

