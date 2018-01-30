---
title: "사용자 라이선스 보기 | Microsoft Docs"
description: "관리자는 PowerApps 및 Microsoft Flow에 대한 사용자 라이선스 목록을 다운로드할 수 있습니다."
services: 
suite: powerapps
documentationcenter: na
author: manasmamsft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/02/2017
ms.author: manasma
ms.openlocfilehash: bc3d1c94deec6cf5e7c0ba5b73e65cab67d3ee25
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="identify-powerapps-users-in-your-organization"></a>조직에서 PowerApps 사용자 식별
Office 365에 대한 전역 관리자이거나 Azure Active Directory에 대한 테넌트 관리자인 경우, PowerApps, Microsoft Flow에 대한 사용이 허가되었으며 동시에 해당 제품 중 하나에 대한 액세스 권한이 있는 조직 내 사용자의 목록을 다운로드할 수 있습니다. 목록에는 각 사용자의 이름, 이메일 주소, 라이선스 유형 및 기타 정보가 포함되어 있습니다. 예를 들어 사용자는 다음을 가질 수 있습니다.

* PowerApps 또는 Microsoft Flow에 대한 평가판 라이선스
* Office 365 라이선스를 통한 두 제품에 대한 액세스
* Dynamics 365 라이선스를 통한 두 제품에 대한 액세스
* PowerApps 및 Microsoft Flow 계획에서의 액세스

### <a name="download-the-list-of-users"></a>사용자 목록 다운로드
1. PowerApps 관리 센터에서 왼쪽 가장자리 근처에 있는 **사용자 라이선스**를 클릭하거나 탭합니다.
   
    > [!IMPORTANT]
> 이 옵션은 Office 365 전역 관리자 및 Azure Active Directory 테넌트 관리자만 사용할 수 있습니다.
   
    ![파일 및 공유](./media/admin-view-user-licenses/leftnav.png)
2. **활성 사용자 라이선스 목록 다운로드**를 클릭하거나 탭합니다.
   
    ![파일 및 공유](./media/admin-view-user-licenses/download-list.png)
   
    파일을 다운로드하는 데 몇 분 정도 걸릴 수 있습니다. .csv 파일이 다운로드되기까지 몇 분 기다린 다음 Excel에서 엽니다.
   
    > [!NOTE]
> 파일 다운로드가 완료되기 전에 창을 닫으면 프로세스를 다시 시작해야 할 수 있습니다.

이 예제에서는 다른 방법을 통해 PowerApps 및 Microsoft Flow 모두에 대한 라이선스가 있는 두 사용자가 나와 있습니다. Jane Doe는 Office 365에 대한 구독을 통해 액세스할 수 있고 John Doe는 각 제품에 대한 평가판 라이선스가 있습니다.

![파일 및 공유](./media/admin-view-user-licenses/table2.png)

이 목록에는 PowerApps 및 Microsoft Flow에 대한 라이선스가 있으나 한 번도 액세스하지 않은 사용자는 포함되지 않습니다. [Office 365 관리 센터][1]에서 모든 사용자 라이선스를 볼 수 있습니다.

사용자가 조직을 떠난 경우 목록에서 **사용자 이름** 및 **이메일** 주소와 같은 열에 **알 수 없음**으로 표시됩니다. 목록에 **알 수 없음**으로 표시되지만 조직을 떠난 사람이 없는 경우 몇 분 정도 기다린 다음 목록을 다시 다운로드합니다.

사용자 라이선스를 추가하려면 [Office 365 관리 센터][1]를 엽니다.

<!--Reference links in article-->
[1]:https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc
