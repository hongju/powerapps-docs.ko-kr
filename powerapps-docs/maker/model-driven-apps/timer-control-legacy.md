---
title: PowerApps의 모델 기반 앱 타이머 컨트롤 | Microsoft Docs
description: 타이머 컨트롤 사용 방법 이해
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
ms.assetid: b2b64771-083b-42f9-a3d5-2218f9d8a713
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: 7df13482e7773abc3e6762f80bd9f6b99c7ba9e6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691159"
---
# <a name="model-driven-app-timer-control-overview"></a>모델 기반 앱 타이머 컨트롤 개요

 특정 시간 기준 중요 시점을 충족해야 하는 레코드가 있는 양식에 타이머 컨트롤을 사용합니다. 타이머 컨트롤은 활성 레코드 해결에 있어 작업을 완료하는 데 사용 가능한 시간 또는 작업 완료 시간이 경과된 이후 경과한 시간을 보여줍니다. 최소한 타이머 컨트롤은 작업 완료 성공 또는 실패를 보여주도록 구성되어야 하며, 조건이 실패에 도달할 때 경고를 표시하도록 구성할 수도 있습니다.  
  
 타이머 컨트롤은 어떠한 엔터티의 양식에도 추가할 수 있지만, 특히 서비스 수준 계약을 추적하는 필드에 연결되어 있는 경우 사례 엔터티에 가장 자주 사용됩니다. 한 양식의 본문에 여러 타이머 컨트롤을 추가할 수 있으며, 머리글 또는 바닥글에는 추가할 수 없습니다.  
  
 타이머 컨트롤 **데이터 원본** 속성은 엔터티에 대한 필드를 사용합니다.  
  
-   **실패 시간 필드**는 날짜-시간 필드를 사용하여 시간을 설정합니다.  
  
-   세 가지 조건 필드는 엔터티에 **옵션 집합**, **두 가지 옵션**, **상태** 또는 **상태 이유** 중 하나를 사용합니다.  

타이머 컨트롤을 만들려면 양식 디자이너에서 **Insert** 탭을 선택한 후 도구 모음에서 **타이머**를 선택합니다. 

  ![타이머 컨트롤 삽입](media/insert-timer-control.png)

타이머 컨트롤 속성 페이지에서 원하는 속성을 입력하거나 선택한 후 **확인**을 선택합니다. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>타이머 컨트롤 속성  
 다음 표에서는 타이머 컨트롤의 속성에 대해 설명합니다.  
  
|그룹|이름|설명|  
|-----------|----------|-----------------|  
|이름|이름|**필수**. 컨트롤의 고유한 이름입니다.|  
||레이블|**필수**. 타이머 컨트롤을 표시할 레이블입니다.|  
|데이터 원본|실패 시간 필드|**필수**. 중요 시점이 성공적으로 완료되면 표시할 엔터티의 날짜-시간 필드 중 하나를 선택합니다.|  
||성공 조건|**필수**. 중요 시점의 성공을 평가할 엔터티 필드를 선택한 후 성공을 나타내는 옵션을 선택합니다.|  
||경고 조건|위태로울 때 경고를 표시하도록 중요 시점의 성공 여부를 평가할 엔터티 필드를 선택한 후 경고가 표시되어야 함을 나타내는 옵션을 선택합니다.|  
||취소 조건|중요 시점 달성의 취소 여부를 평가할 엔터티 필드를 선택한 후 중요 시점이 취소되었음을 나타내는 옵션을 선택합니다.|  

## <a name="next-steps"></a>다음 단계

[양식 편집기 사용자 인터페이스 개요](form-editor-user-interface-legacy.md)