---
title: "갤러리 레이아웃 사용자 지정| Microsoft Docs"
description: "표시하려는 컨트롤, 각 컨트롤에서 표시하려는 필드, 그리고 레코드를 정렬하고 검색하기 위해 사용할 열을 지정합니다."
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/02/2017
ms.author: sharik
ms.openlocfilehash: c581abad70012eb66413a31bd765437df69b7a70
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="customize-a-gallery-layout-in-powerapps"></a>PowerApps에서 갤러리 레이아웃 사용자 지정
PowerApps에서 자동으로 앱을 생성한 후 기본으로 표시되는 찾아보기 화면을 사용자 지정합니다. 사용할 레이아웃, 표시할 열, 레코드를 정렬하고 필터링할 때 사용할 열을 지정합니다.

* 자동으로 앱을 생성하는 방법에 대한 정보는 [SharePoint 목록에서 데이터를 관리하는 앱 생성](app-from-sharepoint.md)을 참조하세요.
* PowerApps에 대해 잘 모르는 경우 [PowerApps 소개](getting-started.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건
자습서에서 일반적인 개념을 살펴볼 수 있습니다. 또는 이 단계를 완료하면 자습서의 내용을 정확하게 따를 수 있습니다.

1. PowerApps에서 SharePoint로 [연결을 생성](connect-to-sharepoint.md)합니다.
2. 이러한 열을 포함하는 **AppGen**이라는 SharePoint 목록을 만듭니다.
   
    ![SharePoint의 샘플 열](./media/customize-layout-sharepoint/list-columns.png)
3. 방금 만든 목록에 이러한 항목을 추가합니다.
   
    ![샘플 데이터](./media/customize-layout-sharepoint/sample-data.png)
4. 방금 만든 목록에 기반한 [앱을 자동으로 생성](app-from-sharepoint.md)합니다.
5. 왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.
   
    ![보기 토글](./media/customize-layout-sharepoint/toggle-view.png)

## <a name="customize-the-gallery"></a>갤러리 사용자 지정
1. 왼쪽 탐색 모음에서 맨 위의 썸네일을 클릭하거나 탭하여 **BrowseScreen1**이 선택되었는지 확인합니다.
   
    ![BrowseScreen1의 축소판 그림](./media/customize-layout-sharepoint/browse-thumbnail.png)
   
    **BrowseScreen1**은 SharePoint 목록에서 각 항목의 **AccountID** 및 **Title**을 보여 줍니다.
   
    ![찾아보기 화면이 제목과 계정 ID를 표시합니다.](./media/customize-layout-sharepoint/browse-accountid.png)
   
    다음으로 각 항목에 대한 **OrderDate**가 **AccountID** 대신 표시되도록 지정합니다.
2. 화면의 첫 번째 항목에 대한 **AccountID**를 클릭하거나 탭합니다.
   
    UI 요소(컨트롤이라고 함)를 클릭하거나 탭하면 선택이 되고 크기 조정 핸들이 있는 선택 테두리가 컨트롤 주변에 표시됩니다.
   
    ![첫 번째 항목의 본문 선택](./media/customize-layout-sharepoint/select-body.png)
3. 오른쪽 창에서 **Title1** 목록을 연 다음 **OrderDate**를 클릭하거나 탭합니다.
   
    ![제목 표시](./media/customize-layout-sharepoint/bind-data.png)
   
    **BrowseScreen1**는 변경 내용을 반영합니다.
   
    ![날짜가 있는 레이아웃](./media/customize-layout-sharepoint/browse-dates.png)

갤러리에 대한 자세한 내용은 [PowerApps에서 항목 목록 표시](add-gallery.md)를 참조하세요.

## <a name="set-the-sort-and-search-columns"></a>열 정렬 및 검색 설정
1. 첫 번째를 제외한 모든 레코드를 클릭하거나 탭하여 **갤러리** 컨트롤을 선택합니다.
   
    ![갤러리 선택](./media/customize-layout-sharepoint/select-gallery.png)
2. 왼쪽 위 모서리 근처에서 속성 목록이 **항목**을 표시하는지 확인합니다.
   
    ![항목 속성](./media/customize-layout-sharepoint/items-property.png)
   
    수식 입력줄에 표시되는 이 속성의 값은 화면에 표시되는 데이터의 원본뿐만 아니라 필터 및 정렬 열도 결정합니다.
   
    예를 들어 수식 입력줄은 기본으로 이 수식을 포함할 수 있습니다.
   
    ![기본 항목 속성](./media/customize-layout-sharepoint/default-items.png)
   
    이 수식에 따라 사용자는 **AccountID** 열에서 하나 이상의 문자로 시작하는 레코드만 표시할 수 있습니다.
   
    ![기본 검색 열](./media/customize-layout-sharepoint/default-search.png)
   
    예를 들어, 사용자가 검색 창에 "A"를 입력하면 화면에 유럽어에 대한 레코드가 표시됩니다. 해당 레코드의 제목은 검색 조건과 일치하지 않지만 계정 ID는 일치합니다. 이 절차의 후반에서 **Title** 열로 레코드를 필터링하도록 수식을 변경합니다.
   
    생성된 앱에서 사용자는 오른쪽 위 모서리 근처의 정렬 단추를 클릭하거나 탭하여 사전 오름차순 또는 내림차순으로 레코드를 정렬할 수 있습니다. 이 수식은 레코드가 **AccountID** 열을 기반으로 정렬되도록 지정합니다.
   
    ![기본 정렬 열](./media/customize-layout-sharepoint/default-sort.png)
   
    이 절차의 후반에서 **제목** 열로 대신 레코드를 정렬하도록 수식을 변경합니다.
3. 수식 입력줄에서 **AccountID**의 두 인스턴스를 **Title**(두 번째 인스턴스의 큰따옴표 포함)로 대체합니다.
   
    이제 수식 입력줄은 이 예제와 비슷한 수식을 포함해야 합니다.<br>
    **SortByColumns(Filter(AppGen, StartsWith(Title, TextSearchBox1.Text)), "Title", If(SortDescending1, Descending, Ascending))**
   
    **참고**: 이전에 수행한 작업에 따라 **TextSearchBox** 다음에 나타나는 숫자는 더 높을 수 있습니다. 하지만 수식은 여전히 예상대로 작동해야 합니다.

## <a name="test-sorting-and-searching"></a>정렬 및 검색 테스트
1. F5 키를 눌러 (또는 오른쪽 위 모서리의 재생 단추를 클릭하거나 탭하기) 미리 보기 모드를 엽니다.
   
    ![미리 보기 모드 열기](./media/customize-layout-sharepoint/open-preview.png)
2. **BrowseScreen1**의 오른쪽 위 모서리 근처에서 정렬 단추를 한 번 이상 클릭하거나 탭하여 알파벳 정렬을 오름차순과 내림차순 중에서 변경합니다.
   
    ![정렬 단추 테스트](./media/customize-layout-sharepoint/test-sort.png)
3. 검색 상자에서 한 글자 이상을 입력하여 입력한 글자로 시작하는 제목의 레코드만 표시하도록 합니다.
   
    ![검색 표시줄 테스트](./media/customize-layout-sharepoint/test-search.png)
4. 검색 표시줄에서 모든 텍스트를 삭제한 다음 Esc키를 눌러 (또는 PowerApps의 제목 표시줄 *아래*의 닫기 아이콘을 클릭하거나 탭하기) 미리 보기 모드를 닫습니다.
   
    ![미리 보기 모드 닫기](./media/customize-layout-sharepoint/close-preview.png)

## <a name="change-the-title-of-the-screen"></a>화면 제목 변경
1. 화면의 제목을 클릭하거나 탭하여 선택합니다.
   
    ![화면 제목 선택](./media/customize-layout-sharepoint/select-screen-title.png)
2. 속성 목록이 **텍스트**를 표시하는지 확인한 후 수식 표시줄에 큰따옴표와 함께 원하는 이름을 입력합니다.
   
    ![화면 제목 업데이트](./media/customize-layout-sharepoint/update-screen-title.png)
   
    **BrowseScreen1**는 변경 내용을 반영합니다.
   
    ![새 화면 제목](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="next-steps"></a>다음 단계
* Ctrl-S를 눌러 변경 내용을 저장합니다.
* 양식이 표시하는 필드를 표시하고 숨기고 다시 정렬하여 앱에서 [양식을 사용자 지정합니다](customize-forms-sharepoint.md).

