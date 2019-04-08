---
title: 캔버스 앱의 항목 목록 표시 | Microsoft Docs
description: 갤러리를 사용하여 캔버스 앱에서 항목 목록을 표시하고 조건을 지정하여 목록을 필터링합니다.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/28/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f45948bc16f036669a09ed2c566c60440d24a797
ms.sourcegitcommit: 2180982e57f0d161610be584fdae9424fe7e06b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58616711"
---
# <a name="show-a-list-of-items-in-powerapps"></a>PowerApps에서 항목 목록 표시

**[갤러리](controls/control-gallery.md)** 컨트롤을 캔버스 앱에 추가하여 모든 데이터 원본에서 항목 목록을 표시합니다. 이 토픽에서는 데이터 원본으로 Excel을 사용합니다. **[텍스트 입력](controls/control-text-input.md)** 컨트롤의 필터 조건과 일치하는 항목만 표시하도록 **갤러리** 컨트롤을 구성하여 목록을 필터링합니다.

## <a name="prerequisites"></a>필수 조건

- PowerApps에서 [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아봅니다.

- 샘플 데이터 설정:
    1. 이 자습서에 대한 샘플 데이터를 포함하는 [이 Excel 파일](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)을 다운로드합니다.

    2. Excel 파일을 비즈니스용 OneDrive와 같은 [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 업로드합니다.

- 빈 앱을 엽니다.
    1. [PowerApps에 로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)합니다.

    1. **고유한 앱 만들기**에서 **빈 페이지의 캔버스 앱**을 선택합니다.

    1. 앱의 이름을 지정하고, **전화**를 선택한 다음, **만들기**를 선택합니다.

    1. **PowerApps Studio 시작** 대화 상자에서 **건너뛰기**를 선택합니다.

    1. Excel 파일의 **FlooringEstimates** 테이블에 [연결을 추가](add-data-connection.md)합니다.

## <a name="add-a-gallery-to-a-blank-screen"></a>빈 화면에 갤러리 추가

1. **삽입** 탭에서 **갤러리**를 선택한 후 **세로**를 선택합니다.

    ![세로 갤러리 추가](./media/add-gallery/gallery-dropdown.png)

1. 오른쪽 창의 **속성** 탭을 열고 **항목** 목록을 열고 **Flooring Estimates**를 선택합니다.

    ![바닥 예상치](./media/add-gallery/select-layout.png)

1. (선택 사항) **레이아웃** 목록에서 다른 옵션을 선택합니다.

## <a name="add-a-gallery-in-a-screen"></a>화면에서 갤러리 추가

1. 에 **Home** 탭을 선택 **새 화면** > **목록 화면**합니다.

    포함 된 화면을 **갤러리** 컨트롤 및 검색 표시줄과 같은 다른 컨트롤에 표시 됩니다.

1. 갤러리의 **Items** 속성을 `FlooringEstimates`로 설정합니다.

    **갤러리** 컨트롤은 샘플 데이터를 보여 줍니다.

    ![데이터 표시](./media/add-gallery/show-data-default.png)

## <a name="add-a-control-to-the-gallery-control"></a>갤러리 컨트롤에 컨트롤 추가
다른 사용자 지정을 수행 하기 전에 확인에 대 한 레이아웃에 **갤러리** 원하는 컨트롤 가장 밀접 하 게 일치 합니다. 여기에서 계속 수정할 수 있습니다는 **갤러리** 템플릿을 결정 하는 방법의 모든 데이터를 **갤러리** 컨트롤이 나타납니다.

1. 클릭 하거나 눌러 아래쪽에 있는 템플릿을 선택 합니다 **갤러리** 컨트롤과 후의 왼쪽 위 모서리에서 연필 아이콘을 선택 합니다.

    ![갤러리 템플릿 편집](./media/add-gallery/edit-item.png)

2. 템플릿을 여전히 선택한 채로 **[레이블](controls/control-text-box.md)** 컨트롤을 추가한 다음 템플릿의 다른 컨트롤과 겹치지 않도록 이동하고 크기를 조정합니다.

    ![레이블 추가](./media/add-gallery/add-text-box.png)

3. 갤러리를 선택 하 고 선택한 **편집할** 옆에 **필드** 에 **속성** 오른쪽 창의 탭 합니다.

4. 이 절차의 앞부분에서 추가한 레이블을 선택한 다음 **데이터** 창에서 강조 표시된 목록을 엽니다.

    ![드롭다운 목록 열기](./media/add-gallery/open-dropdown.png)

5. 해당 목록에서 **가격**을 클릭하거나 탭합니다.

    **갤러리** 컨트롤은 새 값을 보여 줍니다.

    ![최종 갤러리](./media/add-gallery/final-gallery.png)

## <a name="filter-and-sort-a-gallery"></a>필터 및 정렬 된 갤러리
**갤러리** 컨트롤의 **[Items](controls/properties-core.md)** 속성은 표시하는 항목을 결정합니다. 이 절차에서는 또한 나타나는 레코드 순서 및 필터 조건에 따라 결정 되도록 해당 속성 구성.

![검색 상자 및 정렬 아이콘](./media/add-gallery/text-search-box.png)

1. **갤러리** 컨트롤의 **[Items](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.

    ```powerapps-dot
    Sort
        (If
            (IsBlank(TextSearchBox1.Text),
            FlooringEstimates,
            Filter(
                FlooringEstimates,
                TextSearchBox1.Text in Text(Name)
            )
        ),
        Name,
        If(
            SortDescending1,
            SortOrder.Descending,
            SortOrder.Ascending
        )
    )
    ```

    이 수식의 함수에 대한 자세한 내용은 [수식 참조](formula-reference.md)를 참조하세요.

1. 검색 상자를 두 번 클릭 하 고 그 안에 제품 이름의 전체 또는 일부를 입력 합니다.

    필터 조건을 충족 하는 항목만 표시 됩니다.

1. Alt 키를 누른 정렬 아이콘을 정렬 순서를 전환 하려면 한 번 이상 선택 합니다.

    레코드를 오름차순과 내림차순 제품 이름을 기준으로 알파벳 순서 사이 전환 합니다.

## <a name="highlight-the-selected-item"></a>선택한 항목 강조 표시
설정 된 **갤러리** 컨트롤의 **TemplateFill** 속성을 수 있지만이 예제와 비슷한 수식으로 하려는 경우 서로 다른 색을 지정할 수 있습니다.

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>기본 선택 변경
**갤러리** 컨트롤의 **Default** 속성을 기본으로 선택하려는 레코드로 설정합니다. 예를 들어, 다섯 번째 항목을 지정할 수 있습니다 합니다 **FlooringEstimates** 데이터 원본:

**Last(FirstN(FlooringEstimates, 5))**

이 예제에서는 **FlooringEstimates** 데이터 원본의 **Hardwood** 범주에서 첫 번째 항목을 지정합니다.

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>다음 단계
[양식](working-with-forms.md) 및 [수식](working-with-formulas.md)을 사용하는 방법을 알아봅니다.
