---
title: PowerApps를 사용하여 번역된 엔터티 및 필드 텍스트 가져오기 | MicrosoftDocs
description: 번역된 엔터티 및 필드 텍스트를 가져오는 방법 알아보기
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2417f7ad75e327fdfc54d4cd4fdd3f62395326b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697735"
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>번역된 엔터티 및 필드 텍스트를 앱으로 다시 가져오기

필드 레이블 또는 드롭다운 목록 값과 같은 엔터티 또는 필드 텍스트를 사용자 지정한 경우, 환경의 기본 언어 버전으로 작업하지 않는 조직의 사용자에게 해당 언어로 지정된 텍스트를 제공할 수 있습니다. 이렇게 하려면 조직에서 사용하는 언어로 번역할 수 있도록 모든 사용자 지정에 대한 텍스트 문자열을 내보냅니다.  
  
 변역 후 사용자가 변경 내용을 활용하려면 먼저 번역된 텍스트 문자열을 사용자 환경으로 가져와야 합니다.  
  
> [!IMPORTANT]
> - 가져오는 파일은 CrmTranslations.xml 및 루트에 있는 [Content_Types].xml 파일이 포함된 압축 파일이어야 합니다.  
> - 500자를 넘는 번역된 텍스트는 가져올 수 없습니다. 번역 파일의 항목이 500자를 초과하면 가져오기 프로세스가 실패합니다. 가져오기 프로세스가 실패하면 오류를 발생시킨 파일에서 줄을 검토하여 문자 수를 줄이고 다시 가져오기를 시도합니다. 또한 번역된 텍스트를 가져온 후에는 사용자 지정을 다시 게시해야 합니다.  
  
1. [솔루션 탐색기](../model-driven-apps/advanced-navigation.md#solution-explorer)를 엽니다.  
  
2. 솔루션 탐색기의 작업 도구 모음에서 **번역 가져오기**를 선택합니다.  
3.  **번역된 텍스트 가져오기** 대화 상자에서 번역된 텍스트가 포함된 파일을 지정한 다음, **가져오기**를 선택합니다.  
  
4.  가져오기가 완료되면 **닫기**를 선택합니다.  
  
> [!NOTE]
>  사용자 지정 게시는 정상적인 시스템 작동을 방해할 수 있습니다. 사용자에게 가장 방해가 적을 때 게시를 예약하는 것이 좋습니다.  

## <a name="community-tools"></a>커뮤니티 도구

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/)는 XrmToolBox 커뮤니티가 Dynamics 365 고객 참여를 위해 개발한 도구입니다. Easy Translator를 사용하여 컨텍스트 정보가 포함된 번역을 내보내고 가져올 수 있습니다. 

> [!NOTE]
> 커뮤니티 도구는 Microsoft에서 지원하지 않습니다. 도구에 대한 질문이 있으면 게시자에게 문의하세요. 자세한 정보: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>다음 단계  
 [번역을 위한 사용자 지정 엔터티 및 필드 텍스트 내보내기](export-customized-entity-field-text-translation.md)
