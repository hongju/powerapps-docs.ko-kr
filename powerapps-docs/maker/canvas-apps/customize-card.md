---
title: 캔버스 앱에서 카드 사용자 지정 | Microsoft Docs
description: 세부 정보 카드에 표시 되는 기본 컨트롤 변경 또는 캔버스 앱에서 양식을 편집
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ddc1c677ed95caf10d8cd6e0e7e12e6aaf88a0f5
ms.sourcegitcommit: f4b71ea0996603b3358377a0da21b9e4428a287c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58870911"
---
# <a name="customize-a-card-in-a-canvas-app"></a>캔버스 앱에서 카드 사용자 지정

해당 컨트롤을 변경하는 등의 방법으로 (카드를 잠금 해제하지 않고) 기본 사용자 지정 을 수행합니다. 기본값으로 가능하지 않은 컨트롤을 추가하는 등의 방법으로 카드를 잠금 해제하여 고급 사용자 지정을 수행합니다.

개요를 보려면 [데이터 카드 이해](working-with-cards.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건

- [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아보세요.
- 이 항목에서는 일반적인 개념만 검토할 수 있습니다 하거나 먼저이 항목의 절차를 완료 하면 단계별로 따를 수 있습니다.

    1. [앱 생성](data-platform-create-app.md)
    1. [해당 갤러리 사용자 지정](customize-layout-sharepoint.md)
    1. [해당 양식 사용자 지정](customize-forms-sharepoint.md)

## <a name="customize-a-locked-card"></a>잠긴 카드 사용자 지정

이 절차에서는 바꿉니다를 **[텍스트 입력](controls/control-text-input.md)** 컨트롤을 **[슬라이더] (컨트롤/컨트롤-slider.md** 카드를 잠금 해제 하지 않고 컨트롤입니다.

1. 를 생성 하 고 사용자 지정 하는 앱에서 선택 **EditForm1** 왼쪽 탐색 모음에서 선택한 후 **필드를 편집할** 에 **속성** 오른쪽 창의 탭 합니다.

1. 필드 목록의 아래쪽 화살표를 선택 **Number of Employees**를 연 다음 아래의 목록 **컨트롤 형식과**합니다.

    > [!div class="mx-imgBorder"]
    > ![숫자 카드에 대한 옵션의 드롭다운 목록](./media/customize-card/card-selector.png)

1. 선택 **슬라이더 편집**합니다.

    화면은 변경 내용을 반영합니다.

    > [!div class="mx-imgBorder"]
    > ![슬라이더 컨트롤이 있는 EditForm1](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>카드 잠금 해제 및 사용자 지정

이 절차에서는 카드를 잠금 해제 및 업데이트 됩니다 합니다 **최대** 의 속성을 **슬라이더** 방금 추가한 컨트롤입니다.

1. **EditForm1**를 선택 합니다 **슬라이더** 에서 제어할 합니다 **Number of Employees** 카드.

    > [!div class="mx-imgBorder"]
    > ![슬라이더를 선택 합니다.](./media/customize-card/select-slider.png)

1. 에 **고급** 탭 오른쪽 창의 카드의 잠금을 해제 하려면 자물쇠 아이콘을 선택 합니다.

    > [!div class="mx-imgBorder"]
    > ![카드를 잠금 해제](./media/customize-card/lock-icon.png)

1. 설정 합니다 **최대** 의 속성을 **슬라이더** 10,000 컨트롤.

    > [!div class="mx-imgBorder"]
    > ![고급 탭에서 최대 속성](./media/customize-card/max-property.png)

    합니다 **슬라이더** 컨트롤에 더 정확한 값을 보여 줍니다.

    > [!div class="mx-imgBorder"]
    > ![슬라이더 범위: 0-10,000](./media/customize-card/final-slider.png)

## <a name="next-steps"></a>다음 단계

이제 앱을 생성하고 갤러리, 양식 및 카드를 사용자 지정하는 방법에 대한 기본적인 이해를 마쳤으므로 [처음부터 직접 앱을 빌드](data-platform-create-app-scratch.md)할 수 있습니다.