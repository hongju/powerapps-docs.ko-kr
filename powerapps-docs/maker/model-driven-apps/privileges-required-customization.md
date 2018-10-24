---
title: 모델 기반 앱 사용자 지정에 필요한 권한 | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 43cf7f3a-7e26-4990-8b5a-c817ac6d51bb
caps.latest.revision: 13
ms.author: matp
manager: kvivek
author: Mattp123
ms.openlocfilehash: dd0c7e05d756145a701bb6bfb137dc07cb8c45fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692148"
---
# <a name="privileges-required-for-model-driven-app-customization"></a>모델 기반 앱 사용자 지정에 필요한 권한

앱 사용자는 시스템을 개인 설정하고 사용자 지정 중 일부를 다른 사람과 공유할 수 있지만 올바른 권한을 가진 사용자만 모든 사용자에 대해 변경 내용을 적용할 수 있습니다.  
  
> [!NOTE]
>  이 섹션에서는 보안 역할을 사용하는 방법을 알고 있다고 가정합니다. 보안 역할을 사용하는 방법에 대한 자세한 내용은 [사용자 만들기 및 보안 역할 할당](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles)을 참조하세요.  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>시스템 관리자 및 시스템 사용자 지정자 보안 역할  
 사용자 지정하는 모든 사용자에게 해당 계정과 연결된 시스템 관리자 또는 시스템 사용자 지정자 보안 역할이 있습니다. 이러한 보안 역할은 앱을 사용자 지정하는 데 필요한 권한을 제공합니다.  
  
|시스템 관리자|시스템 사용자 지정자|  
|--------------------------|-----------------------|  
|시스템을 사용자 지정하기 위한 전체 권한이 있음|시스템을 사용자 지정하기 위한 전체 권한이 있음|  
|시스템의 모든 데이터를 볼 수 있음|만드는 시스템 엔터티에 대한 레코드만 볼 수 있음|  
  
 시스템 관리자 및 시스템 사용자 지정자 보안 역할 간의 차이는 시스템 관리자는 시스템에서 대부분의 레코드에 대한 권한을 읽고 모든 것을 볼 수 있다는 점입니다. 사용자 지정 작업을 수행해야 하지만 시스템 엔터티의 모든 데이터를 확인하지 않아도 되는 사용자에게 시스템 사용자 지정자 역할을 할당합니다. 그러나 테스트는 시스템을 사용자 지정 하는 중요한 부분입니다. 시스템 사용자 지정자가 모든 데이터를 확인할 수 없는 경우 해당 사용자 지정을 테스트하려면 레코드를 만들어야 합니다. 기본적으로 시스템 사용자 지정자에게는 사용자 지정 엔터티에 대한 전체 액세스 권한이 있습니다. 시스템 엔터티에 대한 것과 동일한 제한을 설정하려는 경우 액세스 수준이 사용자 지정 엔터티에 대한 **조직**보다는 **사용자**가 되도록 시스템 사용자 지정자 보안 역할을 조정해야 합니다.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>사용자 지정 작업 위임  
 필요한 변경 내용을 적용할 수 있도록 신뢰할 수 있는 사용자에게 일부 작업을 위임하려 할 수 있습니다. 모든 사용자가 자신의 사용자 계정과 연결된 여러 보안 역할을 보유할 수 있으며, 보안 역할에서 부여하는 권한 및 액세스 권한은 *가장 제한이 적은* 수준의 사용 권한에 따릅니다.  
  
 즉, 시스템 사용자 지정자 보안 역할을 이미 다른 보안 역할(아마도 영업 관리자)이 있는 사용자에게 제공할 수 있습니다. 이 기능을 사용하면 이미 보유한 다른 권한 외에 시스템을 사용자 지정할 수 있습니다. 이미 보유한 보안 역할은 편집할 필요가 없으며, 원하는 경우 사용자의 사용자 계정에서 시스템 사용자 지정자 보안 역할을 제거할 수 있습니다.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>사용자 지정 권한 없이 사용자 지정 테스트  
 사용자 지정 권한이 없는 사용자 계정을 사용하여 수행한 모든 사용자 지정을 테스트해야 합니다. 이렇게 하면 시스템 관리자 또는 시스템 사용자 지정자 보안 역할이 없는 사용자도 사용자 지정을 사용할 수 있게 됩니다. 이를 효과적으로 하려면 두 개의 사용자 계정에 액세스해야 합니다. 즉, 시스템 관리자 보안 역할이 있는 사용자 계정 및 사용자 지정을 사용하는 사용자를 나타내는 보안 역할이 있는 사용자 계정입니다.  
  
> [!IMPORTANT]
>  하나의 사용자 계정만 있는 경우 시스템 관리자 보안 역할을 제거하려고 하지 마세요. 제거하려고 시도하면 시스템에서 경고하지만 그래도 계속 진행하면 되돌릴 수 없게 됩니다. 대부분 보안 역할은 사용자의 보안 역할을 편집할 수 없습니다.  
  
## <a name="next-steps"></a>다음 단계  
 [사용자 지정 시작](getting-started-customization.md)

