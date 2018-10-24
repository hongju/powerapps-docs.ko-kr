---
title: PowerApps에서 모델 기반 앱 양식 성능 최적화 | Microsoft Docs
description: 양식 로드 속도를 저하시키는 양식 설계를 피하는 방법 알아보기
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
ms.assetid: 59cfa5e6-638a-437f-a462-fddfd26fb07d
caps.latest.revision: 8
ms.author: matp
manager: kvivek
ms.openlocfilehash: c9dd764fe565b59e68411dabf453207c4e01a320
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690676"
---
# <a name="optimize-model-driven-app-form-performance"></a>모델 기반 앱 양식 성능 최적화

느리게 로드되는 양식은 생산성과 사용자 도입을 감소시킬 수 있습니다. 양식이 로드되는 속도를 극대화하려면 이러한 권장 사항을 따르세요. 이러한 권장 사항은 대부분 개발자가 조직의 양식 스크립트를 구현하는 방법에 내용입니다. 양식의 스크립트를 만드는 개발자와 이러한 권장 사항을 논의하세요.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>양식 디자인  
 사용자가 양식으로 수행할 상호 작용과 양식에 표시되어야 하는 데이터의 양을 생각해 보세요.  
  
 **필드 수를 최소로 유지**  
 양식에 필드가 많을수록 각 레코드를 볼 때 인터넷이나 인트라넷을 통해 전송해야 하는 데이터가 많아집니다.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>양식 스크립트  
 양식 스크립트를 사용하는 사용자 지정 항목이 있을 경우 개발자는 이러한 전략을 이해해야 성능을 개선할 수 있습니다.  
  
 **불필요한 JavaScript 웹 리소스 라이브러리 포함 안 함**  
 양식에 추가하는 스크립트가 많을수록 다운로드하는 데 더 오래 걸립니다. 일반적으로 스크립트는 처음 로드된 후 브라우저에 캐시되지만 양식을 처음 볼 때의 성능은 강렬한 인상을 남길 수 있습니다.  
  
 **Onload 이벤트의 모든 스크립트 로드 방지**  
 필드의 `OnChange` 이벤트 또는 `OnSave` 이벤트만 지원하는 코드가 있는 경우 `OnLoad` 이벤트 대신 이러한 이벤트의 이벤트 처리기로 스크립트 라이브러리를 설정하도록 하세요. 이렇게 하면 이러한 라이브러리를 로드할 때 지연 시간이 발생할 수 있고, 양식이 로드되면 성능이 증가할 수 있습니다.  
  
 **축소된 탭을 사용하여 웹 리소스 로드 시간 지연**  
 웹 리소스 또는 IFRAME이 축소된 탭 내 섹션에 포함된 경우 탭이 축소되면 웹 리소스 또는 IFRAME이 로드되지 않습니다. 탭이 확장되면 로드됩니다. 탭 상태가 변경되면 `TabStateChange` 이벤트가 발생합니다. 축소된 탭 내에서 웹 리소스 또는 IFRAME을 지원하는 데 필요한 코드는 **TabStateChange** 이벤트의 이벤트 처리기를 사용하고, `OnLoad` 이벤트에서 발생하는 코드를 줄일 수 있습니다.  
  
 **기본 표시 옵션 설정**  
 `OnLoad` 이벤트에서 양식 요소를 숨기는 양식 스크립트 사용을 피합니다. 양식이 로드될 때 기본적으로 표시되지 않도록 숨겨진 양식 요소의 기본 표시 여부 옵션을 대신 설정하세요. 그런 다음, `OnLoad` 이벤트의 스크립트를 사용하여 표시하려는 양식 요소를 표시합니다.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>명령 모음 또는 리본  
 명령 모음 또는 리본 메뉴를 편집할 때 이러한 권장 사항을 염두에 두세요.  
  
 **컨트롤 수를 최소로 유지**  
 양식의 명령 모음 또는 리본 메뉴에서 필요한 컨트롤을 평가하고 필요하지 않은 컨트롤을 숨기세요. 표시되는 컨트롤이 늘어날수록 브라우저에 다운로드되어야 하는 리소스가 증가합니다.  
  
## <a name="next-steps"></a>다음 단계  
 [양식 만들기 및 설계](create-design-forms.md)    
    
 
