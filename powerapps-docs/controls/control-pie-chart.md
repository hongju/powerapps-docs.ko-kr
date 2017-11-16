---
title: "원형 차트 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 원형 차트 컨트롤에 관한 정보"
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
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 1388eac45e5086f677cb83c8db9593fe01a9819f
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="pie-chart-control-in-powerapps"></a>PowerApps의 원형 차트
서로 비교하는 상대 값을 보여주는 컨트롤입니다.

## <a name="description"></a>설명
맨 왼쪽 열의 레이블과 왼쪽에서 두 번째 열에 값을 포함한 표에서 상대적 데이터를 표시하려는 경우 **원형 차트** 컨트롤을 추가합니다.

## <a name="key-properties"></a>주요 속성
**[Items](properties-core.md)**  – 갤러리, 목록 또는 차트 등의 컨트롤에서 나타나는 데이터 원본입니다.

**ShowLabels** – 원형 차트에서 각 웨지가 연결되어 있는 값을 표시할지 여부를 선택합니다.

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**Explode** – 원형 차트에서 웨지 사이의 거리입니다.

**[Font](properties-text.md)** – 텍스트가 표시되는 글꼴의 제품군 이름입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**ItemBorderColor** – 원형 차트에서 각 웨지 둘레의 테두리 색입니다.

**ItemBorderThickness** – 원형 차트에서 각 웨지 둘레의 테두리 두께입니다.

**ItemColorSet** – 차트에서 각 데이터 요소의 색입니다.

**LabelPosition** – 원형 차트에서 웨지와 상대적인 레이블의 위치입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[Size](properties-text.md)** -컨트롤에 표시되는 텍스트의 글꼴 크기입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)**  – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)**  – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**Max**( *DataSource*, *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>예
1. **[단추](control-button.md)** 컨트롤을 추가하고 이 수식에 **[OnSelect](properties-core.md)** 속성을 설정합니다.<br>
   **Collect(Revenue2015, {Product:"Europa", Revenue:27000}, {Product:"Ganymede", Revenue:26300}, {Product:"Callisto", Revenue:29200})**
   
    [컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?
   
    **[Collect](../functions/function-clear-collect-clearcollect.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
2. F5 키를 누르고, **[단추](control-button.md)** 컨트롤을 클릭하거나 탭한 다음, 기본 작업 영역으로 돌아가려면 Esc 키를 누릅니다.
3. **원형 차트** 컨트롤을 추가하고 **[항목](properties-core.md)** 속성을 **Revenue2015**로 설정합니다.
   
    **원형 차트** 컨트롤은 다른 제품과 관련하여 각 제품에 대한 수입 데이터를 보여줍니다.

