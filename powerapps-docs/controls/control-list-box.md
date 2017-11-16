---
title: "목록 상자 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 목록 상자 컨트롤에 관한 정보"
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
ms.openlocfilehash: ada7fed1ac9fabb9a89f79a876fcce68b4415d30
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="list-box-control-in-powerapps"></a>PowerApps의 목록 상자 컨트롤
사용자가 하나 또는 여러 개의 항목을 선택할 수 있는 목록입니다.

## <a name="description"></a>설명
**목록 상자** 컨트롤은 항상 사용 가능한 선택 항목을 모두 표시하며(**[드롭다운](control-drop-down.md)** 컨트롤과 다름) 이중에서 사용자가 한번에 둘 이상의 항목을 선택할 수 있습니다(**[라디오](control-radio.md)** 컨트롤과 다름).

## <a name="key-properties"></a>주요 속성
**[Default](properties-core.md)** – 사용자가 변경하기 전에 컨트롤의 초기 값입니다.

**[Items](properties-core.md)** – 갤러리, 목록 또는 차트 등의 컨트롤에서 나타나는 데이터 원본입니다.

[!INCLUDE [long-items](../../includes/long-items.md)]

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[FocusedBorderThickness](properties-color-border.md)** - 키보드 포커스가 있을 때 컨트롤의 테두리 두께입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[DisabledColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 텍스트 색입니다.

**[DisabledFill](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 배경색입니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Font](properties-text.md)** – 텍스트가 표시되는 글꼴의 제품군 이름입니다.

**[FontWeight](properties-text.md)** - 컨트롤의 텍스트 굵기입니다. **Bold**, **Semibold**, **Normal** 또는 **Lighter**로 설정합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**[HoverColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 텍스트 색입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**[Italic](properties-text.md)** - 컨트롤의 텍스트를 기울임꼴로 설정할지 여부를 선택합니다.

**ItemPaddingLeft** – 목록 상자의 텍스트와 왼쪽 가장자리 사이의 거리입니다.

**[LineHeight](properties-text.md)** - 텍스트 선 또는 목록의 항목 등, 항목 사이의 거리입니다.

**[OnChange](properties-core.md)** – 사용자가 컨트롤의 값을 변경할 때(예: 슬라이더 조절) 앱이 응답하는 방식입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 하단 가장자리 사이의 거리입니다.

**[PaddingLeft](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 왼쪽 가장자리 사이의 거리입니다.

**[PaddingRight](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 오른쪽 가장자리 사이의 거리입니다.

**[PaddingTop](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 상단 가장자리 사이의 거리입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[PressedColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 텍스트 색입니다.

**[PressedFill](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 배경색입니다.

**[Reset](properties-core.md)** – 컨트롤을 기본값으로 되돌릴지 여부를 선택합니다.

**[SelectionColor](properties-color-border.md)** – 목록에서 선택한 항목의 텍스트 색 또는 펜 컨트롤에서 선택 도구의 색입니다.

**[SelectionFill](properties-color-border.md)** – 펜 컨트롤의 목록 또는 선택한 영역에서 선택한 항목 또는 항목의 배경색입니다.

**SelectMultiple** – 사용자는 목록 상자에서 여러 항목을 선택할 수 있는지 여부를 선택합니다.

**[Size](properties-text.md)** -컨트롤에 표시되는 텍스트의 글꼴 크기입니다.

**[Strikethrough](properties-text.md)** - 컨트롤에 표시되는 텍스트 중앙에 선을 표시할지 여부를 선택합니다.

**[TabIndex](properties-accessibility.md)** – 0 이외의 값으로 설정된 경우 런타임 시 컨트롤의 탭 순서를 사용자 지정합니다.

**[Tooltip](properties-core.md)** – 사용자가 컨트롤을 마우스로 가리킬 때 나타나는 설명 텍스트입니다.

**[Underline](properties-text.md)** – 컨트롤에 표시되는 텍스트 아래에 선을 표시할지 여부를 선택합니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**Distinct**( *DataSource*, *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>예
1. **목록 상자** 컨트롤을 추가하고 이름을 **CategoryList**로 지정한 다음 **[Items](properties-core.md)** 속성을 다음 수식으로 설정합니다.<br>
   **["Carpet","Hardwood","Tile"]**
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
   
    ![목록 상자의 바닥재 범주](./media/control-list-box/category-listbox.png)
2. 3개의 **[드롭다운](control-drop-down.md)** 컨트롤을 추가하고 **CategoryList** 아래로 이동한 다음, 이름을 **CarpetList**, **HardwoodList** 및 **TileList**로 지정합니다.
3. 각 **[드롭다운](control-drop-down.md)** 컨트롤의 **[Items](properties-core.md)** 속성을 다음 값 중에 하나로 설정합니다.
   
   * CarpetList: **["Caserta Stone Beige","Ageless Beauty Clay", "Lush II Tundra"]**
   * HardwoodList: **["Golden Teak","Natural Hickory", "Victoria Mahogany"]**
   * TileList: **["Honey Onyx Marble","Indian Autumn Slate", "Panaria Vitality Ceramic"]**
     
     ![드롭다운 목록의 바닥재 이름](./media/control-list-box/flooring-names.png)
4. 각 **[드롭다운](control-drop-down.md)** 컨트롤의 **[Visible](properties-core.md)** 속성을 다음 값 중에 하나로 설정합니다.
   
   * CarpetList: **If("Carpet" in CategoryList.SelectedItems.Value, true)**
   * HardwoodList: **If("Hardwood" in CategoryList.SelectedItems.Value, true)**
   * TileList: **If("Tile" in CategoryList.SelectedItems.Value, true)**
     
     **[If](../functions/function-if.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
5. F5 키를 누르고 **CategoryList**에서 여러 개의 항목을 선택합니다.
   
    선택 항목에 따라 적절한 **[드롭다운](control-drop-down.md)** 컨트롤이 나타납니다.
   
    ![드롭다운 목록의 바닥재 이름](./media/control-list-box/selected-lists.png)
6. (선택 사항) 기본 작업 영역으로 돌아가려면 Esc 키를 누릅니다.

