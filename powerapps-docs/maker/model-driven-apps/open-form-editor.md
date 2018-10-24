---
title: PowerApps에서 모델 기반 앱 양식 열기 | Microsoft Docs
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 8478a07a-c697-4784-874b-36958eb4f95d
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: e0fe15df88fccbaee3c13a344416a434e1f92923
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691143"
---
# <a name="open-the-model-driven-app-form-editor"></a>모델 기반 앱 양식 편집기 열기 
양식 편집기에서는 섹션, 탭, 필드 및 컨트롤 등의 구성 요소를 양식 편집기 캔버스에 놓아 양식을 디자인합니다. 이 항목에서는 양식 편집기에 액세스하는 여러 다양한 방법을 알아봅니다.
 
양식을 편집하는 과정에서 웹 리소스 등, 새 솔루션 구성 요소를 만들 경우 구성 요소의 이름은 기본 솔루션에 솔루션 게시자 사용자 지정 접두사를 사용하고 이러한 구성 요소는 기본 솔루션에만 포함됩니다. 관리되지 않는 특정 솔루션에 새 솔루션 구성 요소를 포함하려는 경우에는 이 관리되지 않는 솔루션을 통해 양식 편집기를 열어야 합니다.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>PowerApps 사이트에서 양식 편집기 액세스

1. [PowerApps](https://web.powerapps.com/)에 로그인합니다. 

2. **모델 기반** > **데이터** > **엔터티**를 선택한 후 원하는 엔터티(예: 계정 엔터티)를 선택합니다. 

3. **양식** 탭을 선택한 후 원하는 양식(예: **계정** 기본 양식)을 엽니다.

## <a name="access-the-form-editor-from-solution-explorer"></a>솔루션 탐색기에서 양식 편집기 액세스
  
1.  [솔루션 탐색기](advanced-navigation.md#solution-explorer)를 엽니다.
  
2.  **구성 요소**에서 **엔터티**를 확장한 후 원하는 엔터티를 선택하고 **양식**을 클릭합니다.  
  
3.  양식 목록에서 편집하려는 양식을 클릭합니다.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>모델 기반 앱 내에서 명령 모음을 통해 양식 편집기에 액세스 
  
1.  레코드를 엽니다.  
  
2.  엔터티에 대해 여러 기본 양식이 있는 경우 해당 양식이 사용자가 편집하려는 것인지 확인합니다. 그렇지 않은 경우 양식 편집기를 사용하여 편집하려는 양식을 선택합니다.  
  
3.  **추가 명령** 단추 ![약속 활동의 추가 명령](media/more-commands.gif "약속 활동의 추가 명령 단추")를 선택합니다.  
  
4.  **양식 편집기**를 선택합니다.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>Dynamics 365 고객 참여 내에서 양식 편집기 액세스
  
 엔터티에 따라 명령 모음을 통해 Dynamics 365 고객 참여에서 양식 편집기에 액세스할 수 있습니다. 이러한 방법 둘 다 기본 솔루션의 컨텍스트에서 양식을 엽니다. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>관리되지 않는 솔루션에 대해 양식 편집기 액세스  
  
1.  [솔루션](advanced-navigation.md#solutions)을 엽니다.  
  
2.  작업할 관리되지 않는 솔루션을 두 번 클릭합니다.  
  
3.  편집하려는 양식을 사용하여 엔터티를 찾습니다. 엔터티가 없는 경우 추가해야 합니다. 자세한 정보: [관리되지 않는 솔루션에 엔터티 추가](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>관리되지 않는 솔루션에 엔터티 추가  
  
1.  **엔터티** 노드를 선택하고 목록 위 도구 모음에서 **기존 추가**를 클릭합니다.  
  
2.  **솔루션 구성 요소 선택** 대화 상자에서 **구성 요소 형식** 선택기가 **엔터티**로 설정된 상태에서 추가하려는 엔터티를 선택하고 **확인**을 클릭합니다.  
  
3.  **필요한 구성 요소 누락** 대화 상자가 나타난 경우, 이 관리되지 않은 솔루션을 다른 환경으로 내보내려고 하는 경우가 아니라면 **아니요, 필요한 구성 요소 포함 안 함**을 클릭할 수 있습니다. 지금 누락된 필요한 구성 요소를 포함하지 않으려면 나중에 추가할 수 있습니다. 나중에 이 솔루션을 내보낼 경우 다시 알림을 받게 됩니다.  
  
5.  솔루션 탐색기에서 편집하려는 양식의 엔터티를 확장하고 **양식**을 선택합니다.  
  
6.  양식 목록에서 편집하려는 양식을 두 번 클릭합니다.  

## <a name="next-steps"></a>다음 단계

[양식 만들기 및 설계](create-design-forms.md)
