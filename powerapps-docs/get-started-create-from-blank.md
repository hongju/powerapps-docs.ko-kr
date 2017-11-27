---
title: "처음부터 앱 만들기 | Microsoft Docs"
description: "비즈니스에 활력을 넣는 일상적인 데이터를 관리하도록 각 UI 요소와 동작을 구성하여 처음부터 앱을 만듭니다."
services: 
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: karthikb
ms.openlocfilehash: f489310ee7fc12471c2250ee10d96a9dd2f0aa55
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="create-an-app-from-scratch"></a>앱을 처음부터 만들기
다양한 데이터 원본 중 하나를 사용하고 원하는 경우 더 많은 원본을 추가하여 처음부터 사용자 고유 앱을 만듭니다. 정확한 목표와 워크플로에 대한 결과를 최적화할 수 있도록 각 UI 요소의 동작과 모양을 지정합니다. 이 접근 방식은 [앱을 자동으로 생성](get-started-create-from-data.md)하는 것보다 훨씬 시간 집약적이지만, 노력한 앱 제작자는 요구 사항에 맞는 최고의 앱을 빌드할 수 있습니다.

**참고**: 이 토픽은 Windows용 PowerApps Studio용으로 작성되었지만, [브라우저에서 PowerApps를 여는](create-app-browser.md) 경우 단계가 유사합니다.

이 자습서를 따라 두 화면을 포함하는 앱을 만듭니다. 한 화면에서 사용자는 레코드 집합을 통해 찾아볼 수 있습니다.

![사용자가 데이터의 집합을 통해 스크롤할 수 있는 화면](./media/get-started-create-from-blank/first-screen-final.png)

다른 화면에서 사용자는 한 레코드를 만들고 한 레코드에서 하나 이상의 필드를 업데이트하거나 전체 레코드를 삭제할 수 있습니다.

![사용자가 데이터를 추가하거나 업데이트할 수 있는 화면](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="prerequisites"></a>필수 조건
자습서에서 일반적인 개념을 살펴볼 수 있습니다. 또는 이 단계를 완료하면 자습서의 내용을 정확하게 따를 수 있습니다.

1. 이 데이터를 복사한 다음 Excel 파일에 붙여넣습니다.
   
   | 시작 날짜 | 시작 시간 | 자원 1 | 자원 2 |
   | --- | --- | --- | --- |
   | 토요일 |오전 10시 정오 |Vasquez |Kumashiro |
   | 토요일 |정오~오후 2시 |Ice |Singhal |
   | 토요일 |오후 2시~4시 |Myk |Mueller |
   | 일요일 |오전 10시 정오 |Li |Adams |
   | 일요일 |오전 10시 정오 |Singh |Morgan |
   | 일요일 |오전 10시 정오 |Batye |Nguyen |
2. PowerApps에서 정보를 구문 분석할 수 있도록 해당 데이터를 **Schedule**이라는 테이블로 형식을 지정합니다.
   
    자세한 내용은 [워크시트에서 Excel 테이블 만들기](https://support.office.com/en-us/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664)를 참조하세요.
3. **eventsignup.xls** 이름으로 저장한 다음, OneDrive와 같은 [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)으로 업로드합니다.
4. PowerApps를 처음 접하는 경우:
   
   * [컨트롤을 추가하고 해당 속성을 설정](add-configure-controls.md)하는 방법을 배우며, 컨트롤이 표시되고 동작하는 방법을 설명합니다.
   * [화면을 추가하고 이름을 변경](add-screen-context-variables.md)하는 방법을 배웁니다.

## <a name="create-a-blank-app-and-connect-to-data"></a>새 앱을 만들고 데이터에 연결
1. PowerApps Studio에서 (화면의 왼쪽 가장자리에 있는) **파일** 메뉴에서 **새로 만들기**를 클릭하거나 탭합니다.
   
    ![파일 메뉴의 새 옵션](./media/get-started-create-from-blank/file-new.png)
2. **비어 있는 앱** 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.
   
    ![데이터에서 앱을 만드는 옵션](./media/get-started-create-from-blank/create-from-blank.png)
3. 메시지가 표시되면 둘러보기 소개를 사용하여 PowerApps의 주요 영역을 이해합니다(또는 **건너뛰기**를 클릭하거나 탭하기).
   
    ![둘러보기](./media/get-started-create-from-blank/quick-tour.png)
   
    화면의 왼쪽 위 모서리에 있는 물음표 아이콘을 클릭하거나 탭한 후 **소개 둘러보기**를 클릭하거나 탭하여 둘러보기를 나중에 항상 이용할 수 있습니다.
4. 왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.
   
    ![보기 토글](./media/get-started-create-from-blank/toggle-view.png)
5. 오른쪽 창에서 **데이터 원본 추가**를 클릭하거나 탭합니다.
   
    ![데이터 원본 추가](./media/get-started-create-from-blank/add-data-source.png)
6. 다음의 단계 중 하나를 수행합니다.
   
   * 클라우드 저장소 계정에 대해 이미 연결되어 있는 경우, 클릭하거나 탭합니다.
   * 클라우드 저장소 계정에 대한 연결이 없는 경우, **연결 추가**를 클릭하거나 탭하고, 계정 형식을 클릭하거나 탭하거나, 또는 **연결**을 클릭하거나 탭한 다음, (메시지가 표시된 경우) 자격 증명을 제공합니다.
7. **Excel 파일 선택**에서 **eventsignup.xlsx**를 찾아 클릭하거나 탭합니다.
   
    ![사용할 Excel 파일 지정](./media/get-started-create-from-blank/select-excel-file.png)
8. **표 선택**에서 **일정** 확인란을 선택한 다음 **연결**을 클릭하거나 탭합니다.
   
    ![Excel에서 사용할 표 지정](./media/get-started-create-from-blank/select-table.png)
   
    오른쪽 창의 **데이터 원본** 탭은 앱에 추가된 데이터 원본을 보여 줍니다.
   
    ![연결된 데이터 원본 표시](./media/get-started-create-from-blank/data-connect.png)
   
    이 자습서에는 데이터 원본이 하나만 필요하지만 나중에 더 많은 데이터 원본을 추가할 수 있습니다.

## <a name="show-the-data"></a>데이터 표시
1. **홈** 탭에서 **새 화면**을 클릭하거나 탭한 다음, **목록 화면**을 클릭하거나 탭합니다.
   
    ![제목, 부제목 및 본문 요소가 있는 레이아웃 추가](./media/get-started-create-from-blank/add-gallery.png)
   
    화면에는 검색 상자와 **[갤러리](controls/control-gallery.md)** 컨트롤 등의 여러 기본 컨트롤이 추가됩니다. 갤러리는 검색 상자에서 전체 화면을 처리합니다.
2. 화살표를 제외한 갤러리의 어디에서나(예: 검색 상자 아래에서 바로) 클릭하거나 탭합니다.
   
    ![갤러리 선택](./media/get-started-create-from-blank/select-gallery.png)
3. 오른쪽 창에서 **레이아웃** 목록을 연 다음 제목, 부제목 및 본문을 보여주는 옵션을 클릭하거나 탭합니다.
   
    ![갤러리 선택](./media/get-started-create-from-blank/select-layout.png)
4. 속성 목록에서 **[항목](controls/properties-core.md)**을 클릭하거나 탭하여 수식 입력줄에 붙여넣습니다.
   
    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Volunteer_x0020_1"), "Volunteer_x0020_1", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**
   
    속성 목록이 있는지 확실하지 않은 경우 [컨트롤 추가 및 구성](add-configure-controls.md)을 참조하세요.
   
    **참고:** 공백이 있는 열 이름이 포함된 Excel 또는 SharePoint 데이터 원본의 경우 PowerApps는 공백을 **"\_x0020\_"**으로 바꿉니다. 이 예제에서는 열 **"Volunteer 1"**은 **"Volunteer_x0020_1"**에서 수식으로 나타납니다.
   
    이 갤러리는 **일정** 표에서 데이터를 표시합니다.
   
    ![기본적으로 갤러리의 일정 데이터](./media/get-started-create-from-blank/show-data-default.png)
   
    검색 상자는 사용자가 입력한 텍스트를 기반으로 갤러리를 필터링할 수 있습니다. 사용자가 검색 상자에 하나 이상의 문자를 입력하는 경우, 갤러리는 **자원 봉사 1** 필드에 사용자가 입력한 텍스트를 포함한 이 레코드만을 표시합니다.
   
    정렬 단추는 **자원 봉사 1** 열의 데이터를 기반으로 레코드를 정렬할 수 있습니다. 사용자가 해당 단추를 클릭하거나 탭하면, 정렬 순서가 오름차순과 내림차순 사이에 전환됩니다.
   
    이 수식에는 **Sort**, **If**, **IsBlank**, **Filter** 및 **Text** 함수가 포함됩니다. 이 함수를 비롯한 기타 함수에 대한 자세한 내용은 [수식 참조](formula-reference.md)를 참조하세요.
5. 검색 상자에 **i**를 입력하고 정렬 단추를 한 번(또는 홀수 번) 클릭하거나 누릅니다.
   
    갤러리에 다음 결과가 표시됩니다.
   
    ![갤러리 정렬 및 필터링](./media/get-started-create-from-blank/sort-filter.png)
   
    **[정렬](functions/function-sort.md)**, **[필터](functions/function-filter-lookup.md)** 및 [다른 함수](formula-reference.md)에 대한 자세한 내용
6. 컨트롤을 클릭하거나 탭하여 화면 맨 위의 **[레이블](controls/control-text-box.md)** 컨트롤을 선택합니다.
   
    ![제목 표시줄 선택](./media/get-started-create-from-blank/select-title-bar.png)
7. 속성 목록에서 **[텍스트](controls/properties-core.md)**를 클릭하거나 탭하여 이 텍스트를 복사한 후 수식 입력줄에 붙여넣습니다.<br>
   **"레코드 보기"**
   
    ![제목 표시줄 변경](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-changescreen-and-its-banner"></a>ChangeScreen 및 배너 만들기
1. **Screen1**을 삭제하고 **Screen2**의 이름을 **ViewScreen**으로 바꿉니다.
   
    ![화면 이름 바꾸기](./media/get-started-create-from-blank/rename-screen.png)
2. 화면을 추가하고 이름을 **ChangeScreen**으로 변경합니다.
   
    ![화면 추가 및 이름 바꾸기](./media/get-started-create-from-blank/add-screen.png)
3. **삽입** 탭에서 **텍스트**, **[레이블](controls/control-text-box.md)**을 차례로 클릭하거나 탭합니다.
4. 방금 추가한 **레이블** 컨트롤을 구성합니다.
   
   * **Text** 속성을 다음 수식으로 설정합니다.
     <br>**"레코드 변경"**
   * **Fill** 속성을 다음 수식으로 설정합니다.
     <br>**RGBA(62, 96, 170, 1)**.
   * **Color** 속성을 다음 수식으로 설정합니다.
     <br>**RGBA(255, 255, 255, 1)**
   * **Align** 속성을 **Center**로 설정합니다.
   * **X** 속성을 **0**으로 설정합니다.
   * **Width** 속성을 **640**으로 설정합니다.
     
     **레이블** 컨트롤은 변경 사항을 반영합니다.
     
     ![배너가 있는 ChangeScreen](./media/get-started-create-from-blank/change-screen-blank.png)

## <a name="add-and-configure-a-form"></a>양식 추가 및 구성
1. **삽입** 탭에서 **양식**, **편집**을 차례로 클릭하거나 탭합니다.
2. 대부분의 화면을 포함하도록 양식을 이동하고 양식 크기를 조정합니다.
   
    ![양식 추가](./media/get-started-create-from-blank/add-form.png)
   
    이미 양식을 추가하고 제거하지 않는 경우 기본적으로 양식 이름은 **Form1**입니다. 이 경우 양식 양식의 이름을 **Form1**으로 변경합니다.
3. **Form1**의 **[DataSource](controls/control-form-detail.md)** 속성을 **Schedule**로 설정합니다.
4. **Form1**의 **Item** 속성을 다음 식으로 설정합니다.
   <br>**BrowseGallery1.Selected**
5. 오른쪽 창에서 각 필드의 확인란을 클릭하거나 탭하여 표시합니다.
   
    ![양식에 필드 표시](./media/get-started-create-from-blank/schedule-checkbox.png)
6. 양식의 맨 나래 근처에서 **사용자 지정 카드 추가**를 클릭하거나 탭합니다.
   
    ![사용자 지정 카드 추가](./media/get-started-create-from-blank/add-custom-card.png)
7. 새 카드에서 **[레이블](controls/control-text-box.md)** 컨트롤을 추가합니다.
8. 새 컨트롤의 **[AutoHeight](controls/control-text-box.md)** 속성을 **true**로 설정하고 해당 **[Text](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.
   <br>**Form1.Error**
   
    레이블은 양식에서 오류를 표시합니다.
9. 왼쪽 탐색 모음에서 선택하려면 **ChangeScreen**의 썸네일을 클릭하거나 탭합니다.
10. **삽입** 탭에서 **아이콘**을 클릭하거나 탭하고 **뒤로 화살표** 추가 옵션을 클릭하거나 탭한 다음, 화살표를 화면의 왼쪽 아래 모서리로 이동합니다.
11. 화살표의 **[OnSelect](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.
    
     **ResetForm(Form1);Navigate(ViewScreen,ScreenTransition.None)**
    
      사용자가 화살표를 클릭하거나 탭하면 **[Navigate](functions/function-navigate.md)** 함수는 **ViewScreen**을 엽니다.
12. 양식에서 **[단추](controls/control-button.md)** 컨트롤을 추가하고 단추의 **[텍스트](controls/properties-core.md)** 속성을 **"저장"**으로 설정합니다.
    
     ![저장 단추 추가](./media/get-started-create-from-blank/add-save-button.png)  
13. 단추의 **[OnSelect](controls/properties-core.md)** 속성을 이 수식에 설정::
    
    **SubmitForm(Form1); If(Form1.ErrorKind = ErrorKind.None, Navigate(ViewScreen, ScreenTransition.None))**
    
    사용자가 단추를 클릭하거나 탭하면 **[SubmitForm](functions/function-form.md)** 함수는 데이터 원본에 변경 내용을 저장하며 **ViewScreen**이 다시 나타납니다.  
14. 화면 맨 아래에서 다른 단추를 추가하고, 해당 **[텍스트](controls/properties-core.md)** 속성을 **"제거"**로 설정하고, 해당 **[OnSelect](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.
    
    **Remove(Schedule,BrowseGallery1.Selected);<br>If(IsEmpty(Errors(Schedule)),Navigate(ViewScreen,ScreenTransition.None))**
    
    사용자가 이 단추를 클릭하거나 탭하면 **[제거](functions/function-remove-removeif.md)** 함수는 레코드를 제거하면 **ViewScreen**이 다시 나타납니다.
15. **Remove** 단추의 **[Visible](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.
    <br>**Form1.Mode=FormMode.Edit**
    
    이 단계는 사용자가 레코드를 만들 때 **제거** 단추를 숨깁니다.
    
    **ChangeScreen**은 이 예제와 일치합니다.
    
    ![Final ChangeScreen](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="set-navigation-from-viewscreen"></a>ViewScreen에서 탐색 설정
1. 왼쪽 탐색 모음에서 **ViewScreen**의 썸네일을 클릭하거나 탭합니다.
   
    ![ViewScreen 열기](./media/get-started-create-from-blank/select-viewscreen.png)
2. 갤러리의 첫 번째 레코드에 대해 **다음 화살표**를 클릭하거나 탭합니다.
   
    ![다음 화살표](./media/get-started-create-from-blank/next-arrow.png)
3. 해당 화살표의 **[OnSelect](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.
   
    **Navigate(ChangeScreen,ScreenTransition.None)**
4. 오른쪽 위 모서리에서 더하기(+) 아이콘을 클릭하거나 탭합니다.
   
    ![레코드 추가](./media/get-started-create-from-blank/add-record.png)
5. 선택된 아이콘의 **[OnSelect](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.
   
    **NewForm(Form1);Navigate(ChangeScreen,ScreenTransition.None)**`
   
     사용자가 이 아이콘을 클릭하거나 탭하면 **ChangeScreen**은 비어 있는 각 필드를 표시하며, 사용자는 레코드를 보다 쉽게 만들 수 있습니다.

## <a name="run-the-app"></a>앱 실행
이 섹션에서 보여주는 단계처럼, 앱을 사용자 지정할 때 미리 보기 모드에서 앱을 실행하여 변경 내용을 테스트할 수 있습니다.

1. 왼쪽 탐색 모음에서 상단 썸네일을 클릭하거나 탭하여 **ViewScreen**을 선택합니다.
   
    ![ViewScreen 선택](./media/get-started-create-from-blank/select-viewscreen.png)
2. F5를 눌러 (또는 오른쪽 위 모서리의 **미리 보기** 아이콘을 클릭하거나 탭하기) 미리 보기 모드를 엽니다.
   
    ![미리 보기 모드 열기](./media/get-started-create-from-blank/open-preview.png)
3. 레코드에 대한 다음 화살표를 클릭하거나 탭하여 해당 레코드에 대한 세부 정보를 표시합니다.
4. **ChangeScreen**에서 하나 이상의 필드에서 정보를 변경한 후, **저장**을 클릭하거나 탭하여 변경 내용을 저장하거나 **제거**를 클릭하거나 탭하여 레코드를 제거합니다.
5. Esc 키를 눌러 (또는 제목 표시줄 아래의 닫기 아이콘을 클릭하거나 탭하기) 미리 보기 모드를 닫습니다.
   
    ![미리 보기 모드 닫기](./media/get-started-create-from-blank/close-preview.png)

## <a name="next-steps"></a>다음 단계
* 다른 장치에서 실행할 수 있도록 앱을 클라우드에 저장하려면 Ctrl-S를 누릅니다.
* 다른 사용자가 앱을 실행할 수 있도록 [앱을 공유](share-app.md)하세요.
* [갤러리](add-gallery.md), [양식](add-form.md) 및 [수식](working-with-formulas.md)에 대한 자세한 내용을 배웁니다.

