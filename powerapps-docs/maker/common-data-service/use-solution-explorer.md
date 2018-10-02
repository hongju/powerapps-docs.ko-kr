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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-the-solution-explorer"></a>솔루션 탐색기 사용

 솔루션 탐색기에서 다음 스크린샷과 같이 왼쪽의 탐색 창을 사용하여 노드 계층 구조를 탐색할 수 있습니다.  
  
 ![축소된 엔터티의 기본 솔루션](media/crm-itpro-cust-defaultsolutionentitiescollapsed.PNG "축소된 엔터티의 기본 솔루션")  
  
> [!NOTE]
>  솔루션 탐색기에서 사용자 지정 도구로 작업할 때 마우스와 키보드를 사용합니다. 응용 프로그램은 이 부분은 터치에 최적화되어 있지 않습니다.  
  
 각 노드를 선택하면 솔루션 구성 요소의 목록을 볼 수 있습니다. 명령 모음에 사용할 수 있는 작업은 선택한 노드의 컨텍스트와 솔루션이 기본 솔루션인지 아니면 관리형 솔루션인지에 따라 달라집니다. 기본 솔루션이 아닌 비관리형 솔루션을 사용하면 **기존 항목 추가** 명령을 사용하여 솔루션에 아직 없는 솔루션 구성 요소를 가져옵니다.  
  
관리형 솔루션을 사용하면 사용 가능한 명령이 없으므로 다음과 같은 메시지가 표시됩니다.  

> [!NOTE]
> 관리형 솔루션 내에서 구성 요소를 직접 편집할 수 없습니다. 솔루션 구성 요소에 대해 관리 속성이 사용자 지정을 허용하도록 설정된 경우 PowerApps 도구를 사용하여 또는 다른 개방형 솔루션에서 편집할 수 있습니다.    
  
 기본 솔루션에서 솔루션 구성 요소를 찾아 거기서 편집하거나 사용자가 만든 다른 비관리형 솔루션에 추가합니다. 솔루션 구성 요소는 사용자 지정할 수 없습니다. 자세한 내용은 [관리 속성](solutions-overview.md#managed-properties)을 참조하십시오.
  
 수행하려는 많은 사용자 지정 항목에는 엔터티가 포함됩니다. **엔터티** 노드를 확장하여 어떤 방식으로든 사용자 지정할 수 있는 시스템의 모든 엔터티 목록을 표시할 수 있습니다. 또한 다음 스크린샷에 거래처 엔터티와 같이 표시된 엔터티의 일부인 솔루션 구성 요소를 확인하기 위해 각 엔터티를 확장할 수 있습니다.  
  
 ![확장된 거래처 엔터티를 표시하는 기본 솔루션](media/crm-itpro-cust-defaultsolution.PNG "확장된 거래처 엔터티를 표시하는 기본 솔루션")  
  
 솔루션에서 찾은 개별 솔루션 구성 요소를 사용자 지정하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   엔터티, 엔터티 관계, 필드 및 메시지 사용자 지정에 대한 자세한 내용은 [메타데이터](create-edit-metadata.md)를 참조하십시오.  
  
-   엔터티 항목에 대한 자세한 내용은 [양식](../model-driven-apps/create-design-forms.md)을 참조하십시오.  
  
-   프로세스에 대한 자세한 내용은 [프로세스](../model-driven-apps/guide-staff-through-common-tasks-processes.md)를 참조하십시오.  
  
-   비즈니스 규칙은 [비즈니스 규칙](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)을 참조하십시오.  
