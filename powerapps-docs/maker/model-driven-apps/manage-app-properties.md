---
title: PowerApps 앱 디자이너에서 모델 기반 앱 속성 관리 | Microsoft Docs
description: 앱에 대한 속성을 관리하는 방법 알아보기
keywords: ''
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: e773e60f-0211-4c4b-a1af-663be4997629
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 14
topic-status: Drafting
ms.openlocfilehash: 62129690a0f5969b6f0f749e110eca001f2c0c8b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693300"
---
# <a name="manage-model-driven-app-properties-in-the-app-designer"></a>앱 디자이너에서 모델 기반 앱 속성 관리

앱 속성은 제목 또는 URL과 같은 앱에 대한 중요한 세부 정보를 정의합니다. 앱을 만들 때 앱 속성을 정의합니다. 나중에 이러한 속성을 변경하려는 경우는 앱 디자이너에서 할 수 있습니다.  
  
1.  앱 디자이너의 오른쪽에서 **속성** 탭을 선택합니다.  
  
    ![앱 디자이너의 속성 창](media/app-designer-properties-tab.png "앱 디자이너의 속성 창")  
  
2.  다음과 같은 필요에 따라 정보를 변경합니다.  

    |속성|설명|  
    |--------------|-----------------|
    |**Name**|앱에 대한 고유하고 의미 있는 이름을 입력합니다.|  
    |**설명**|앱에 대한 간단한 설명을 입력합니다.|  
    |**아이콘**|기본적으로 **기본 앱 사용** 확인란이 선택돼 있습니다. 앱에 대한 아이콘으로 다른 웹 리소스를 선택하려면 확인란의 선택을 취소한 다음, 드롭다운 목록에서 아이콘을 선택합니다. 이 아이콘은 앱의 미리 보기 타일에 표시됩니다.|
    |**고유 이름**| 고유 이름은 변경할 수 없습니다. 고유 이름을 사용하여 데이터베이스에서 데이터를 가져오려면 테이블을 쿼리할 수 있습니다.| 
    |**클라이언트**|앱이 사용될 클라이언트의 형식을 정의합니다.<br/>-  **웹:** 클래식 Dynamics 365 사용자 지정 참여 웹 브라우저 클라이언트입니다.<br/>-  **통합 인터페이스:** PC 및 모바일 장치에 유사한 인터페이스가 있는 새 웹 브라우저 클라이언트입니다.|
    |**앱 URL 접미사**| 앱을 만들 때 선택한 URL은 기본적으로 여기에 표시됩니다. **앱 관리** 대화 상자에서 앱 URL을 변경할 수 있습니다. 현재는 솔루션을 통해 앱 URL 접미사를 내보내거나 가져올 수 없습니다.|
    |**앱에 대한 시작 페이지 선택**|이 옵션을 사용하면 사용자 환경에서 사용할 수 있는 웹 리소스에서 선택할 수 있습니다. 만든 시작 페이지에는 비디오에 대한 링크, 업그레이드 지침 또는 시작 정보와 같은 사용자에게 유용한 정보가 포함될 수 있습니다. 시작 페이지로 사용할 수 있는 HTML 파일과 같은 웹 리소스를 만드는 방법에 대한 자세한 내용은 [웹 응용 프로그램을 확장하기 위한 웹 리소스 만들기 및 편집](create-edit-web-resources.md)을 참조하세요.|
    |**모바일 오프라인 사용**|이 옵션은 **모바일 오프라인 프로필** 드롭다운 목록을 사용하여 선택된 프로필에 대해 앱을 모바일에서 오프라인으로 사용할 수 있도록 설정합니다.|
  
3.  앱을 저장합니다.  
  
## <a name="next-steps"></a>다음 단계  
 [앱 만들기 또는 편집](create-edit-app.md)
