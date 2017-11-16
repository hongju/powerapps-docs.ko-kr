---
title: "앱 사용자 지정(Common Data Service) | Microsoft Docs"
description: "앱 화면, 컨트롤 및 필드 업데이트"
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: wHy72cOe8Os
courseduration: 12m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: bc5ce767124f531e70c32c34087e0572a87923f2
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="customize-the-app-common-data-service"></a>앱 사용자 지정(Common Data Service)
이 섹션의 처음 두 항목에서 Common Data Service 엔터티에서 앱을 생성하고 이 앱을 탐색하여 3개 화면 앱을 구성하는 방법에 대해 더 잘 이해하게 되었습니다. PowerApps에서 생성한 앱은 유용하지만 생성된 앱을 사용자 지정하는 경우가 종종 있습니다. 이 항목에서는 앱의 찾아보기 화면에 대한 몇 가지 변경 사항을 단계별로 살펴보겠습니다. 모든 화면을 사용자 지정할 수 있지만, 하나에 집중하여 사용자 지정을 좀 더 깊이 있게 설명하려고 했습니다. 엔터티, Excel 파일 또는 다른 원본에서 생성한 앱을 모두 가져와서 사용자 지정할 수 있는 방법을 확인하는 것이 좋습니다. 실제로 이는 앱을 결합하는 방법을 배우는 가장 좋은 방법입니다.

## <a name="change-gallery-and-data-bindings"></a>갤러리 및 데이터 바인딩 변경
PowerApps에서 앱을 생성할 때 사용할 레이아웃과 각 화면에 표시할 특정 필드를 결정했습니다. 이 앱의 경우 상태 표시줄이 있는 갤러리 컨트롤을 선택해 보겠습니다(상태 표시줄을 바로 사용자 지정했음). 오른쪽 창의 **레이아웃** 탭에서 원하는 레이아웃을 선택합니다. PowerApps에서 변경할 때 앱을 업데이트하기 때문에 결과가 바로 표시됩니다.

![찾아보기 화면 레이아웃 변경](./media/learning-case-app-customize/change-layout.png)

오른쪽의 기본 레이아웃을 사용하여 표시되는 필드를 변경합니다. 첫 번째 항목에서 필드를 클릭하거나 탭한 다음 오른쪽 창에서 각 항목에 대해 표시되는 데이터를 변경합니다. 이는 엔터티의 각 항목에 대해 더 나은 요약을 제공합니다.

![찾아보기 화면 필드 변경](./media/learning-case-app-customize/change-browse-fields.png)

## <a name="change-the-app-theme"></a>앱 테마 변경
PowerApps는 PowerPoint와 마찬가지로 앱에서 사용할 수 있는 테마 집합을 제공합니다. 다음 화면에서 **모래 언덕** 테마가 적용되었으며 간단한 로고가 앱에 붙여졌습니다. 이는 기본적인 변경 사항이지만 앱의 모양을 개선하기 위해 많은 작업을 수행할 수 있습니다. 

![테마 변경 및 로고 추가](./media/learning-case-app-customize/change-theme.png)

## <a name="use-a-formula-to-show-the-case-status"></a>수식을 사용하여 사례 상태 표시
PowerApps의 주요 이점 중 하나로서 기존 응용 프로그램 코드를 작성하지 않아도 되므로 개발자가 아니더라도 앱을 만들 수 있습니다. 하지만 여전히 앱에서 논리를 표현하고 앱의 탐색, 필터링, 정렬 및 기타 기능을 제어할 수 있는 방법이 필요합니다. 이로 인해 수식이 도입되는 것입니다.

Excel 수식을 사용한 적이 있으면 PowerApps에서 사용하는 방식이 익숙하게 느껴질 것입니다. 사례가 해결되면 상태 표시줄을 녹색으로 표시하고 그렇지 않으면 빨간색으로 표시한다고 가정합니다. 이렇게 하려면 화면에서 상태 컨트롤을 선택한 다음 수식 입력줄에서 해당 컨트롤의 **채우기** 속성을 `If(Status="Resolved", Color.Green, Color.Red)` 수식으로 설정합니다. 이 수식이 Excel 수식과 비슷하지만 PowerApps 수식은 스프레드시트의 셀이 아니라 컨트롤과 기타 앱 요소를 나타냅니다. 다음 이미지에서는 수식을 설정할 위치와 앱의 결과를 보여 줍니다.

![사례 상태를 표시하는 수식](./media/learning-case-app-customize/case-status.png)

## <a name="sort-and-filter-based-on-date"></a>날짜 기준 정렬 및 필터링
찾아보기 화면에서 생성된 앱을 사용하여 사례를 검색하고 갤러리의 항목 목록을 정렬할 수 있습니다. 검색 및 정렬 기능을 제거하여 날짜를 기준으로 한 사례를 표시하겠습니다. 이러한 방법들을 결합할 수도 있지만, 여기서는 이 앱의 날짜 기준 방식에 집중하겠습니다. 아래 이미지에서 추가한 다음 항목을 볼 수 있습니다.

* 사용자가 수행할 작업을 알려주는 텍스트 레이블("사례 표시 기준 날짜(이후):"): **삽입** > **텍스트** > **레이블**로 차례로 이동하여 **채우기** 수식을 **흰색**으로 변경합니다.
* 날짜 선택: **삽입** > **컨트롤** > **날짜 선택**으로 차례로 이동합니다.
* 찾아보기 갤러리 **항목** 속성을 날짜 선택에 연결하는 수식: `Filter(Case, DatePicker1.SelectedDate < LastModifiedDateTime)`

날짜가 10월 20일로 설정되고 앱에서 이 날짜 이후에 만든 사례를 보여 주는 결과가 표시됩니다. 기본적으로 엔터티의 모든 사례에는 마지막으로 수정한 동일한 날짜가 있습니다. 필터를 하나 이상 업데이트하여 필터링 작동 방식을 확인할 수 있습니다. 엔터티 데이터 작업은 이 과정의 뒷부분에서 다룹니다.

![날짜 선택을 사용하도록 업데이트된 앱](./media/learning-case-app-customize/date-picker.png)

## <a name="show-total-number-of-cases"></a>총 사례 수 표시
여기서 많은 부분을 다루고 있지만 사용자 지정이 거의 완료되었습니다. 이 항목에서 마지막으로 수행할 작업은 총 사례 수 및 날짜 기준 필터와 일치하는 사례 수의 두 가지 숫자를 보여 주는 레이블을 추가하는 것입니다.

![총 사례 수 및 필터링된 사례 수 표시](./media/learning-case-app-customize/number-cases.png)

동영상에서 두 개의 레이블을 추가하는 방법에 대해 자세히 설명하지만 다음은 각 레이블에 대해 설정한 속성의 기본 사항입니다.

* **맞춤** = `Center`
* **너비** = `Parent.Width/2`
* 왼쪽 상자 **텍스트** = `"Total cases: " & CountRows(Case)` - 여기에는 엔터티에 있는 모든 사례가 포함됩니다. 
* 오른쪽 상자 **텍스트** = `Filtered cases: " & CountRows(BrowseGallery1.AllItems)` - 여기에는 날짜 기준 필터와 일치하는 사례만 포함됩니다.

예, 이제 앱 사용자 지정을 마무리합니다. 다음 항목에서는 데이터 원본과 흐름을 추가하고 완성된 앱을 보여 줍니다.

