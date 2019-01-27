---
title: 평가판 환경 | Microsoft Docs
description: PowerApps 미리 보기 프로그램을 사용하여 기능에 미리 액세스
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 01/09/2019
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: bd05c4c1251058d464034de71d9b1c287e714190
ms.sourcegitcommit: 170deba334c922157bbb826c795bed3fa858b85e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54196143"
---
# <a name="about-trial-environments"></a>평가판 환경 정보

현재 두 가지 유형의 앱용 CDS(Common Data Service) 환경을 만들 수 있습니다. 평가판 또는 프로덕션. 평가판 환경은 고객 참여 앱용 Dynamics 365를 무료로 사용해 보는 데 유용합니다. 평가판 환경은 30일 후에 만료됩니다.

**환경** 페이지를 열어 사용 중인 환경 유형과 평가판 환경의 예정된 만료 날짜를 확인합니다.

> [!div class="mx-imgBorder"] 
> ![PowerApps 환경](media/powerapps-environments75b.png "PowerApps 환경")

## <a name="convert-a-trial-environment-to-production"></a>평가판 환경을 프로덕션으로 변환

평가판 환경을 사용하는 동안 30일 보다 오래 유지하려는 리소스를 만든 경우 평가판을 프로덕션 환경으로 변환합니다.

프로덕션 환경으로 변환하려면 다음 조건을 충족해야 합니다.

**적합한 PowerApps 플랜**. 프로덕션 환경(PowerApps 플랜 2)을 만들 수 있는 플랜입니다. 프로덕션 환경을 포함하는 PowerApps 플랜에 대한 정보는 [팀에 적합한 요금제 선택](https://powerapps.microsoft.com/pricing/)을 참조하세요. PowerApps 플랜을 확인하려면 [내 플랜을 식별하는 방법](#how-do-i-identify-my-plans)을 참조하세요.
**사용 가능한 프로덕션 할당량**. 플랜으로 생성할 수 있는 고정된 수의 프로덕션 환경이 있습니다. 예를 들어, PowerApps 플랜 2를 사용하면 두 개의 프로덕션 환경을 만들 수 있습니다. 이미 두 개의 프로덕션 환경을 만든 경우 기존 프로덕션 환경을 삭제할 때까지는 더 이상 프로덕션 환경을 만들 수 없습니다. 자세한 내용은 [환경 만들기](environments-overview.md#creating-an-environment)를 참조하세요.

평가판 환경을 프로덕션 환경으로 변환하려면 다음 단계를 수행합니다.

1. [https://admin.powerapps.com/environments](https://admin.powerapps.com/environments)로 이동하여 관리자 권한으로 로그인합니다.
 
2. **환경** 페이지를 열고 프로덕션으로 변환할 평가판 환경을 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![평가판 환경 선택](media/powerapps-environments75b-select-trial.png "평가판 환경 선택")

3. **세부 정보** 탭에서 **변환**을 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![변환 선택](media/powerapps-trial-select-convert.png "변환 선택")

4. **확인** 선택:

    > [!div class="mx-imgBorder"] 
    > ![확인 선택](media/powerapps-trial-select-confirm.png "확인 선택")

환경에 데이터베이스가 있는 경우에는 프로덕션 환경으로 변환하는 데 몇 시간이 걸릴 수 있습니다. **세부 정보** 탭에서 알림을 통해 진행률을 모니터링할 수 있습니다.

  > [!div class="mx-imgBorder"] 
  > ![변환 시작](media/powerapps-trial-conversion-started.png "변환 시작")

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="who-can-convert-a-trial-environment-to-a-production-environment"></a>누가 평가판 환경을 프로덕션 환경으로 변환할 수 있나요?

평가판 환경을 프로덕션 환경으로 변환하려면 다음 조건을 충족해야 합니다.

**적합한 PowerApps 플랜 수립**. 프로덕션 환경(예: PowerApps 플랜 2)을 만들 수 있는 플랜이 필요합니다. 프로덕션 환경을 포함하는 PowerApps 플랜에 대한 정보는 [팀에 적합한 요금제 선택](https://powerapps.microsoft.com/pricing/)을 참조하세요. PowerApps 플랜을 확인하려면 [내 플랜을 식별하는 방법](#how-do-i-identify-my-plans)을 참조하세요.
**사용 가능한 프로덕션 할당량 확보**. 플랜으로 생성할 수 있는 고정된 수의 프로덕션 환경이 있습니다. 예를 들어, PowerApps 플랜 2를 사용하면 두 개의 프로덕션 환경을 만들 수 있습니다. 이미 두 개를 만든 경우 기존 항목을 삭제할 때까지는 더 이상 만들 수 없습니다.

### <a name="what-if-i-dont-have-available-quota-for-production-environments"></a>프로덕션 환경에 사용 가능한 할당량이 없는 경우 어떻게 해야 하나요?

Office 365 글로벌 관리자 또는 Azure AD(Azure Active Directory) 테넌트 관리자에 문의하여 다음을 수행하세요.
- PowerApps 플랜 2를 할당합니다. 
- 사용 가능한 프로덕션 환경 할당량을 가진 다른 사용자를 찾습니다.

PowerApps 플랜을 구매할 수도 있습니다.

### <a name="can-every-office-365-global-admin-or-azure-ad-tenant-admin-convert-a-trial-environment-to-a-production-environment"></a>모든 Office 365 글로벌 관리자 또는 Azure AD 테넌트 관리자가 평가판 환경을 프로덕션 환경으로 변환할 수 있나요?

아닙니다. 글로벌 관리자 및 Azure AD 테넌트 관리자는 평가판 환경을 프로덕션 환경으로 변환할 수 있도록 프로덕션 환경에 사용 가능한 할당량이 있어야 합니다.

### <a name="is-there-a-way-to-recover-a-deleted-trial-environment"></a>삭제된 평가판 환경을 복구할 수 있나요?

삭제된 평가판 환경의 복구를 보장할 수 없지만 삭제 후 7일 이내의 복구하기 위해 최선을 다할 것입니다. 환경의 데이터베이스를 복구할 수 없지만 PowerApps으로 만든 앱과 흐름을 복구할 수 있습니다.

### <a name="how-can-i-retain-my-data-and-resources-if-i-dont-have-a-way-to-convert-the-trial-environment-to-a-production-environment"></a>평가판 환경을 프로덕션 환경으로 변환할 방법이 없으면 데이터와 리소스를 어떻게 유지할 수 있나요?

리소스 및 데이터를 다른 환경으로 내보낼 수 있습니다. 더 오랜 기간 유지하려는 경우 프로덕션 환경 또는 개별 환경(PowerApps 커뮤니티 플랜 사용)을 만들고 리소스를 해당 환경으로 내보내는 것이 좋습니다. 

다음은 리소스 내보내기에 대한 몇 가지 지침입니다.

|환경의 리소스 유형  |내보내려면 어떻게 해야 하나요?  |
|---------|---------|
|앱(캔버스와 모델 기반 앱) 및 흐름     |[패키징](environment-and-tenant-migration.md)을 사용하여 하나의 환경에서 앱 및 흐름을 내보낼 수 있습니다.         |
|데이터베이스의 데이터(앱용 CDS(Common Data Service) 환경)     |여러 옵션이 있습니다.<br/><ul><li>[Excel로 내보내](../user/export-data-excel.md)고 데이터를 저장합니다. 다른 환경으로 [데이터를 가져올](../user/import-data.md) 수 있습니다.</li><br/><li>[Data Integrator 서비스](data-integrator.md) 및 API를 사용하여 데이터를 다른 환경으로 내보낼 수 있습니다.</li></ul> |

30일 동안 환경 데이터베이스에서 활동이 없는 평가판 환경을 삭제합니다.

### <a name="how-can-i-create-a-production-or-an-individual-environment"></a>프로덕션 또는 개별 환경을 만드는 방법은?

프로덕션 환경 생성을 제공하는 PowerApps 플랜이 있어야 합니다. 자세한 내용은 [환경 만들기](environments-overview.md#creating-an-environment)를 참조하세요.

[PowerApps 커뮤니티 플랜](https://powerapps.microsoft.com/communityplan/)에 등록하여 개별 환경을 만들 수 있습니다. 개별 환경에서 앱 공유 시 제한 사항이 있습니다. 이러한 환경은 개인 용도로만 사용됩니다.

### <a name="how-do-i-identify-my-plans"></a>내 플랜을 식별하는 방법은?

플랜을 확인하려면 PowerApps 사이트의 오른쪽 위 모서리에 있는 **기어** 아이콘을 선택한 다음, **플랜**을 선택합니다.

> [!div class="mx-imgBorder"] 
> ![플랜 선택](media/powerapps-plans.png "플랜 선택")

### <a name="see-also"></a>참고 항목
[PowerApps에서 환경 관리](environments-administration.md)<br/>
[환경 개요](environments-overview.md)<br/>
[팀에 적합한 요금제 선택](https://powerapps.microsoft.com/pricing/)<br/>
[라이선스 개요](pricing-billing-skus.md)<br/>
