---
title: 지역 개요 | Microsoft Docs
description: 'PowerApps의 지역: 앱을 배포할 경우 사용 가능한 지역이며 지역에 특정된 기능입니다.'
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: ab5443ae628a80d52d5bbcb1fa46ceed05391794
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="regions-overview-in-powerapps"></a>PowerApps의 지역 개요
## <a name="how-do-i-find-out-where-my-app-is-deployed"></a>내 앱을 배포한 위치를 찾으려면 어떻게 할까요?
앱은 환경을 호스팅하는 지역에 배포됩니다. 예를 들어 유럽 지역에서 환경을 만든 경우 앱은 유럽 데이터 센터에 배포됩니다.

사용자가 관리자인 경우 PowerApps 관리 센터에서 각 환경의 지역을 확인할 수 있습니다.

* [관리 센터](https://admin.powerapps.com)로 이동하고 회사 계정으로 로그인합니다.
  
    관리 센터에 모든 기존 환경은 **환경** 탭에 나열됩니다. 이 목록은 앱을 배포한 **지역**을 보여줍니다.
  
   ![환경 탭](./media/regions-overview/environment-list.png)

## <a name="what-regions-are-available"></a>사용 가능한 지역은 어디인가요?
* 미국
* 캐나다
* 유럽
* 아시아
* 오스트레일리아
* 인도
* 일본
* 영국

## <a name="what-features-are-specific-to-a-given-region"></a>지정된 지역에만 특정된 기능은 무엇인가요?
환경은 다른 지역에 만들 수 있으며 해당 지리적 위치에 바인딩됩니다. 환경에서 앱을 만들면 해당 앱은 해당 지리적 위치의 데이터 센터에 배포됩니다. 이 기능은 해당 환경에서 만든 Common Data Service의 데이터베이스, 앱, 연결, 게이트웨이 및 사용자 지정 커넥터를 비롯한 모든 항목에 적용됩니다.

최적의 성능을 위해서는 사용자가 유럽에 있는 경우 유럽 지역에서 환경을 만들고 사용합니다. 사용자가 미국에 있는 경우 미국에서 환경을 만들고 사용합니다.

> [!NOTE]
> 현재는 프로덕션 또는 평가판 환경에서만 데이터베이스를 만들 수 있으며, 이 환경은 Azure AD 또는 Office 365 테넌트의 홈 영역과 동일한 지역에 있습니다. 테넌트의 홈 위치와 다른 지역에서 만든 환경에서도 데이터베이스를 만들 수 있도록 작업을 진행 중입니다. 또한 현재는 기본 환경 및 개별 환경(PowerApps 커뮤니티 계획으로 만든)에서 데이터베이스를 만들 수 없습니다.

> [!NOTE]
> 온-프레미스 데이터 게이트웨이는 인도 지역 또는 사용자 지정 환경에서 사용할 수 없습니다. 기본 환경에서 게이트웨이를 만들어야 합니다.


