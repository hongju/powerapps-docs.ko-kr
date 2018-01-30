---
title: "SharePoint 목록의 데이터를 관리하는 앱 생성 | Microsoft Docs"
description: "사이트가 온-프레미스에 있거나 클라우드에 있을 때 SharePoint 목록의 데이터를 관리하는 세 화면 앱을 생성합니다."
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
ms.date: 06/05/2017
ms.author: sharik
ms.openlocfilehash: 36a9188615c14262de0bfdea21d58010a053e01f
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="generate-an-app-to-manage-data-in-a-sharepoint-list"></a>SharePoint 목록의 데이터를 관리하는 앱 생성



PowerApps에서 사이트가 온-프레미스에 있거나 클라우드에 있을 때 SharePoint 목록의 데이터를 관리하는 세 화면 앱을 자동으로 생성합니다.

기본적으로, 생성된 모든 앱에는 레코드 탐색을 위한 화면, 레코드의 세부 정보 표시를 위한 화면, 및 레코드 생성 및 업데이트를 위한 화면이 있습니다. 각 화면에 대한 초기 레이아웃과 콘텐츠는 자동으로 결정되지만, 사용자의 요구 사항에 맞게 앱을 사용자 지정해야 할 수도 있습니다.

PowerApps에 대해 잘 모르는 경우 [PowerApps 소개](getting-started.md)를 참조하세요.

이 문서가 작성된 시점부터 PowerApps는 라이브러리가 아닌 사용자 지정 목록을 지원합니다. 또한 데이터를 열에서 **선택** 및 **그림**과 같은 일부 형식으로 표시할 수 있지만 해당 데이터를 업데이트할 수 없습니다. 자세한 내용은 [알려진 문제](connections/connection-sharepoint-online.md#known-issues)를 참조하세요.

> [!NOTE]
> 열 이름에 공백이 있으면 PowerApps에서 **“\_x0020\_”**으로 표시됩니다. 예를 들어 **“Column Name”**은 **“Column_x0020_Name”**으로 표시됩니다.

## <a name="specify-a-sharepoint-app"></a>SharePoint 앱 지정
1. 아직 [SharePoint에 연결](connect-to-sharepoint.md)을 만들지 않은 경우 하나를 만듭니다.
2. 다음 중 *한 가지* 방법으로 PowerApps를 엽니다.
   
   * [Windows용 PowerApps Studio를 설치](http://aka.ms/powerappsinstall)하고 연 다음 등록할 때 사용했던 동일한 자격 증명으로 로그인합니다. 왼쪽 가장자리 부근에서 **새로 만들기**를 클릭하거나 탭합니다.
     
       ![파일 메뉴의 새 옵션](./media/app-from-sharepoint/file-menu.png)
   * 브라우저에서 [웹용 PowerApps Studio를 엽니다](https://create.powerapps.com/api/start).
     
       웹용 PowerApps Studio의 미리 보기 릴리스에서 지원되는 브라우저 목록 및 제한 사항은 [브라우저에서 앱 생성 또는 편집](create-app-browser.md)을 참조하세요.
3. **데이터를 통해 시작**에서 SharePoint 타일의 **휴대폰 레이아웃**을 클릭하거나 탭합니다.
   
    ![](./media/app-from-sharepoint/sharepoint-tile.png)

## <a name="specify-a-site-and-a-list"></a>사이트 및 목록 지정
1. **SharePoint 사이트에 연결** 아래에서 사용하려는 목록이 포함된 사이트에 URL을 입력하거나 붙여넣기한 다음 **이동**을 클릭하거나 탭합니다.
   
    > [!NOTE]
> URL에는 특정 목록을 포함하지 않습니다.
   
    ![](./media/app-from-sharepoint/specify-site.png)
2. **목록 선택** 아래에서 사용하려는 목록의 이름을 클릭하거나 탭합니다.
   
    정렬 단추를 클릭하거나 탭하면 목록 이름을 사전순으로 정렬할 수 있습니다.
   
    ![](./media/app-from-sharepoint/sort-button.png)
   
    또한 검색 상자에 최소 하나의 문자를 입력하거나 붙여넣으면 지정한 텍스트가 포함된 목록 이름만 표시할 수 있습니다.
   
    ![](./media/app-from-sharepoint/choose-list.png)
   
    일부 목록 형식은 기본적으로 표시되지 않습니다. 사용할 목록의 이름이 표시되지 않는 경우 아래쪽으로 스크롤한 다음 **사용자 지정 목록 이름 입력**이 포함된 상자에 목록 이름을 입력합니다.
   
    ![](./media/app-from-sharepoint/custom-list.png)
3. 앱을 생성하려면 **연결**을 클릭하거나 탭합니다.
   
    ![연결 단추](./media/app-from-sharepoint/connect-button.png)
4. 소개 둘러보기를 시작한 경우 PowerApps 인터페이스의 주요 영역에 친숙해지려면 **다음**을 클릭하거나 탭합니다(또는 **건너뛰기**를 클릭하거나 탭하기).
   
    ![소개 둘러보기 화면 열기](./media/app-from-sharepoint/quick-tour.png)
   
    나중에 오른쪽 위 모서리의 물음표 아이콘을 클릭하거나 탭한 다음 **소개 둘러보기**를 클릭하거나 탭하면 언제든지 둘러보기를 시작할 수 있습니다.

## <a name="next-steps"></a>다음 단계
* 방금 생성한 앱을 저장하려면 Ctrl-S 키를 누릅니다.
* 찾아보기 화면(기본으로 나타남)을 사용자 지정하려면 [레이아웃 사용자 지정](customize-layout-sharepoint.md)을 참조하세요.
* 세부 정보를 사용자 지정하거나 화면을 편집하려면 [양식 사용자 지정](customize-forms-sharepoint.md)을 참조하세요.

