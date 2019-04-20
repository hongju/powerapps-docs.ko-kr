---
title: 반응형 레이아웃에서 캔버스 앱 만들기 | Microsoft Docs
description: 캔버스 앱에서 컨트롤의 높이, 너비, X 및 Y 속성을 구성 하는 방법에 대한 참조 정보
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 776a542d8e790cc9ae3591b6cda9f08d0d347ef7
ms.sourcegitcommit: 38f91423933749ca19557f29e86cd8f5ad06e1eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59042781"
---
# <a name="create-responsive-layouts-in-canvas-apps"></a>반응형 레이아웃에서 캔버스 앱 만들기

PowerApps의 캔버스 앱을 빌드하기 전에, 휴대폰 또는 태블릿 앱 여부를 지정 합니다. 이 선택은 빌드하는 앱의 캔버스 모양과 크기를 결정 합니다.

선택하고 나서, **파일** > **앱 설정** > **화면 크기 + 방향**을 선택하게 되면 몇 가지 다른 옵션을 선택할 수 있습니다. 세로 또는 가로 방향 및 화면 크기 (태블릿에만 해당)를 선택할 수 있습니다. 또한 가로 세로 비율 잠금 해제 및 잠금과 장치 회전을(장치에 따라) 지원 합니다.

이러한 선택은 화면 레이아웃 설계할 때 결정하는 다른 모든 선택의 기반이 됩니다. 다른 크기의 장치에서 또는 웹에서 앱이 실행 되는 경우, 전체 레이아웃 크기는 앱이 실행 하는 화면에 맞게 조정 합니다. 휴대폰을 위해 설계된 앱이 큰 브라우저 창에서 실행 되는 경우, 앱의 보정을 위해 크기가 조정 되고 해당 공간에 바해 지나치게 커보이게 됩니다. 앱은 더 많은 컨트롤 또는 콘텐츠를 표시 하여 추가 픽셀을 활용할 수 없습니다.

반응형 레이아웃을 만들게 되면, 컨트롤은 다양한 경험으로 더 자연스럽게 느끼도록 다른 장치와 창 크기에 응답할 수 있습니다. 반응형 레이아웃을 달성하기위해 앱의 일부 설정을 조정 하고 식을 작성 합니다. 

## <a name="disable-scale-to-fit"></a>영역 안에 맞추기 해제

앱이 실행 되는 실제 공간에 해당 레이아웃이 맞게 조정 되도록 각 화면을 구성할 수 있습니다.

기본적으로 켜져있는 **영역 안에 맞추기** 설정을 해제하여 응답성을 활성화 합니다. 이 설정을 해제하게 되면, 특정 화면 모양을 디자인하지 못하기 때문에 **가로 세로 비율 고정**도 해제 됩니다. (앱이 장치 회전을 지원하는 여부는 여전히 지정할 수 있습니다)

![확장을 사용 하지 않도록 설정에 맞게](media/create-responsive-layout/scale-to-fit-off.png)

앱의 응답성이 뛰어나게 하려면, 추가 단계를 수행 해야 하지만 이러한 변경은 응답성을 만들기 위한 첫 단계입니다.

## <a name="understand-app-and-screen-dimensions"></a>앱 및 화면 크기 이해

화면 크기에 대한 변경 내용에 응답 하는 앱의 레이아웃을 만들려면 화면의 **Width**와 **Height** 속성을 사용 하는 수식을 작성 합니다. 이러한 속성을 표시 하려면, PowerApps Studio에서 앱을 열고 화면을 선택 합니다. 오른쪽 창의 **고급** 탭에 이러한 속성의 기본 수식이 표시 됩니다.

**Width** = `Max(App.Width, App.DesignWidth)`

**Height** = `Max(App.Height, App.DesignHeight)`

이 수식은 앱의 **Width**, **Height**, **DesignWidth** 및 **DesignHeight** 속성을 참조 합니다. 앱의 **Width**와 **Height** 속성은 앱이 실행 되는 장치 또는 브라우저 창의 크기에 해당 하는 속성입니다. 사용자가 브라우저 창 크기를 조정 하는 경우 (또는 **방향 고정** 해제되어 있는 장치를 회전하는 경우), 이러한 속성의 값을 동적으로 변경 합니다. 화면의 **Width**와 **Height** 속성에서 수식은 이러한 값을 변경 하는 경우 다시 계산 됩니다.

**DesignWidth**와 **DesignHeight** 속성은 **앱 설정**의 **화면 크기 + 방향** 창에서 지정한 크기입니다. 예를 들어, 휴대폰 레이아웃을 세로 방향으로 선택하게 되면, **DesignWidth**은 640이며 **DesignHeight** 1136이 됩니다.

화면의 **Width**와 **Height** 속성에 수식에서 사용되므로, 앱을 디자인하기 위해 최소 크기로 **DesignWidth** 및 **DesignHeight**을 생각할 수 있습니다 . 앱에 사용할 수 있는 실제 영역이 이러한 최소 크기 보다 작은 경우, 화면의 **Width**와 **Height** 속성의 수식은 이러한 값이 최소값보다 더 작지 않도록 합니다. 이 경우 사용자는 모든 화면의 콘텐츠를 보려면 스크롤해야 합니다.

앱의 **DesignWidth**와 **DesignHeight**를 설정한 후, (대부분의 경우)각 화면의 **Width**와 **Height** 속성의 기본 수식을 변경하지 않아도 됩니다. 이 항목의 뒤에서 이러한 수식을 사용자 지정 하려는 경우를 설명 합니다.

## <a name="use-formulas-for-dynamic-layout"></a>동적 레이아웃에 대한 수식 사용

반응형 디자인을 만들려면 각 컨트롤의 크기와 위치에 절대(일정) 좌표 값 대신 수식을 사용합니다. 이러한 수식에는 각 컨트롤의 위치 및 크기가 전체 화면 크기를 기준 또는 화면의 다른 컨트롤을 기준으로 표현합니다.

> [!IMPORTANT]
> 컨트롤의 **X**, **Y**, **Widht**와 **Height** 속성에 대한 수식을 작성 한 후, 캔버스 편집기에서 컨트롤을 끌게 되면 수식은 상수값으로 덮어쓰게 됩니다. 수식을 사용 하여 동적 레이아웃을 만들려면, 컨트롤을 끌어서 놓는 것을 하지 마십시오.

가장 간단한 경우로 하나의 컨트롤로 전체 화면을 채웁니다. 이 효과를 만들려면 컨트롤의 속성을 다음 값으로 설정 합니다.

| 속성      | 값            |
|--------|---------------|
| **X**      | 0             |
| **Y**      | 0             |
| **Width**  | `Parent.Width`  |
| **Height** | `Parent.Height` |

위 수식은 **Parent** 연산자를 사용 합니다. 화면에 직접 배치 되는 컨트롤을 위해 **Parent**는 화면을 가리킵니다. 이러한 속성 값을 사용 하여 컨트롤은 화면의 왼쪽 위 모서리(0, 0)에 표시 되고 화면과 동일한 **Width**와 **Height**가 됩니다.

이 항목의 뒷부분에서, 갤러리, 그룹 컨트롤, 구성요소와 같은 다른 컨테이너 내에서 컨트롤의 위치에 이러한 원칙과 **Parent** 연산자를 적용 합니다.

다른 방법으로, 컨트롤을 화면 위쪽 절반만 채울 수 있습니다. 이 효과를 만들려면 다른 수식은 변경하지 않고 **Height** 속성을 **Parent.Height/2**로 설정합니다.

동일한 화면의 아래쪽 절반에 두 번째 컨트롤을 채우려면, 해당 수식을 만드는 두 개 이상의 방법을 수행할 수 있습니다. 편의상,다음 접근 방식을 사용할 수 있습니다.

| 컨트롤 | 속성 | 수식           |
|-|----------|-------------------|
| **Upper** | **X**        | 0                 |
| **Upper** | **Y**        | 0                 |
| **Upper** | **Width**    | `Parent.Width`      |
| **Upper** | **Height**   | `Parent.Height / 2` |
| **Lower** | **X**        | 0                 |
| **Lower** | **Y**        | `Parent.Height / 2` |
| **Lower** | **Width**    | `Parent.Width`      |
| **Lower** | **Height**   | `Parent.Height / 2` |

![위 높아지고 컨트롤](media/create-responsive-layout/dynamic-layout.png)

이 구성이 원하는 효과를 달성 하지만, 컨트롤의 상대 크기를 변경한 경우 각 수식을 편집 해야 합니다. 예를 들어, 위쪽 컨트롤을 화면의 1/3을 차지하도록 하고 아래쪽 컨트롤은 아래 2 / 3 를 채우도록 결정할 수 있습니다. 

해당 효과를 만들려면, **Upper** 컨트롤의 **Height** 속성과 **Lower** 컨트롤의 **Height** 속성을 업데이트 해야 합니다. 대신, 다음 예제와 같이  **Upper** 컨트롤 (및 자체)을 기준으로 **Lower** 컨트롤의 수식을 작성하는 것을 고려해야 합니다:


| 컨트롤 | 속성 | 수식           |
|-|----------|-------------------|
| **Upper** | **X**        | 0                 |
| **Upper** | **Y**        | 0                 |
| **Upper** | **Width**    | `Parent.Width`      |
| **Upper** | **Height**   | `Parent.Height / 2` |
| **Lower** | **X**        | 0                       |
| **Lower** | **Y**        | `Upper.Y + Upper.Height`  |
| **Lower** | **Width**    | `Parent.Width`            |
| **Lower** | **Height**   | `Parent.Height - Lower.Y` |

![상위 및 하위 컨트롤 상대 크기 조정](media/create-responsive-layout/dynamic-layout2.png)

화면 높이의 다른 부분을 표현 하기 위해 이 수식의 **Upper** 화면의 **Height**의 속성을 업데이트 해야 합니다. **Lower** 컨트롤은 자동으로 이동 하 고 변경에 맞게 크기를 조정 합니다.

이러한 수식 패턴을 사용 하여 **C**라는 컨트롤, 부모 또는 **D**라는 형제 컨트롤 사이의 일반적인 레이아웃 관계를 나타냅니다.

| C와 해당 부모 간의 관계 | 속성 | 수식 | 그림 |
|--|--|--|--|
| **C**를 *N* 여백으로 부모의 너비를 채웁니다  | **X**| *N* | ![부모의 C 채우기 너비의 예](media/create-responsive-layout/c1.png) |
|  | **Width** | `Parent.Width - (N * 2)` |  |
| **C**를 *N* 여백으로 부모의 높이 채웁니다 | **Y** | *N* | ![부모의 C 채우기 높이의 예](media/create-responsive-layout/c2.png) |
|  | **Height** | `Parent.Height - (N * 2)` |  |
| **C**를 *N* 여백으로 부모의 오른쪽 가장자리에 맞춥니다  | **X** | `Parent.Width - (C.Width + N)` | ![부모의 가장자리에 맞게 조정 하는 C의 예](media/create-responsive-layout/c3.png) |
| **C**를 *N* 여백으로 부모의 아래쪽 가장자리에 맞춥니다 | **Y** | `Parent.Height - (C.Height + N)` | ![부모의 가장자리에 맞게 조정 하는 C의 예](media/create-responsive-layout/c4.png) |
| **C**를 부모에서 가로 방향으로 가운데에 맞춥니다 | **X** | `(Parent.Width - C.Width) / 2` | ![부모에서 가로 방향으로 가운데 C의 예](media/create-responsive-layout/c5.png) |
| **C**를 부모에 세로 방향으로 가운데에 맞춥니다 | **Y** | `(Parent.Height - C.Height) / 2` | ![부모에서 세로 방향으로 가운데 C의 예](media/create-responsive-layout/c6.png) |

| C 및 D 간의 관계 | 속성 | 수식 | 그림 |
|--|--|--|--|
| **C**를 **D** 와 동일한 너비로 **D**와 가로로 맞춥니다 | **X** | `D.X` | ![패턴의 예](media/create-responsive-layout/d1.png) |
|  | **Width**    | `D.Width` |  |
| **C**를 **D** 와 같은 높이로 **D**와 세로로 맞춥니다   | **Y** | `D.Y` | ![패턴의 예](media/create-responsive-layout/d2.png) |
|  | **Height** | `D.Height` |  |
| **C**의 오른쪽 가장자리를 **D**의 오른쪽 가장자리에 맞춥니다  | **X** | `D.X + D.Width - C.Width` | ![패턴의 예](media/create-responsive-layout/d3.png) |
| **C**의 아래쪽 가장자리를 **D**의 아래쪽 가장자리에 맞춥니다 | **Y** | `D.Y + D.Height - C.Height` | ![패턴의 예](media/create-responsive-layout/d4.png) |
| **C**를 **D** 기준으로 가로 방향으로 가운데에 맞춥니다  | **X** | `D.X + (D.Width - C.Width) / 2`  | ![패턴의 예](media/create-responsive-layout/d5.png) |
| **C**를 **D** 기준으로 세로 방향으로 가운데에 맞춥니다  | **Y** | `D.Y + (D.Height - C.Height) /2` | ![패턴의 예](media/create-responsive-layout/d6.png) |
| **C**를 N 간격으로 **D**의 오른쪽에 배치합니다  | **X** | `D.X + D.Width - N` | ![패턴의 예](media/create-responsive-layout/d7.png) |
| **C**를 N 간격으로 **D**의 아래쪽에 배치합니다  | **Y** | `D.Y + D.Height + N` | ![패턴의 예](media/create-responsive-layout/d8.png) |
| **C**를 **D**와 부모의 오른쪽 가장자리의 공간에 채웁니다 | **X** | `D.X + D.Width` | ![패턴의 예](media/create-responsive-layout/d9.png) |
|  | **Width** | `Parent.Width - C.X` |  |
| **C**를 **D**와 부모의 아래쪽 가장자리의 공간에 채웁니다 | Y | `D.Y + D.Height` | ![패턴의 예](media/create-responsive-layout/d10.png) |

## <a name="hierarchical-layout"></a>계층형 레이아웃

더 많은 컨트롤을 포함 하는 화면을 생성 하게 될때 형제 컨트롤 또는 화면을 기준으로 하지 않고 부모 컨트롤을 기준으로 컨트롤을 배치하는 것이 보다 더 편리합니다(또는 필요할수 있습니다). 계층 구조로 컨트롤을 구성 하면, 수식을 쉽게 작성하고 유지 관리할 수 있습니다.

### <a name="galleries"></a>갤러리

앱에서 갤러리를 사용 하는 경우, 갤러리의 템플릿 내에서 컨트롤을 배치 해야 합니다. 갤러리 템플릿을 참조 하는 **Parent** 연산자를 사용 하는 수식을 작성 하여 이러한 컨트롤을 배치할 수 있습니다. 갤러리 템플릿 내에서 컨트롤의 수식에 **Parent.TemplateHeight** 및 **Parent.TemplateWidth** 속성사용 합니다. 갤러리의 전체 크기를 나타내는 **Parent.Width** 및 **Parent.Height**를 사용 하지 마십시오.

![세로 갤러리 템플릿 너비와 높이 표시 합니다.](media/create-responsive-layout/gallery-vertical.png)

### <a name="enhanced-group-control"></a>향상된 그룹 컨트롤

부모 컨트롤로 향상된 **그룹** 컨트롤 실험적 기능을 사용할 수 있습니다. 이 기능을 켜려면 **파일** > **앱 설정** > **고급 설정**을 선택 합니다.

화면 맨 위에 있는 머리글의 예를 살펴보세요. 사용자에게 작용할 수 있는 여러 아이콘과 제목으로 머리글이 일반적입니다. **레이블** 컨트롤과 두 **아이콘** 컨트롤을 포함하는 향상된 **그룹** 컨트롤을 사용 하여 이러한 머리글을 생성할 수 있습니다:

![그룹을 사용 하는 헤더 예제](media/create-responsive-layout/header-group.png)

이러한 컨트롤에 대한 속성을 다음 값으로 설정 합니다.

| 속성 | Header | Menu | Close | Title |
|--|--|--|--|--|
| **X** | 0  | 0 | `Parent.Width - Close.Width` | `Menu.X + Menu.Width` |
| **Y** | 0 | 0 | 0 | 0 |
| **너비**  | `Parent.Width` | `Parent.Height` | `Parent.Height` | `Close.X - Title.X` |
| **Height** | 64 | `Parent.Height` | `Parent.Height` | `Parent.Height` |

**Header** 컨트롤의 경우 `Parent`는 화면을 가리킵니다. 다른 컨트롤의 경우 `Parent`는 **Header** 컨트롤을 가리킵니다.

이러한 수식을 작성하였으므로, 해당 속성에 대한 수식을 변경하여 **Header** 컨트롤의 크기 또는 위치를 조정할 수 있습니다. 자식 컨트롤의 위치와 크기는 자동으로 적절 하게 조정 됩니다.

### <a name="components"></a>구성 요소

Components로 명명된 다른 실험적 기능을 사용 하는 경우, 구성 요소를 생성할 수 있으며 앱 전체에서 재사용할 수 있습니다. **그룹** 컨트롤과 마찬가지로, 구성 요소 내에 배치한 컨트롤은 크기와 위치 수식을 구성 요소의 크기를 참조하는 `Parent.Width` 및 `Parent.Height`를 기준으로 해야 합니다. 자세한 정보: [구성 요소를 만드는](create-component.md)

## <a name="adapting-layout-for-device-size-and-orientation"></a>장치 크기 및 방향에 대한 레이아웃 조정

지금까지 수식을 사용 하여 서로 기준으로 정렬된 컨트롤을 유지 하는 동안 사용 가능한 공간에 응답하는 각 컨트롤의 크기를 변경 하는 방법을 알아보았습니다. 하지만 다른 장치 크기 및 방향에 응답하는 더 많은 레이아웃 변경을 생성하거나 원할 수 있습니다. 장치를 가로 방향으로 세로에서 회전할 때, 수평 레이아웃을 세로 레이아웃에서 전환을 원할 수 있습니다. 더 큰 장치에 더 많은 콘텐츠를 제공할 수도 있고 보다 매력적 레이아웃을 제공 하도록 다시 정렬할 수 있습니다. 더 작은 장치에서는 여러 화면으로 콘텐츠를 분할 해야 합니다.

### <a name="device-orientation"></a>장치 방향

앞에서 설명한 화면의 **Width**와 **Height** 속성의 기본 수식은 사용자가 장치를 회전한다면 반드시 좋은 경험을 제공하지 않습니다. 예를 들어, 세로 방향으로 휴대폰에 대한 설계된 앱은 **DesignWidth**이 640과 **DesignHeight**이 1136 됩니다. 가로 방향에서 휴대폰의 동일한 앱은 다음 속성 값이 적용 됩니다.

- 화면의 **Width** 속성을 `Max(App.Width, App.DesignWidth)`로 설정 합니다. 앱의 **Width**(1136)는 해당 **DesignWidth** (640) 보다 큽니다. 그래서 1136으로 수식을 계산 합니다.
- 화면의 **Height** 속성을 `Max(App.Height, App.DesignHeight)`로 설정 합니다. 앱의 **Height** (640)는 해당 **DesignHeight** (1136) 보다 작습니다. 그러므로 1136으로 수식을 계산 합니다.

화면이 1136의 **Height** 이고 640의 장치 높이(이 방향)이므로, 사용자는 모든 컨텐츠를 표시 하려면 세로로 화면을 스크롤하게 되어 사용자가 원하는 경험이 아닐 수 있습니다.

화면의 **Width**와 **Height** 속성을 장치 방향에 맞도록 하려면, 다음 수식을 사용할 수 있습니다.

**Width** = `Max(App.Width, If(App.Width < App.Height, App.DesignWidth, App.DesignHeight))`

**Height** = `Max(App.Height, If(App.Width < App.Height, App.DesignHeight, App.DesignWidth))`

이러한 수식은 장치의 너비 보다 세로 방향 높이가 작거나 가로 방향 높이가 큰지 여부에 따라 앱의 **DesignWidth**와 **DesignHeight**를 교환 합니다. 

화면의 **Width**와 **Height** 수식을 조정한 후,사용 가능한 공간을 더욱 효율적으로 사용 하기 위해 화면 내에서 컨트롤을 다시 정렬 할 수 있습니다. 예를 들어, 화면의 절반을 두 컨트롤이 차지하는 경우, 세로 방향일때는 컨트롤을 쌓거나 가로 방향일때는 나란히 정렬할 수 있습니다.

> [!NOTE]
> 가로 방향에서는 **Upper**와 **Lower** 컨트롤이 왼쪽 및 오른쪽 컨트롤로 표시 합니다.

| 컨트롤 | 속성 | 수식 |
|--|----------|---|
| **Upper** | **X** | 0 |
| **Upper** | **Y** | 0 |
| **Upper** | **Width** | `If(Parent.Width < Parent.Height, Parent.Width, Parent.Width / 2)` |
| **Upper** | **Height**   | `If(Parent.Width < Parent.Height, Parent.Height / 2, Parent.Height)` |
| **Lower** | X | `If(Parent.Width < Parent.Height, 0, Upper.X + Upper.Width)`  |
| **Lower** | Y | `If(Parent.Width < Parent.Height, Upper.Y + Upper.Height, 0)` |
| **Lower** | **Width** | `Parent.Width - Lower.X` |
| **Lower** | **Height** | `Parent.Height - Lower.Y` |

![세로 방향에 맞게 식](media/create-responsive-layout/portrait.png)

![가로 방향에 맞게 식](media/create-responsive-layout/landscape.png)

### <a name="known-limitations"></a>알려진 제한 사항

제작하는 캔버스는 크기 조정 수식에 응답 하지 않습니다. 반응형 동작을 테스트 하려면, 앱을 저장 하고 게시한 다음 장치에서 앱을 열거나 또는 다양한 크기 및 방향의 브라우저 창에서 엽니다.

컨트롤의 **X**, **Y**, **Width** 및 **Height** 속성에 수식을 작성 하는 경우, 다른 위치로 컨트롤을 끌거나 컨트롤의 테두리를 끌어 크기를 조정할 경우는 해당 수식을 덮어쓰게 됩니다.
