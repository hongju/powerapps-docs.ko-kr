---
title: "도형 컨트롤 및 아이콘 모양을: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯하여 도형 컨트롤과 아이콘 컨트롤에 관한 정보"
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
ms.openlocfilehash: 7a71695460453816dd5c63dad8477cb7ccc703d7
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>PowerApps의 도형 컨트롤 및 아이콘 컨트롤
모양 및 동작 속성을 구성할 수 있는 그래픽입니다.

## <a name="description"></a>설명
이러한 컨트롤에는 fill, size 및 location 등의 속성을 구성할 수 있는 화살표, 기하학적 도형, 작업 아이콘 및 기호가 있습니다. 또한, 사용자가 컨트롤을 클릭하거나 탭할 경우 앱이 응답하도록 **[OnSelect](properties-core.md)** 속성을 구성할 수도 있습니다.

## <a name="key-properties"></a>주요 속성
**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

## <a name="additional-properties"></a>추가 속성
**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[FocusedBorderThickness](properties-color-border.md)** - 키보드 포커스가 있을 때 컨트롤의 테두리 두께입니다.

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

