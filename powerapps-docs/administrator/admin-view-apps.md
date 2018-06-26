---
title: 환경에 만들어진 앱 목록을 다운로드하는 빠른 시작 | Microsoft Docs
description: 이 빠른 시작에서는 환경에 만들어진 앱 목록을 다운로드하는 방법을 알아봅니다.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimh
ms.openlocfilehash: d9c379ca95bb299c56639bb01803f45c1744d8f2
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34552602"
---
# <a name="quickstart-download-a-list-of-apps-created-in-your-environments"></a>빠른 시작: 환경에 만들어진 앱 목록 다운로드
환경 관리자인 경우 자신이 관리하는 환경에 만들어진 앱 목록을 살펴보고 다운로드할 수 있습니다. Office 365 전역 관리자 또는 Azure Active Directory 테넌트 관리자인 경우 조직 내 모든 환경에 만들어진 앱 목록을 살펴보고 다운로드할 수 있습니다.

이 빠른 시작에서는 단일 환경에서 만든 앱 목록을 .csv 파일로 다운로드한 후 Excel에서 목록을 보는 방법을 알아봅니다.

## <a name="prerequisites"></a>필수 조건
 이 빠른 시작을 수행하려면 다음 항목이 필요합니다.
 * PowerApps 요금제 2 또는 Microsoft Flow 요금제 2 라이선스. 또는 [평가판 PowerApps 계획 2](https://web.powerapps.com/signup?redirect=marketing&email=)에 등록할 수 있습니다.
 * PowerApps 환경 관리자, Office 365 전역 관리자 또는 Azure Active Directory 테넌트 관리자 권한이 필요합니다. 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps 관리 센터에 로그인
[https://admin.powerapps.com]([https://admin.powerapps.com)에서 관리 센터에 로그인합니다.

## <a name="download-the-list-of-apps"></a>앱 목록 다운로드
1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 앱 목록을 다운로드하려는 환경을 클릭하거나 탭합니다.

    ![파일 및 공유](./media/admin-view-apps/environment.png)
2. **리소스** 탭에서 **앱**을 클릭하거나 탭한 다음, **앱 목록 다운로드**를 클릭하거나 탭합니다.

    ![파일 및 공유](./media/admin-view-apps/resources-app.png)

    앱 목록은 .csv 파일로 다운로드됩니다. 이 프로세스는 몇 분 정도 걸릴 수 있습니다. 목록이 완전히 다운로드되거나 프로세스를 다시 시작해야 하기 전에는 창을 닫지 마세요.

## <a name="view-the-list"></a>목록 보기
.csv 파일이 만들어지면 Excel에서 엽니다. 목록에는 앱 표시 이름, 앱 소유자, 앱에서 데이터 원본에 연결하는 데 사용하는 모든 커넥터 및 기타 정보가 포함됩니다.

![파일 및 공유](./media/admin-view-apps/excel-view.png)

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 조직 내 환경에서 만든 앱 목록을 다운로드하고 살펴보는 방법을 배웠습니다. 다음으로, 조직에서 만든 앱을 관리하는 방법을 알아보겠습니다.

> [!div class="nextstepaction"]
> [조직에서 만든 앱 관리](admin-manage-apps.md)
