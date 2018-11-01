---
title: 모델 기반 앱 삭제 | MicrosoftDocs
description: PowerApps 환경에서 모델 기반 앱을 삭제하거나 제거하는 방법에 대해 알아봅니다.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="delete-a-model-driven-app"></a>모델 기반 앱 삭제

환경에서 사용되지 않는 앱을 삭제 또는 제거합니다.

1. [PowerApps](https://web.powerapps.com/)에 로그인합니다.
2. [솔루션 탐색기](advanced-navigation.md#solution-explorer)를 엽니다. 
3. 솔루션 창에서 **구성 요소** 아래의 **앱**을 선택합니다.
4. 삭제하려는 앱을 선택한 후 명령 모음에서 **삭제**를 선택합니다.

    ![앱 삭제](media/app-module-solution-window.png "앱 삭제")

5. 표시되는 확인 메시지에서 **삭제**를 선택합니다.

   환경에서 앱이 삭제됩니다.
  
구성 요소가 관계와 같은 종속성을 가지고 있을 경우, 앱을 삭제하기 전에 종속성을 먼저 제거해야 합니다. 앱의 종속성을 확인하려면 앱을 선택하고 명령 모음에서 **종속성 표시**를 선택합니다.

> [!NOTE]
> 앱을 삭제하면 관련 사이트 맵을 삭제하는 것이 좋습니다. 연결된 사이트 맵을 삭제하지 않으면 같은 이름의 다른 앱을 처음 만들 때 사이트 맵 디자이너에 오류가 표시됩니다. 그러나 오류를 무시할 수 있으며 앱을 다시 만들려고 하면 오류가 나타나지 않습니다.


