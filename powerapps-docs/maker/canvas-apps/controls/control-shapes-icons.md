---
title: '도형 컨트롤 및 아이콘 모양을: 참조 | Microsoft Docs'
description: 속성 및 예제를 비롯하여 도형 컨트롤과 아이콘 컨트롤에 관한 정보
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: e2c5d384c29766d6c30db8aa85ad4d7d45b48e04
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838151"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>PowerApps의 도형 컨트롤 및 아이콘 컨트롤
모양 및 동작 속성을 구성할 수 있는 그래픽입니다.

## <a name="description"></a>설명
이러한 컨트롤에는 fill, size 및 location 등의 속성을 구성할 수 있는 화살표, 기하학적 도형, 작업 아이콘 및 기호가 있습니다. 또한, 사용자가 컨트롤을 클릭하거나 탭할 경우 앱이 응답하도록 **[OnSelect](properties-core.md)** 속성을 구성할 수도 있습니다.

## <a name="key-properties"></a>주요 속성
**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

## <a name="additional-properties"></a>추가 속성
**[AccessibleLabel](properties-accessibility.md)** – 화면 읽기 프로그램의 레이블입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[FocusedBorderColor](properties-color-border.md)** – 컨트롤에 포커스가 있을 때 컨트롤의 테두리 색입니다.

**[FocusedBorderThickness](properties-color-border.md)** – 컨트롤에 포커스가 있을 때 컨트롤의 테두리 두께입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[PressedFill](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 배경색입니다.

**[TabIndex](properties-accessibility.md)** – 다른 컨트롤에 관련된 키보드 탐색 순서입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**Navigate**( *ScreenName*, *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>예
1. 기본 **[화면](control-screen.md)** 컨트롤의 이름을 **Target**으로 지정하고 **[레이블](control-text-box.md)** 컨트롤을 추가하며 **[Text](properties-core.md)** 속성을 **Target**을 표시하도록 설정합니다.
   
    [컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. **[화면](control-screen.md)** 컨트롤을 추가하고 이름을 **Source**로 지정합니다.
3. **Source**에서 **도형** 컨트롤을 추가하고 다음 수식에 **[OnSelect](properties-core.md)** 속성을 설정합니다.
   <br>**Navigate(Target, ScreenTransition.Fade)**
4. F5 키를 누르고 **도형** 컨트롤을 클릭하거나 탭합니다.
   
    **Target** 화면이 나타납니다.
5. (선택 사항) Esc 키를 눌러 기본 작업 영역으로 돌아가고 **도형** 컨트롤을 **Target**에 추가한 다음, **도형** 컨트롤의 **[OnSelect](properties-core.md)** 속성을 다음 서식으로 설정합니다.
   <br>**Navigate(Source, ScreenTransition.Fade)**


## <a name="accessibility-guidelines"></a>접근성 지침
### <a name="color-contrast"></a>색 대비
다음은 단추로 사용되거나 장식용으로만 사용되지 않는 그래픽에만 적용됩니다.

아이콘:
* **[Color](properties-color-border.md)** 및 **[Fill](properties-color-border.md)**
* 기타 [표준 색 대비 요구 사항](../accessible-apps-color.md)이 적용됨(단추로 사용되는 경우)

테두리가 있는 셰이프:
* **[BorderColor](properties-color-border.md)** 및 컨트롤 외부 색
* **[FocusedBorderColor](properties-color-border.md)** 및 컨트롤 외부 색(단추로 사용되는 경우)

테두리가 없는 셰이프:
* **[Fill](properties-color-border.md)** 및 컨트롤 외부 색
* **[PressedFill](properties-color-border.md)** 및 컨트롤 외부 색(단추로 사용되는 경우)
* **[HoverFill](properties-color-border.md)** 및 컨트롤 외부 색(단추로 사용되는 경우)

### <a name="screen-reader-support"></a>화면 판독기 지원
* 그래픽이 단추로 사용되거나 장식용으로만 사용되지 않는 경우에는 **[AccessibleLabel](properties-accessibility.md)** 이 있어야 합니다.
* 그래픽이 장식용으로만 사용되는 경우 **[AccessibleLabel](properties-accessibility.md)** 은 비어 있거나 빈 문자열 **""** 이어야 합니다. 이렇게 하면 화면 읽기 프로그램이 그래픽을 무시합니다.
* 그래픽이 중복 정보를 제공하는 경우 **[AccessibleLabel](properties-accessibility.md)** 은 비어 있거나 빈 문자열 **""** 일 수 있습니다.
    * 예를 들어 **[AccessibleLabel](properties-accessibility.md)** 이 **설정**으로 설정된 **설정** 아이콘이 있습니다. 이 아이콘은 단추로 사용되지 않습니다. **설정**으로도 표시된 **[레이블](control-text-box.md)** 옆에 있습니다. 화면 읽기 프로그램은 아이콘을 **설정**으로 읽고 레이블을 다시 **설정**으로 읽습니다. 이는 불필요하게 자세한 정보입니다. 이 경우 아이콘에는 **[AccessibleLabel](properties-accessibility.md)** 이 필요하지 않습니다.

    > [!IMPORTANT]
> 화면 읽기 프로그램은 **[AccessibleLabel](properties-accessibility.md)** 이 비어 있는 경우에도 항상 0 이상의 **[TabIndex](properties-accessibility.md)** 가 있는 아이콘 또는 셰이프를 읽습니다. 이는 이미지가 단추로 렌더링되기 때문입니다. **[AccessibleLabel](properties-accessibility.md)** 이 제공되지 않으면 화면 읽기 프로그램은 그래픽을 **단추**로만 읽습니다.

### <a name="keyboard-support"></a>키보드 지원
* 그래픽이 단추로 사용되는 경우 **[TabIndex](properties-accessibility.md)** 는 0 이상이어야 합니다. 이 경우 키보드 사용자가 이미지로 이동할 수 있습니다.
* 그래픽이 단추로 사용되는 경우 포커스 표시기는 명확하게 표시되어야 합니다. **[FocusedBorderColor](properties-color-border.md)** 및 **[FocusedBorderThickness](properties-color-border.md)** 를 사용하여 이를 달성합니다.

    > [!NOTE]
> **[TabIndex](properties-accessibility.md)** 가 0 이상이면 아이콘 또는 셰이프가 단추로 렌더링됩니다. 시각적 모양은 변경되지 않지만 화면 읽기 프로그램은 이미지를 단추로 올바르게 식별합니다. **[TabIndex](properties-accessibility.md)** 가 0보다 작으면 아이콘 또는 셰이프가 이미지로 식별됩니다.
