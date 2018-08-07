---
title: '드롭다운 컨트롤: 참조 | Microsoft Docs'
description: 속성 및 예제를 포함한 드롭다운 컨트롤에 관한 정보
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 9b26af9a2a1fb9b187023ec3ccc9cd86580aa4cf
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39017919"
---
# <a name="drop-down-control-in-powerapps"></a>PowerApps의 드롭다운 컨트롤
사용자가 열지 않는 한 첫 번째 항목만 표시하는 목록입니다.

## <a name="description"></a>설명
**드롭다운** 컨트롤은 특히 목록에 선택항목이 많은 경우 화면 사용 공간을 절약합니다. 이 컨트롤은 사용자가 펼침 단추를 선택하여 다른 선택을 표시하지 않으면 한 줄만 취합니다.

## <a name="key-properties"></a>주요 속성
**[Default](properties-core.md)** – 사용자가 컨트롤을 변경하기 전의 초기 값입니다.

**[Items](properties-core.md)** – 갤러리, 목록 또는 차트와 같은 컨트롤에 표시되는 데이터 원본입니다.

[!INCLUDE [long-items](../../../includes/long-items.md)]

**Selected** – 선택한 항목입니다.

## <a name="additional-properties"></a>추가 속성
**[AccessibleLabel](properties-accessibility.md)** – 화면 읽기 프로그램의 레이블입니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**ChevronBackground** – 드롭다운 목록에서 아래쪽 화살표의 배경색입니다.

**ChevronFill** – 드롭다운 목록에서 아래쪽 화살표의 색입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[DisabledColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 텍스트 색입니다.

**[DisabledFill](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 배경색입니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[FocusedBorderColor](properties-color-border.md)** – 컨트롤에 포커스가 있을 때 컨트롤의 테두리 색입니다.

**[FocusedBorderThickness](properties-color-border.md)** – 컨트롤에 포커스가 있을 때 컨트롤의 테두리 두께입니다.

**[Font](properties-text.md)** – 텍스트가 표시되는 글꼴의 제품군 이름입니다.

**[FontWeight](properties-text.md)** - 컨트롤의 텍스트 굵기입니다. **Bold**, **Semibold**, **Normal** 또는 **Lighter**로 설정합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**[HoverColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 텍스트 색입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**[Italic](properties-text.md)** - 컨트롤의 텍스트를 기울임꼴로 설정할지 여부를 선택합니다.

**[OnChange](properties-core.md)** – 사용자가 컨트롤의 값을 변경할 때(예: 슬라이더 조절) 앱이 응답하는 방식입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 아래쪽 가장자리 사이의 거리입니다.

**[PaddingLeft](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 왼쪽 가장자리 사이의 거리입니다.

**[PaddingRight](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 오른쪽 가장자리 사이의 거리입니다.

**[PaddingTop](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 위쪽 가장자리 사이의 거리입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[PressedColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 텍스트 색입니다.

**[PressedFill](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 배경색입니다.

**[Reset](properties-core.md)** – 컨트롤이 기본값으로 되돌아가는지 여부입니다.

**[SelectionColor](properties-color-border.md)** – 목록에서 선택한 항목의 텍스트 색 또는 펜 컨트롤에 있는 선택 도구의 색입니다.

**[SelectionFill](properties-color-border.md)** – 목록에서 선택한 항목 또는 펜 컨트롤에서 선택한 영역의 배경색입니다.

**[Size](properties-text.md)** -컨트롤에 표시되는 텍스트의 글꼴 크기입니다.

**[Strikethrough](properties-text.md)** - 컨트롤에 표시되는 텍스트 중앙에 선을 표시할지 여부를 선택합니다.

**[TabIndex](properties-accessibility.md)** – 다른 컨트롤에 관련된 키보드 탐색 순서입니다.

**[Tooltip](properties-core.md)** – 사용자가 마우스로 컨트롤을 가리킬 때 표시되는 설명 텍스트입니다.

**[Underline](properties-text.md)** – 컨트롤에 표시되는 텍스트 아래에 선을 표시할지 여부를 선택합니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="example"></a>예
1. **[단추](control-button.md)** 컨트롤을 추가하고 **[Text](properties-core.md)** 속성을 **Collect**를 표시하도록 설정합니다.
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. **[단추](control-button.md)** 컨트롤의 **[OnSelect](properties-core.md)** 속성을 이 수식으로 설정합니다.
   <br>**ClearCollect(CityPopulations, {City:"London", Country:"United Kingdom", Population:8615000}, {City:"Berlin", Country:"Germany", Population:3562000}, {City:"Madrid", Country:"Spain", Population:3165000}, {City:"Rome", Country:"Italy", Population:2874000}, {City:"Paris", Country:"France", Population:2273000}, {City:"Hamburg", Country:"Germany", Population:1760000}, {City:"Barcelona", Country:"Spain", Population:1602000}, {City:"Munich", Country:"Germany", Population:1494000}, {City:"Milan", Country:"Italy", Population:1344000})**
   
    **[ClearCollect](../functions/function-clear-collect-clearcollect.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
3. F5를 누르고 **[단추](control-button.md)** 컨트롤을 클릭하거나 탭한 다음 Esc 키를 누릅니다.
4. **드롭다운** 컨트롤을 추가하고 이름을 **Countries**로 지정한 다음 **[Items](properties-core.md)** 속성을 다음 수식으로 설정합니다.
   <br>**Distinct(CityPopulations, Country)**
5. 가로/세로 방향으로 **텍스트 갤러리**를 추가하고 **[Items](properties-core.md)** 속성을 다음 수식으로 설정합니다.
   <br>**Filter(CityPopulations, Countries.Selected.Value in Country)**
6. **텍스트 갤러리** 컨트롤의 첫 항목에서 **[레이블](control-text-box.md)** 컨트롤의 **[Text](properties-core.md)** 속성을 **ThisItem.City**로 설정하고 맨 아래 **[레이블](control-text-box.md)** 컨트롤을 삭제합니다. 
7. **텍스트 갤러리** 컨트롤의 **[TemplateSize](control-gallery.md)** 속성을 **80**으로 설정합니다.
8. F5를 누르고 **Countries** 목록의 펼침 단추를 클릭하거나 탭한 다음 해당 목록에서 옵션을 선택합니다.
   
    **텍스트 갤러리** 컨트롤은 사용자가 선택한 국가의 도시만 표시합니다.


## <a name="accessibility-guidelines"></a>접근성 지침
### <a name="color-contrast"></a>색 대비
다음 사이에 적절한 색 대비가 있어야 합니다.
* **ChevronFill** 및 **ChevronBackground**
* **ChevronHoverFill** 및 **ChevronHoverBackground**
* **SelectionColor** 및 **SelectionFill**
* **SelectionFill** 및 **[Fill](properties-color-border.md)**

이는 [표준 색 대비 요구 사항](../accessible-apps-color.md)에 추가됩니다.

### <a name="screen-reader-support"></a>화면 판독기 지원
* **[AccessibleLabel](properties-accessibility.md)** 이 있어야 합니다.

### <a name="keyboard-support"></a>키보드 지원
* 키보드 사용자가 탐색할 수 있도록 **[TabIndex](properties-accessibility.md)** 가 0 이상이어야 합니다.
* 포커스 표시기가 명확하게 표시되어야 합니다. **[FocusedBorderColor](properties-color-border.md)** 및 **[FocusedBorderThickness](properties-color-border.md)** 를 사용하여 이를 달성합니다.
