---
title: PowerApps에서 SharePoint에 대한 연결 만들기 | Microsoft Docs
description: powerapps.com에서 앱을 자동으로 생성하거나 처음부터 새로 빌드하는 데 사용하도록 SharePoint에 대한 연결을 만듭니다.
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/03/2016
ms.author: sharik
ms.openlocfilehash: 2b058fc1fd3b3af24485aa20bdab9511aa5d0b79
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="create-a-connection-to-sharepoint-from-powerapps"></a>PowerApps에서 SharePoint에 대한 연결 만들기
SharePoint Online 또는 온-프레미스 SharePoint 중 하나에 대한 연결을 만들면 앱을 자동으로 생성하거나 처음부터 새로 빌드할 수 있습니다.

PowerApps에 대해 잘 모르는 경우 [PowerApps 소개](getting-started.md)를 참조하세요.

이 문서가 작성된 시점부터 PowerApps는 라이브러리가 아닌 사용자 지정 목록을 지원합니다. 또한 데이터를 열에서 **선택** 및 **그림**과 같은 일부 형식으로 표시할 수 있지만 해당 데이터를 업데이트할 수 없습니다. 자세한 내용은 [알려진 문제](connections/connection-sharepoint-online.md#known-issues)를 참조하세요.

## <a name="specify-a-sharepoint-connection"></a>SharePoint 연결 지정
1. 아직 등록하지 않은 경우 [PowerApps에 등록](../signup-for-powerapps.md)합니다.

2. 등록 시 사용한 동일한 자격 증명을 사용하여 [powerapps.com](https://web.powerapps.com)에 로그인합니다.

3. 왼쪽 탐색 모음에서 **관리**를 클릭하거나 탭한 다음 **연결**을 클릭하거나 탭합니다.

    ![파일 메뉴의 새 옵션](./media/connect-to-sharepoint/manage-connections.png)

4. 오른쪽 위 모서리에서 **새 연결**을 클릭하거나 탭합니다.

    ![새 연결 단추](./media/connect-to-sharepoint/new-connection.png)

5. 연결 목록에서 **SharePoint**를 클릭하거나 탭합니다.

    ![SharePoint 연결 추가](./media/connect-to-sharepoint/add-sp-portal.png)

6. 이 토픽 후반부에 나오는 이러한 절차의 각 단계를 따릅니다.

   * [SharePoint Online 사이트에 연결](connect-to-sharepoint.md#connect-to-a-sharepoint-online-site)합니다.
   * [온-프레미스 SharePoint 사이트에 연결](connect-to-sharepoint.md#connect-to-an-on-premises-sharepoint-site)합니다.

## <a name="connect-to-a-sharepoint-online-site"></a>SharePoint Online 사이트에 연결
1. **직접 연결(클라우드 서비스)**을 클릭하거나 탭한 다음 **연결 추가**를 클릭하거나 탭합니다.

    ![SharePoint Online 선택](./media/connect-to-sharepoint/choose-online.png)

2. 이 토픽 마지막에 있는 [다음 단계](connect-to-sharepoint.md#next-steps)로 이동합니다.

## <a name="connect-to-an-on-premises-sharepoint-site"></a>온-프레미스 SharePoint 사이트에 연결
1. **온-프레미스 데이터 게이트웨이를 사용한 연결**을 클릭하거나 탭합니다.

    ![온-프레미스 SharePoint 선택](./media/connect-to-sharepoint/choose-onprem.png)

    > [!NOTE]
> 게이트웨이 및 온-프레미스 연결은 사용자의 [기본 환경](working-with-environments.md)에서만 생성하고 사용할 수 있습니다.

2. 사용자 이름과 암호를 지정합니다.

    자격 증명에 도메인 이름이 포함된 경우 *Domain\Alias* 형식으로 지정합니다.

    ![자격 증명 지정](./media/connect-to-sharepoint/specify-credentials.png)

3. 온-프레미스 데이터 게이트웨이를 설치하지 않은 경우 [하나를 설치](gateway-reference.md)한 다음 게이트웨이 목록을 새로 고침하는 아이콘을 클릭하거나 탭합니다.

    ![게이트웨이 설치](./media/connect-to-sharepoint/install-gateway.png)

4. **게이트웨이 선택** 아래에서 사용하려는 게이트웨이를 클릭하거나 탭한 다음 **연결 추가**를 클릭하거나 탭합니다.

    ![게이트웨이 선택](./media/connect-to-sharepoint/choose-gateway.png)

## <a name="next-steps"></a>다음 단계
* 지정한 목록에 기반한 [앱을 자동으로 생성합니다](app-from-sharepoint.md). 해당 앱에는 기본적으로 3개의 화면이 있는데 레코드를 검색하고, 단일 레코드에 대한 세부 정보를 표시하며, 레코드를 생성 또는 업데이트하기 위한 화면들입니다.
* [앱을 처음부터 빌드합니다](get-started-create-from-blank.md). 이 토픽은 Excel에 대해 작성되었지만 SharePoint에도 동일한 원칙이 적용됩니다.
