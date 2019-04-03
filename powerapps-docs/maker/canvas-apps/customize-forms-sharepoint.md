---
title: 캔버스 앱에서 양식 사용자 지정 | Microsoft Docs
description: PowerApps에서 캔버스 앱 형식으로 표시할 데이터를 어떤 순서와 어떤 컨트롤 방식으로 표시할지 지정합니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1a6465a00f135489d594bad75b8a25942e05dd25
ms.sourcegitcommit: f4b71ea0996603b3358377a0da21b9e4428a287c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58870934"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>PowerApps에서 캔버스 앱 양식 사용자 지정

캔버스 앱에서 **표시 양식** 컨트롤과 **편집 양식** 컨트롤을 사용자 지정하여 사용자가 데이터를 쉽게 파악하고 업데이트할 수 있도록 가장 직관적인 순서로 데이터를 표시합니다.

각 양식은 하나 이상의 카드로 구성되어 있으며, 각 카드는 데이터 원본의 특정 열에서 데이터를 표시합니다. 이 항목의 단계에 따라 양식에 표시할 카드를 지정하고, 양식 내에서 카드를 위아래로 이동할 수 있습니다.

캔버스 pps를 사용 하 여 잘 모르는 경우 [캔버스 앱 이란 무엇 인가요?](getting-started.md)합니다.

## <a name="prerequisites"></a>필수 조건

Common Data Service에서 [앱을 생성](data-platform-create-app.md)한 다음, 해당 앱에서 [갤러리를 사용자 지정](customize-layout-sharepoint.md)합니다.

## <a name="show-and-hide-cards"></a>카드 표시 및 숨기기

1. 에 로그인 [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)를 생성 하 고 사용자 지정 하는 앱을 엽니다.

1. 왼쪽된 탐색 표시줄에 입력 하거나 붙여 넣습니다 **D** 요소인 목록을 필터링 한 다음 선택 하려면 검색 표시줄에서 **DetailForm1**합니다.

    > [!div class="mx-imgBorder"]
    > ![세부 정보 화면 선택](./media/customize-forms-sharepoint/select-detailform.png)

1. 오른쪽 창의 **속성** 탭에서 **필드 편집**을 선택하여 **필드** 창을 엽니다.

    > [!div class="mx-imgBorder"]
    > ![Open 필드 창](./media/customize-forms-sharepoint/edit-fields.png)

1. 같은 필드를 숨기려면 **설명을**가리키면 나타나는 줄임표 (...)를 선택 하 고 다음을 선택 하 여 **제거**합니다.

    > [!div class="mx-imgBorder"]
    > ![필드 목록](./media/customize-forms-sharepoint/hide-fields.png)

1. 선택 하 여 필드를 보여 줍니다 **추가 필드**, 입력 또는 검색 상자, 필드의 확인란을 선택 하 고 선택한 다음 필드 이름의 처음 몇 문자를 붙여 **추가**합니다.

    > [!div class="mx-imgBorder"]
    > ![필드 목록](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>카드 재정렬

1. 에 **필드** 창으로 끕니다 합니다 **계정 이름** 필드를 필드 목록의 위쪽입니다.

    카드 **DetailForm1** 변경 내용을 반영 합니다.

    > [!div class="mx-imgBorder"]
    > ![재정렬된 카드](./media/customize-forms-sharepoint/reordered-card.png)

1. (선택 사항) 이 시퀀스에 다른 카드를 다시 정렬 합니다.

    - 계정 이름
    - 직원 수
    - 연간 수익
    - 기본 전화
    - 주소 1: 번지 1
    - 주소 1: 나머지 주소 2
    - 주소 1: 도시
    - 주소 1: 우편 번호

1. 왼쪽된 탐색 표시줄에 입력 하거나 붙여 넣습니다 **Ed** 검색 모음을 선택한 후 **EditForm1** 하 여 선택 합니다.

1. **EditForm1**의 필드가 **DetailForm1**의 필드와 일치하도록 이전 절차와 현재의 단계를 반복합니다.

## <a name="run-the-app"></a>앱 실행

1. 왼쪽된 탐색 표시줄에 입력 하거나 붙여 넣습니다 **Br** 검색 모음을 선택한 후 **BrowseScreen1** 하 여 선택 합니다.

1. F5 키를 누르거나 오른쪽 위 모서리의 **미리 보기** 아이콘을 선택하여 미리 보기 모드를 실행합니다.

    > [!div class="mx-imgBorder"]
    > ![미리 보기 아이콘](./media/customize-forms-sharepoint/open-preview.png)

1. 오른쪽 위 모서리에서 레코드를 추가 하려면 더하기 아이콘을 선택 **EditScreen1**합니다.

    > [!div class="mx-imgBorder"]
    > ![레코드 추가](./media/customize-forms-sharepoint/add-record.png)

1. 하 고 변경 내용을 저장 하 고 돌아갑니다 오른쪽 위 모서리에 있는 확인 표시 아이콘을 선택한 모든 데이터를 추가할 **BrowseScreen1**합니다.

    > [!div class="mx-imgBorder"]
    > ![레코드 저장](./media/customize-forms-sharepoint/save-record.png)

1. 화살표를 선택 하 여 해당 항목에 대 한 세부 정보 표시를 방금 만든 항목에 대 한 **DetailScreen1**합니다.

    > [!div class="mx-imgBorder"]
    > ![오른쪽 화살표](./media/customize-forms-sharepoint/right-arrow.png)

1. 오른쪽 위 모서리에서 레코드를 업데이트 하려면 편집 아이콘을 선택 **EditScreen1**합니다.

    > [!div class="mx-imgBorder"]
    > ![레코드 편집](./media/customize-forms-sharepoint/edit-record.png)

1. 하나 이상의 필드에서 정보를 변경 하 고 변경 내용을 저장 하 고 돌아갑니다 오른쪽 위 모서리에 있는 확인 표시를 클릭 **DetailScreen1**합니다.

    > [!div class="mx-imgBorder"]
    > ![변경 내용 저장](./media/customize-forms-sharepoint/save-record.png)

1. 오른쪽 위 모서리 근처 방금 업데이트 레코드를 삭제 하 고 돌아가려면 휴지통 아이콘을 선택 **BrowseScreen1**합니다.

    > [!div class="mx-imgBorder"]
    > ![레코드 삭제](./media/customize-forms-sharepoint/delete-record.png)

1. Esc 키를 눌러 (또는 왼쪽 위 모서리 근처에서 닫기 아이콘을 선택 하 여) 미리 보기 모드를 닫습니다.

## <a name="next-steps"></a>다음 단계

- 앱을 [저장하고 게시합니다](save-publish-app.md).
- 앱에서 [카드를 사용자 지정합니다](customize-card.md).