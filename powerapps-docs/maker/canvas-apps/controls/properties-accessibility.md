---
title: 캔버스 앱에 대 한 접근성 속성 | Microsoft Docs
description: TabIndex 도구 설명 등의 속성에 대 한 참조 정보
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/26/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5fa8b6fecdf690114cbf6a0945f2dfec66b067c3
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560418"
---
# <a name="accessibility-properties-for-canvas-apps"></a>캔버스 앱에 대 한 내게 필요한 옵션 속성

장애가 있는 사용자에게 적합한 컨트롤과 상호 작용하는 다른 방법을 지원하는 속성의 구성입니다.

## <a name="properties"></a>속성

**AccessibleLabel** – 화면 읽기 프로그램의 레이블입니다. 이미지, 아이콘 및 셰이프 컨트롤에 대한 값이 비어 있으면 컨트롤이 화면 판독기에서 보이지 않고 장식으로 처리됩니다.

**라이브** – 화면 판독기에 콘텐츠 변경 내용을 알리기 해야 하는 방법입니다. 에서만 사용할 수는 **[레이블을](control-text-box.md)** 제어 합니다.

* 로 설정 하면 **해제**, 화면 판독기에서 변경 내용을 발표 하지 않습니다.
* 로 설정 하면 **정중**, 화면 판독기는 화면 판독기가 말하는 동안 발생 한 모든 변경 사항을 발표 앞에서 이야기를 완료 합니다.
* 로 설정 하면 **Assertive**, 화면 판독기를 중단 하는 화면 판독기가 말하는 동안 발생 한 변경 내용을 발표할 자체입니다.

에 대해 알아봅니다 하는 방법 [라이브 지역으로 동적 변경을 알립니다](../accessible-apps-live-regions.md)합니다.

**TabIndex** – 다른 컨트롤에 관련된 키보드 탐색 순서입니다.

기본값 0은 컨트롤의 XY 좌표에 따라 기본 탭 순서를 지정합니다.  0 보다 큰 값으로 설정하면 해당 컨트롤의 탭 순서가 기본 값의 모든 컨트롤보다 앞으로 이동합니다.  TabIndex 값이 2인 컨트롤은 TabIndex가 3 이상인 컨트롤보다 탭 순서가 앞으로 지정됩니다.

양식 및 갤러리 컨트롤 등의 컨테이너는 컨트롤 외부의 컨트롤로 진행하기 전에 항상 컨테이너의 모든 요소를 탭으로 진행합니다.  컨테이너의 탭 순서는 자식 컨트롤의 최저 값 TabIndex의 순서입니다.

TabIndex를 -1로 설정하면 컨트롤에 대한 탭 액세스가 비활성화되고 이미지, 아이콘 및 셰이프의 경우 비 대화형 요소가 됩니다.
