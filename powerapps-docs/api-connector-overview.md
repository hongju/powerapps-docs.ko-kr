---
title: "API 커넥터 개요 | Microsoft Docs"
description: "ISV 및 SaaS 서비스 소유자는 커넥터를 빌드하고 Microsoft에서 인증 받을 수 있습니다."
services: 
suite: powerapps
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 74bac3b0f5bad2b95ab9b6b312fc5209bf5da3a2
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="api-connector-overview-powerapps"></a>API 커넥터 개요(PowerApps)
**API 커넥터**는 기본 서비스가 [Microsoft Flow](https://flow.microsoft.com), [PowerApps](https://powerapps.microsoft.com) 및 [Logic Apps](https://docs.microsoft.com/azure/logic-apps/)와 통신할 수 있도록 하는 REST API의 OpenAPI(Swagger) 기반 래퍼입니다. 사용자가 자신의 계정을 연결하고 미리 작성된 **트리거** 및 **작업**의 집합을 활용하여 자신의 앱 및 워크플로를 작성하는 방법을 제공합니다.

**ISV(독립 소프트웨어 공급 업체)** 또는 **SaaS 서비스 소유자**로서 사용자를 위해 다양한 비즈니스 및 생산성 시나리오를 활성화하도록 커넥터를 빌드할 수 있습니다. 커넥터를 통해 한정된 통합의 집합을 넘어서 서비스의 도달률, 검색 가능성 및 사용량을 늘릴 수 있습니다.

## <a name="requirements"></a>요구 사항
커넥터를 빌드하고 제출하려면 서비스는 다음 요구 사항을 충족해야 합니다.

* Microsoft Flow, PowerApps 및 Logic Apps와 잘 맞는 비즈니스 사용자 시나리오
* 안정적인 REST API로 공개적으로 사용할 수 있는 서비스

## <a name="build-your-connector"></a>커넥터 빌드
API 커넥터를 빌드하는 첫 단계는 모든 기능을 갖춘 사용자 지정 커넥터를 빌드하는 것입니다. 사용자 지정 커넥터는 API 커넥터와 똑같이 작동하지만 작성자의 테넌트 내에서 해당 작성자 및 특정 사용자로 가용성이 제한됩니다.

커넥터를 빌드하기 위한 프로세스에는 여러 단계가 포함됩니다.

![API 커넥터 작성 단계](./media/api-connectors-overview/authoring-steps.png)

API 커넥터를 개발하는 방법에 대해 [자세히 알아봅니다](api-connector-dev.md).

## <a name="submit-for-certification"></a>인증 제출
커넥터를 빌드한 후 인증을 위해 제출합니다. 타사 인증 과정의 일부로 Microsoft는 게시하기 전에 커넥터를 검토합니다.

이 프로세스는 Microsoft Flow 및 PowerApps에서 커넥터 기능의 유효성을 검사하고 기술 및 콘텐츠 준수를 검사합니다.

인증 및 게시를 위해 커넥터를 제출하는 프로세스에 대해 [자세히 알아봅니다](api-connector-submission.md).

## <a name="get-support"></a>지원 받기
온보딩 및 개발 지원의 경우 [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com)으로 메일을 보내주세요. 이 계정은 적극적으로 모니터링되고 관리됩니다. 개발자 쿼리 및 인시던트는 신속하게 해당 팀에게 전달됩니다.

