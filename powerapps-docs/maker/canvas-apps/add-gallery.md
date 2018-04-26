---
title: 항목 목록 표시 | Microsoft Docs
description: 갤러리를 사용하여 앱에서 항목 목록을 표시하고 조건을 지정하여 목록을 필터링합니다.
documentationcenter: na
author: karthik-1
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 09/28/2017
ms.author: sharik
ms.openlocfilehash: 60ec1fc7f896aeb3391ed794920e987b232d09f3
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="show-a-list-of-items-in-powerapps"></a>PowerApps에서 항목 목록 표시
**[갤러리](controls/control-gallery.md)** 컨트롤을 앱에 추가하여 모든 데이터 원본에서 항목 목록을 표시합니다. 이 토픽에서는 데이터 원본으로 Excel을 사용합니다. **[텍스트 입력](controls/control-text-input.md)** 컨트롤의 필터 조건과 일치하는 항목만 표시하도록 **갤러리** 컨트롤을 구성하여 목록을 필터링합니다.

## <a name="prerequisites"></a>필수 조건
* PowerApps에서 [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아봅니다.

* 샘플 데이터 설정:
    1. 이 자습서에 대한 샘플 데이터를 포함하는 [이 Excel 파일](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)을 다운로드합니다.

    2. Excel 파일을 비즈니스용 OneDrive와 같은 [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 업로드합니다.

## <a name="add-a-gallery-control"></a>갤러리 컨트롤 추가
1. PowerApps를 연 다음 왼쪽 가장 자리 부근의 **새로 만들기**를 클릭하거나 탭합니다.

2. **비어 있는 앱** 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.

3. **PowerApps Studio 시작** 대화 상자에서 **건너뛰기**를 클릭하거나 탭합니다.

4. Excel 파일의 **FlooringEstimates** 테이블에 [연결을 추가](add-data-connection.md)합니다.

5. (선택 사항) **삽입** 탭을 클릭하거나 탭하고, **갤러리**를 클릭하거나 탭한 다음 비어 있거나 컨트롤의 기본 집합을 포함하는 **갤러리** 컨트롤을 클릭하거나 탭하여 **갤러리** 컨트롤을 기본 화면에 추가합니다.

    이러한 옵션은 가로 또는 세로로 스크롤하는 **갤러리** 컨트롤을 포함합니다. 자동으로 각 항목의 콘텐츠 양에서 해당 크기를 기반으로 하는 **갤러리** 컨트롤을 추가할 수도 있습니다.

    ![갤러리 추가](./media/add-gallery/gallery-dropdown.png)

6. **홈** 탭에서 **새 화면**을 클릭하거나 탭합니다.

    비어 있고, 스크롤하고, **갤러리** 컨트롤을 포함하거나 양식을 포함하는 화면을 추가할 수 있습니다.

7. **목록 화면**을 클릭하거나 탭하여 **갤러리** 컨트롤 및 검색 표시줄과 같은 다른 컨트롤을 포함하는 화면을 추가합니다.

    > [!NOTE]
> 새 화면 또는 기존 화면에 **갤러리** 컨트롤을 추가하는지 여부는 **갤러리** 컨트롤의 아래쪽 가까이에 있는 탭을 클릭하거나 탭하여 선택하고, 오른쪽 창에서 **바닥재 견적**을 클릭하거나 탭한 다음 **데이터** 창에서 다른 레이아웃을 클릭하거나 탭할 수 있습니다. 이 자습서의 경우 기본 레이아웃을 그대로 둡니다.

    ![갤러리 레이아웃 선택](./media/add-gallery/select-layout.png)

8. 방금 추가한 화면에서 **갤러리** 컨트롤을 클릭하거나 탭합니다.

9. 오른쪽 창의 **속성** 탭에서 **CustomGallerySample**을 클릭하거나 탭합니다.

10. **데이터** 창에서 **CustomGallerySample**을 클릭하거나 탭한 다음 **FlooringEstimates**를 클릭하거나 탭합니다.

    ![데이터 원본 선택](./media/add-gallery/choose-data.png)

    **갤러리** 컨트롤은 샘플 데이터를 보여 줍니다.

    ![데이터 표시](./media/add-gallery/show-data-default.png)

    이 토픽의 뒷부분에 나오는 정렬 및 검색을 구성합니다.

## <a name="add-a-control-to-the-gallery-control"></a>갤러리 컨트롤에 컨트롤 추가
사용자 지정을 수행하기 전에 **갤러리** 컨트롤 레이아웃을 결정합니다. **갤러리** 컨트롤에서 첫 번째 컨트롤 집합은 **갤러리** 컨트롤의 모든 데이터가 표시되는 방식을 결정하는 템플릿입니다.

1. **갤러리** 컨트롤의 아래쪽 근처를 클릭하거나 탭하여 템플릿을 선택한 다음 왼쪽 위 모서리에 있는 연필 아이콘을 클릭하거나 탭합니다.

    ![갤러리 템플릿 편집](./media/add-gallery/edit-item.png)

2. 템플릿을 여전히 선택한 채로 **[레이블](controls/control-text-box.md)** 컨트롤을 추가한 다음 템플릿의 다른 컨트롤과 겹치지 않도록 이동하고 크기를 조정합니다.

    ![레이블 추가](./media/add-gallery/add-text-box.png)
3. 템플릿을 선택한 다음 오른쪽 창의 **바닥재 견적**을 클릭하거나 탭하여 **데이터** 창을 엽니다.

4. 이 절차의 앞부분에서 추가한 레이블을 선택한 다음 **데이터** 창에서 강조 표시된 목록을 엽니다.

    ![드롭다운 목록 열기](./media/add-gallery/open-dropdown.png)

5. 해당 목록에서 **가격**을 클릭하거나 탭합니다.

    ![레이블 바인딩 변경](./media/add-gallery/change-binding.png)

    **갤러리** 컨트롤은 새 값을 보여 줍니다.

    ![최종 갤러리](./media/add-gallery/final-gallery.png)

## <a name="filter-the-gallery-control"></a>갤러리 컨트롤 필터링
**갤러리** 컨트롤의 **[Items](controls/properties-core.md)** 속성은 표시하는 항목을 결정합니다. 이 절차에서는 **갤러리** 컨트롤이 제품 이름에서 **TextSearchBox1**의 텍스트를 포함하는 해당 항목만 표시하도록 해당 속성을 구성합니다.

![텍스트 검색 상자](./media/add-gallery/text-search-box.png)

1. 해당 컨트롤의 아래쪽 근처를 클릭하거나 탭하여 **갤러리** 컨트롤을 선택합니다.

2. **고급** 탭에서 **갤러리** 컨트롤의 **[Items](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.

    **If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name)))**

    이 수식의 함수에 대한 자세한 내용은 [수식 참조](formula-reference.md)를 참조하세요.

3. 검색 상자에 제품 이름의 일부 또는 전체를 입력합니다.

    **갤러리** 컨트롤은 필터 조건에 맞는 해당 항목만 표시합니다.

## <a name="sort-the-gallery-control"></a>갤러리 컨트롤 정렬
**갤러리** 컨트롤의 **[Items](controls/properties-core.md)** 속성은 표시하는 항목의 순서를 결정합니다. 이 절차에서는 **갤러리** 컨트롤이 **ImageSortUpDown1**에서 설정한 대로 항목의 순서를 표시하도록 해당 속성을 구성합니다.

![정렬을 위한 이미지](./media/add-gallery/image-sorting.png)

1. **갤러리** 컨트롤의 **[Items](controls/properties-core.md)** 속성을 이 수식으로 설정합니다.

    **Sort(If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name))), Name, If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

2. 정렬 아이콘을 선택하여 제품의 이름으로 **갤러리** 컨트롤의 정렬 순서를 변경합니다.

**갤러리** 컨트롤을 정렬 *및* 필터링하려면:

* 이 수식에서 *DataSource*의 두 인스턴스를 데이터 원본의 이름으로 바꿉니다.

* *ColumnName*의 두 인스턴스를 정렬 및 필터링하려는 열의 이름으로 바꿉니다.

**Sort(If(IsBlank(TextSearchBox1.Text),** *DataSource*, **Filter(** *DataSource*, **TextSearchBox1.Text in Text(** *ColumnName* **))),** *ColumnName*, **If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

## <a name="highlight-the-selected-item"></a>선택한 항목 강조 표시
**갤러리** 컨트롤의 **TemplateFill** 속성을 이 예제와 비슷한 수식으로 설정합니다.

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>기본 선택 변경
**갤러리** 컨트롤의 **Default** 속성을 기본으로 선택하려는 레코드로 설정합니다. 예를 들어, **FlooringEstimates** 데이터 원본에서 다섯 번째 항목을 지정합니다.

**Last(FirstN(FlooringEstimates, 5))**

이 예제에서는 **FlooringEstimates** 데이터 원본의 **Hardwood** 범주에서 첫 번째 항목을 지정합니다.

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>다음 단계
[양식](working-with-forms.md) 및 [수식](working-with-formulas.md)을 사용하는 방법을 알아봅니다.
