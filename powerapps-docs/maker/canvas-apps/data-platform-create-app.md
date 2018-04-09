---
title: PowerApps에서 Common Data Service for Apps 앱 생성(빠른 시작) | Microsoft Docs
description: Common Data Service for Apps의 데이터를 관리하는 앱을 PowerApps에서 자동으로 생성합니다.
services: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/10/2018
ms.author: anneta
ms.openlocfilehash: 78429fc5d0220b5cc9e8dc726583c2e9e543f85a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-for-generating-an-app-in-powerapps-for-the-common-data-service-for-apps"></a>PowerApps에서 Common Data Service for Apps 앱을 생성하는 빠른 시작

이 빠른 시작에서는 PowerApps를 사용하여 [Common Data Service for Apps](../common-data-service/data-platform-intro.md)의 샘플 계정 목록에 따라 첫 번째 앱을 자동으로 생성합니다. 이 앱에서는 모든 계정을 찾아보고, 단일 계정의 세부 정보를 표시하며, 계정을 생성, 업데이트 또는 삭제할 수 있습니다.

이 빠른 시작을 수행하려면 Common Data Service의 데이터베이스가 만들어지고 데이터가 포함된 [환경](working-with-environments.md)으로 전환해야 합니다. 이러한 환경이 없고 관리자 권한이 있으면 이 요구 사항을 충족하는 [환경을 만들 수 있습니다](../../administrator/environments-administration.md#create-an-environment).

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="generate-an-app"></a>앱 생성
1. [PowerApps](https://web.powerapps.com)에 로그인합니다.

    ![PowerApps 홈 페이지](./media/data-platform-create-app/sign-in.png)

1. **이러한 앱 만들기** 아래에서 **데이터로 시작** 위를 마우스로 가리킨 다음, **이 앱 만들기**를 선택합니다.

    ![앱 만들기 옵션](./media/data-platform-create-app/make-this-app.png)

1. **데이터로 시작** 아래에서 오른쪽을 가리키는 화살표를 선택합니다.

    ![화살표 아이콘](./media/data-platform-create-app/right-arrow.png)

1. **연결** 아래에서 Common Data Service에 대한 연결을 선택합니다.

1. 검색 상자(오른쪽 가장자리 근처)에서 **계정**을 입력하고, **테이블 선택** 아래에서 **계정**을 선택한 다음, **연결**을 선택합니다.

    ![엔터티 선택](./media/data-platform-create-app/select-entity.png)

몇 분 후에 앱이 찾아보기 화면에 열리고 계정 목록이 표시됩니다. 화면 위쪽 근처의 제목 표시줄에는 목록 새로 고침, 목록 나열 및 계정 만들기 아이콘이 표시됩니다. 제목 표시줄 아래의 검색 상자에서 입력하거나 붙여넣을 텍스트를 기준으로 목록을 필터링하는 옵션을 제공합니다. 

기본적으로 목록에는 이미지, 이메일 주소, 도시 및 해당 계정에 대한 ID가 표시됩니다. 그러나 갤러리라고 하는 목록을 사용자 지정하여 다른 형식의 데이터를 표시할 수 있습니다.

![찾아보기 화면](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>앱 저장
이 앱을 사용하거나 다른 사용자와 공유하기 전에 더 많은 변경 작업을 수행하려고 할 것입니다. 가장 좋은 방법은 진행하기 전에 지금까지의 작업을 저장하는 것입니다.

1. 왼쪽 위 모서리에서 **파일** 탭을 클릭하거나 탭합니다.

1. **앱 설정** 페이지에서 앱 이름을 **AppGen**으로 설정하고, 배경색을 진한 빨간색으로, 아이콘을 확인 표시로 변경합니다.

    ![앱 설정 페이지](./media/data-platform-create-app/app-settings.png)

1. 왼쪽 가장자리 근처에서 **저장**을 클릭하거나 탭합니다.

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서 Common Data Service for Apps의 계정에 대한 샘플 데이터를 관리하는 앱을 만들었습니다. 다음 단계에서는 사용자의 요구 사항에 맞게 기본 찾아보기 화면을 사용자 지정합니다.

> [!div class="nextstepaction"]
> [기본 찾아보기 화면 사용자 지정](customize-layout-sharepoint.md)
