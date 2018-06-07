---
title: Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기 | Microsoft Docs
description: 앱을 만들어 레코드를 추가, 업데이트 및 삭제합니다.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: a0aab890e52b49bb0cac382338a8fa02eec736a0
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838490"
---
# <a name="create-an-app-from-scratch-using-a-common-data-service-database"></a>Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기
표준 엔터티(기본 제공), 사용자 지정 엔터티(사용자 조직에서 만듦), 또는 모두를 사용하여 Common Data Service에 저장된 데이터를 관리하는 앱을 빌드합니다.

Common Data Service에서 앱을 빌드하면, SharePoint, Dynamics 365 및 Salesforce와 같은 데이터 원본에서와 마찬가지로 PowerApps에서 연결을 만들 필요가 없습니다. 앱에서 두 활동 모두에 대해 표시, 관리 또는 사용하려는 엔터티를 지정하기만 하면 됩니다.

## <a name="prerequisites"></a>필수 조건
- 앱을 처음부터 만들기 전에 [앱을 생성](data-platform-create-app.md)한 다음, 해당 앱의 [갤러리](customize-layout-sharepoint.md), [양식](customize-forms-sharepoint.md) 및 [카드](customize-card.md)를 사용자 지정하여 PowerApps 기본 사항에 익숙해지도록 합니다.
- 샘플 데이터를 사용하여 데이터베이스를 만든 [환경으로 전환합니다](working-with-environments.md). 적절한 라이선스를 있는 경우 이 요구 사항이 충족되는 [환경을 만들 수 있습니다](../../administrator/create-environment.md).

## <a name="open-a-blank-app"></a>비어 있는 앱 열기
1. [PowerApps](http://web.powerapps.com)에 로그인합니다.

    ![PowerApps 홈 페이지](./media/data-platform-create-app-scratch/sign-in.png)

1. **이러한 앱 만들기** 아래에서 **비어 있는 상태에서 시작** 타일 위를 마우스로 가리키고, 전화 아이콘을 클릭하거나 탭한 다음, **이 앱 만들기**를 클릭하거나 탭합니다.

    ![비어 있는 앱 타일](./media/data-platform-create-app-scratch/blank-app.png)

    전화 또는 다른 장치(예: 태블릿)에 사용할 앱을 처음부터 디자인할 수 있습니다. 이 항목에서는 전화용 앱 디자인에 대해 중점적으로 설명합니다.

## <a name="specify-an-entity"></a>엔터티 지정
1. 화면 가운데에서 **데이터에 연결**을 클릭하거나 탭한 다음, **데이터** 창에서 **Common Data Service** 연결을 클릭하거나 탭합니다.

1. 검색 상자에서 **Accounts**의 처음 몇 글자를 입력하거나 붙여넣어 엔터티 목록을 필터링하고, **Accounts** 확인란을 선택한 다음, **연결**을 클릭하거나 탭합니다.

    ![Accounts 엔터티 지정](./media/data-platform-create-app-scratch/cds-connect.png)

1. 오른쪽 위 모서리에서 닫기 아이콘을 클릭하거나 탭하여 **데이터** 창을 닫습니다.

## <a name="add-a-list-screen"></a>목록 추가 화면
1. **홈** 탭에서 **새 화면**에 대한 아래쪽 화살표를 클릭하거나 탭한 다음, **목록 화면**을 클릭하거나 탭합니다.

    ![목록 추가 화면](./media/data-platform-create-app-scratch/list-screen.png)

1. 왼쪽 탐색 모음에서 **TemplateGalleryList1**을 클릭하거나 탭하여 선택한 다음, **Items** 속성의 값을 다음 수식으로 설정합니다.

    `SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))`

    이 수식에서 지정한 작업은 다음과 같습니다.

    - 갤러리에서 **계정** 엔터티의 데이터를 표시합니다.
    - 사용자가 정렬 단추를 클릭하거나 탭하여 정렬 순서를 토글할 때까지 데이터를 오름차순으로 정렬합니다.
    - 사용자가 검색 창에 하나 이상의 문자를 입력하거나 붙여넣으면 목록에서 사용자가 지정한 문자가 이름 필드에 포함된 계정만 표시합니다.

    [이러한 함수와 다른 많은 함수](formula-reference.md)를 사용하여 앱의 표시 방식과 작동 방식을 지정할 수 있습니다.

    ![갤러리의 Items 속성 설정](./media/data-platform-create-app-scratch/gallery-items.png)

1. 각 계정의 이름만 표시하도록 갤러리의 레이아웃을 설정하고, [갤러리 사용자 지정](customize-layout-sharepoint.md)에서 설명한 대로 **찾아보기** 단어를 표시하도록 제목 표시줄을 구성합니다.

    ![찾아보기 화면](./media/data-platform-create-app-scratch/final-browse.png)

1. 왼쪽 탐색 모음에서 **Screen1** 위를 마우스로 가리키고, 줄임표 아이콘(...)을 클릭하거나 탭한 다음, **삭제**를 클릭하거나 탭합니다.

1. 왼쪽 탐색 모음에서 **Screen2** 위를 마우스로 가리키고, 줄임표 아이콘(...)을 클릭하거나 탭한 다음, **이름 바꾸기**를 클릭하거나 탭합니다.

1. **BrowseScreen**을 입력하거나 붙여넣은 다음, 해당 화면의 갤러리 이름을 **BrowseGallery**로 바꿉니다.

    ![찾아보기 화면 및 갤러리 이름 바꾸기](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>양식 화면 추가
1. 이전 절차의 첫 번째 단계를 반복합니다. 단, **목록 화면** 대신 **양식 화면**을 추가합니다.

1. 오른쪽 창의 **고급 탭**에 표시된 대로 양식의 **DataSource** 속성을 **Accounts**, 해당 **Item** 속성을 **BrowseGallery.Selected**로 설정합니다.

    ![양식의 Datasource 및 Item 속성 설정](./media/data-platform-create-app-scratch/form-datasource.png)

1. 오른쪽 창의 **속성** 탭에서 **Accounts**를 클릭하거나 탭하여 **데이터** 창을 열고, 다음 필드에 대한 확인란을 선택합니다.

    - 계정 이름
    - 주소 1: 나머지 주소
    - 주소 1: 구/군/시
    - 주소 1: 우편 번호
    - 직원 수
    - 연간 수익

1. **만들기/편집**을 표시하도록 제목 표시줄의 **Text** 속성을 설정합니다.

    화면에 변경 내용이 반영됩니다.

    ![양식의 Datasource 및 Item 속성 설정](./media/data-platform-create-app-scratch/field-list.png)

1. 이 화면의 이름을 **FormScreen**으로 변경합니다.

## <a name="configure-icons"></a>아이콘 구성
1. **BrowseScreen**에서 화면 위쪽 근처에서 원형 아이콘을 클릭하거나 탭하고, **OnSelect** 속성을 다음 수식으로 설정합니다.<br>
`Refresh(Accounts)`

    ![새로 고침 아이콘](./media/data-platform-create-app-scratch/refresh-icon.png)

1. 더하기 아이콘을 클릭하거나 탭하고, **OnSelect** 속성을 다음 수식으로 설정합니다.<br>
`NewForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![추가 아이콘](./media/data-platform-create-app-scratch/plus-icon.png)

1. 오른쪽을 가리키는 첫 번째 화살표를 클릭하거나 탭하고, **OnSelect** 속성을 다음 수식으로 설정합니다.<br>
`EditForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![다음 아이콘](./media/data-platform-create-app-scratch/next-icon.png)

1. **FormScreen**에서 취소 아이콘을 클릭하거나 탭하고, **OnSelect** 속성을 다음 수식으로 설정합니다.<br>
`ResetForm(EditForm1);Navigate(BrowseScreen, ScreenTransition.None)`

    ![취소 아이콘](./media/data-platform-create-app-scratch/cancel-icon.png)

1. 확인 표시 아이콘을 클릭하거나 탭하고, **OnSelect** 속성을 다음 수식으로 설정합니다.<br>
`SubmitForm(EditForm1); Navigate(BrowseScreen, ScreenTransition.None)`

    ![확인 표시 아이콘](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. **삽입** 탭에서 **아이콘**을 클릭하거나 탭한 다음, **휴지통** 아이콘을 클릭하거나 탭합니다.

1. **휴지통** 아이콘의 **Color** 속성을 **White**로 설정하고, **OnSelect** 속성을 다음 수식으로 설정합니다.<br>
`Remove(Accounts, BrowseGallery.Selected); Navigate(BrowseScreen, ScreenTransition.None)`

    ![휴지통 아이콘](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>앱 테스트
1. 왼쪽 탐색 모음에서 **BrowseScreen**을 선택한 다음, F5 키를 누르거나 오른쪽 위 모서리 근처에서 재생 아이콘을 클릭하거나 탭하여 미리 보기를 엽니다.

    ![미리 보기 열기](./media/data-platform-create-app-scratch/open-preview.png)

1. 오름차순 및 내림차순 정렬 순서 간에 목록을 설정/해제하고, 각 계정 이름의 특정 문자를 기준으로 목록을 필터링합니다.

1. 계정을 추가하고, 추가한 계정을 편집하고, 계정 업데이트를 시작하지만, 변경 내용을 취소한 다음, 계정을 삭제합니다.

## <a name="next-steps"></a>다음 단계
[하나 이상의 샘플 앱을 열고](open-and-run-a-sample-app.md), 만들 수 있는 다양한 유형의 앱을 살펴봅니다.

