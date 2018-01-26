---
title: "양식 사용자 지정 | Microsoft Docs"
description: "어떤 데이터를 어떤 순서와 어떤 컨트롤 방식으로 표시할지 지정합니다."
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
ms.date: 10/16/2016
ms.author: sharik
ms.openlocfilehash: 51b784376834d8eaa5d186ad0d517e20cf088f38
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="customize-forms-in-powerapps"></a>PowerApps 양식 사용자 지정
**표시 양식** 컨트롤과 **편집 양식** 컨트롤을 사용자 지정하면 가장 직관적인 순서와 컨트롤 방식으로 가장 중요한 데이터를 표시하므로 사용자가 데이터를 쉽게 파악하고 업데이트할 수 있게 됩니다.

각 양식은 하나 이상의 카드로 구성되어 있으며, 각 카드는 데이터 원본의 특정 열에서 데이터를 표시합니다. 이 토픽의 단계를 따르면 양식에 어떤 카드를 표시할지 지정하고, 양식 내에서 카드를 위아래로 이동하며, 각 열의 데이터를 카드 내에 어떻게 표시할지 구성할 수 있습니다.

PowerApps에 대해 잘 모르는 경우 [PowerApps 소개](getting-started.md)를 참조하세요.

## <a name="prerequisites"></a>필수 조건
자습서에서 일반적인 개념을 살펴볼 수 있습니다. 또는 이 단계를 완료하면 자습서의 내용을 정확하게 따를 수 있습니다.

1. PowerApps에서 SharePoint로 [연결을 생성](connect-to-sharepoint.md)합니다.

2. [레이아웃 사용자 지정](customize-layout-sharepoint.md)에서 설명하는SharePoint 목록을 생성합니다.

3. 해당 목록을 따라 [앱을 자동으로 생성](app-from-sharepoint.md)합니다.

4. 왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.

    ![보기 토글](./media/customize-forms-sharepoint/toggle-view.png)

## <a name="show-and-hide-cards"></a>카드 표시 및 숨기기
1. 왼쪽 탐색 모음에서 중간 축소판 그림을 클릭하거나 탭하여 **DetailsScreen1**을 선택합니다.

    ![세부 정보 화면 선택](./media/customize-forms-sharepoint/details-thumbnail.png)

2. 카드를 클릭하거나 탭하여 선택하면 오른쪽 창에 해당 양식의 사용자 지정 옵션이 나타납니다.

    ![카드 선택](./media/customize-forms-sharepoint/select-card.png)

3. 오른쪽 창에서 카드를 숨기려면 **AccountID** 카드의 확인란을 클릭하거나 탭하고, 카드를 표시하려면 **ID** 열의 확인란을 클릭하거나 탭합니다.

    ![카드 표시](./media/customize-forms-sharepoint/checkbox.png)

## <a name="reorder-the-cards"></a>카드 재정렬
* **제목** 카드를 클릭하거나 탭하여 선택한 다음 **OrderDate** 카드가 강조 표시될 때까지 제목 표시줄을 위로 드래그합니다.

    ![카드 이동](./media/customize-forms-sharepoint/move-card.png)

    이동 중인 카드는 마우스 단추를 놓을 때까지 강조 표시된 카드 바로 위에 표시됩니다.

    ![재정렬된 카드](./media/customize-forms-sharepoint/reordered-card.png)

## <a name="run-the-app"></a>앱 실행
1. 왼쪽 탐색 모음에서 상단 축소판 그림을 클릭하거나 탭하여 **BrowseScreen1**을 선택합니다.

    ![BrowseScreen1의 축소판 그림](./media/customize-forms-sharepoint/browse-thumbnail.png)

2. F5 키를 누르거나 오른쪽 위 모서리의 **미리 보기** 아이콘을 선택하여 미리 보기 모드를 실행합니다.  

    ![미리 보기 아이콘](./media/customize-forms-sharepoint/open-preview.png)

3. 오른쪽 위 모서리에서 더하기 아이콘을 클릭하거나 탭하여 **EditScreen1**의 레코드를 추가합니다.

    ![레코드 추가](./media/customize-forms-sharepoint/add-record.png)

4. 원하는 모든 데이터를 추가한 다음 오른쪽 위 모서리의 확인 표시 아이콘을 클릭하거나 탭하여 SharePoint 목록에 새 레코드를 저장하고 **BrowseScreen1**으로 돌아옵니다.

    ![레코드 저장](./media/customize-forms-sharepoint/save-record.png)

5. 방금 생성한 항목의 화살표를 클릭하거나 탭하여 해당 항목에 대한 세부 정보를 **DetailScreen1**에 표시합니다.  

    ![오른쪽 화살표](./media/customize-forms-sharepoint/right-arrow.png)

6. 오른쪽 위 모서리에서 편집 아이콘을 클릭하거나 탭하여 **EditScreen1**의 해당 레코드를 업데이트합니다.

    ![레코드 편집](./media/customize-forms-sharepoint/edit-record.png)

7. 하나 이상의 필드에서 정보를 변경한 다음 오른쪽 위 모서리의 확인 표시를 클릭하거나 탭하여 SharePoint 목록에서 변경 내용을 저장하고 **DetailScreen1**으로 돌아옵니다.  

    ![변경 내용 저장](./media/customize-forms-sharepoint/save-record.png)

8. 오른쪽 위 모서리에서 휴지통 아이콘을 클릭하거나 탭하여 방금 업데이트한 레코드를 삭제하고 **BrowseScreen1**으로 돌아옵니다.

    ![레코드 삭제](./media/customize-forms-sharepoint/delete-record.png)

9. Esc 키를 누르거나, PowerApps의 제목 표시줄 *아래*에서 왼쪽 위 모서리의 닫기 아이콘을 클릭하거나 탭하여 미리 보기 모드를 닫습니다.

    ![미리 보기 모드 닫기](./media/customize-forms-sharepoint/close-preview.png)

## <a name="next-steps"></a>다음 단계
* 다른 장치에서 실행할 수 있도록 앱을 저장하려면 Ctrl-S를 누릅니다.
* 다른 사용자가 앱을 실행할 수 있도록 [앱을 공유](share-app.md)하세요.
