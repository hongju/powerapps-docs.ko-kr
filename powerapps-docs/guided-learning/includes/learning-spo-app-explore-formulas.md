PowerApps의 주요 이점 중 하나로서 기존 응용 프로그램 코드를 작성하지 않아도 되므로 개발자가 아니더라도 앱을 만들 수 있습니다. 하지만 여전히 앱에서 논리를 표현하고 앱의 탐색, 필터링, 정렬 및 기타 기능을 제어할 수 있는 방법이 필요합니다. 이로 인해 수식이 도입되는 것입니다. Excel 수식을 사용한 적이 있으면 PowerApps에서 사용하는 방식이 익숙하게 느껴질 것입니다. 이 항목에서는 텍스트 서식 지정을 위한 몇 가지 기본 수식을 보여 주고 PowerApps에서 생성된 앱에 포함된 세 가지 수식을 단계별로 살펴보겠습니다. 수식에서 수행할 수 있는 작업을 경험할 것입니다. 그런 다음 생성된 앱에서 다른 수식을 보고 자신의 앱을 작성하는 데 약간의 시간을 보낼 수 있습니다.

## <a name="understanding-formulas-and-properties"></a>수식 및 속성 이해
이전 항목에서 가격 필드가 찾아보기 화면 갤러리에 포함되었지만 통화 기호가 없는 일반 숫자로 표시되었습니다. 달러 기호를 추가하고 품목 비용에 따라 텍스트 색을 변경한다고 가정합니다(예: 5달러를 초과하면 빨간색, 그렇지 않으면 녹색). 다음 이미지에서는 아이디어를 보여 줍니다.

![색 및 통화에 대한 텍스트 서식 지정](./media/learning-spo-app-explore-formulas/text-formatting.png)

통화 서식 지정에서 시작하겠습니다. 기본적으로 PowerApps는 가격을 표시하는 레이블의 **Text** *속성*으로 설정된 각 항목의 가격 값을 가져옵니다.

![가격 기본 서식 지정](./media/learning-spo-app-explore-formulas/price-default.png)

미국 통화 기호를 추가하려면 레이블 컨트롤을 클릭하거나 탭한 다음 수식 입력줄에서 **Text** 속성을 이 수식으로 설정합니다.

![가격 통화 서식 지정](./media/learning-spo-app-explore-formulas/price-formatted.png)

`Text(Price, "[$-en-US]$ ##.00"` 수식은 **텍스트** *함수*를 사용하여 숫자 서식을 지정하는 방법을 지정합니다. 수식이 Excel 수식과 비슷하지만 PowerApps 수식은 스프레드시트의 셀이 아니라 컨트롤과 기타 앱 요소를 나타냅니다. 컨트롤을 클릭하거나 탭한 다음 속성 드롭다운 목록을 클릭하거나 탭하면 해당 컨트롤과 관련된 속성 목록이 표시됩니다. 예를 들어 다음은 레이블의 속성 목록 중 일부입니다. 일부 속성은 다양한 컨트롤과 관련이 있으며, 다른 속성은 특정 컨트롤에만 해당됩니다.

![속성 설정](./media/learning-spo-app-explore-formulas/properties.png)

가격에 따라 조건부로 색 서식을 지정하려면 레이블의 **Color** 속성에 대해 `If(Price > 5, Color.Red, Color.Green)`과 같은 수식을 사용합니다.

![가격 색 서식 지정](./media/learning-spo-app-explore-formulas/color-formatted.png)

## <a name="formulas-included-in-the-generated-app"></a>생성된 앱에 포함된 수식
이제 속성과 함께 수식을 사용하는 방법을 이해했으므로 PowerApps에서 생성된 앱에 사용하는 수식의 세 가지 예를 살펴보겠습니다. 이 예에서는 모두 찾아보기 화면에서 제공되며, 앱 컨트롤을 클릭하거나 탭하면 발생하는 동작을 정의한 OnSelect 속성과 함께 작동합니다.

* 첫 번째 수식은 **IconNewItem1** 컨트롤(![새 항목 아이콘](./media/learning-spo-app-explore-formulas/icon-add-item.png))과 연결됩니다. 이 컨트롤을 클릭하거나 탭하면 찾아보기 화면에서 편집/만들기 화면으로 이동하고 항목을 만들 수 있습니다. 
  
  * 수식은 `NewForm(EditForm1);Navigate(EditScreen1, ScreenTransition.None)`입니다.
  * 수식은 새 편집 양식을 *인스턴스화*한 다음 편집/만들기 화면으로 이동하여 새 항목을 만들 수 있습니다. `ScreenTransition.None` 값은 화면 간에 전환이 없음을 나타냅니다(예: 페이드).
* 두 번째 수식은 **IconSortUpDown1** 컨트롤(![갤러리 정렬 아이콘](./media/learning-spo-app-explore-formulas/icon-sort.png))과 연결됩니다. 이 컨트롤을 클릭하거나 탭하면 찾아보기 화면 갤러리에서 항목 목록을 정렬할 수 있습니다.
  
  * 수식은 `UpdateContext({SortDescending1: !SortDescending1})`입니다.
  * 수식은 `UpdateContext`를 사용하여 `SortDescending1`이라는 *변수*를 업데이트합니다. 컨트롤을 클릭하면 변수 값이 앞뒤로 전환됩니다. 그러면 이 화면의 갤러리에 항목을 정렬하는 방법을 알려줍니다(자세한 내용은 비디오 참조). 
* 세 번째 수식은 **NextArrow1** 컨트롤(![세부 정보로 이동 화살표 아이콘](./media/learning-spo-app-explore-formulas/icon-arrow.png))과 연결됩니다. 이 컨트롤을 클릭하거나 탭하면 찾아보기 화면에서 세부 정보 화면으로 이동할 수 있습니다.
  
  * 수식은 `Navigate(DetailScreen1, ScreenTransition.None)`입니다.
  * 수식은 아무런 전환 없이 세부 정보 화면으로 다시 이동합니다.

앱에는 다른 수식이 다양하게 있으므로 컨트롤을 클릭하고 다양한 속성에 대해 수식이 설정되어 있는지 확인하는 데 약간의 시간을 보냅니다.

## <a name="wrapping-it-all-up"></a>요약
이제 생성된 앱을 탐색하고, 앱에 기능을 제공하는 화면, 컨트롤, 속성 및 수식에 대한 정보를 살펴보는 섹션의 끝 부분에 있습니다. 여기까지 진행해 왔다면 생성된 앱의 작동 방식을 더 잘 이해해야 합니다. 이제 이러한 이해를 통해 자신만의 앱을 만들 수 있습니다. 

다음 섹션으로 이동하기 전에 SharePoint로 돌아가서 현재 앱이 목록 환경과 어떻게 통합되어 있는지 보여 주겠습니다. 이제 목록의 *보기*로 작동하는 **FlooringApp**을 볼 수 있으므로 **열기**를 클릭하여 앱을 시작합니다. 이는 친숙한 사용자 지정 환경에서 목록을 관리하는 간단한 방법을 제공합니다.

![Sharepoint 목록 보기 앱](./media/learning-spo-app-explore-formulas/list-view.png)

이제 SharePoint 앱 섹션을 살펴보았으므로 다음으로 이동할 위치를 선택할 수 있습니다.

* [앱 관리](https://docs.microsoft.com/powerapps/guided-learning/manage-apps#step-1)
* [Common Data Service에서 앱 만들기 및 사용자 지정](https://docs.microsoft.com/powerapps/guided-learning/create-app-cds#step-1)

관리 섹션에서는 앱을 공유하고 버전을 지정하는 방법을 보여 주고 앱, 데이터 및 기타 리소스의 컨테이너인 환경을 소개합니다. 모든 사람들이 어느 시점에서 관리 섹션으로 이동하는 것이 좋지만 Common Data Service 섹션에는 자세한 앱 사용자 지정을 포함하여 몇 가지 중요한 정보가 있습니다. 

