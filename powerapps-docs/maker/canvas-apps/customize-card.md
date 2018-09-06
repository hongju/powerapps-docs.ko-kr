---
title: 카드 사용자 지정 | Microsoft Docs
description: PowerApps에서 세부 정보 또는 편집 양식의 카드에 표시되는 기본 컨트롤 변경
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
ms.openlocfilehash: 31c0810b9da5a52bcd5cc3b28b6def858541e15b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42841789"
---
# <a name="customize-a-card-in-powerapps"></a>PowerApps에서 카드 사용자 지정
해당 컨트롤을 변경하는 등의 방법으로 (카드를 잠금 해제하지 않고) 기본 사용자 지정 을 수행합니다. 기본값으로 가능하지 않은 컨트롤을 추가하는 등의 방법으로 카드를 잠금 해제하여 고급 사용자 지정을 수행합니다.

개요를 보려면 [데이터 카드 이해](working-with-cards.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건

* [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아보세요.
* 이 항목에서 일반적인 개념만을 살펴보거나 이 항목의 절차를 완료하면 단계별로 따를 수 있습니다.

  1. [앱 생성](data-platform-create-app.md)
  2. [해당 갤러리 사용자 지정](customize-layout-sharepoint.md)
  3. [해당 양식 사용자 지정](customize-forms-sharepoint.md)

## <a name="customize-a-locked-card"></a>잠긴 카드 사용자 지정
이 절차에서는 카드를 잠금 해제하지 않고 **[텍스트 입력](controls/control-text-input.md)** 컨트롤을 **[슬라이더](controls/control-slider.md)** 컨트롤로 바꿉니다.

1. [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인합니다.

    ![PowerApps 홈 페이지](./media/customize-card/sign-in.png)

1. 생성 및 사용자 지정한 앱을 열고, **EditForm1**을 선택한 다음, 오른쪽 창에서 **계정**을 선택하여 **데이터** 창을 엽니다.

1. 필드 목록에서 **직원 수**에 대한 아래쪽 화살표를 선택하여 옵션의 목록을 표시한 다음, **슬라이더 편집**을 선택합니다.

    ![숫자 카드에 대한 옵션의 드롭다운 목록](./media/customize-card/card-selector.png)

    화면은 변경 내용을 반영합니다.

    ![슬라이더 컨트롤이 있는 EditForm1](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>카드 잠금 해제 및 사용자 지정
이 절차에서는 카드를 잠금 해제한 다음, **[토글](controls/control-toggle.md)** 컨트롤을 **[확인란](controls/control-check-box.md)** 컨트롤로 바꿉니다.

1. **EditForm1**에서 **마케팅 자료 보내기** 필드를 표시합니다.

    ![마케팅 자료 보내기에 대한 필드 표시](./media/customize-card/show-field.png)

2. 해당 카드를 선택하고, 오른쪽 창의 맨 위 근처의 **고급**을 클릭하거나 탭한 다음, 잠금 아이콘을 클릭하거나 탭하여 카드를 잠금 해제합니다.

    ![마케팅 자료 보내기에 대한 필드 표시](./media/customize-card/unlock-card.png)

1. 카드에서 **토글** 컨트롤을 삭제하고, **확인란** 컨트롤을 추가하고, 새 컨트롤 **chkMktg**에 이름을 지정합니다.

    ![확인란으로 토글 대체](./media/customize-card/add-checkbox.png)

1. 방금 업데이트한 카드를 선택합니다.

    ![카드 선택](./media/customize-card/select-card.png)

1. 오른쪽 창에서 **고급** 탭이 여전히 표시되는지 확인한 다음, **추가 옵션**을 클릭하거나 탭합니다.

    ![추가 옵션 버튼](./media/customize-card/more-options.png)

1. 카드의 **업데이트** 속성의 값을 이 식으로 변경합니다.
<br>`chkMktg.Value`

1. 해당 카드에 대한 오류 메시지의 **Y** 속성 값을 이 식으로 변경합니다.<br>
`chkMktg.Y + chkMktg.Height`

    ![새 카드에 대한 오류 메시지 선택](./media/customize-card/select-error.png)

1. **chkMktg**의 **텍스트** 속성 값을 **예**로 변경합니다.

    화면은 변경 내용을 반영하고, 오류가 해결됩니다.

    ![오류가 해결된 최종 화면](./media/customize-card/final-screen.png)

## <a name="next-steps"></a>다음 단계
이제 앱을 생성하고 갤러리, 양식 및 카드를 사용자 지정하는 방법에 대한 기본적인 이해를 마쳤으므로 [처음부터 직접 앱을 빌드](data-platform-create-app-scratch.md)할 수 있습니다.
