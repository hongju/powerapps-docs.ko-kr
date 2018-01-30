---
title: "Common Data Service 데이터베이스를 사용하여 앱 생성 | Microsoft Docs"
description: "앱을 생성하여 레코드를 추가, 업데이트 및 삭제합니다."
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: 159bfc93ce7979bf5ca3ca0e701c8a78c27dbb40
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="generate-an-app-by-using-a-common-data-service-database"></a>Common Data Service 데이터베이스를 사용하여 앱 생성
Common Data Service에 저장된 데이터를 관리하는 앱을 자동으로 생성할 수 있습니다. 모델에 기본 제공되는 여러 표준 엔터티 또는 사용자 또는 조직에서 다른 사람이 만든 사용자 지정 엔터티 중 하나에서 데이터를 관리할 수 있습니다.

Common Data Service에 대해 잘 모르는 경우 [엔터티 이해](data-platform-intro.md)를 참조하세요.

이 토픽에서는 지정하는 단일 엔터티를 기반으로 하는 앱을 자동으로 생성하는 방법을 설명합니다. 둘 이상의 엔터티를 기반으로 하는 앱을 빌드하는 방법에 대한 내용은 [앱을 처음부터 빌드하기](data-platform-create-app-scratch.md)를 참조하세요.

기본적으로 Microsoft PowerApps가 생성하는 모든 앱은 세 개의 화면이 있습니다.

* 찾아보기 화면은 사용자가 특정 레코드를 쉽게 찾을 수 있도록 하나 이상의 필드의 하위 집합, 검색 표시줄 및 정렬 단추를 표시합니다.
* 세부 정보 화면에는 특정 레코드에 대한 더 많은 또는 모든 필드가 표시됩니다.
* 편집 화면은 사용자가 레코드를 만들거나 업데이트하고 변경 내용을 저장할 수 있도록 하는 UI 요소를 제공합니다.

> [!NOTE]
> Common Data Service에서 앱을 생성하면, SharePoint, Dynamics 365 및 Salesforce와 같은 데이터 원본으로 만들듯이 PowerApps에서 연결을 만들지 않아도 됩니다. 앱에서 표시, 관리하거나 표시하고 관리할 엔터티를 지정해야 합니다.

## <a name="generate-an-app"></a>앱 생성
1. Common Data Service 데이터베이스를 만듭니다. 자세한 내용은 [ Common Data Service 데이터베이스 만들기](create-database.md)를 참조하세요.

2. Windows용 PowerApps Studio에서 **파일** 메뉴(왼쪽 모서리를 따라)의 **새로 만들기**를 클릭하거나 탭합니다.

3. **데이터를 통해 시작** 아래의 **Common Data Service** 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.

4. **엔터티 선택**에서 **연락처** 엔터티를 클릭하거나 탭합니다.

5. **연결**을 클릭하거나 탭하여 앱을 자동으로 생성합니다.

    이 시점에서 소개를 둘러보라는 메시지가 표시될 수 있습니다. 나중에 오른쪽 위 모서리의 물음표 아이콘을 클릭하거나 탭한 다음 **소개 둘러보기**를 클릭하거나 탭하여 둘러보기를 시작할 수도 있습니다.

6. 왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.

    ![보기 토글](./media/data-platform-create-app/toggle-view.png)

## <a name="customize-the-browse-screen"></a>찾아보기 화면 사용자 지정
1. 오른쪽 창에서 머리글만을 표시하는 레이아웃을 클릭하거나 탭합니다.

    ![레이아웃 선택](./media/data-platform-create-app/choose-gallery-layout.png)

2. 검색 상자에서 **레이블** 컨트롤을 클릭하거나 탭하여 선택합니다.

    ![레이블 선택](./media/data-platform-create-app/select-textbox.png)

3. 오른쪽 창의 드롭다운 목록에서 **이름의 성**을 선택합니다.

    선택한 **레이블** 컨트롤은 해당 필드의 데이터를 보여 줍니다.

4. 찾아보기 화면에서 위의 이름을 제외한 이름을 클릭하거나 탭하여 갤러리를 선택합니다.

    선택 상자는 갤러리를 둘러쌉니다.

    ![갤러리 선택](./media/data-platform-create-app/select-gallery.png)

5. 다음 수식을 선택한 다음 Ctrl+C를 눌러 복사합니다.

    **SortByColumns(Search(Contact, TextSearchBox1.Text, "Name_Surname"), "Name_Surname", If(SortDescending1, Descending, Ascending))**

6. 왼쪽 위 모서리 근처에서 속성 목록이 **항목**을 표시하는지 확인합니다.

7. 수식 입력줄에서 기본 수식을 선택합니다.

    ![항목 속성의 기본값](./media/data-platform-create-app/default-items.png)

8. Delete 키를 눌러 기본 수식을 삭제한 다음 복사한 수식을 붙여넣습니다. 갤러리의 이름은 사전순으로 정렬됩니다.

## <a name="test-the-browse-screen"></a>찾아보기 화면 테스트
1. F5 키를 누르거나 오른쪽 위 모서리의 **재생** 단추를 클릭하거나 탭하여 미리 보기 모드를 엽니다.

2. 터치 스크린 또는 마우스 휠을 사용하거나 스크롤 막대가 나타나도록 마우스로 갤러리를 가리켜서 모든 레코드를 스크롤합니다.

3. 오른쪽 위 모서리에서 정렬 단추를 한 번 이상 클릭하거나 탭하여 이름이 나열된 순서를 변경합니다.

    ![정렬 순서 변경](./media/data-platform-create-app/sort-button.png)

4. 검색 상자에 해당 문자를 포함하는 이름만 표시하도록 문자를 입력합니다.

5. 검색 상자에서 모든 텍스트를 제거한 다음 목록에서 첫 번째 이름 오른쪽에 있는 화살표를 클릭하거나 탭합니다.

    세부 정보 화면이 열리고 선택한 연락처에 대한 자세한 정보를 보여 줍니다.

6. Esc 키를 누르거나 제목 막대의 왼쪽 위 모서리에서 **닫기** 버튼을 클릭하거나 탭하여 디자인 작업 영역으로 돌아갑니다.

## <a name="customize-the-other-screens"></a>다른 화면 사용자 지정
1. **DetailScreen**이 표시되지 않는 경우 왼쪽 탐색 모음에서 중간 썸네일을 클릭하거나 탭합니다.

2. **DetailScreen**의 위쪽에서 **전체 이름**을 클릭하거나 탭하여 해당 화면의 양식을 사용자 지정하기 위한 옵션을 표시합니다.

3. 오른쪽 창에서 **Name_MiddleName**에 대한 눈 모양 단추를 클릭하거나 탭하여 해당 필드를 숨깁니다.

4. 오른쪽 창에서 **Name_Surname**에 대한 눈 모양 단추를 클릭하거나 탭하여 해당 필드를 표시합니다.

5. 오른쪽 창에서 **Name_Surname**을 위로 끌어서 놓고, **Name_GivenName** 아래에 끌어서 놓습니다.

    **DetailScreen**은 변경 내용을 반영합니다.

6. 왼쪽 탐색 모음에서 아래쪽 썸네일을 클릭하거나 탭하여 **EditScreen**을 표시한 다음 **EditScreen**이 **DetailScreen**과 일치하도록 이 절차에서 이전 단계를 반복합니다.

## <a name="test-the-app"></a>앱 테스트
1. 왼쪽 탐색 모음에서 상단 썸네일 이미지를 클릭하거나 탭하여 찾아보기 화면을 엽니다.

2. F5 키를 누르거나 오른쪽 위 모서리의 **재생** 단추를 클릭하거나 탭하여 미리 보기 모드를 엽니다.

3. 찾아보기 화면 오른쪽 위 모서리에서 더하기 기호 버튼(**+**)을 클릭하거나 탭하여 레코드를 작성합니다.

4. **이름** 및 **성** 필드에 텍스트를 추가한 다음 확인 표시 단추를 클릭하거나 탭하여 새 레코드를 저장하고 찾아보기 화면으로 돌아옵니다.

5. 방금 만든 레코드를 찾은 다음 레코드의 오른쪽 화살표를 클릭하거나 탭하여 세부 정보 화면에 레코드를 표시합니다.

6. 오른쪽 위 모서리에서 연필 버튼을 클릭하거나 탭하여 편집 화면에 레코드를 표시합니다.

7. **이름** 필드의 데이터를 변경한 다음 확인 표시 단추를 클릭하거나 탭하여 변경 내용을 저장합니다.

8. 오른쪽 위 모서리에서 휴지통 버튼을 클릭하거나 탭하여 만들고 업데이트한 레코드를 삭제합니다.

## <a name="next-steps"></a>다음 단계
[Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](data-platform-create-app-scratch.md)
