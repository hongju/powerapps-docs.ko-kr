---
title: 갤러리 사용자 지정 자습서 | Microsoft Docs
description: 이 자습서에서는 PowerApps에서 생성된 앱의 갤러리를 포함하여 기본 찾아보기 화면을 사용자 지정합니다.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/11/2018
ms.author: anneta
ms.openlocfilehash: 30ec6be11b40e01dddfe09cf0ac8af0ed3a8a437
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>자습서: PowerApps에서 갤러리 사용자 지정
이 자습서에서는 PowerApps에서 생성된 앱의 갤러리를 포함하여 기본 찾아보기 화면을 사용자 지정합니다. 기본 앱을 사용자 지정하지 않고 사용하여 데이터를 관리할 수 있지만, 다음과 같이 변경하면 훨씬 더 강력하고 사용하기 쉽습니다.

> [!div class="checklist"]
> * 레이아웃 변경
> * 표시되는 데이터 변경
> * 필터링 및 정렬할 열 설정
> * 필터링 및 정렬 테스트
> * 제목 변경
> * 스크롤 막대 표시

이 자습서는 [Common Data Service for Apps](../common-data-service/data-platform-intro.md)에서 생성된 앱으로 시작하지만, SharePoint, Excel 및 기타 데이터 원본에서 생성된 앱에도 동일한 개념이 적용됩니다. 

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="prerequisites"></a>필수 조건
이 자습서를 시작하기 전에 Common Data Service for Apps에서 [앱을 생성](data-platform-create-app.md)합니다.

## <a name="open-the-generated-app"></a>생성된 앱 열기
1. [PowerApps](https://web.powerapps.com)에 로그인한 다음, 왼쪽 가장자리 근처에 있는 **앱**을 클릭하거나 탭합니다.

    ![PowerApps 홈 페이지](./media/customize-layout-sharepoint/sign-in.png)

1. 생성한 앱을 찾은 다음, 오른쪽 가장자리 근처에 있는 줄임표 아이콘(**...**)을 클릭하거나 탭합니다.

    ![앱 목록](./media/customize-layout-sharepoint/open-for-edit.png)

1. 표시되는 메뉴에서 앱을 편집하는 옵션을 클릭하거나 탭합니다. 

## <a name="customize-the-gallery"></a>갤러리 사용자 지정
1. 찾아보기 화면에서 계정 목록의 첫 번째 항목을 제외한 항목을 클릭하거나 탭합니다.

    이 단계에서는 계정 목록을 보여 주는 **갤러리** 컨트롤을 선택합니다.

    ![선택한 갤러리](./media/customize-layout-sharepoint/select-gallery.png)

1. 오른쪽 창에서 **데이터** 레이블의 오른쪽에 있는 **계정**을 클릭하거나 탭합니다.

    ![**데이터** 창 열기](./media/customize-layout-sharepoint/open-data-pane.png)

1. **데이터** 창의 **레이아웃** 아래에서 아래쪽 화살표를 클릭하거나 탭하여 옵션 목록을 엽니다.

    ![레이아웃 옵션 표시](./media/customize-layout-sharepoint/show-layouts.png)

1. 옵션 목록에서 제목만 표시하는 옵션을 클릭하거나 탭합니다.

    ![제목 전용 레이아웃 선택](./media/customize-layout-sharepoint/choose-layout.png)

1. **데이터** 창에서 아래쪽 화살표를 클릭하거나 탭하여 제목 옵션 목록을 엽니다.

    ![제목 전용 레이아웃 선택](./media/customize-layout-sharepoint/show-title-options.png)

1. 옵션 목록에서 **이름**을 클릭하거나 탭하여 해당 데이터를 **갤러리**에 표시합니다.

    ![최종 갤러리](./media/customize-layout-sharepoint/final-gallery.png)


## <a name="set-the-sort-and-search-columns"></a>열 정렬 및 검색 설정
1. 이전 섹션에서 설명한 대로 **갤러리** 컨트롤을 선택합니다.

    ![갤러리 선택](./media/customize-layout-sharepoint/select-gallery-title.png)

2. 왼쪽 위 모서리 근처에서 속성 목록이 **항목**을 표시하는지 확인합니다.

    ![항목 속성](./media/customize-layout-sharepoint/items-property.png)

    이 속성의 값은 수식 입력줄에 표시되며, 갤러리의 데이터 원본뿐만 아니라 필터링 및 정렬 열도 결정합니다.

1. 수식 입력줄에서 **emailaddress1**의 두 인스턴스를 **name**으로 바꾸고, 각 인스턴스를 둘러싼 큰따옴표를 유지합니다.

    수식은 다음 예제와 일치해야 합니다.

    ![Items 속성에 대한 수식](./media/customize-layout-sharepoint/items-value.png)

    **name**의 첫 번째 인스턴스는 목록을 필터링하여 사용자가 검색 창에 입력한 텍스트가 계정 이름에 포함된 레코드만 표시하도록 지정합니다. **name**의 두 번째 인스턴스는 사용자가 목록을 계정 이름별 사전순으로 정렬할 수 있도록 지정합니다. 이러한 함수 및 다른 함수에 대한 자세한 내용은 [수식 참조](formula-reference.md)를 참조하세요.

## <a name="test-sorting-and-searching"></a>정렬 및 검색 테스트
1. F5 키를 눌러 (또는 오른쪽 위 모서리의 재생 단추를 클릭하거나 탭하기) 미리 보기 모드를 엽니다.

    ![미리 보기 모드 열기](./media/customize-layout-sharepoint/open-preview.png)

1. 브라우저 화면의 오른쪽 위 모서리 근처에서 정렬 아이콘을 한 번 이상 클릭하거나 탭하여 사전순 정렬 순서를 오름차순과 내림차순 중에서 변경합니다.

    ![정렬 아이콘 테스트](./media/customize-layout-sharepoint/sort-button.png)

1. 검색 상자에서 **k**를 입력하여 이름에 입력한 문자가 포함된 계정만 표시합니다.

    ![검색 표시줄 테스트](./media/customize-layout-sharepoint/test-filter.png)

1. 검색 표시줄에서 모든 텍스트를 삭제한 다음 Esc키를 눌러 (또는 PowerApps의 제목 표시줄 *아래*의 닫기 아이콘을 클릭하거나 탭하기) 미리 보기 모드를 닫습니다.

## <a name="change-the-title-of-the-screen"></a>화면 제목 변경
1. 화면의 제목을 클릭하거나 탭하여 선택합니다.

    ![화면 제목 선택](./media/customize-layout-sharepoint/select-title.png)

1. 속성 목록에 **Text**가 표시되는지 확인한 다음, 수식 입력줄에서 **찾아보기**를 큰따옴표로 묶어 입력합니다.

    ![화면 제목 업데이트](./media/customize-layout-sharepoint/change-screen-title.png)

    화면은 변경 내용을 반영합니다.

    ![새 화면 제목](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scroll-bar"></a>스크롤 막대 표시
사용자가 터치 스크린 또는 마우스 휠을 가지고 있지 않은 경우 사용자가 **갤러리** 컨트롤 위를 마우스로 가리키면 스크롤 막대를 표시하도록 이 컨트롤을 구성합니다. 이렇게 하면 화면에 모든 계정을 한 번에 표시할 수 없는 경우에도 모든 계정을 표시할 수 있습니다.

1. 첫 번째 절차에서 설명한 대로 **갤러리** 컨트롤을 선택합니다.

    ![갤러리 선택](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. **갤러리** 탭에서 **스크롤 막대 표시**를 클릭하거나 탭하고 해당 속성 값이 **true**로 변경되었는지 확인합니다. 

    ![스크롤 막대 표시](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>다음 단계
이 자습서에서는 **갤러리** 컨트롤 및 생성된 앱의 기본 찾아보기 화면에 대한 제목을 사용자 지정했습니다. 세부 정보를 표시하고 계정을 만들거나 업데이트하는 기본 화면을 사용자 지정할 수도 있습니다. 이러한 화면에는 **표시 양식** 컨트롤 및 **편집 양식** 컨트롤이 포함되어 있으며, 표시되는 데이터의 형식과 순서를 변경할 수 있습니다.

> [!div class="nextstepaction"]
> [양식 사용자 지정](customize-forms-sharepoint.md)