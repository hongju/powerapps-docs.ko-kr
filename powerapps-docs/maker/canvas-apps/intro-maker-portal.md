---
title: 처음으로 로그인 | Microsoft Docs
description: 앱의 모든 제작자를 위한 새 홈입니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/06/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3ecf468f8c1b15d20b144aa127fe31c13dba484e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849752"
---
# <a name="sign-in-to-powerapps-for-the-first-time"></a>PowerApps에 처음으로 로그인

[PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인하면 사이트에서 자체 앱을 만들고, 다른 사용자가 만든 앱을 열거나 관련 작업을 수행하기 위한 다양한 옵션을 제공합니다. 이러한 작업은 액세스 권한을 제공하는 라이선스 또는 라이선스의 식별과 같은 가장 간단한 작업부터 특정 데이터 원본에 대한 사용자 지정 연결 생성과 같은 고급 기능에 이르기까지 다양합니다.

세 가지 일반 영역에서 옵션을 선택할 수 있습니다.

- 페이지 맨 위에 있는 헤더

    ![헤더](media/intro-maker-portal/header.png)

- 페이지 왼쪽 가장자리를 있는 탐색 모음

    ![탐색 모음](media/intro-maker-portal/nav-bar.png)

- 페이지 중간에 있는 눈에 잘 띄는 기능인 큰 아이콘

    ![홈 페이지의 중심 영역](media/intro-maker-portal/center-area.png)

최상의 결과를 얻으려면 먼저 홈 페이지가 올바른 환경으로 설정되어 있는지 확인합니다.

## <a name="choose-an-environment"></a>환경 선택

앱용 Common Data Service에서 앱, 흐름, 데이터 연결 또는 엔터티 중 어느 것을 만들든 간에, PowerApps에서 수행하는 작업의 대부분은 특정 환경에 포함되어 있습니다. 환경에서는 다양한 유형의 작업 간에 경계를 만듭니다. 예를 들어, 조직은 부서마다 별도의 환경이 있을 수 있습니다. 많은 조직에서 환경을 사용하여 광범위하게 사용할 준비가 된 앱에서 아직 개발 중인 앱을 분리합니다. 여러 환경 또는 하나의 환경에만 액세스할 수 있으며 적절한 사용 권한이 있는 경우 고유한 환경을 만들 수 있습니다.

어떤 환경에 속해 있는지 확인하려면 헤더의 오른쪽 근처에 있는 환경 전환기를 찾습니다.

![환경 전환기](media/intro-maker-portal/environment-switcher.png)

한 환경에서 앱을 만드는 경우 다른 환경에서 확인할 수 없습니다. 또한 앱을 실행하려는 사용자는 만든 환경에 액세스할 수 있어야 합니다.

> [!IMPORTANT]
> 앱, 흐름, 또는 유사한 구성 요소를 만들기 *전에* 올바른 환경에 있는지 확인합니다. 한 환경에서 다른 환경으로 구성 요소를 쉽게 이동할 수 없습니다.

자세한 내용은 [환경 개요](../../administrator/environments-overview.md)를 참조하세요.

## <a name="choose-an-app-type"></a>앱 유형 선택

PowerApps에서 다음 유형의 앱을 만들고 실행할 수 있습니다.

- **캔버스 앱**은 사용자 지정 UI를 디자인하고 다양한 소스의 데이터에 연결할 수 있도록 지원합니다.
- **모델 기반 앱**은 표준 UI가 있으며 앱용 CDS(Common Data Service)에서만 데이터에 연결합니다. 그러나 보기, 대시보드 및 다양한 유형의 비즈니스 논리와 같은 다른 요소를 더 쉽게 만들 수 있습니다.

기본적으로 **홈** 페이지에는 캔버스 앱을 만들고 실행하기 위한 옵션이 표시됩니다. 대신 모델 기반 옵션을 표시하려면 앱용 CDS 데이터베이스가 있는 환경을 선택한 다음, 왼쪽 아래 모서리에 있는 메뉴를 엽니다.

![캔버스와 모델 기반 앱 간 전환](media/intro-maker-portal/mode-switcher.png)

## <a name="play-or-edit-an-app"></a>앱 재생 또는 편집

앱을 이미 만든 경우(또는 다른 사용자가 앱을 만들어 사용자와 공유한 경우) **앱** 페이지에서 앱을 재생하거나 편집할 수 있습니다.

- 최근에 열었는지 등의 기준에 따라 필터링하여 캔버스 앱을 찾을 수 있습니다.

    ![캔버스 앱 목록](media/intro-maker-portal/org-apps.png)

    앱을 검색하거나 오른쪽 상단 모서리 근처에 표시되는 검색 표시줄에 하나 이상의 문자를 입력하여 검색할 수도 있습니다. 원하는 앱을 찾으면 줄임표 아이콘을 선택하여 앱을 재생하거나 편집할 수 있는 옵션을 표시합니다.

    ![줄임표 메뉴](media/intro-maker-portal/ellipsis-menu.png)

- 모델 기반 앱 목록을 필터링할 수는 없지만 오른쪽 상단 모서리 근처에 표시되는 검색 표시줄에 하나 이상의 문자를 입력하여 앱을 검색할 수 있습니다. 원하는 앱을 찾으면 줄임표 아이콘을 선택하여 앱을 재생하거나 편집할 수 있는 옵션을 표시합니다.

    ![줄임표 메뉴가 열린 모델 기반 앱 목록](media/intro-maker-portal/model-driven-list.png)

## <a name="create-an-app"></a>앱 만들기

**홈** 페이지에서 다음과 같은 여러 가지 방법으로 앱을 만들 수 있습니다.

- [데이터 집합에서 캔버스 앱을 자동으로 생성](data-platform-create-app.md)
- [캔버스 앱의 미리 빌드된 샘플 사용자 지정](open-and-run-a-sample-app.md)
- [빈 화면에서 캔버스 앱 빌드](data-platform-create-app-scratch.md)
- [고유 모델 기반 앱 만들기](../model-driven-apps/overview-model-driven-samples.md)
- [모델 기반 앱에 대해 미리 빌드된 샘플 사용자 지정](../model-driven-apps/build-first-model-driven-app.md)

## <a name="learn-more"></a>자세한 정보

다음과 같은 두 가지 방법으로 캔버스 앱 또는 모델 기반 앱에 대한 자세한 정보를 확인할 수 있습니다.

- 왼쪽 탐색 모음에서 **학습**을 선택합니다.
- 헤더에서 물음표 아이콘을 선택합니다.

    ![줄임표 메뉴가 열린 모델 기반 앱 목록](media/intro-maker-portal/help-icon.png)

두 옵션 모두 이 설명서 집합, PowerApps 커뮤니티(다른 조직의 사용자와 정보를 공유할 수 있는 위치) 및 PowerApps 블로그(최신 기능이 발표되는 위치)에 대한 링크를 보여줍니다.

## <a name="other-common-tasks"></a>기타 일반 작업

헤더 및 왼쪽 탐색 모음에서 옵션을 선택하면 앱을 만들고 여는 것 이상을 수행할 수 있습니다.

### <a name="from-the-header"></a>헤더에서

- 앱을 실행할 수 있는 모바일 및 기타 클라이언트를 다운로드하려면 아래쪽 화살표를 선택합니다.

    자세한 내용은 [앱 찾기 및 실행](../../user/index.md)을 참조하세요.

- 기어 아이콘을 선택하여 데이터 원본에 연결, PowerApps 라이선스 또는 라이선스 식별, 그리고 관리 작업을 수행할 수 있는 페이지 열기와 같은 작업을 수행합니다.

    자세한 내용은 다음 항목을 참조하세요.

  - [캔버스 앱 커넥터 개요](connections-list.md)
  - [캔버스 앱용 사용자 지정 커넥터 빌드 및 인증](register-custom-api.md)
  - [온-프레미스 데이터 게이트웨이 관리](gateway-management.md)
  - [PowerApps 관리](../../administrator/index.md)
  - [라이선스 개요](../../administrator/pricing-billing-skus.md)
  - [모델 기반 앱 빌드에 대한 개요](../model-driven-apps/model-driven-app-overview.md)

### <a name="from-the-left-navigation-bar"></a>왼쪽 탐색 표시줄에서

다음 작업을 수행하여 앱의 기능을 확장합니다.

- [앱용 Common Data Service](../common-data-service/data-platform-intro.md)에서 엔터티, 옵션 집합 및 데이터 통합을 관리합니다.
- [Microsoft Flow](https://docs.microsoft.com/flow/getting-started)에서 비즈니스 논리를 구성합니다.
- [솔루션](../../developer/common-data-service/introduction-solutions.md) 작성, 패키지 및 유지 관리합니다.
