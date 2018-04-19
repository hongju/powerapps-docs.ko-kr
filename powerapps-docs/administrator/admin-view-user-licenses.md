---
title: 테넌트의 활성 사용자 목록을 다운로드하는 빠른 시작 | Microsoft Docs
description: 이 빠른 시작에서는 테넌트의 활성 사용자 목록을 다운로드하는 방법을 알아봅니다.
services: powerapps
suite: powerapps
documentationcenter: na
author: SKjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: 8d1f04f5b559e179e1549c92e75c16dac79210df
ms.sourcegitcommit: d7ed5144f96d1ecc17084c30ed0e2ba3c6b03c26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="quickstart-download-a-list-of-active-users-in-your-tenant"></a>빠른 시작: 테넌트의 활성 사용자 목록 다운로드
365 전역 관리자 또는 Azure Active Directory 테넌트 관리자인 경우 테넌트의 활성 사용자 목록을 다운로드할 수 있으므로 PowerApps, Microsoft Flow 또는 둘 모두에 액세스한 사용자뿐 아니라 해당 사용자에게 할당된 라이선스까지 볼 수 있습니다.

이 빠른 시작에서는 활성 사용자 목록을 .csv 파일로 다운로드한 후 Excel에서 목록을 보는 방법을 알아봅니다.

이 빠른 시작을 수행하려면 Office 365 전역 관리자 또는 Azure Active Directory 테넌트 관리자 권한이 필요합니다.

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps 관리 센터에 로그인
[https://admin.powerapps.com]([https://admin.powerapps.com)에서 관리 센터에 로그인합니다.

## <a name="download-the-list-of-users"></a>사용자 목록 다운로드
탐색 창에서 **사용자 라이선스**를 클릭 또는 탭한 후 **활성 사용자 라이선스 목록 다운로드**를 클릭 또는 탭합니다.

![파일 및 공유](./media/admin-view-user-licenses/download-list.png)

사용자 목록은 .csv 파일로 다운로드됩니다. 이 프로세스는 몇 분 정도 걸릴 수 있습니다. 목록이 완전히 다운로드되거나 프로세스를 다시 시작해야 하기 전에는 창을 닫지 마세요.

## <a name="view-the-list"></a>목록 보기
.csv 파일이 만들어지면 Excel에서 엽니다. 목록에는 각 사용자의 이름, 이메일 주소, 라이선스 유형 및 기타 정보가 포함되어 있습니다.

제품에 한 번 이상 액세스한 사용자는 *활성 사용자*로 간주됩니다. 이 목록은 활성 사용자 목록이므로 PowerApps 및 Microsoft Flow에 대한 라이선스가 있으나 한 번도 액세스하지 않은 사용자는 포함되지 않습니다. [Office 365 관리 센터](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)에서 모든 사용자 라이선스를 볼 수 있습니다.

다음 예제에서는 PowerApps 및 Microsoft Flow에 대한 라이선스가 있는 두 사용자를 보여줍니다. Jane Doe는 Office 365에 대한 구독을 통해 액세스할 수 있고 John Doe는 각 제품에 대한 평가판 라이선스가 있습니다.

![파일 및 공유](./media/admin-view-user-licenses/table2.png)

사용자가 조직을 떠난 경우 이 목록의 **사용자 이름** 및 **이메일 주소** 열이 **알 수 없음**으로 표시됩니다. 목록에 **알 수 없음**으로 표시되지만 조직을 떠난 사람이 없는 경우 몇 분 정도 기다린 다음 목록을 다시 다운로드합니다.

사용자 라이선스를 추가하려면 [Office 365 관리 센터](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)를 엽니다.

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 테넌트의 활성 사용자 목록을 다운로드하는 방법을 배웠습니다. 환경에 만들어진 앱 목록을 다운로드하여 보는 방법을 알아보려면 그 다음 빠른 시작을 계속 진행하세요.

> [!div class="nextstepaction"]
> [환경에 만들어진 앱 목록 다운로드](admin-view-apps.md)
