---
title: 캔버스 앱에 화면 추가 및 화면 간 이동 | Microsoft Docs
description: 캔버스 앱에 화면을 추가하고 다음 및 뒤로 화살표를 사용하여 PowerApps에서 화면 간 이동
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/10/2017
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f7e03402690cb448a10c64882fdb6d79713cffcb
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42858910"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>캔버스 앱에 화면 추가 및 화면 간 이동

여러 화면이 있는 캔버스 앱을 만들고 사용자가 이들 사이를 이동할 수 있는 방법을 추가합니다.

## <a name="prerequisites"></a>필수 조건

* [컨트롤을 구성](add-configure-controls.md)하는 방법을 알아봅니다.
* 앱을 만들거나 엽니다.

## <a name="add-and-rename-a-screen"></a>화면 추가 및 이름 바꾸기

1. **홈** 탭에서 **새 화면**을 클릭하거나 탭합니다.

    ![홈 탭에서 화면 옵션 추가](./media/add-screen-context-variables/add-screen.png)

2. 오른쪽 창에서 화면의 이름(**속성** 탭 바로 위)을 클릭하거나 탭한 후 새 이름으로 **Source**를 입력합니다.

    ![기본 화면 이름 바꾸기](./media/add-screen-context-variables/name-source-screen.png)

3. 다른 화면을 추가하고 이름을 **Target**으로 지정합니다.

    ![왼쪽 탐색 표시줄에서 두 개의 화면](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="add-navigation"></a>탐색 추가
1. **Source** 화면을 선택한 상태에서 **삽입** 탭을 열고 **아이콘**을 클릭하거나 탭한 후 **다음 화살표**를 클릭하거나 탭합니다.  

    ![[삽입] 탭에 있는 [셰이프] 옵션](./media/add-screen-context-variables/add-next-arrow.png)

2. (선택 사항) 화면의 오른쪽 아래 모서리에 표시되도록 화살표를 이동합니다.

3. 화살표를 선택한 상태로 **작업** 탭을 클릭하거나 탭한 후 **탐색**을 클릭하거나 탭합니다.

    화살표에 대한 **[OnSelect](controls/properties-core.md)** 속성이 **Navigate** 함수로 자동으로 설정됩니다.  

    ![Navigate 함수로 설정된 OnSelect 속성](./media/add-screen-context-variables/onselect-default.png)

    사용자가 화살표를 클릭하거나 탭하면 **Target** 화면이 사라집니다.

4. **Target** 화면에서 **뒤로 화살표**를 추가하고 **[OnSelect](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.
   <br>**Navigate(Source, ScreenTransition.Fade)**

5. 미리 보기 모드(![](./media/add-screen-context-variables/preview.png) 또는 F5 키 누르기)를 연 후 추가한 화살표를 클릭하거나 탭하여 화면 사이를 전환합니다.

6. 기본 작업 영역으로 돌아가려면 **Esc** 키를 누릅니다.
