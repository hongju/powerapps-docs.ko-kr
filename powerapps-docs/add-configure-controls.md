---
title: "컨트롤 추가 및 구성 | Microsoft Docs"
description: "도구 모음의 속성 탭 또는 수식 입력줄에서 직접 컨트롤을 추가 및 구성하기 위한 단계별 지침입니다."
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
ms.date: 07/10/2017
ms.author: sharik
ms.openlocfilehash: 6173db69fadd35e179a667ba11e1258d08632968
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="add-and-configure-a-control-in-powerapps"></a>PowerApps에서 컨트롤 추가 및 구성
도구 모음, **속성** 탭 또는 수식 입력줄에서 직접 앱에 다양한 UI 요소를 추가하고 모양과 동작의 측면을 구성합니다. 이러한 UI 요소는 컨트롤이라고 하며, 구성하는 측면은 속성이라고 합니다. 

**필수 조건**

1. PowerApps에 [등록](signup-for-powerapps.md)하여 [설치](http://aka.ms/powerappsinstall)하고 연 다음 등록 시 사용했던 동일한 자격 증명으로 로그인합니다.
2. PowerApps Studio에서 **파일** 메뉴(왼쪽 모서리를 따라)에서 **새로 만들기**를 클릭하거나 탭합니다.
   
    ![파일 메뉴의 새 옵션](./media/add-configure-controls/file-new.png)
3. **비어 있는 앱** 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.
   
    ![앱을 처음부터 만들기](./media/add-configure-controls/blank-app.png)
4. 소개 둘러보기를 시작한 경우 PowerApps 인터페이스의 주요 영역에 친숙해지려면 **다음**을 클릭하거나 탭합니다(또는 **건너뛰기**를 클릭하거나 탭하기).
   
    ![소개 둘러보기 화면 열기](./media/add-configure-controls/quick-tour.png)
   
    나중에 오른쪽 위 모서리의 물음표 아이콘을 클릭하거나 탭한 다음 **소개 둘러보기**를 클릭하거나 탭하면 언제든지 둘러보기를 시작할 수 있습니다.

## <a name="add-a-control"></a>컨트롤 추가
도구 모음의 **삽입** 탭을 누르고, 범주를 클릭하거나 누른 다음, 원하는 컨트롤을 클릭하거나 눌러 다양한 범위의 컨트롤을 추가할 수 있습니다. 이 섹션에서 각 범주의 컨트롤을 검토하여 추가할 수 있는 컨트롤 유형과 각 유형을 찾을 수 있는 위치를 익혀야 합니다.

* **삽입** 탭에서 이러한 범주를 클릭하거나 탭한 다음, 추가하려는 컨트롤을 클릭하거나 탭합니다.
  
    **텍스트**: 레이블, 텍스트 입력, HTML 텍스트, 펜 입력<br>
    **컨트롤**: 단추, 드롭다운, 날짜 선택기, 목록 상자, 확인란, 라디오, 토글, 슬라이더, 등급, 타이머<br>
    **갤러리**: 세로, 가로, 유연한 높이, 세로(비어 있음), 가로(비어 있음), 유연한 높이(비어 있음)<br>
    **데이터 테이블**<br>
    **양식**: 편집, 표시, 엔터티 양식<br>
    **미디어**: 이미지, 카메라, 바코드, 비디오, 오디오, 마이크, 그림 추가<br>
    **차트**: 세로 막대형 차트, 꺾은선형 차트, 원형 차트<br>
    **아이콘**

**팁**: 컨트롤에 더 많은 공간이 필요한 경우 [다른 화면 을 추가](add-screen-context-variables.md)합니다.

## <a name="configure-a-control-directly"></a>컨트롤 직접 구성
이 절차에서는 **레이블** 컨트롤을 추가 및 구성하지만, 많은 동일한 원칙을 다른 컨트롤에 적용할 수 있습니다.

1. **삽입** 탭을 클릭하거나 탭한 다음, **레이블**를 클릭하거나 탭합니다.
   
    ![삽입 탭](./media/add-configure-controls/insert-text-box.png)
   
    컨트롤을 추가할 때 기본적으로 선택됩니다. 클릭하거나 탭하여 기존 컨트롤을 선택할 수도 있습니다. 컨트롤이 선택되면 해당 컨트롤과 UI 변경의 다른 영역 둘레에 선택 상자가 생겨 선택한 컨트롤을 구성할 수 있습니다. 예를 들어 선택한 **레이블** 컨트롤은 이 그래픽과 유사합니다.
   
    ![선택한 레이블](./media/add-configure-controls/selected-text-box.png)
   
    **중요:** 컨트롤이 선택되면 다른 컨트롤 또는 화면의 다른 영역을 선택할 때 첫 번째 요소가 더 이상 선택되지 않습니다.
2. 선택 상자의 오른쪽 가장자리에 있는 핸들을 왼쪽으로 끌어 **레이블** 컨트롤을 좁게 만드세요. (가운데 핸들는 확대하는 경우에 나타납니다.)
   
    ![크기가 조정된 레이블](./media/add-configure-controls/shorter-text-box.png)
   
     또한 **[높이](controls/properties-size-location.md)**, **[너비](controls/properties-size-location.md)**, 또는 이 토픽에서 나중에 설명하는 대로 두 속성을 수정하여 컨트롤의 크기를 조정할 수도 있습니다.
3. 선택 상자 자체를 끌거나(**[X](controls/properties-size-location.md)**, **[Y](controls/properties-size-location.md)**, 또는 이 토픽에서 나중에 설명하는 대로 두 속성을 수정하여) **레이블** 컨트롤을 이동합니다.
4. **레이블** 컨트롤에 나타나는 텍스트를 세 번 클릭한 다음 **Hello, world**를 입력합니다.
   
    ![사용자 지정 텍스트가 포함된 레이블](./media/add-configure-controls/change-text-directly.png)
   
     또한 이 토픽에서 나중에 설명하는 대로 이 컨트롤의 **[텍스트](controls/properties-core.md)** 속성을 설정하여 이 텍스트를 수정할 수도 있습니다.

## <a name="configure-a-control-from-the-toolbar"></a>도구 모음에서 컨트롤 구성
도구 모음에서 컨트롤을 구성하여 컨트롤을 직접 구성하여 할 수 있는 더 광범위한 옵션을 지정할 수 있습니다.

1. **레이블** 컨트톨을 선택한 상태에서 도구 모음의 **홈** 탭을 클릭하거나 탭합니다.
   
    ![홈 탭](./media/add-configure-controls/home-tab.png)
2. **채우기**를 클릭하거나 탭한 다음, 청록색과 같은 색을 클릭하거나 탭합니다.
   
    ![채우기 옵션](./media/add-configure-controls/fill-option.png)
   
    **레이블** 컨트롤은 선택 항목을 반영합니다.
   
    ![청록색 채우기가 있는 레이블](./media/add-configure-controls/change-fill.png)
3. 텍스트의 글꼴 패밀리와 크기를 변경합니다(예: 18pt Georgia).
   
    ![글꼴 컨트롤](./media/add-configure-controls/font-size.png)
   
    **레이블** 컨트롤은 선택 항목을 반영합니다.
   
    ![18pt Georgia](./media/add-configure-controls/change-font.png)
4. **레이블** 탭을 클릭하거나 탭하거나 **VerticalAlign**을 클릭하거나 탭한 다음, **위쪽**을 클릭하거나 탭합니다.
   
    ![텍스트 상자 탭](./media/add-configure-controls/text-box-tab.png)
   
    **레이블** 컨트롤은 선택 항목을 반영합니다.
   
    ![상자 위쪽에 맞게 정렬된 레이블](./media/add-configure-controls/change-align.png)

## <a name="configure-a-control-from-the-properties-tab"></a>속성 탭에서 컨트롤 구성
**속성** 탭을 사용하여 수식을 쓰지 않아도 컨트롤을 구성할 수 있습니다. 이 절차에서는 또 다른 **레이블l** 컨트롤을 추가 및 구성하지만, 많은 동일한 원칙을 다른 컨트롤에 적용할 수 있습니다.

1. 이 토픽이 앞부분에서 설명한 대로 또 다른 **레이블** 컨트롤을 추가합니다.
2. 새 컨트를을 선택한 상태에서 오른쪽 창의 **속성** 탭을 클릭하거나 탭합니다.
   
    ![속성 패널](./media/add-configure-controls/properties-panel.png)
3. **텍스트** 상자에서 **속성 탭**을 누릅니다.
   
    ![속성 패널 레이블 텍스트](./media/add-configure-controls/properties-panel-text.png)
   
    **레이블** 컨트롤은 입력된 텍스트를 보여줍니다.
   
    ![속성 패널 캔버스 텍스트](./media/add-configure-controls/properties-panel-canvas-text.png)
4. **속성** 패널에서 **채우기**를 클릭하거나 탭한 다음, 색을 클릭하거나 탭합니다.
   
    ![속성 패널 색 텍스트](./media/add-configure-controls/properties-panel-color.png)
   
    **레이블** 컨트롤은 선택 항목을 반영합니다.
   
    ![속성 패널 캔버스 색](./media/add-configure-controls/properties-panel-canvas-color.png)
5. 속성 패널에서 **색** 속성을 클릭하거나 탭합니다.
   
    ![속성 패널 속성](./media/add-configure-controls/properties-panel-property.png)
   
    **색** 속성의 값은 수식 입력줄에서 강조 표시됩니다.
   
    ![속성 패널 속성 식](./media/add-configure-controls/properties-panel-property-expression.png)
   
   1. 클릭하거나 탭한 다음 삭제를 눌러 두 번째 **레이블** 컨트롤을 삭제합니다.

## <a name="configure-a-control-in-the-formula-bar"></a>수식 입력줄에서 컨트롤 구성
수식 입력줄을 사용하여 **속성** 탭 또는 도구 모음에서 직접 설정할 수 없는 속성을 설정할 수 있습니다. 예를 들어 사용자가 클릭하거나 탭하지 않고 컨트롤을 가리킬 때 나타나는 도구 설정을 설정할 수 있습니다. 또한, 앱의 성능을 높이는 복잡한 수식을 지정할 수도 있습니다.

이 토픽의 앞부분에서 적용한 각 변경 사항은 사용자가 구성한 컨트롤에 대한 [속성](reference-properties.md)의 값을 업데이트했습니다.

* 컨트롤 크기를 조정했을 때 **[너비](controls/properties-size-location.md)** 속성을 변경했습니다.
* 컨트롤을 이동했을 때 **[X](controls/properties-size-location.md)** 및 **[Y](controls/properties-size-location.md)** 속성을 변경했습니다.
* 컨트롤에서 표시하는 텍스트를 변경했을 때 **[텍스트](controls/properties-core.md)** 속성을 변경했습니다.

**속성** 탭, 또는 도구 모음에서 컨트롤을 직접 구성하는 대신, 속성 목록에서 선택한 다음 수식 입력줄에서 값을 지정하여 속성의 값을 업데이트할 수도 있습니다. 이 접근 방법을 사용하여 속성을 알파벳 순서로 검색하고, 값의 추가 유형을 지정할 수 있습니다.

1. 나머지 **레이블** 컨트롤이 선택된 상태에서 속성 목록의 **[텍스트](controls/properties-core.md)**를 클릭하거나 탭한 다음, 수식 입력줄에 **"My Company Name"**(큰따옴표 포함)을 입력합니다.
   
    ![레이블의 리터럴 문자열](./media/add-configure-controls/text-literal.png)
   
    큰따옴표 안에 텍스트 문자열을 넣으면 입력한 것과 정확히 처리되어야 한다는 것을 지정합니다. 또는, 수식에 속성의 값을 설정할 수 있습니다.
2. **레이블** 컨트롤이 선택된 상태에서 속성 목록에서 **[텍스트](controls/properties-core.md)**를 클릭하거나 탭한 다음, 수식 입력줄에 **Today()**(큰따옴표 제외)를 입력합니다.
   
    이 컨트롤은 현재 날짜를 보여줍니다.
   
    ![Today 함수](./media/add-configure-controls/today-function.png)
   
    **팁:** 계산을 수행할 뿐만 아니라 다양한 방식으로 [날짜와 시간의 형식을 지정](show-text-dates-times.md)할 수 있습니다.

## <a name="configure-two-controls-to-interact-with-each-other"></a>서로 상호 작용할 두 컨트롤 구성
이 절차에서는 확인란을 추가한 다음, 해당 확인란을 선택한 경우에만 나타나야 하는 레이블을 구성합니다.

1. **삽입** 탭을 클릭하거나 탭합니다.
   
    ![삽입 탭](./media/add-configure-controls/insert-tab.png)
2. **컨트롤**을 클릭하거나 탭한 다음, **확인란**을 클릭하거나 탭합니다.
   
    ![확인란 삽입](./media/add-configure-controls/insert-check-box.png)
3. **레이블** 컨트롤 아래에 나타나도록 **확인란** 컨트롤을 이동하고 **텍스트 표시**가 나타나도록 **확인란** 컨트롤의 **[텍스트](controls/properties-core.md)** 속성을 설정합니다.
   
    ![확인란 구성](./media/add-configure-controls/configure-check-box.png)
4. **확인란** 컨트롤이 선택된 상태에서 **속성** 탭 바로 위의 이름을 클릭하거나 탭한 다음, **MyCheckbox**를 누릅니다.
   
    ![확인란 이름 바꾸기](./media/add-configure-controls/properties-panel-rename.png)
5. **레이블** 컨트롤을 클릭하거나 탭하여 선택합니다.
6. **속성** 탭에서 **Visible** 속성을 클릭하거나 탭합니다.
   
    ![Visible 속성](./media/add-configure-controls/properties-panel-visible-property.png)
7. 수식 입력줄에서 **true**를 삭제한 다음, 이 수식을 입력하거나 붙여넣습니다.
   
    **If(MyCheckbox.Value = true, true, false)**
   
    이 **[If 함수](functions/function-if.md)**는 해당 확인란을 선택한 경우에만 레이블이 나타나도록 명시합니다. 해당 확인란이 지워졌으므로 **레이블** 컨트롤이 사라집니다(선택 상자 제외).
   
    ![Visible 수식](./media/add-configure-controls/visible-formula.png)
8. **확인란** 컨트롤을 클릭하거나 탭하여 선택 상자를 추가한 다음, 다시 클릭하거나 탭하여 확인 표시를 추가합니다.
   
    **레이블**이 다시 나타납니다.
   
    ![확인란을 선택하면 레이블이 나타납니다.](./media/add-configure-controls/show-text.png)
9. **확인란** 컨트롤을 선택 취소하여 **레이블** 컨트롤을 숨깁니다.
   
    ![확인란을 선택 취소하면 레이블이 사라집니다.](./media/add-configure-controls/hide-text.png)

이 예제는 기본적이지만, 단순에서 복잡까지 하나 이상의 [수식](formula-reference.md)을 빌드하여 앱의 동작과 모양을 구성할 수 있습니다.

## <a name="rename-a-screen-or-a-control"></a>화면 또는 컨트롤 이름 바꾸기
화면 또는 컨트롤의 이름을 바꿔 읽고 유지하기 훨씬 쉬운 수식을 빌드할 수 있습니다.

1. 이름을 바꾸려는 화면 또는 컨트롤을 클릭하거나 탭합니다.
2. 오른쪽 창에서 컨트롤의 이름(**속성** 탭 바로 위)을 클릭하거나 탭한 다음, 원하는 이름을 입력합니다.
   
    ![확인란 이름 바꾸기](./media/add-configure-controls/properties-panel-rename.png)

## <a name="find-and-select-a-screen-or-a-control"></a>화면 또는 컨트롤 찾기 및 선택
숨겨져 있거나 다른 컨트롤과 겹치는 경우에도 왼쪽 창에서 검색하여 화면 또는 컨트롤을 찾아 선택할 수 있습니다. 이 창에는 앱의 각 화면의 썸네일 또는 각 화면과 포함되어 있는 컨트롤의 계층 보기를 보여줍니다.

* **썸네일과 계층적 보기 간에 전환하려면** 창의 오른쪽에서 아이콘을 클릭하거나 탭합니다.
  
    ![보기 토글](./media/add-configure-controls/toggle-view.png)
* **컨트롤을 찾으려면** 하나 이상의 문자를 입력하여 사용하자 입력한 텍스트가 포함된 컨트롤 이름을 강조 표시합니다.
  
    검색 결과를 클릭하거나 탭할 경우 앱에서 해당 컨트롤을 선택합니다.
  
    ![트리 보기에서 검색](./media/add-configure-controls/search.png)
* **화면을 위로 또는 아래로 이동, 복제, 삭제 또는 이름을 바꾸려면** 마우스 오른쪽 단추로 클릭(또는 옆의 줄임표를 클릭하거나 탭)한 다음, 원하는 옵션을 클릭하거나 탭합니다.
  
    ![트리 뷰 상황에 맞는 메뉴](./media/add-configure-controls/context.png)
* **컨트롤을 복사/붙여넣거나, 삭제 또는 이름을 바꾸려면** 마우스 오른쪽 단추로 클릭(또는 옆의 줄임표를 클릭하거나 탭)한 다음, 원하는 옵션을 클릭하거나 탭합니다.

