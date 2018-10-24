---
title: PowerApps에서 보기의 모델 기반 앱 관리 속성 | Microsoft Docs
description: 보기의 관리 속성 설정 방법 알아보기
ms.custom: ''
ms.date: 06/12/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: a9014576-8fb2-4f28-b8bb-5d2d49d76e12
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 9f33212ae81de0418dfc3695d5ae3c8e5acf36da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693375"
---
# <a name="model-driven-app-managed-properties-for-views"></a>보기의 모델 기반 앱 관리 속성

<a name="BKMK_ManagedProperties"></a>   
 
 분산할 관리 솔루션에 포함하려는 PowerApps에서 사용자 지정 공용 보기를 만드는 경우 솔루션을 설치하는 모든 사용자의 보기를 사용자 지정하는 능력을 제한할 수 있습니다.  
  
 기본적으로 대부분의 보기에서는 **사용자 지정할 수 있는** 해당 관리 자산을 true로 설정하므로 보기를 사용자 지정할 수 있습니다. 이 설정을 변경하려는 매우 합당한 이유가 있지 않는 한 앱의 보기를 사용자 지정하도록 허용하는 것이 좋습니다.  
  
## <a name="set-managed-properties-for-a-view"></a>보기의 관리 속성 설정  
  
1.  [솔루션 탐색기](advanced-navigation.md#solution-explorer)를 열고 **엔터티**를 확장하고 원하는 엔터티를 선택한 다음, **보기**를 선택합니다.  
  
2.  사용자 지정 공용 보기를 선택합니다.  
  
3.  메뉴 모음에서 **기타 작업** > **관리 속성**을 선택합니다.  

    ![관리 속성 메뉴](media/managed-properties.png)
  
4.  **사용자 지정 가능한** 또는 **삭제 가능한** 옵션을 **True** 또는 **False**로 설정합니다.  

    ![관리 속성 설정](media/set-managed-properties.png)
  
> [!NOTE]
> 보기가 관리 솔루션으로 포함된 솔루션을 내보내고 다른 환경에 설치할 때까지 해당 설정은 적용되지 않습니다.  

## <a name="next-steps"></a>다음 단계
[보기 이해](create-edit-views.md)
