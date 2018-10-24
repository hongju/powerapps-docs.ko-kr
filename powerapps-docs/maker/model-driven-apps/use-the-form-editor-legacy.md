---
title: PowerApps의 모델 기반 앱 양식 내에서 탐색 창 변경 | Microsoft Docs
description: 양식 내에서 탐색 창을 변경하는 방법 알아보기
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 4c379202-9f0e-4003-a49c-efff53e7f79f
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: 5a8156875f669854a4ba4649e50a23e340f3ceff
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690055"
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>모델 기반 앱 양식 내에서 탐색 창 변경

 양식 내 탐색 메뉴는 앱 사용자가 관련 레코드 목록을 볼 수 있게 해줍니다. 각 엔터티 관계에는 표시 여부를 제어하는 속성이 있습니다. 자세한 정보: [기본 엔터티의 탐색 창 항목](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 양식 편집기 내에서 표시하도록 구성된 모든 엔터티 관계를 재정의할 수 있습니다. 양식 탐색을 통해 웹 리소스 또는 다른 웹 사이트에 대한 탐색 링크를 포함할 수도 있습니다.  
  
 단계별 지침은 [앱용 Common Data Service의 엔터티 관계 생성 및 편집](../common-data-service/create-edit-entity-relationships.md)을 참조하세요.  
  
 탐색 창 편집을 활성화하려면 먼저 양식 디자이너의 **홈** 탭에서 **선택** 그룹에 있는 **탐색**을 선택해야 합니다.  
 
 ![탐색 명령](media/navigation-command.png)
 
 오른쪽 창의 **관계 탐색기**에서 1:N(일 대 다) 또는 N:N(다 대 다) 관계로 필터링하거나 사용 가능한 모든 관계를 볼 수 있습니다. **사용하지 않는 관계만 표시 확인란**이 비활성화되고 선택됩니다. 따라서 각 관계를 한 번만 추가할 수 있습니다.  
  
 ![관계 탐색기](media/relationship-explorer.png)

 **관계 탐색기**에서 관계를 추가하려면 관계를 두 번 클릭하기만 하면 됩니다. 그러면 탐색 영역의 현재 선택된 관계 아래에 해당 단계가 추가됩니다. 탐색 영역에서 관계를 두 번 클릭하고 **표시** 탭에서 레이블을 변경할 수 있습니다. **이름** 탭에서 관계에 대한 정보를 볼 수 있습니다. 엔터티의 정의를 열려면 **편집** 단추를 사용합니다.  
  
 탐색 영역에는 5개의 그룹이 있습니다. 이를 끌어서 위치를 변경하거나 두 번 클릭하여 레이블을 변경할 수 있지만 제거할 수는 없습니다. 이러한 그룹은 포함된 항목이 있는 경우에만 표시됩니다. 따라서 그룹을 표시하지 않으려면 그룹에 아무것도 추가하지 않으면 됩니다.  
  
 웹 리소스에 대한 링크 또는 외부 URL을 추가하려면 **삽입** 탭의 **제어** 그룹에서 **탐색 링크** 단추를 사용합니다.  
 
 ![탐색 링크](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>탐색 링크 속성  
 탐색 링크에는 다음과 같은 속성이 있습니다.  
  
|속성|설명|  
|--------------|-----------------|  
|이름|**필수**: 레이블로 표시할 텍스트|  
|아이콘|32 x 32 픽셀 웹 리소스를 사용합니다. 투명한 배경의 PNG 이미지를 사용하는 것이 좋습니다.|  
|웹 리소스|양식의 기본 창에 표시할 웹 리소스를 지정합니다.|  
|외부 URL|양식의 기본 창에 표시할 페이지 URL을 지정합니다.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>개인정보취급방침  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>다음 단계

[양식 편집기 사용자 인터페이스 개요](form-editor-user-interface-legacy.md)