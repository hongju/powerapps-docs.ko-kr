---
title: PowerApps에서 SharePoint로부터 앱을 생성하는 빠른 시작 | Microsoft Docs
description: SharePoint 목록의 데이터를 관리하는 앱을 PowerApps에서 자동으로 생성합니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/12/2018
ms.author: anneta
ms.openlocfilehash: b9404b2ac7d67f9594b77ee73de55b46a94e7afa
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39016815"
---
# <a name="quickstart-for-generating-an-app-in-powerapps-from-sharepoint"></a>PowerApps에서 SharePoint로부터 앱을 생성하는 빠른 시작

이 빠른 시작에서는 PowerApps를 사용하여 SharePoint에서 만든 목록에 따라 첫 번째 앱을 자동으로 생성합니다. 이 앱에서는 목록의 모든 항목을 찾아보고, 단일 항목의 세부 정보를 표시하며, 항목을 생성, 업데이트 또는 삭제할 수 있습니다.

SharePoint에 목록이 있으면 이 빠른 시작에서 개념과 기술을 알아볼 수 있습니다. 이 빠른 시작을 정확하게 수행하려면 SharePoint Online 사이트에서 **Title** 열이 포함된 **SimpleApp**이라는 목록을 만듭니다. 목록에서 **바닐라**, **초콜릿** 및 **딸기**에 대한 항목을 만듭니다.

텍스트, 날짜, 숫자 및 통화와 같은 다양한 형식의 여러 열이 포함된 훨씬 더 복잡한 목록을 만들 수 있습니다. 앱을 생성하는 원칙은 변경되지 않습니다. 또한 데이터 게이트웨이를 통해 [사이트에 연결](connect-to-sharepoint.md)하는 경우, 온-프레미스 SharePoint 사이트의 목록에서 앱을 생성할 수도 있습니다.

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="generate-an-app"></a>앱 생성
1. [PowerApps](https://web.powerapps.com)에 로그인합니다.

    ![PowerApps 홈 페이지](./media/app-from-sharepoint/sign-in.png)

1. **이러한 앱 만들기** 아래에서 **데이터로 시작** 위를 마우스로 가리킨 다음, **이 앱 만들기**를 선택합니다.

    ![앱 만들기 옵션](./media/app-from-sharepoint/make-this-app.png)

1. SharePoint 타일에서 **전화 레이아웃**을 선택합니다.

    ![앱 만들기 옵션](./media/app-from-sharepoint/sharepoint-tile.png)

1. **직접 연결** 옵션을 선택하고 **만들기**를 선택합니다.

    ![연결 만들기](./media/app-from-sharepoint/create-connection.png)

1. **SharePoint 사이트에 연결** 아래에서 SharePoint Online 사이트에 대한 URL을 입력하거나 붙여넣은 다음, **이동**을 선택합니다.

    다음 예와 같이 사이트 URL(목록 이름이 아님)만 포함합니다.<br>`https://microsoft.sharepoint.com/teams/Contoso`

1. **목록 선택** 아래에서 **SimpleApp**을 선택한 다음, **연결**을 선택합니다.

몇 분 후에 앱이 찾아보기 화면에 열리고 목록에 만든 항목이 표시됩니다. 목록에 **Title**보다 많은 열의 데이터가 있는 경우 앱에 해당 데이터가 표시됩니다. 화면 위쪽 근처의 제목 표시줄에는 목록 새로 고침, 목록 나열 및 목록에 항목 만들기 아이콘이 표시됩니다. 제목 표시줄 아래의 검색 상자에서 입력하거나 붙여넣을 텍스트를 기준으로 목록을 필터링하는 옵션을 제공합니다. 

![찾아보기 화면](./media/app-from-sharepoint/browse-screen.png)

이 앱을 사용하거나 다른 사용자와 공유하기 전에 더 많은 변경 작업을 수행하려고 할 것입니다. 가장 좋은 방법은 진행하기 전에 Ctrl-S를 눌러 지금까지의 작업을 저장하는 것입니다. 앱에 이름을 지정한 다음, **저장**을 선택합니다.

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 SharePoint 목록의 데이터를 관리하는 앱을 만들었습니다. 다음 단계에서는 더 복잡한 목록에서 앱을 생성한 다음, 사용자의 요구 사항에 맞게 앱을 사용자 지정합니다(찾아보기 화면으로 시작).

> [!div class="nextstepaction"]
> [기본 찾아보기 화면 사용자 지정](customize-layout-sharepoint.md)