---
title: PowerApps에서 솔루션 탐색기 사용 | MicrosoftDocs
description: 솔루션 탐색기를 사용하여 앱을 만들거나 사용자 지정하는 방법 알아보기
ms.custom: ''
ms.date: 06/18/2018
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
ms.assetid: 72bacfbb-96a3-4daa-88ff-11bdaaac9a3d
caps.latest.revision: 57
ms.author: matp
manager: kvivek
ms.openlocfilehash: 6abbe701a6207e68ac367fbe80495a7d04a6e682
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691652"
---
# <a name="use-the-solution-explorer"></a>솔루션 탐색기 사용

 다음 스크린샷에 표시된 것처럼 솔루션 탐색기 내에서 왼쪽에 있는 탐색 창을 사용하여 노드의 계층 구조를 탐색할 수 있습니다.  
  
 ![엔터티가 축소된 기본 솔루션](media/crm-itpro-cust-defaultsolutionentitiescollapsed.PNG "엔터티가 축소된 기본 솔루션")  
  
> [!NOTE]
>  솔루션 탐색기에서 사용자 지정 도구를 사용하여 작업할 때 마우스와 키보드를 사용합니다. 응용 프로그램의 이 부분은 터치에 최적화되지 않았습니다.  
  
 각 노드를 선택하면 솔루션 구성 요소 목록을 볼 수 있습니다. 명령 모음에서 사용할 수 있는 작업은 선택한 노드의 컨텍스트와 솔루션이 기본 솔루션인지, 관리형 솔루션인지에 따라 달라집니다. 기본 솔루션이 아닌 비관리형 솔루션의 경우 **기존 항목 추가** 명령을 사용하여 솔루션에 아직 없는 솔루션 구성 요소를 가져올 수 있습니다.  
  
관리형 솔루션을 사용하면 사용할 수 있는 명령이 없으며 메시지가 표시됩니다.  

> [!NOTE]
> 관리형 솔루션 내에서 구성 요소를 직접 편집할 수는 없습니다. 솔루션 구성 요소의 관리 속성이 사용자 지정을 허용하도록 설정된 경우 PowerApps 디자인 도구나 다른 비관리형 솔루션을 사용하여 편집할 수 있습니다.    
  
 기본 솔루션에서 솔루션 구성 요소를 찾아서 거기에서 편집하거나 작성한 다른 비관리형 솔루션에 추가해야 합니다. 솔루션 구성 요소는 사용자 지정할 수 없습니다. 자세한 정보: [관리 속성](solutions-overview.md#managed-properties)
  
 수행할 대부분의 사용자 지정은 엔터티와 관련됩니다. **엔터티** 노드를 확장하여 어떤 방식으로든 사용자 지정할 수 있는 시스템에서 모든 엔터티 목록을 볼 수 있습니다. 각 엔터티를 확장하여 다음 스크린샷의 계정 엔터티에 표시된 것처럼 엔터티의 일부인 솔루션 구성 요소를 볼 수 있습니다.  
  
 ![확장된 계정 엔터티를 보여 주는 기본 솔루션](media/crm-itpro-cust-defaultsolution.PNG "확장된 계정 엔터티를 보여 주는 기본 솔루션")  
  
 솔루션 탐색기에서 포함된 개별 솔루션 구성 요소를 사용자 지정하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   엔터티, 엔터티 관계, 필드 및 메시지 사용자 지정은 [메타데이터](create-edit-metadata.md)를 참조하세요.  
  
-   엔터티 양식은 [양식](../model-driven-apps/create-design-forms.md)을 참조하세요.  
  
-   프로세스는 [프로세스](../model-driven-apps/guide-staff-through-common-tasks-processes.md)를 참조하세요.  
  
-   비즈니스 규칙은 [비즈니스 규칙](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)을 참조하세요.  
