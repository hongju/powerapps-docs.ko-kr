---
title: 캔버스 앱 컨트롤 추가 및 구성 | Microsoft Docs
description: 도구 모음의 속성 탭 또는 수식 입력줄에서 직접 캔버스 앱 컨트롤을 추가 및 구성하기 위한 단계별 지침입니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/25/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 798a355e1c8728b41f3e92f183d4a4e2831b7cc2
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799459"
---
# <a name="add-and-configure-a-canvas-app-control-in-powerapps"></a>PowerApps에서 캔버스 앱 컨트롤 추가 및 구성

도구 모음, **속성** 탭 또는 수식 입력줄에서 직접 캔버스 앱에 다양한 UI 요소를 추가하고 모양과 동작의 측면을 구성합니다. 이러한 UI 요소는 컨트롤이라고 하며, 구성하는 측면은 속성이라고 합니다.

## <a name="prerequisites"></a>필수 조건

1. PowerApps 라이선스를 아직 없는 경우 [등록할](../signup-for-powerapps.md)를 차례로 [로그인](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)합니다.
1. 아래 **고유한 앱 만들기**를 마우스로 **비어 있는 상태에서 캔버스 앱**를 선택한 후 **이 앱 만들기**합니다.
1. 소개 둘러보기 묻는 선택 **다음** PowerApps 인터페이스의 주요 영역에 살펴보려면 (누르거나 **건너뛰기**).

    있습니다 수 항상 나중에 둘러보기를 선택한 다음 화면의 오른쪽 위 모서리의 물음표 아이콘을 선택 하 여 **소개 둘러보기**합니다.

## <a name="add-and-select-a-control"></a>추가 하 고 컨트롤을 선택 합니다.

에 **삽입** 탭에서 다음이 단계 중 하나를 수행 합니다.

- 선택 **레이블을** 하거나 **단추** 이러한 유형의 컨트롤 중 하나를 추가 합니다.
- 컨트롤의 범주를 선택 하 고 추가 하려는 컨트롤 종류를 선택 합니다.

예를 들어, 선택 **새 화면**, 선택한 후 **빈** 앱에 빈 화면을 추가 합니다. (화면은 다른 유형의 컨트롤을 포함할 수 있는 컨트롤의 형식입니다.)

![화면 추가](./media/add-configure-controls/add-screen.png)

새 화면 라고 **Screen2** 왼쪽된 탐색 창에 나타납니다. 이 창을 쉽게 찾습니다 하 고 각 컨트롤을 선택할 수 있도록 앱에서 컨트롤의 계층적 목록을 보여 줍니다.

![목록의 Screen2](./media/add-configure-controls/list-screen2.png)

이 목록은 작동 원리를 보여 주기 위해 선택 **레이블을** 에 **삽입** 탭 합니다. 새 컨트롤 아래에 나타납니다 **Screen2** 계층적 목록의 합니다.

![목록의 Screen2](./media/add-configure-controls/add-label.png)

화면에서 6 개의 핸들을 사용 하 여 상자는 기본적으로 레이블을 둘러쌉니다. 해당 유형의 상자 어떤 컨트롤이 선택 되어 둘러쌉니다. 화면 클릭 하거나 눌러에 (하지만 레이블을 외부)을 선택 하면 상자 레이블의 사라집니다. 레이블을 선택 합니다 다시 클릭 하거나, 탭 또는 클릭 하거나 탭 할 **Label2** 컨트롤의 계층적 목록에 있습니다.

> [!IMPORTANT]
> 컨트롤을 구성 하기 전에 항상 선택 해야 합니다.

## <a name="rename-a-control"></a>컨트롤 이름 바꾸기

컨트롤 이름 바꾸기 하려는 컨트롤 위로 마우스를 가져가고의 계층적 목록에 나타나고 다음을 선택 하는 줄임표 단추를 선택 **이름 바꾸기**합니다. 그런 다음 앱을 쉽게 만들 수 있도록 고유 하 고 기억 하기 쉬운 이름을 입력할 수 있습니다.

![컨트롤 이름 바꾸기](./media/add-configure-controls/rename-control.png)

## <a name="delete-a-control"></a>컨트롤 삭제

삭제 하려는 컨트롤 위로 마우스를 가져가고 컨트롤의 계층적 목록에 나타나고 다음을 선택 하는 줄임표 단추를 선택 **삭제**합니다. 화면에 없는 컨트롤을 삭제 하려면 캔버스에서 컨트롤을 선택할 수도 하 수 Delete 키를 누릅니다.

![컨트롤 삭제](./media/add-configure-controls/delete-control.png)

## <a name="reorder-screens"></a>화면을 다시 정렬

위로 또는 아래로 나타나는 줄임표 단추를 선택 하려는 화면을 마우스로으로 컨트롤의 계층적 목록에서 선택한 후 **위로 이동** 하거나 **아래로 이동**합니다.

![화면을 다시 정렬](./media/add-configure-controls/reorder-screen.png)

> [!NOTE]
> 에 앱을 열 때 컨트롤의 계층적 목록 맨 위에 있는 화면이 일반적으로 첫 번째를 나타납니다. 하지만 설정 하 여 다른 화면을 지정할 수 있습니다는 **[OnStart](controls/control-screen.md)** 속성을 포함 하는 수식으로는 **[탐색](functions/function-navigate.md)** 함수입니다.

## <a name="move-and-resize-a-control"></a>이동 하 고 컨트롤 크기 조정

컨트롤을 이동 하려면 중심 위로 마우스를 가져가고 십자형 화살표 표시 되도록 선택한 다음 다른 위치로 컨트롤을 끌어 옵니다.

![컨트롤 이동](./media/add-configure-controls/move-control.png)

컨트롤의 크기를 조정 하려면 선택 상자에 임의 핸들 위로 마우스를 가져가고 나타나도록 양방향 화살표를 선택한 다음 핸들을 끕니다.

![컨트롤 이동](./media/add-configure-controls/resize-control.png)

> [!NOTE]
> 이 항목 뒷부분에서 설명한 대로 이동할 수 있으며 모든 조합을 수정 하 여 컨트롤의 크기 조정 해당  **[X](controls/properties-size-location.md)** 하십시오  **[Y](controls/properties-size-location.md)**,  **[높이](controls/properties-size-location.md)**, 및 **[너비](controls/properties-size-location.md)** 수식 입력줄에는 속성입니다.

## <a name="change-the-text-of-a-label-or-a-button"></a>레이블 또는 단추 텍스트 변경

레이블 또는 단추를 선택, 컨트롤에서 표시 되는 텍스트를 두 번 클릭 하 고 원하는 텍스트를 입력 합니다.

![텍스트 변경](./media/add-configure-controls/change-text.png)

> [!NOTE]
> 이 항목에서는 나중에 설명 된 대로 변경할 수도 있습니다이 텍스트를 수정 하 여 해당 **[텍스트](controls/properties-core.md)** 수식 입력줄에는 속성입니다.

## <a name="configure-a-control-from-the-toolbar"></a>도구 모음에서 컨트롤 구성

도구 모음에서 컨트롤을 구성하여 컨트롤을 직접 구성하여 할 수 있는 더 광범위한 옵션을 지정할 수 있습니다.

예를 들어, 있습니다 수 레이블을 선택 합니다 **홈** 탭을 클릭 한 다음 레이블의 텍스트의 글꼴을 변경 합니다.

![글꼴 변경](./media/add-configure-controls/change-font.png)

## <a name="configure-a-control-from-the-properties-tab"></a>속성 탭에서 컨트롤 구성

사용 하 여 합니다 **속성** 탭, 도구 모음에서 컨트롤을 구성 하 여 수 있는 것 보다 더 광범위 한 여러 가지 옵션을 지정할 수 있습니다.

예를 들어, 컨트롤을 선택 하 고 표시 하거나 숨길 수 있습니다이 변경 하 여 해당 **Visible** 속성입니다.

![표시 설정](./media/add-configure-controls/set-visibility.png)

## <a name="configure-a-control-in-the-formula-bar"></a>수식 입력줄에서 컨트롤 구성

직접, 도구 모음에서 또는 컨트롤을 구성 하는 대신 합니다 **속성** 탭 속성 목록의 속성을 선택 하 고 다음 수식 입력줄에서 값을 지정 하 여 컨트롤을 구성할 수 있습니다. 이 접근 방법을 사용하여 속성을 알파벳 순서로 검색하고, 값의 추가 유형을 지정할 수 있습니다.

예를 들어, 레이블을 선택 하 고 다음과 같은이 방법으로 구성한 수 있습니다.

- 선택 하 여 **X** 하거나 **Y** 속성 목록 및 다음 수식 입력줄에 다른 수를 지정 합니다.

    ![X 설정 속성](./media/add-configure-controls/x-property.png)

- 선택 하 여 크기를 조정할 **높이** 또는 **너비** 속성 목록 및 다음 수식 입력줄에 다른 수를 지정 합니다.

    ![높이 속성 설정](./media/add-configure-controls/height-property.png)

- 선택 하 여 해당 텍스트를 변경 **텍스트** 속성 목록 및 다음 수식 입력줄에서 리터럴 문자열, 식 또는 수식을 조합을 지정 합니다.

    - 리터럴 문자열은 따옴표로 및 입력 한 대로 정확 하 게 표시 됩니다. **"Hello, world"** 리터럴 문자열입니다.

        ![리터럴 문자열을 텍스트 속성을 설정 합니다.](./media/add-configure-controls/literal-string.png)

    - 식을 함수를 포함 하지 않습니다 하 고 종종 다른 컨트롤의 속성에 기반 합니다. **Screen1.Height** 식의 높이 보여주는 **Screen1**합니다.

        ![식 텍스트 속성을 설정 합니다.](./media/add-configure-controls/expression.png)

    - 수식에는 하나 이상의 함수가 포함 됩니다. **이제** 함수에서 현지 표준 시간대, 현재 날짜 및 시간을 반환 하며 **텍스트** 함수 같은 날짜, 시간 및 통화 값의 형식을 지정.

        ![수식에 텍스트 속성을 설정 합니다.](./media/add-configure-controls/formula.png)

        수식은 일반적으로이 예제 보다 훨씬 더 복잡 하므로 데이터 업데이트, 정렬, 필터링, 및 다른 작업을 수행할 수 있습니다. 자세한 내용은 참조는 [수식 참조](formula-reference.md)합니다.

## <a name="next-steps"></a>다음 단계

- 와 같은 공용 컨트롤을 구성 하기 위한 단계별 절차를 확인할 [스크린](add-screen-context-variables.md), [나열](add-list-box-drop-down-list-radio-button.md)를 [갤러리](add-gallery.md), [forms](add-form.md), 및 [차트](use-line-pie-bar-chart.md)합니다.
- 컨트롤의 각 형식에 대 한 참조 정보는 [제어 참조](reference-properties.md)합니다.
