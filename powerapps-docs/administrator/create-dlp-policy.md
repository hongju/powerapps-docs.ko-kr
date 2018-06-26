---
title: DLP(데이터 손실 방지) 정책을 만드는 방법에 대한 빠른 시작 | Microsoft Docs
description: 이 빠른 시작에서는 PowerApps에서 DLP(데이터 손실 방지) 정책을 만드는 방법을 알아봅니다.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/30/2018
ms.author: jimh
ms.openlocfilehash: da4be42ea0374d6cb50da2f9a9b17eef15d5b316
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34552372"
---
# <a name="quickstart-create-a-data-loss-prevention-dlp-policy"></a>빠른 시작: DLP(데이터 손실 방지) 정책 만들기
조직의 데이터를 보호하기 위해 PowerApps를 사용하여 공유 가능한 소비자 커넥터 관련 비즈니스 데이터를 정의하는 정책을 만들고 적용할 수 있습니다. 데이터를 공유할 수 있는 방법을 정의하는 이러한 정책을 DLP(데이터 손실 방지) 정책이라고 합니다. DLP 정책은 조직 전체에서 데이터가 일관적인 방법으로 관리되도록 보장하고, 중요한 비즈니스 데이터가 소셜 미디어 사이트 같은 커넥터에 실수로 게시되지 않도록 방지합니다.

이 빠른 시작에서는 Common Data Service 및 SharePoint 데이터베이스에 저장된 데이터가 Twitter에 게시되지 않도록 방지하는 단일 환경용 DLP 정책을 만드는 방법을 알아봅니다.

## <a name="prerequisites"></a>필수 조건
이 빠른 시작을 수행하려면 다음 항목 중 **하나**가 필요합니다.
* Azure Active Directory 테넌트 관리자 권한
* Office 365 전역 관리자 권한
* PowerApps 환경 관리자 권한과 PowerApps 요금제 2, Microsoft Flow 요금제 2 또는 [PowerApps 요금제 2 평가판](https://web.powerapps.com/signup?redirect=marketing&email=) 라이선스

자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps 관리 센터에 로그인
[https://admin.powerapps.com]([https://admin.powerapps.com)에서 관리 센터에 로그인합니다.

## <a name="create-a-dlp-policy"></a>DLP 정책 만들기
1. 탐색 창에서 **데이터 정책**을 클릭하거나 탭한 다음, **새 정책**을 클릭하거나 탭합니다.

    ![](./media/create-dlp-policy/new-data-policy.png)
2. **데이터 정책 이름** 필드는 정책이 만들어진 날짜와 시간을 기준으로 자동으로 채워집니다. 이를 **Secure Data Access for Contoso**로 바꿉니다.

    ![](./media/create-dlp-policy/policy-name.png)
3. **환경** 탭의 옵션은 환경 관리자인지 테넌트 관리자인지 여부에 따라 다릅니다. 환경 관리자인 경우 드롭다운 목록에서 환경을 선택한 다음, **계속**을 클릭하거나 탭합니다.

    ![](./media/create-dlp-policy/select-environment.png)

    테넌트 관리자인 경우 하나 이상의 환경 또는 테넌트 내의 모든 환경(평가판 라이선스를 사용하여 만든 라이선스 포함)에 적용되는 DLP 정책을 만들 수 있습니다. 이 빠른 시작에서는 **선택한 환경에만 적용**을 클릭하거나 탭하고 드롭다운 목록에서 환경을 선택한 다음, **계속**을 클릭하거나 탭합니다.

    ![](./media/create-dlp-policy/select-environment-tenant.png)

    환경 DLP 정책은 테넌트 전체 DLP 정책을 재정의할 수 없습니다.
4. **데이터 그룹** 탭의 **비즈니스 데이터만** 아래에서 **추가**를 클릭하거나 탭합니다.

    ![](./media/create-dlp-policy/data-groups.png)
5. **커넥터 추가** 창에서 **Common Data Service** 및 **SharePoint**를 선택하고(아래로 스크롤하거나 검색해야 할 수도 있음),  **커넥터 추가**를 클릭하거나 탭하여 **비즈니스 데이터만** 데이터 그룹에 추가합니다.

    ![](./media/create-dlp-policy/add-connectors.png)

    커넥터는 한 번에 하나의 데이터 그룹에만 상주할 수 있으며 기본적으로 **비즈니스 데이터 허용 안 됨** 그룹에 추가됩니다. Common Data Service 및 SharePoint를 **비즈니스 데이터만** 그룹으로 이동하면 사용자는 이 두 커넥터를 **비즈니스 데이터 허용 안 됨** 그룹의 커넥터와 결합하는 흐름 및 앱을 만들 수 없습니다.

6. **정책 저장**을 클릭합니다.

    ![](./media/create-dlp-policy/save-policy.png)

Secure Data Access for Contoso 정책이 만들어지고 데이터 손실 방지 정책 목록에 나타납니다. Twitter 커넥터가 **비즈니스 데이터 허용 안 됨** 데이터 그룹에 상주하기 때문에 이 정책은 Common Data Service와 SharePoint가 데이터를 Twitter와 공유하지 않도록 방지합니다.

관리자는 사용자가 앱을 만들기 전에 정책을 인식할 수 있도록 DLP 정책 목록을 조직과 공유하는 것이 좋습니다.

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 중요한 비즈니스 데이터를 실수로 Twitter 같은 커넥터에 게시하지 않도록 방지하는 단일 환경용 DLP 정책을 만드는 방법을 배웠습니다. DLP 정책에 대한 자세한 내용은 정책 관리 방법에 대한 문서를 살펴보세요.

> [!div class="nextstepaction"]
> [DLP(데이터 손실 방지) 정책 관리](prevent-data-loss.md)
