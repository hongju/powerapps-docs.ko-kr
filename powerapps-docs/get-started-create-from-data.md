---
title: "Excel 데이터에서 앱 생성 | Microsoft Docs"
description: "클라우드에서 Excel 파일에 따라 자동으로 앱을 만들고, 앱을 사용자 지정한 후 진행 방법을 탐색합니다."
services: 
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: sharik
ms.openlocfilehash: 1558dba59f4b755ded709329c099feb94b55fac6
ms.sourcegitcommit: e827813cd898ca9a1046b5952ea5e32ce2989a65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="generate-an-app-from-excel-data"></a>Excel 데이터에서 앱 생성
OneDrive와 같은 클라우드 저장소 계정에 업로드하는 Excel 파일에서 데이터에 따라 자동으로 앱을 만듭니다. 앱을 생성한 후에 필요에 더 잘 맞도록 사용자 지정한 다음 예상대로 작동하는지 확인하도록 실행합니다.

생성된 앱에는 기본적으로 세 개의 화면이 있습니다.

* **BrowseScreen1**은 사용자가 특정 레코드를 쉽게 찾을 수 있도록 하나 이상의 필드의 하위 집합, 검색 표시줄 및 정렬 단추를 표시합니다.
* **DetailsScreen1**은 특정 레코드에 대한 더 많은 또는 모든 필드를 표시합니다.
* **EditScreen1**은 사용자가 레코드를 만들거나 업데이트하고 변경 내용을 저장할 수 있도록 하는 UI 요소를 제공합니다.

> [!NOTE]
> [사용자 지정 SharePoint 목록](app-from-sharepoint.md)을 기반으로 앱을 생성할 수도 있습니다.

## <a name="prerequisites"></a>필수 조건
* PowerApps에 [등록](signup-for-powerapps.md)하고 다음 단계 중 하나를 수행합니다.
  * Windows 8, Windows 8.1 또는 Windows 10을 실행하는 컴퓨터에 [Windows용 PowerApps Studio](http://aka.ms/powerappsinstall)를 설치합니다.
  * 브라우저에서 [웹용 PowerApps Studio](create-app-browser.md)(미리 보기)를 엽니다.
* 등록 시 사용한 동일한 자격 증명을 사용하여 PowerApps에 로그인합니다.
* 이 자습서를 정확하게 수행하려면 이 [Excel 파일](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)을 다운로드합니다.
  
    > [!IMPORTANT]
> 데이터가 테이블 형식인 경우 사용자 고유의 Excel 파일을 사용할 수 있습니다. 자세한 내용은 [워크시트에서 Excel 테이블 만들기](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664)를 참조하세요.
* Excel 파일을 OneDrive 또는 다른 [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 업로드합니다.

## <a name="create-an-app"></a>앱 만들기
1. PowerApps Studio에서 **파일** 메뉴(왼쪽 모서리를 따라)에서 **새로 만들기**를 클릭하거나 탭합니다.
   
    ![파일 메뉴의 새 옵션](./media/get-started-create-from-data/file-new.png)
2. 다음 단계 중 하나를 수행합니다.
   
   * 클라우드 저장소 계정이 **데이터와 함께 시작** 아래에 표시되는 경우 **휴대폰 레이아웃**을 클릭하거나 탭합니다.
     
     ![데이터에서 앱을 만드는 옵션](./media/get-started-create-from-data/create-from-data.png)
   * 클라우드 저장소 계정이 **데이터와 함께 시작** 아래에 표시되지 않는 경우 타일의 행 끝에 있는 화살표를 클릭합니다. 계정이 연결 목록에 나타나는 경우 해당 항목을 클릭하거나 탭합니다.
   * 클라우드 저장소 계정이 **데이터와 함께 시작** 아래 또는 연결 목록에 표시되지 않는 경우 **새 연결**을 클릭하거나 탭한 다음 계정에 대한 항목을 클릭하거나 탭합니다. **연결**을 클릭하거나 탭하고, 프롬프트를 따라 연결을 구성합니다.
     
     ![OneDrive에 연결](./media/get-started-create-from-data/connect-onedrive.png)
3. **Excel 파일 선택** 아래에서 **FlooringEstimates.xlsx**를 찾아 클릭하거나 탭합니다.
   
    ![FlooringEstimates Excel 파일](./media/get-started-create-from-data/choose-spreadsheet.png)  
4. **표 선택** 아래에서 **FlooringEstimates**를 클릭하거나 탭합니다.  
   
    ![FlooringEstimates 표 선택](./media/get-started-create-from-data/choose-table.png)
5. 앱을 생성하려면 **연결**을 클릭하거나 탭합니다.
6. 소개 둘러보기를 시작한 경우 PowerApps 사용자 인터페이스의 주요 영역에 친숙해지려면 **다음**을 클릭하거나 탭합니다(또는 **건너뛰기**를 클릭하거나 탭하기).
   
    ![둘러보기를 위해 다음 선택](./media/get-started-create-from-data/quick-tour.png)
   
    > [!NOTE]
> 나중에 오른쪽 위 모서리의 물음표 아이콘을 클릭하거나 탭한 다음 **소개 둘러보기**를 클릭하거나 탭하면 언제든지 둘러보기를 시작할 수 있습니다.

## <a name="change-the-gallery-layout"></a>갤러리 레이아웃 변경
앱을 만든 경우 데이터를 기반으로 하는 기본 레이아웃을 포함하지만 필요에 맞게 갤러리 레이아웃을 사용자 지정할 수 있습니다.

1. 왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.
   
    ![보기 토글](./media/get-started-create-from-data/toggle-view.png)
2. 맨 위의 썸네일을 클릭하거나 탭하여 찾아보기 화면(**BrowseScreen1**)이 선택되었는지 확인합니다.
3. 첫 번째 이미지와 같은 갤러리에서 아무 곳이나 클릭하거나 탭합니다.
   
    ![이미지 선택](./media/get-started-create-from-data/select-image.png)
4. 오른쪽 창에서 **레이아웃** 목록을 연 다음 이미지, 제목 및 부제목을 포함하는 레이아웃을 클릭하거나 탭합니다.
   
    ![레이아웃 선택](./media/get-started-create-from-data/select-layout.png)
   
    선택한 내용을 반영하는 앱 변경 내용의 레이아웃입니다.
   
    ![새 레이아웃이 있는 BrowseScreen1](./media/get-started-create-from-data/browse-layout.png)

## <a name="change-the-data-that-appears"></a>표시되는 데이터 변경
1. **항목 검색** 아래에서 **카페트**를 클릭하거나 탭하여 **레이블** 컨트롤을 선택합니다.
   
   연결된 목록이 오른쪽 창에 강조 표시됩니다.
   
   ![첫 번째 레이블 선택](./media/get-started-create-from-data/select-gallery-textbox.png)
2. 오른쪽 창에서 강조 표시된 목록을 연 다음 **이름**을 클릭하거나 탭합니다.
   
    ![첫 번째 레이블 설정](./media/get-started-create-from-data/set-gallery-textbox.png)
3. 아래 목록을 연 다음 **범주**를 클릭하거나 탭합니다.
   
    ![범주 설정](./media/get-started-create-from-data/set-category.png)
   
    **BrowseScreen1**은 각 레코드에 대한 이름 및 범주를 표시하도록 변경합니다.
   
    ![새 콘텐츠가 있는 BrowseScreen1](./media/get-started-create-from-data/browse-content.png)
   
    > [!NOTE]
> 기본적으로 마우스 휠을 사용하거나 터치 화면에서 위아래로 살짝 밀어서 목록(갤러리라고도 함)을 스크롤할 수 있습니다. 휠 없이 트랙패드 또는 마우스 중 하나를 사용하려면 갤러리를 선택하고, 속성 목록에서 **스크롤 막대 표시**를 클릭하거나 탭한 다음 수식 입력줄에서 **false**를 **true**로 바꿉니다.

## <a name="change-the-order-of-fields-in-a-form"></a>양식의 필드 순서 변경
1. 왼쪽 탐색 모음에서 중간 썸네일을 클릭하거나 탭하여 세부 정보 화면(**DetailsScreen1**)을 엽니다.
   
    ![DetailScreen 1 축소판 그림](./media/get-started-create-from-data/detail-screen-thumbnail.png)
2. 이미지를 클릭하거나 탭하여 양식을 사용자 지정할 수 있는 옵션을 표시합니다.
   
    ![카드 선택](./media/get-started-create-from-data/select-card.png)
3. 오른쪽 창에서 **이름** 필드를 목록의 맨 위로 끌어서 놓습니다.
   
    ![카드 이동](./media/get-started-create-from-data/move-card.png)
   
    화면은 변경 내용을 반영하도록 업데이트합니다.
   
    ![화면 위쪽에 이름 지정](./media/get-started-create-from-data/name-first.png)

## <a name="change-a-control"></a>컨트롤 변경
1. 왼쪽 탐색 모음에서 하단 썸네일을 클릭하거나 탭하여 편집 화면(**EditScreen1**)을 엽니다.
   
    ![EditScreen1 썸네일](./media/get-started-create-from-data/edit-screen-thumbnail.png)
2. **개요**를 클릭하거나 탭합니다.
   
    이 단계는 개요 카드를 선택합니다. 각 카드는 카드의 용도를 설명하는 텍스트를 포함합니다. 카드의 컨트롤을 사용자 지정할 수도 있습니다. 자세한 내용은 [PowerApps의 카드 컨트롤](controls/control-card.md)을 참조하세요.
   
    ![개요 카드 선택](./media/get-started-create-from-data/select-overview.png)
3. 오른쪽 창에서 카드에 대한 아래쪽 화살표를 클릭하거나 탭하고, 아래로 스크롤한 다음 **여러 줄 텍스트 편집**을 클릭하거나 탭합니다.
   
    이 단계는 텍스트를 표시하기에 충분히 큰 컨트롤에서 각 제품의 개요를 보여 줍니다.
   
    ![카드 변경](./media/get-started-create-from-data/card-selector.png)

## <a name="run-the-app"></a>앱 실행
앱을 사용자 지정할 때 미리 보기 모드에서 앱을 실행하여 변경 내용을 테스트할 수 있습니다.

1. 왼쪽 탐색 모음에서 상단 썸네일을 클릭하거나 탭하여 찾아보기 화면(**BrowseScreen1**)을 엽니다.
2. F5 키를 눌러 또는 오른쪽 위 모서리의 **재생** 단추를 클릭하거나 탭하여 미리 보기 모드를 엽니다.
   
    ![미리 보기 아이콘](./media/get-started-create-from-data/open-preview.png)
3. **BrowseScreen1**에서 레코드의 오른쪽 화살표를 클릭하거나 탭하여 세부 정보 화면(**DetailsScreen1**)에 레코드를 표시합니다.
   
    ![BrowseScreen1에서 화살표 선택](./media/get-started-create-from-data/select-record.png)
4. **DetailsScreen1**에서 오른쪽 위 모서리의 연필 아이콘을 클릭하거나 탭하여 편집 화면(**EditScreen1**)에 레코드를 표시합니다.
   
    ![레코드 편집](./media/get-started-create-from-data/edit-record.png)
5. **EditScreen1**에서 하나 이상의 필드에서 정보를 변경한 다음 오른 쪽 위 모서리의 확인 표시를 클릭하거나 탭하여 변경 내용을 저장합니다.
   
    ![EditScreen1에서 변경 내용 저장](./media/get-started-create-from-data/save-record.png)
6. Esc 키를 눌러 (또는 제목 표시줄 아래의 닫기 아이콘을 클릭하거나 탭하여) 미리 보기 모드를 닫습니다.
   
    ![미리 보기 모드 닫기](./media/get-started-create-from-data/close-preview.png)

### <a name="known-limitations"></a>알려진 제한 사항
조직 내에서 Excel 데이터를 공유하는 방법에 대한 자세한 내용은 [이러한 제한 사항을 검토](connections/cloud-storage-blob-connections.md#sharing-excel-tables)하세요.

## <a name="next-steps"></a>다음 단계
* 다른 장치에서 실행할 수 있도록 앱을 저장하려면 Ctrl-S를 누릅니다.
* 이제 데이터에서 앱을 생성하는 방법을 배웠으므로 [처음부터 앱을 만들](get-started-create-from-blank.md) 수 있습니다.
* 다른 사용자가 앱을 실행할 수 있도록 [앱을 공유](share-app.md)하세요.

