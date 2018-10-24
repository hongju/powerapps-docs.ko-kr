---
title: PowerApps의 게시물에 대한 정보에 액세스할 수 있도록 모델 기반 앱 노트 제어 설정 | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: f10cdf1c-3540-439c-a171-27a10e72da45
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: 014f0c2516813b7cbcaa8e44a188455b07056c71
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697279"
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>게시물에 대한 정보에 액세스할 수 있도록 모델 기반 앱 노트 제어 설정

 [업데이트된 양식](main-form-presentations.md#updated-forms)을 사용하여 특정 시스템 엔터티용 PowerApps 양식에서 Notes 컨트롤은 **게시물**, **작업** 및 **노트**에 대한 정보에 액세스할 수 있는 기능을 제공합니다. 노트 및 작업을 사용하도록 설정한 사용자 지정 엔터티의 경우 **노트** 및 **작업**만 표시됩니다. **게시물**를 포함하려면 사용자 지정 엔터티에 사용하도록 설정해야 합니다.  
  
## <a name="enable-posts-for-a-custom-entity"></a>사용자 지정 엔터티 게시물 사용  
  
1.  **[설정](advanced-navigation.md#settings)** > **작업 피드 구성**으로 이동합니다. 
  
2.  사용자 지정 엔터티에 대한 레코드를 엽니다.  
  
3.  **이 형식의 레코드 양식에 대해 벽 사용**이 선택되었는지 확인하고 레코드를 저장합니다.  
  
4.  명령 모음에서 **작업**을 선택합니다.  
  
5.  벽을 사용하도록 설정해야 하는 경우 해당 엔터티를 게시해야 합니다.  
  
 기본적으로 시스템 엔터티의 경우 노트 컨트롤은 양식 맨 위에 있는 세 개의 열 탭 중앙에 있는 소셜 창 섹션에 배치됩니다. 단 한 번의 양식으로 나타날 수 있습니다. 노트 컨트롤을 이동하거나 제거할 수 있습니다. 다시 추가하려면 **삽입** 탭의 **컨트롤** 그룹에서 **노트** 단추를 사용합니다.  
  
 다음 표에서는 Notes 컨트롤의 속성에 대해 설명합니다.  
  
|탭|속성|설명|  
|---------|--------------|-----------------|  
|**표시**|**레이블**|**필수**: 레이블이 기본적으로 표시되지 않더라도 레이블이 필요합니다.|  
||**양식에 레이블 표시**|레이블을 표시하도록 선택할 수 있습니다.|  
||**양식의 필드 잠금**|이렇게 하면 실수로 양식에서 노트가 제거되지 않습니다.|  
||**기본 탭**|기본적으로 표시할 탭을 선택합니다. 옵션은 다음과 같습니다.<br /><br /> - **작업**<br />- **게시물**<br />- **참고**|  
|**서식 지정**|**컨트롤이 차지하는 열 수 선택**|노트 컨트롤을 포함하는 섹션에 둘 이상의 열이 있다면 섹션에 있는 최대 열 수를 차지하도록 필드를 설정할 수 있습니다.|  
||**행 수**|컨트롤이 차지하는 행 수를 선택하여 노트 컨트롤의 높이를 제어합니다.|  
||**사용 가능한 공간을 사용하도록 자동으로 확장**|여러 행으로 높이를 설정하는 대신 노트 컨트롤 높이를 사용 가능한 공간으로 확장할 수 있습니다.|  
  
## <a name="next-steps"></a>다음 단계
[양식 편집기 열기](open-form-editor.md)
