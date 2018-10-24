---
title: 모델 기반 앱 삭제 | MicrosoftDocs
description: PowerApps 환경에서 모델 기반 앱을 삭제하거나 제거하는 방법에 대해 알아봅니다.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 9
topic-status: Drafting
ms.openlocfilehash: 9512c0b1c13f408b92c0c18f08946ea9afa1e62b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696054"
---
# <a name="delete-a-model-driven-app"></a>모델 기반 앱 삭제

환경에서 사용되지 않은 앱을 삭제하거나 제거합니다.

1. [PowerApps](https://web.powerapps.com/)에 로그인합니다.
2. [솔루션 탐색기](advanced-navigation.md#solution-explorer)를 엽니다. 
3. 솔루션 창의 **구성 요소**에서 **앱**을 선택합니다.
4. 삭제할 앱을 선택한 다음, 명령 모음에서 **삭제**를 선택합니다.

    ![앱 삭제](media/app-module-solution-window.png "앱 삭제")

5. 표시되는 확인 메시지에서 **삭제**를 선택합니다.

   앱은 사용자 환경에서 삭제됩니다.
  
구성 요소에 종속성(예: 관계)이 있는 경우 먼저 종속성을 제거해야 앱을 삭제할 수 있습니다. 앱의 종속성을 보려면 앱을 선택한 다음, 명령 모음에서 **종속성 표시**를 선택합니다.

> [!NOTE]
> 앱을 삭제할 때는 연결된 사이트 맵을 삭제하는 것이 좋습니다. 연결된 사이트 맵을 삭제하지 않으면 같은 이름의 다른 앱을 처음 만들 때 사이트 맵 디자이너가 오류를 표시합니다. 그러나 오류는 무시할 수 있으며, 앱을 다시 만들 때 오류가 나타나지 않습니다.


