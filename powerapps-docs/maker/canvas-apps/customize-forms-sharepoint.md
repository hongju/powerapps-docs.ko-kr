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
ms.openlocfilehash: bb6f8edb35bd6f19bff06516f6fb9d22de1320a0
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42852672"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>PowerApps에서 캔버스 앱 양식 사용자 지정

캔버스 앱에서 **표시 양식** 컨트롤과 **편집 양식** 컨트롤을 사용자 지정하여 사용자가 데이터를 쉽게 파악하고 업데이트할 수 있도록 가장 직관적인 순서로 데이터를 표시합니다.

각 양식은 하나 이상의 카드로 구성되어 있으며, 각 카드는 데이터 원본의 특정 열에서 데이터를 표시합니다. 이 항목의 단계에 따라 양식에 표시할 카드를 지정하고, 양식 내에서 카드를 위아래로 이동할 수 있습니다.

PowerApps에 대해 잘 모르는 경우 [PowerApps 소개](getting-started.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건

Common Data Service에서 [앱을 생성](data-platform-create-app.md)한 다음, 해당 앱에서 [갤러리를 사용자 지정](customize-layout-sharepoint.md)합니다.

## <a name="show-and-hide-cards"></a>카드 표시 및 숨기기

1. [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인합니다.

    ![PowerApps 사이트의 홈 페이지](./media/customize-forms-sharepoint/sign-in.png)


1. 사용자 지정하여 생성한 앱을 엽니다.

1. 왼쪽 탐색 모음의 검색 창에서 **D**를 입력하거나 붙여넣어 요소 목록을 필터링한 다음, **DetailForm1**을 클릭하거나 탭하여 선택합니다.

    ![세부 정보 화면 선택](./media/customize-forms-sharepoint/select-detailform.png)

1. 오른쪽 창에서 **데이터** 탭을 클릭하거나 탭하여 **데이터** 창을 표시합니다.

    ![데이터 창 표시](./media/customize-forms-sharepoint/show-data-pane.png)

1. **데이터** 창에서 **기본 연락처**, **설명** 및 **주소 1: 나머지 주소 2** 확인란의 선택을 취소하여 해당 필드를 숨깁니다.

    ![필드 목록](./media/customize-forms-sharepoint/hide-fields.png)

1.  **데이터** 창에서 **주소 1: 우편 번호** 확인란을 선택하여 해당 필드를 표시합니다.

    ![필드 목록](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>카드 재정렬
1. **데이터** 창에서 **거래처 이름** 필드를 필드 목록의 맨 위로 끕니다.

    ![카드 이동](./media/customize-forms-sharepoint/move-card.png)

    **DetailForm1**의 카드에 동일한 변경 내용이 반영됩니다.

    ![재정렬된 카드](./media/customize-forms-sharepoint/reordered-card.png)

1. 다른 카드를 다음 순서로 다시 정렬합니다.

    - 거래처 이름
    - 주소 1: 나머지 주소
    - 주소 1: 구/군/시
    - 주소 1: 우편 번호
    - 직원 수
    - 연간 수익

1. 왼쪽 탐색 모음의 검색 창에서 **Ed**를 입력하거나 붙여넣은 다음, **EditForm1**을 클릭하거나 탭하여 선택합니다.

1. **EditForm1**의 필드가 **DetailForm1**의 필드와 일치하도록 이전 절차와 현재의 단계를 반복합니다.

## <a name="run-the-app"></a>앱 실행
1. 왼쪽 탐색 모음에서 **Br**을 입력하거나 붙여넣어 목록을 필터링한 다음, **BrowseScreen1**을 클릭하거나 탭하여 선택합니다.

2. F5 키를 누르거나 오른쪽 위 모서리의 **미리 보기** 아이콘을 선택하여 미리 보기 모드를 실행합니다.

    ![미리 보기 아이콘](./media/customize-forms-sharepoint/open-preview.png)

3. 오른쪽 위 모서리에서 더하기 아이콘을 클릭하거나 탭하여 **EditScreen1**의 레코드를 추가합니다.

    ![레코드 추가](./media/customize-forms-sharepoint/add-record.png)

4. 원하는 데이터를 모두 추가한 다음, 오른쪽 위 모서리에 있는 확인 표시 아이콘을 클릭하거나 탭하여 변경 내용을 저장하고, **BrowseScreen1**로 돌아갑니다.

    ![레코드 저장](./media/customize-forms-sharepoint/save-record.png)

5. 방금 생성한 항목의 화살표를 클릭하거나 탭하여 해당 항목에 대한 세부 정보를 **DetailScreen1**에 표시합니다.  

    ![오른쪽 화살표](./media/customize-forms-sharepoint/right-arrow.png)

6. 오른쪽 위 모서리에서 편집 아이콘을 클릭하거나 탭하여 **EditScreen1**의 해당 레코드를 업데이트합니다.

    ![레코드 편집](./media/customize-forms-sharepoint/edit-record.png)

7. 하나 이상의 필드에서 정보를 변경한 다음 오른쪽 위 모서리의 확인 표시를 클릭하거나 탭하여 SharePoint 목록에서 변경 내용을 저장하고 **DetailScreen1**으로 돌아옵니다.  

    ![변경 내용 저장](./media/customize-forms-sharepoint/save-record.png)

8. 오른쪽 위 모서리에서 휴지통 아이콘을 클릭하거나 탭하여 방금 업데이트한 레코드를 삭제하고 **BrowseScreen1**으로 돌아옵니다.

    ![레코드 삭제](./media/customize-forms-sharepoint/delete-record.png)

9. Esc 키를 누르거나 왼쪽 위 모서리의 닫기 아이콘을 클릭하거나 탭하여 미리 보기 모드를 닫습니다.

## <a name="next-steps"></a>다음 단계
- 앱을 [저장하고 게시합니다](save-publish-app.md).
- 앱에서 [카드를 사용자 지정합니다](customize-card.md).
