---
title: PowerApps의 필드에 대한 관리 속성 설정 | MicrosoftDocs
description: 필드의 관리 속성 설정 방법 알아보기
ms.custom: ''
ms.date: 06/19/2018
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
ms.assetid: 4ddcfcf3-5604-4b93-a5ee-589d4fb97fa4
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: be3b04bbc324520904c765506e32d6027927e214
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697207"
---
# <a name="set-managed-properties-for-fields"></a>필드의 관리 속성 설정

<a name="BKMK_SettingManagedProperties"></a>   

 관리 속성은 관리형 솔루션에 필드를 포함하고 솔루션을 다른 환경으로 가져올 경우에만 적용됩니다. 이러한 설정을 통해 솔루션 작성자는 관리형 솔루션을 설치하는 사용자가 이 필드를 사용자 지정할 때 가질 수 있는 사용자 지정 수준을 어느 정도 제어할 수 있습니다. 필드의 관리 속성을 설정하려면 메뉴 모음에서 **관리 속성**을 선택합니다.  
  
 **사용자 지정 가능** 옵션은 다른 모든 옵션을 제어합니다. 이 옵션이 `False`이면 다른 설정이 적용되지 않습니다. 이 옵션이 `True`이면 다른 사용자 지정 옵션을 지정할 수 있습니다.  
  
 필드를 사용자 지정할 수 있는 경우 다음 옵션을 `True` 또는 `False`로 설정합니다.  
  
- **표시 이름 수정 가능**  
  
- **요구 사항 수준 변경 가능**  
  
- **추가 속성 변경 가능**  
  
 이러한 옵션은 설명이 따로 필요 없습니다. 모든 개별 옵션을 `False`로 설정하는 경우 **사용자 지정 가능**을 `False`로 설정하는 것이 좋습니다.  

 ## <a name="next-steps"></a>다음 단계

 [필드 만들기 및 편집](create-edit-fields.md)