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
ms.author: fikaradz
ms.openlocfilehash: d35b4bc7a6e479ce47ad0a0b841a6ed9ccfd1a52
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="accessibility-properties-in-powerapps"></a>PowerApps의 접근성 속성
장애가 있는 사용자에게 적합한 컨트롤과 상호 작용하는 다른 방법을 지원하는 속성의 구성입니다.

### <a name="properties"></a>속성
**AccessiblityLabel** – 화면 판독기가 읽을 컨트롤에 대한 설명입니다.   이미지, 아이콘 및 셰이프 컨트롤에 대한 값이 비어 있으면 컨트롤이 화면 판독기에서 보이지 않고 장식으로 처리됩니다.

* **[Audio](control-audio-video.md)**, **[Button](control-button.md)**, **[Camera](control-camera.md)**, **[Check box](control-check-box.md)**, **[Drop down](control-drop-down.md)**, **[HTML text](control-html-text.md)**, **[Image](control-image.md)**, **[Label](control-text-box.md)**, **[List Box](control-list-box.md)**, **[Microphone](control-microphone.md)**, **[PDF viewer](control-pdf-viewer.md)**, **[Pen input](control-pen-input.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)**, **[Timer](control-timer.md)**, **[Toggle](control-toggle.md)** 및 **[Video](control-audio-video.md)** 컨트롤에 적용됩니다.

**TabIndex** – 런타임 시 컨트롤의 탭 순서를 사용자 지정합니다.

기본값 0은 컨트롤의 XY 좌표에 따라 기본 탭 순서를 지정합니다.  0 보다 큰 값으로 설정하면 해당 컨트롤의 탭 순서가 기본 값의 모든 컨트롤보다 앞으로 이동합니다.  TabIndex 값이 2인 컨트롤은 TabIndex가 3 이상인 컨트롤보다 탭 순서가 앞으로 지정됩니다.

양식 및 갤러리 컨트롤 등의 컨테이너는 컨트롤 외부의 컨트롤로 진행하기 전에 항상 컨테이너의 모든 요소를 탭으로 진행합니다.  컨테이너의 탭 순서는 자식 컨트롤의 최저 값 TabIndex의 순서입니다.

TabIndex를 -1로 설정하면 컨트롤에 대한 탭 액세스가 비활성화되고 이미지, 아이콘 및 셰이프의 경우 비 대화형 요소가 됩니다.

* **[단추](control-button.md)**, **[날짜 선택기](control-date-picker.md)**, **[드롭다운](control-drop-down.md)**, **[이미지](control-image.md)**, **[가져오기](control-export-import.md)**, **[목록 상자](control-list-box.md)**, **[라디오](control-radio.md)**, **[등급](control-rating.md)**, **[슬라이더](control-slider.md)**, **[텍스트 입력](control-text-input.md)** 및 **[토글](control-toggle.md)**  컨트롤에 적용됩니다.
