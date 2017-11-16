이 항목에서는 생성된 앱을 자세히 살펴보고 앱 동작을 정의하는 화면과 컨트롤을 검토합니다. 세부 정보를 모두 다루지는 않겠지만 이 앱의 작동 방식에 대해 자세히 알아보면 앱을 직접 빌드할 수 있습니다. 이후의 항목에서는 화면과 컨트롤을 사용하는 수식을 살펴보겠습니다.

## <a name="run-the-app-in-preview-mode"></a>미리 보기 모드에서 앱 실행
오른쪽 위를 클릭하거나 탭하여 ![앱 미리 보기 시작 화살표](./media/learning-case-app-explore-controls/f5-arrow-sm.png) 앱을 실행합니다. 앱을 탐색하면 엔터티의 데이터를 포함하고 있고 양호한 기본 환경을 제공하고 있음을 알 수 있습니다.

![미리 보기 모드에서 앱 실행](./media/learning-case-app-explore-controls/run-app.png)

## <a name="understanding-controls-in-powerapps"></a>PowerApps 컨트롤 이해
컨트롤은 단순히 관련된 동작이 있는 UI 요소일 뿐입니다. PowerApps의 많은 컨트롤은 레이블, 텍스트 입력 상자, 드롭다운 목록, 탐색 요소 등 다른 앱에서 사용한 컨트롤과 동일합니다. 그러나 PowerApps에는 **갤러리**(요약 데이터 표시)와 **양식**(세부 데이터 표시 및 항목 만들기/편집 가능)과 같은 보다 전문화된 컨트롤이 있습니다. 또한 **이미지**, **카메라** 및 **바코드**와 같은 정말 멋진 컨트롤도 있습니다. 사용할 수 있는 항목을 보려면 리본 메뉴에서 **삽입**을 클릭하거나 탭한 다음 **텍스트**~**아이콘**의 각 옵션을 차례로 클릭하거나 탭합니다.

![PowerApps Studio 리본 메뉴의 컨트롤 탭](./media/learning-case-app-explore-controls/ribbon-controls.png)

## <a name="explore-the-browse-screen"></a>찾아보기 화면 탐색
3개 앱 화면 각각에는 주 컨트롤과 몇 가지 추가 컨트롤이 있습니다. 앱의 첫 번째 화면은 기본적으로 **BrowseScreen1**이라는 찾아보기 화면입니다. 이 화면의 주 컨트롤은 **BrowseGallery1**이라는 갤러리입니다. **BrowseGallery1**에는 **NextArrow1**과 같은 다른 컨트롤(아이콘 컨트롤 - 클릭하거나 탭하면 세부 정보 화면으로 이동)이 포함되어 있습니다. **IconNewItem1**(아이콘 컨트롤 -클릭하거나 탭하면 편집/만들기 화면에서 항목을 만들 수 있음)과 같은 별도의 컨트롤도 화면에 있습니다.

![컨트롤이 있는 찾아보기 화면](./media/learning-case-app-explore-controls/browse-screen.png)

PowerApps에는 다양한 갤러리 유형이 있으므로 앱의 레이아웃 요구 사항에 가장 적합한 갤러리 유형을 사용할 수 있습니다. 이 섹션의 뒷부분에서 레이아웃을 제어하는 더 많은 방법을 보여 줍니다.

![PowerApps 갤러리 옵션](./media/learning-case-app-explore-controls/insert-gallery.png)

## <a name="explore-the-details-screen"></a>세부 정보 화면 탐색
다음은 **DetailScreen1**이라는 기본적인 세부 정보 화면입니다. 이 화면의 주 컨트롤은 **DetailForm1**이라는 표시 양식입니다. **DetailForm1**에는 **DataCard1**(카드 컨트롤 - 이 경우 질문 범주를 표시)과 같은 다른 컨트롤이 포함되어 있습니다. **IconEdit1**(아이콘 컨트롤 -클릭하거나 탭하면 편집/만들기 화면에서 현재 항목을 편집할 수 있음)과 같은 별도의 컨트롤도 화면에 있습니다.

![컨트롤이 있는 세부 정보 화면](./media/learning-case-app-explore-controls/details-screen.png)

많은 갤러리 옵션이 있지만, 양식은 보다 직관적이며 편집 양식 또는 표시 양식 중 하나입니다.

![PowerApps 양식 옵션](./media/learning-case-app-explore-controls/forms.png)

## <a name="explore-the-editcreate-screen"></a>편집/만들기 화면 탐색
앱의 세 번째 화면은 **EditScreen1**이라는 기본적인 편집/만들기 화면입니다. 이 화면의 주 컨트롤은 **EditForm1**이라는 편집 양식입니다. **EditForm1**에는 **DataCard8**(카드 컨트롤 - 이 경우 질문 범주를 편집할 수 있음)과 같은 다른 컨트롤이 포함되어 있습니다. **IconAccept1**(아이콘 컨트롤 -클릭하거나 탭하면 편집/만들기 화면에서 변경 내용을 저장할 수 있음)과 같은 별도의 컨트롤도 화면에 있습니다.

![컨트롤이 있는 편집 화면](./media/learning-case-app-explore-controls/edit-screen.png)

이제 앱이 화면과 컨트롤로 구성되는 방법에 대해 알아보았으므로 다음 항목에서는 앱을 사용자 지정하는 방법에 대해 살펴보겠습니다.

