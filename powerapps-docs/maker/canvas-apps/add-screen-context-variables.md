---
title: 캔버스 앱에 화면 추가 및 화면 간 이동 | Microsoft Docs
description: 캔버스 앱에 화면을 추가하고 다음 및 뒤로 화살표를 사용하여 PowerApps에서 화면 간 이동
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 02/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b6f83d21b2964dac7c4925d45efdf11a3a1e6b02
ms.sourcegitcommit: 7f67cd28c781a48f6a211ed82c2c861ae3acf1a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2019
ms.locfileid: "57800724"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>캔버스 앱에 화면 추가 및 화면 간 이동

여러 화면이 있는 캔버스 앱을 만들고 사용자가 이들 사이를 이동할 수 있는 방법을 추가합니다.

## <a name="add-and-rename-a-screen"></a>화면 추가 및 이름 바꾸기

1. 에 **홈** 탭을 선택 **새 화면**를 추가 하려면 원하는 화면 종류를 선택 합니다.

    ![홈 탭에서 화면 옵션 추가](./media/add-screen-context-variables/add-screen.png)

2. 오른쪽 창에서 화면의 이름을 선택 (바로 위에 합니다 **속성** 탭)를 입력 합니다 **원본**합니다.

    ![기본 화면 이름 바꾸기](./media/add-screen-context-variables/name-source-screen.png)

3. 다른 화면을 추가하고 이름을 **Target**으로 지정합니다.

    ![왼쪽 탐색 표시줄에서 두 개의 화면](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="reorder-screens"></a>화면을 다시 정렬

위로 또는 아래로 나타나는 줄임표 단추를 선택 하려는 화면 왼쪽된 탐색 모음에서 위로 및 선택한 **위로 이동** 하거나 **아래로 이동**합니다.

![화면을 다시 정렬](./media/add-screen-context-variables/reorder-screen.png)

> [!NOTE]
> 에 앱을 열 때 컨트롤의 계층적 목록 맨 위에 있는 화면이 일반적으로 첫 번째를 나타납니다. 하지만 설정 하 여 다른 화면을 지정할 수 있습니다는 **[OnStart](controls/control-screen.md)** 속성을 포함 하는 수식으로는 **[탐색](functions/function-navigate.md)** 함수입니다.

## <a name="add-navigation"></a>탐색 추가

1. 사용 하 여는 **소스** 선택 화면 열기를 **삽입** 탭을 선택 **아이콘**를 선택한 후 **다음 화살표**합니다.  

    ![[삽입] 탭에 있는 [셰이프] 옵션](./media/add-screen-context-variables/add-next-arrow.png)

2. (선택 사항) 화면의 오른쪽 아래 모서리에 표시되도록 화살표를 이동합니다.

3. 여전히 선택 하 고 화살표를 선택 합니다 **동작** 탭을 선택한 후 **탐색**합니다.

    화살표에 대한 **[OnSelect](controls/properties-core.md)** 속성이 **Navigate** 함수로 자동으로 설정됩니다.

    ![Navigate 함수로 설정된 OnSelect 속성](./media/add-screen-context-variables/onselect-default.png)

    사용자가 화살표를 선택 합니다 **대상** 화면이 사라집니다.

4. **Target** 화면에서 **뒤로 화살표**를 추가하고 **[OnSelect](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.

    `Navigate(Source, ScreenTransition.Fade)`

5. Alt 키를 누른 채 각 화면에 있는 화살표를 선택 하 여 화면 사이 전환 합니다.

## <a name="more-information"></a>자세한 정보

[화면 컨트롤 참조](controls/control-screen.md)