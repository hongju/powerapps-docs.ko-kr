---
title: "카드 사용자 지정 | Microsoft Docs"
description: "카드에 기본 및 고급 사용자 지정 수행"
services: 
suite: powerapps
documentationcenter: 
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/30/2016
ms.author: sharik
ms.openlocfilehash: 9fdde89b254e491f2dc333261649df7fd156f2c2
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="customize-a-card-in-microsoft-powerapps"></a>Microsoft PowerApps에서 카드 사용자 지정
해당 컨트롤을 변경하는 등의 방법으로 (카드를 잠금 해제하지 않고) 기본 사용자 지정 을 수행합니다. 기본값으로 가능하지 않은 컨트롤을 추가하는 등의 방법으로 카드를 잠금 해제하여 고급 사용자 지정을 수행합니다.

개요를 보려면 [데이터 카드 이해](working-with-cards.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건

* [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아보세요.
* 일반 개념만을 위해 이 항목을 검토할 수 있습니다. 정확하게 수행하려면(단계별로) 다음 항목의 단계를 따릅니다.

  1. [SharePoint에서 앱 만들기](app-from-sharepoint.md)
  2. [레이아웃 사용자 지정](customize-layout-sharepoint.md)
  3. [양식 사용자 지정](customize-forms-sharepoint.md)

## <a name="customize-a-locked-card"></a>잠긴 카드 사용자 지정
이 절차에서는 카드를 잠금 해제하지 않고 **[토글](controls/control-toggle.md)** 컨트롤을 **[라디오](controls/control-radio.md)** 컨트롤로 바꿉니다.

1. **EditScreen1**에서 **유료** 카드를 클릭하거나 탭하여 선택합니다.

    ![](./media/customize-card/select-paid-card.png)

2. 오른쪽 창에서 **유료** 카드에 대해 카드 선택기를 클릭하거나 탭한 다음 **옵션 편집**을 클릭하거나 탭합니다.

    ![](./media/customize-card/select-toggle-paid.png)

    화면은 변경 내용을 반영합니다.

    ![](./media/customize-card/display-radio.png)
   
    어떤 형식의 SharePoint 열이 어떤 형식의 카드를 지원하는지에 대한 정보는 [알려진 문제](connections/connection-sharepoint-online.md#known-issues)를 참조하세요.

## <a name="unlock-and-customize-a-card"></a>카드 잠금 해제 및 사용자 지정
이 절차에서는 카드를 잠금 해제한 다음 **[텍스트 입력](controls/control-text-input.md)** 컨트롤을 **[슬라이더](controls/control-slider.md)** 컨트롤로 바꿉니다.

1. **EditScreen1**에서 **수량** 카드를 클릭하거나 탭합니다.

2. 오른쪽 창에서 해당 카드에 대한 줄임표 아이콘을 클릭하거나 탭한 다음 **고급 옵션**을 클릭하거나 탭합니다.

    ![고급 옵션 열기](./media/customize-card/advanced-options.png)
3. 오른쪽 창 맨 위에서 잠금 아이콘을 클릭하거나 탭하여 카드를 잠금 해제합니다.

    ![카드 잠금 해제](./media/customize-card/unlock-card.png)
4. 카드에서 **입력 텍스트** 컨트롤을 삭제하고 **슬라이더** 컨트롤을 추가한 다음 새 컨트롤 **QtySlider**에 이름을 지정합니다.

5. 오른쪽 창에서 **수량** 카드의 **업데이트** 속성을 다음의 수식으로 설정합니다.<br>
   **QtySlider.Value**

   > [!NOTE]
> **업데이트** 속성이 표시되지 않는 경우 **데이터** 섹션의 하단에 있는 **더 많은 옵션**을 클릭하거나 탭합니다.


6. 슬라이더를 클릭하거나 탭하여 선택한 다음 오른쪽 창의 맨 위에 있는 컨트롤의 목록을 엽니다.

7. **ErrorMessage4**를 클릭하거나 탭한 다음 해당 **높이** 속성을 다음의 수식으로 설정합니다.<br>
   **QtySlider.Y + QtySlider.Height**
