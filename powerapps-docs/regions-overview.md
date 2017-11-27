---
title: "지역 개요 | Microsoft Docs"
description: "PowerApps의 지역: 앱을 배포할 경우 사용 가능한 지역이며 지역에 특정된 기능입니다."
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/04/2017
ms.author: sharik
ms.openlocfilehash: 1ffa79a35d93249756316e52876922ce1d850c49
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="regions-overview-in-powerapps"></a>PowerApps의 지역 개요
## <a name="how-do-i-find-out-where-my-app-is-deployed"></a>내 앱을 배포한 위치를 찾으려면 어떻게 할까요?
앱은 환경을 호스팅하는 지역에 배포됩니다. 예를 들어 유럽 지역에서 환경을 만든 경우 앱은 유럽 데이터 센터에 배포됩니다.

사용자가 관리자인 경우 PowerApps 관리 센터에서 각 환경의 지역을 확인할 수 있습니다.

* [관리 센터](https://admin.powerapps.com)로 이동하고 회사 계정으로 로그인합니다.
  
    관리 센터에 모든 기존 환경은 **환경** 탭에 나열됩니다. 이 목록은 앱을 배포한 **지역**을 보여줍니다.
  
   ![](./media/regions-overview/environment-list.png)

## <a name="what-regions-are-available"></a>사용 가능한 지역은 어디인가요?
* 미국
* 캐나다
* 유럽
* 아시아
* 오스트레일리아
* 인도
* 일본

## <a name="what-features-are-specific-to-a-given-region"></a>지정된 지역에만 특정된 기능은 무엇인가요?
환경은 다른 지역에 만들 수 있으며 해당 지리적 위치에 바인딩됩니다. 환경에서 앱을 만들면 해당 앱은 해당 지리적 위치의 데이터 센터에 배포됩니다. 이 기능은 해당 환경에서 만든 Common Data Service의 데이터베이스, 앱, 연결, 게이트웨이 및 사용자 지정 커넥터를 비롯한 모든 항목에 적용됩니다.

최적의 성능을 위해서는 사용자가 유럽에 있는 경우 유럽 지역에서 환경을 만들고 사용합니다. 사용자가 미국에 있는 경우 미국에서 환경을 만들고 사용합니다.

**참고**: 온-프레미스 데이터 게이트웨이는 인도 지역 또는 사용자 정의 환경에서 사용할 수 없습니다. 기본 환경에서 게이트웨이를 만들어야 합니다.

