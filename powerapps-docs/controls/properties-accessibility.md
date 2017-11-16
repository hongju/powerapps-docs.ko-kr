---
title: "접근성 속성 | Microsoft Docs"
description: "TabIndex, 도구 설명 등의 속성에 대한 참조 정보"
services: 
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/26/2017
ms.author: anneta
ms.openlocfilehash: d8cc9d6c8586856dcaa27f67d3ea1fdc17fa0433
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="accessibility-properties-in-powerapps"></a>PowerApps의 접근성 속성
## <a name="overview"></a>개요
시각 장애가 있는 사용자에게 적합한 컨트롤과 상호 작용하는 다른 방법을 지원하는 속성의 구성입니다.

## <a name="properties"></a>속성
**Tooltip** – 사용자가 컨트롤을 마우스로 가리킬 때 나타나는 설명 텍스트입니다.  텍스트는 화면 판독기를 지원하는 Aria 레이블에서 사용합니다.

* **[오디오](control-audio-video.md)**, **[단추](control-button.md)**, **[카메라](control-camera.md)**, **[확인란](control-check-box.md)**, **[드롭다운](control-drop-down.md)**, **[HTML 텍스트](control-html-text.md)**, **[이미지](control-image.md)**, **[레이블](control-text-box.md)**, **[목록 상자](control-list-box.md)**, **[마이크](control-microphone.md)**, **[PDF 뷰어](control-pdf-viewer.md)**, **[펜 입력](control-pen-input.md)**, **[라디오](control-radio.md)**, **[등급](control-rating.md)**, **[슬라이더](control-slider.md)**, **[텍스트 입력](control-text-input.md)**, **[타이머](control-timer.md)**, **[토글](control-toggle.md)** 및 **[동영상](control-audio-video.md)** 컨트롤에 적용됩니다.

**TabIndex** – 런타임 시 컨트롤의 탭 순서를 사용자 지정합니다.

기본값 0은 컨트롤의 XY 좌표에 따라 기본 탭 순서를 지정합니다.  0 보다 큰 값으로 설정하면 해당 컨트롤의 탭 순서가 기본 값의 모든 컨트롤보다 앞으로 이동합니다.  TabIndex 값이 2인 컨트롤은 TabIndex가 3 이상인 컨트롤보다 탭 순서가 앞으로 지정됩니다.

양식 및 갤러리 컨트롤 등의 컨테이너는 컨트롤 외부의 컨트롤로 진행하기 전에 항상 컨테이너의 모든 요소를 탭으로 진행합니다.  컨테이너의 탭 순서는 자식 컨트롤의 최저 값 TabIndex의 순서입니다.

TabIndex를 1로 설정하면 컨트롤에 대한 탭 액세스가 비활성화되고 이미지, 아이콘 및 도형의 경우에는 화면 판독기에도 표시되지 않습니다.

* **[단추](control-button.md)**, **[날짜 선택기](control-date-picker.md)**, **[드롭다운](control-drop-down.md)**, **[이미지](control-image.md)**, **[가져오기](control-export-import.md)**, **[목록 상자](control-list-box.md)**, **[라디오](control-radio.md)**, **[등급](control-rating.md)**, **[슬라이더](control-slider.md)**, **[텍스트 입력](control-text-input.md)** 및 **[토글](control-toggle.md)**  컨트롤에 적용됩니다.

