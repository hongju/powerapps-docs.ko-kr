---
title: PowerApps의 필드 삭제 | MicrosoftDocs
description: 필드를 삭제하는 방법 알아보기
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 578ac950-da16-4ec6-a0a4-25f3aaa3b96e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: 82e560f063f2e46190420b6be5cef4cc55d9ab4f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692668"
---
# <a name="delete-fields"></a>필드 삭제

<a name="BKMK_DeletingFields"></a>   
 
 시스템 관리자 보안 역할이 있는 사용자는 관리되는 솔루션에 속하지 않는 사용자 지정 필드를 삭제할 수 있습니다. 필드를 삭제하는 경우 해당 필드에 저장된 모든 데이터가 손실됩니다. 삭제된 필드에서 데이터를 복구하는 유일한 방법은 필드가 삭제되기 이전의 시점에서 데이터베이스를 복원하는 것입니다.  
  
 사용자 지정 엔터티를 삭제하려면 먼저 다른 솔루션 구성 요소에 있을 수 있는 모든 종속성을 제거해야 합니다. 필드를 열고 메뉴 모음에서 **종속성 표시** 단추를 사용하여 **종속 구성 요소**를 확인합니다. 예를 들어 필드를 양식 또는 보기에서 사용하는 경우 먼저 이러한 솔루션 구성 요소에서 필드에 대한 참조를 제거합니다.  
  
 조회 필드를 삭제하면 해당 필드의 일대다 엔터티 관계가 자동으로 삭제됩니다.  

 ## <a name="next-steps"></a>다음 단계

 [사용자 지정 엔터티 삭제](data-platform-delete-entity.md)
