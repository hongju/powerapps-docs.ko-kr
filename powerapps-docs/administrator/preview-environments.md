---
title: 미리 보기 환경 | Microsoft Docs
description: PowerApps 미리 보기 프로그램을 사용하여 기능에 미리 액세스
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 08/29/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: e2c4c735827941b32ce5e019eb8d71e4328e4a7a
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297881"
---
# <a name="powerapps-preview-program"></a>PowerApps 미리 보기 프로그램
PowerApps는 며칠 또는 몇 주마다 플랫폼과 기능을 업데이트합니다. PowerApps 미리 보기 프로그램은 다른 지역(고객 프로덕션 앱 배포 위치)의 가용성에 앞서 예정된 기능 및 업데이트에 대한 초기 액세스 권한을 가져오는 방법입니다. 

PowerApps 미리 보기 프로그램을 통해 다음을 수행할 수 있습니다.
- **예정된 기능 체험, 학습 및 도그푸드**: 많은 기능이 피드백을 받기 위해 며칠 동안 미리 보기에서 먼저 롤아웃됩니다. 미리 보기 프로그램에 참여함으로써 새 기능을 더 빨리 학습하고 피드백을 제공할 수 있습니다. 또한 프로덕션 앱이 생성되는 지역에 도달하는 즉시 새 기능을 신속하게 이용할 수 있습니다.
- PowerApps의 예정된 업데이트(vNext)로 **현재 앱이 계속 작동되도록 하여 비즈니스 연속성을 보장**합니다.

## <a name="what-in-powerapps-is-available-for-preview"></a>PowerApps의 미리 보기에 사용할 수 있는 기능은 무엇입니까?
PowerApps의 미리 보기 기능에 액세스하려면 미리 보기 환경에 있어야 합니다. 미리 보기 환경에 대한 자세한 내용은 다음 섹션에서 설명합니다.
현재 PowerApps에서 다음 시나리오에 대한 미리 보기를 롤아웃할 예정입니다.
1. **앱을 만들기**: 다음 버전의 PowerApps를 사용하여 캔버스 기반 앱을 만들 수 있습니다. 미리 보기 환경에서 앱을 만들어 수행할 수 있습니다. 현재 제한 사항으로는 현재 작업 중인 미리 보기 프로그램에서 모델 기반 앱을 빌드할 수 없습니다.
2. **앱 관리**: [PowerApps 웹 포털][2]을 사용하여 앱을 관리하고 공유할 수 있습니다. 미리 보기 기능에 액세스하려면 미리 보기 환경에 있어야 합니다. 그러면 [PowerApps 웹 포털][3]의 미리 보기 버전으로 연결됩니다.
3. **앱 재생**: 웹 플레이어를 사용하여 미리 보기 환경에서 앱을 재생해야 합니다. 이렇게 하면 자동으로 [웹 플레이어의 미리 보기 버전][4]으로 이동합니다. 앱은 PowerApps 웹 플레이어의 vNext 버전으로 재생됩니다. 현재 제한 사항으로는 iOS, Android 및 Windows용 PowerApps Mobile은 현재 미리 보기할 수 없습니다. 첫 번째 릴리스 환경에서 만든 앱을 재생하지 못할 수 있습니다.
4. **PowerApps 관리**: [PowerApps 관리 센터의 미리 보기 버전][1]을 사용하여 관리자 환경을 미리 보기할 수 있습니다.

## <a name="how-to-get-early-access-to-the-upcoming-updates"></a>예정된 업데이트에 대한 초기 액세스를 가져오는 방법은?
PowerApps의 경우 모든 앱과 관련 리소스가 환경에 저장됩니다. vNext(미리 보기)가 배포된 지역에 생성된 환경에서도 모든 미리 보기 기능에 대한 초기 액세스를 사용할 수 있습니다. 현재는 아래 이미지와 같이 **미리 보기(미국)** 지역이 하나만 있습니다.

![](./media/preview-environment/env3-preview.png)

환경의 지역을 **미리 보기(미국)** 로 선택하고 미리 보기 프로그램 참여에 대한 동의를 수락하여 PowerApps의 다음 버전(vNext)에 액세스할 수 있는 환경을 만듭니다.
이 환경에서 만든 모든 앱 및 기타 리소스는 vNext 버전의 플랫폼(SAAS)에 있습니다.

## <a name="how-to-learn-about-the-latest-updates"></a>최신 업데이트에 대해 알아보는 방법은?
[PowerApps의 새로운 기능][5]에서 미리 볼 수 있는 새로운 기능을 확인할 수 있습니다. 미리 보기에서만 사용할 수 있는 기능에는 '미리 보기' 태그가 있습니다.

## <a name="key-scenarios-to-test-with-the-preview-program"></a>미리 보기 프로그램으로 테스트할 주요 시나리오
1. **예정된 PowerApps 업데이트(vNext)로 프로덕션 앱의 유효성 검사**

   프로덕션 앱을 확인하여 PowerApps의 다음 예정된 업데이트와 원활하게 작동되도록 할 수 있습니다. 프로덕션 환경의 앱을 첫 번재 릴리스의 환경으로 [복사][6]하고 앱을 재생하여 시나리오를 테스트할 수 있습니다. CustomAPI, 흐름 등과 같은 다른 모든 필요한 리소스도 함께 이동해야 합니다. 이렇게 하면 이러한 앱과 필수 리소스의 다른 복사본을 만들어야 합니다. 앱을 재생하는 것뿐만 아니라 앱을 편집하고 관리하는 동안 최신 업데이트를 테스트할 수 있습니다.
   
2. **미리 보기에서 사용할 수 있는 새 기능 체험**

   처음에는 **미리 보기(미국)** 지역에서 많은 새로운 기능을 시작할 예정입니다. 나머지 지역에서 사용하기 전에 새로운 기능을 시험해 볼 수 있습니다(프로덕션 환경에 영향을 줄 수 있음).

## <a name="how-to-provide-feedback-to-the-product-team"></a>제품 팀에 피드백을 제공하는 방법은?
[PowerApps 포럼][8] 및/또는 [지원][9]에 대한 피드백을 제공할 수 있습니다.

## <a name="what-are-the-known-issues-and-limitations"></a>알려진 문제 및 제한 사항은 무엇입니까?
1. **미리 보기에서 사용할 수 없는 PowerApps 포털 및 클라이언트** 

   미리 보기에서 사용할 수 있는 특정 기능, 서비스 및 포털이 있습니다.
   
   ![](./media/preview-environment/table.png)

2. **Windows의 Desktop Studio에서 첫 번째 릴리스 환경으로 만든 앱에 액세스**

   위에서 설명했듯이 Windows의 데스크톱 스튜디오는 미리 보기에서 사용할 수 없습니다. 따라서 미리 보기 환경에서 앱을 만들거나 편집하면 Desktop Studio와 호환되지 않을 수 있으며 다음과 같은 오류 메시지가 표시됩니다.
   
   ![](./media/preview-environment/error2.jpg)

   이러한 경우 웹 Studio를 사용하여 미리 보기 환경에서 앱을 만들거나 편집하는 것이 좋습니다.

3. **미리 보기 영역에서 데이터베이스를 만들 수 없습니다.**

   현재 미리 보기(미국) 지역의 환경에서는 앱용 Common Data Service를 사용하여 데이터베이스를 만들 수 없습니다.


<!--Reference links in article-->
[1]: https://preview.admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://preview.web.powerapps.com
[4]: https://preview.web.powerapps.com/webplayer
[5]: https://docs.microsoft.com/powerapps/maker/canvas-apps/release-notes
[6]: https://docs.microsoft.com/powerapps/administrator/environment-and-tenant-migration
[7]: https://preview.create.powerapps.com
[8]: https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1
[9]: https://powerapps.microsoft.com/support/

