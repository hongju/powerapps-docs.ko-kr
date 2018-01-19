과정의 이 섹션에서는 "바닥재 견적" SharePoint 목록에서 앱을 만들어 보겠습니다. 이 앱은 고객 사이트에서 감정인과 같은 사람이 사용하여 목록을 참조하고 최신 상태로 유지할 수 있습니다. 시작 섹션에서 같은 목록으로부터 앱을 생성하는 방법을 보여 주었습니다. 여기서 다시 살펴보겠습니다. 먼저 PowerApps Studio를 시작하는 대신 PowerApps를 SharePoint Online에 통합하는 방법을 보여 줍니다. 다음으로 앱을 결합하는 방법을 더 자세히 살펴보고 사용자 지정하는 방법을 보여 줍니다. 이 섹션을 진행하면서 분명히 새로운 정보를 얻을 수 있을 것입니다. 이제 시작하겠습니다!

## <a name="generate-the-app"></a>앱 생성
다음 이미지에서는 이름과 가격 같은 기본 정보와 각 바닥 유형에 대한 이미지가 포함된 "바닥재 견적" SharePoint 목록을 보여 줍니다. 이제는 PowerApps 및 Microsoft Flow가 SharePoint Online에 통합되는 방식을 볼 수 있으므로 목록에서 앱과 흐름을 쉽게 빌드할 수 있습니다.

![바닥재 견적 목록](./media/learning-spo-app-generate/flooring-estimates-list.png)

앱을 빌드하려면 **PowerApps**를 클릭한 다음 **앱 만들기**를 클릭합니다. 오른쪽 창에서 앱 이름을 입력한 다음 **만들기**를 클릭합니다. **만들기**을 클릭하면 PowerApps에서 앱을 생성하기 시작합니다. PowerApps는 유용한 정보를 시작 지점으로 생성할 수 있도록 데이터에 대한 모든 종류의 추론을 만듭니다.

![목록에서 앱 생성](./media/learning-spo-app-generate/generate-app.png)

## <a name="view-the-app-in-powerapps-studio"></a>PowerApps Studio에서 앱 보기
PowerApps Studio에서 새로운 3화면 앱이 열립니다. 데이터에서 생성된 모든 앱에는 다음과 같은 동일한 화면 집합이 있습니다.

* **찾아보기** 화면: 목록에서 가져온 데이터를 탐색, 정렬, 필터링 및 새로 고침을 수행하고, (+) 아이콘을 클릭하여 항목을 추가할 수 있습니다.
* **세부 정보** 화면: 항목에 대한 세부 정보를 보고 항목을 삭제하거나 편집할 수 있습니다.
* **편집/만들기** 화면: 기존 항목을 편집하거나 새 항목을 만들 수 있습니다.

왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.

![보기 토글](./media/learning-spo-app-generate/toggle-view.png)

각 썸네일을 클릭하거나 탭하여 해당 화면의 컨트롤을 봅니다.

![생성된 앱](./media/learning-spo-app-generate/generate-finished-app.png)

## <a name="run-the-app-in-preview-mode"></a>미리 보기 모드에서 앱 실행
종 모양 아이콘을 ![앱 미리 보기 시작 화살표](./media/learning-spo-app-generate/f5-arrow-sm.png) 맨 위 오른쪽 모서리에서 앱을 실행합니다. 앱을 탐색하는 경우 목록의 모든 데이터를 포함하고 있고 양호한 기본 환경을 제공하고 있음을 알 수 있습니다.

![미리 보기 모드에서 앱 실행](./media/learning-spo-app-generate/generate-run-app.png)

다음으로 앱을 더 자세히 살펴보고, 나중에 요구 사항에 맞게 앱을 사용자 지정하겠습니다.

