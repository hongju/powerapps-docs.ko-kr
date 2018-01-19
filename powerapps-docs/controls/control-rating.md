---
title: "등급 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 등급 컨트롤에 관한 정보"
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
ms.openlocfilehash: 4dd23b8c94ee4760e40b4513e7a88667f85c3a4b
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="rating-control-in-powerapps"></a>PowerApps의 등급 컨트롤
사용자가 1과 사용자가 지정하는 최대 숫자 사이의 값을 나타낼 수 있는 컨트롤입니다.

## <a name="description"></a>설명
이 컨트롤에서 사용자는 몇 개의 별을 선택하여 좋아하는 정도 등을 나타낼 수 있습니다.

## <a name="key-properties"></a>주요 속성
**[Default](properties-core.md)** – 사용자가 컨트롤을 변경하기 전의 초기 값입니다.

**Max** – 사용자가 슬라이더 또는 등급을 설정할 수 있는 최대값입니다.

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[FocusedBorderThickness](properties-color-border.md)** - 키보드 포커스가 있을 때 컨트롤의 테두리 두께입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[OnChange](properties-core.md)** – 사용자가 컨트롤의 값을 변경할 때(예: 슬라이더 조절) 앱이 응답하는 방식입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**RatingFill** – 등급 컨트롤에서 별의 색입니다.

**ReadOnly** – 사용자가 슬라이더 또는 등급 컨트롤을 변경할 수 있는지 여부를 선택합니다.

**[Reset](properties-core.md)** – 컨트롤이 기본값으로 되돌아가는지 여부입니다.

**ShowValue** – 사용자가 해당 값을 변경하거나 컨트롤을 마우스로 가리킬 때 슬라이더 또는 등급의 값이 나타나는지 여부를 선택합니다.

**[TabIndex](properties-accessibility.md)** – 0 이외의 값으로 설정된 경우 런타임 시 컨트롤의 탭 순서를 사용자 지정합니다.

**[Tooltip](properties-core.md)** – 사용자가 마우스로 컨트롤을 가리킬 때 표시되는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**평균**(*Value1*, *Value2,* ... )](../functions/function-aggregates.md)

## <a name="example"></a>예
1. **등급** 컨트롤을 추가하고 **Quantitative**로 이름을 지정합니다.
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. **[텍스트 입력](control-text-input.md)** 컨트롤을 추가하고 **Qualitative**로 이름을 지정한 후 **등급** 컨트롤 아래로 이동합니다.
3. **[텍스트 입력](control-text-input.md)**의 **[기본값](properties-core.md)** 속성을 **""**로 설정하고 다음 수식에 **HintText**를 설정합니다.
   <br>**If(Quantitative.Value > 3, "특별히 무엇을 하는 것이 좋았나요?", "개선하려면 어떻게 하나요?")**
   
    **[If](../functions/function-if.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
4. F5 키를 누르거나 **등급** 컨트롤에서 4개 또는 5개의 별을 클릭하거나 탭합니다.
   
    **[텍스트 입력](control-text-input.md)** 컨트롤의 힌트 텍스트가 변경되어 높은 등급을 반영합니다.
5. **Quantitative**에서 4개 미만의 별을 클릭하거나 탭합니다.
   
    **[텍스트 입력](control-text-input.md)** 컨트롤의 힌트 텍스트가 변경되어 낮은 등급을 반영합니다.
6. 기본 작업 영역으로 돌아가려면 Esc 키를 누릅니다.

