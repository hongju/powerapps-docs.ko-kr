---
title: 자습서 - 생성된 앱에서 갤러리 사용자 지정 | Microsoft Docs
description: 이 자습서에서는 갤러리에 표시되는 데이터와 PowerApps에 자동으로 생성된 앱의 다른 요소를 사용자 지정합니다.
author: AFTOwen
ms.service: powerapps
ms.topic: tutorial
ms.component: canvas
ms.date: 04/24/2018
ms.author: anneta
ms.openlocfilehash: 6206d520e8bb07c0919f482700c1af861e41109d
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>자습서: PowerApps에서 갤러리 사용자 지정
이 자습서에서는 갤러리를 사용자 지정하고 Microsoft PowerApps에서 자동으로 생성된 앱의 다른 내용을 변경합니다. 이러한 변경 내용이 없어도 사용자는 앱에서 데이터를 관리할 수 있지만 조직의 요구 사항에 맞게 사용자 지정하면 앱을 더 쉽게 사용할 수 있습니다.

> [!div class="checklist"]
> * 갤러리 레이아웃 변경
> * 갤러리에 표시되는 데이터 형식 변경
> * 사용자가 데이터를 정렬 및 검색할 수 있는 기준 열 변경
> * 화면 제목 변경
> * 스크롤 막대 표시

이 자습서는 특정 데이터 원본에서 생성된 앱으로 시작합니다. 그러나 SharePoint 목록, Excel 테이블 또는 다른 데이터 원본을 기반으로 PowerApps에서 생성하는 모든 앱에는 동일한 개념이 적용됩니다. 

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="prerequisites"></a>필수 조건
이 항목에서 일반적인 개념만을 살펴보거나 처음 [이 앱을 생성](data-platform-create-app.md)하는 경우에는 각 단계를 따를 수 있습니다.

## <a name="open-the-generated-app"></a>생성된 앱 열기
1. [PowerApps](https://web.powerapps.com)에 로그인한 다음, 왼쪽 가장자리 근처에서 **앱**을 선택합니다.

    ![PowerApps 홈페이지](./media/customize-layout-sharepoint/sign-in.png)

1. 생성한 앱을 찾고, 앱에 대한 줄임표 아이콘(**...**)을 선택한 다음, **편집**을 선택합니다.

## <a name="change-the-layout"></a>레이아웃 변경
1. 찾아보기 화면에서 계정 목록의 첫 번째 항목을 제외하고 아무 항목이나 클릭하거나 탭하여 갤러리를 선택합니다.

    갤러리가 선택되면 핸들이 있는 선택 상자가 갤러리를 둘러쌉니다.

    ![선택한 갤러리](./media/customize-layout-sharepoint/select-gallery.png)

1. 오른쪽 가장자리 근처에서 **계정**을 선택하여 **데이터** 창을 엽니다.

    ![**데이터** 창 열기](./media/customize-layout-sharepoint/open-data-pane.png)

1. **데이터** 창의 **레이아웃** 아래에서 옵션 목록을 엽니다.

    ![레이아웃 옵션 표시](./media/customize-layout-sharepoint/show-layouts.png)

1. 옵션 목록에서 제목만 표시하는 옵션을 선택합니다.

    ![제목 전용 레이아웃 선택](./media/customize-layout-sharepoint/choose-layout.png)

1. **데이터** 창에서 제목에 대한 옵션 목록을 엽니다.

    ![제목 전용 레이아웃 선택](./media/customize-layout-sharepoint/show-title-options.png)

1. 옵션 목록에서 **계정 이름(이름)** 을 선택한 다음, **데이터** 창을 닫습니다.

    갤러리에 각 계정의 이름이 표시됩니다.

    ![최종 갤러리](./media/customize-layout-sharepoint/final-gallery.png)

## <a name="change-the-sort-and-search-columns"></a>정렬 및 검색 열 변경
1. 이전 섹션에서 설명한 대로 갤러리를 선택합니다.

    ![갤러리 선택](./media/customize-layout-sharepoint/select-gallery-title.png)

2. 왼쪽 위 모서리 근처에서 속성 목록에 **항목**이 표시되는지 확인합니다.

    ![항목 속성](./media/customize-layout-sharepoint/items-property.png)

    이 속성의 값은 수식 입력줄에 표시됩니다. 이 속성을 설정하여 갤러리의 데이터 원본뿐 아니라 사용자가 데이터를 정렬하고 검색할 수 있는 기준 열도 지정합니다.

1. 이 수식을 복사한 다음, 수식 입력줄에 붙여넣습니다.

    ```SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, Descending, Ascending))```

    이 수식을 사용하여 다음을 확인할 수 있습니다.

    - 검색 창에 하나 이상의 문자가 있는 경우 갤러리에는 사용자가 입력한 텍스트가 포함된 계정 이름만 표시됩니다.
    - 사용자가 정렬 아이콘을 선택하면 갤러리는 사용자가 아이콘을 선택하는 횟수에 따라 오름차순 또는 내림차순의 계정 이름별로 사전순으로 정렬됩니다.

    이러한 함수 및 다른 함수에 대한 자세한 내용은 [수식 참조](formula-reference.md)를 참조하세요.

## <a name="test-sorting-and-searching"></a>정렬 및 검색 테스트
1. F5 키를 누르거나 오른쪽 위 모서리 근처에 있는 [재생] 단추를 선택하여 미리 보기 모드를 엽니다.

    ![미리 보기 모드 열기](./media/customize-layout-sharepoint/open-preview.png)

1. 브라우저 화면의 오른쪽 위 모서리 근처에서 정렬 아이콘을 한 번 이상 선택하여 사전순 정렬 순서를 오름차순과 내림차순 중에서 변경합니다.

    ![정렬 아이콘 테스트](./media/customize-layout-sharepoint/sort-button.png)

1. 검색 상자에 **k**를 입력하여 입력한 문자를 포함하는 계정 이름만 표시합니다.

    ![검색 표시줄 테스트](./media/customize-layout-sharepoint/test-filter.png)

1. 검색 창에서 모든 텍스트를 제거한 다음, Esc 키를 누르거나 오른쪽 위 모서리 근처에서 닫기 아이콘을 선택하여 미리 보기 모드를 닫습니다.

## <a name="change-the-screen-title"></a>화면 제목 변경
1. 화면의 제목을 클릭하거나 탭하여 선택합니다.

    ![화면 제목 선택](./media/customize-layout-sharepoint/select-title.png)

1. 속성 목록에 **텍스트**가 표시되는지 확인하고 수식 입력줄에서 **계정**을 **찾아보기**(큰따옴표 유지)로 바꿉니다.

    ![화면 제목 업데이트](./media/customize-layout-sharepoint/change-screen-title.png)

    화면은 변경 내용을 반영합니다.

    ![새 화면 제목](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scroll-bar"></a>스크롤 막대 표시
사용자가 터치 스크린 및 마우스 휠을 가지고 있지 않은 경우 사용자가 갤러리를 마우스로 가리키면 스크롤 막대가 표시되도록 갤러리를 구성합니다. 이렇게 하면 화면에 모든 계정을 한 번에 표시할 수 없는 경우에도 모든 계정을 표시할 수 있습니다.

1. 첫 번째 절차에서 설명한 대로 갤러리를 선택합니다.

    ![갤러리 선택](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. **갤러리** 탭에서 **스크롤 막대 표시**를 선택하고 해당 속성 값이 **true**로 변경되었는지 확인합니다. 

    ![스크롤 막대 표시](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>다음 단계
이 자습서에서는 갤러리를 사용자 지정하고 생성된 앱에서 레코드를 찾아보기 위한 기본 화면의 다른 내용을 변경했습니다. 세부 정보를 표시하고 계정을 만들거나 업데이트하는 기본 화면을 사용자 지정할 수도 있습니다. 찾아보기 화면에는 갤러리가 포함되는 것처럼 앱의 다른 두 화면에는 양식이 포함됩니다. 예를 들어 양식이 표시하는 데이터 형식 및 순서를 변경할 수 있습니다.

> [!div class="nextstepaction"]
> [양식 사용자 지정](customize-forms-sharepoint.md)