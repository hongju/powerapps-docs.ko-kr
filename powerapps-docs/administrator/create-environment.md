---
title: 환경을 만드는 빠른 시작 | Microsoft Docs
description: 이 빠른 시작에서는 환경을 만드는 방법을 배웁니다.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimh
ms.openlocfilehash: f648d68a19c646a2a69a8eebca85ac9e33af0686
ms.sourcegitcommit: 3f5adf07cac1c798f3d4843ed5928505becde30e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2018
---
# <a name="quickstart-create-an-environment"></a>빠른 시작: 환경 만들기
환경은 조직의 비즈니스 데이터, 앱 및 흐름을 저장, 관리 및 공유하는 공간입니다. 또한 각기 다른 역할, 보안 요구 사항 또는 대상 그룹에 따라 앱을 구분하는 컨테이너 기능도 제공합니다. PowerApps는 자동으로 각 테넌트의 단일 기본 환경을 만들며, 이 환경은 해당 테넌트의 모든 사용자 간에 공유됩니다.

모든 환경에는 앱에 대한 저장소를 제공하는 0개 또는 1개의 Common Data Service 데이터베이스가 있습니다. 사용자가 환경에서 앱을 만들면 해당 앱은 연결, 게이트웨이 및 흐름을 포함한 모든 데이터 원본에 연결할 수 있습니다. 그러나 앱이 동일한 환경의 Common Data Service 데이터베이스에 연결하는 것만 허용됩니다. 환경 활용을 선택하는 방식은 해당 조직 및 빌드하려는 앱에 따라 달라집니다. 자세한 내용은 [환경 개요](environments-overview.md)를 참조하세요.

이 빠른 시작에서는 환경을 만들고 해당 환경에 사용할 데이터베이스를 만드는 방법을 배웁니다.

## <a name="prerequisites"></a>필수 조건
 이 빠른 시작을 수행하려면 다음 항목이 필요합니다.
 * PowerApps 요금제 2 또는 Microsoft Flow 요금제 2 라이선스. 또는 [평가판 PowerApps 계획 2](https://web.powerapps.com/signup?redirect=marketing&email=)에 등록할 수 있습니다.
 * PowerApps 환경 관리자, Office 365 전역 관리자 또는 Azure Active Directory 테넌트 관리자 권한이 필요합니다. 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps 관리 센터에 로그인
[https://admin.powerapps.com](https://admin.powerapps.com)에서 관리 센터에 로그인합니다.

## <a name="create-an-environment-and-database"></a>환경 및 데이터베이스 만들기
1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, **새 환경**을 클릭하거나 탭합니다.

    ![파일 및 공유](./media/create-environment/new-environment.png)
2. **새 환경** 대화 상자에서 환경의 이름을 입력하고, 드롭다운 목록에서 지역 및 환경 유형을 선택합니다. 지역은 기본적으로 Azure Active Directory 테넌트 홈 영역으로 설정되지만, 드롭다운 목록에서 원하는 지역을 선택할 수 있습니다. 환경을 만든 후에는 지역을 변경할 수 없습니다. 작업을 마쳤으면 **환경 만들기**를 클릭하거나 탭합니다.

    ![파일 및 공유](./media/create-environment/new-environment-dialog.png)
3. 환경이 만들어지면 대화 상자에 확인 메시지가 표시되고 데이터베이스를 만들라는 메시지가 나타납니다. Common Data Service에 액세스할 수 있도록 **데이터베이스 만들기**를 클릭하거나 탭합니다.

    **참고:** 현재는 Azure Active Directory 테넌트 홈 지역에만 데이터베이스를 만들 수 있습니다.

    ![파일 및 공유](./media/create-environment/create-database-dialog.png)
4. 데이터베이스에 저장된 데이터의 통화 및 언어를 선택합니다. 데이터베이스를 만든 후에는 통화 또는 언어를 변경할 수 없습니다. 작업을 마쳤으면 **데이터베이스 만들기**를 클릭하거나 탭합니다.

    ![파일 및 공유](./media/create-environment/create-database-dialog2.png)

    Common Data Service에 데이터베이스를 만들 때까지 몇 분 정도 걸릴 수 있습니다. 데이터베이스가 만들어지면 **환경** 페이지의 환경 목록에 새 환경이 나타납니다.

    ![파일 및 공유](./media/create-environment/new-environment-created.png)

    환경 세부 정보를 보려면 환경을 클릭하거나 탭합니다.

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 환경을 만들고 해당 환경에 사용할 데이터베이스를 만드는 방법을 배웠습니다. 다음으로, 조직의 환경을 관리하는 방법을 알아봅니다.

> [!div class="nextstepaction"]
> [PowerApps에서 환경 관리](environments-administration.md)
