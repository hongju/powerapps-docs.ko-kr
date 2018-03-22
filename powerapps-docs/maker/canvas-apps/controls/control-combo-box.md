---
title: "콤보 박스 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 콤보 박스 컨트롤에 관한 정보"
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
ms.date: 09/13/2017
ms.author: fikaradz
ms.openlocfilehash: 4d298e24ea967cbf5cb47638d4296f6efbd758c7
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="combo-box-control-in-powerapps"></a>PowerApps의 콤보 박스 컨트롤
사용자가 제공된 선택 항목 중에서 선택할 수 있습니다.  검색과 다중 선택을 지원합니다.

## <a name="description"></a>설명
**콤보 상자** 컨트롤 선택 항목을 검색할 수 있습니다.  검색은 SearchField 속성의 서버 측에서 수행되므로 성능은 매우 큰 데이터 원본에 의해 영향을 받지 않습니다.  

단일 또는 다중 선택 모드는 SelectMultiple 속성을 통해 구성됩니다.

선택할 항목을 검색할 때 각 항목에 대해 데이터 창의 레이아웃 설정을 수정하여 단일 데이터 값, 두 개의 값 또는 그림과 두 개의 값(사람)을 표시하도록 선택할 수 있습니다.

## <a name="people-picker"></a>상대 선택
**콤보 상자**를 상대 선택으로 사용하려면, 데이터 창의 레이아웃 설정에서 **사람** 템플릿을 선택하고, 아래 사람에게 표시할 관련 데이터 속성을 구성합니다.

## <a name="key-properties"></a>주요 속성
**[Items](properties-core.md)**  – 선택 항목을 만들 수 있는 데이터의 원본입니다.

**DefaultItems** – 사용자가 컨트롤과 상호 작용하기 전에 처음 선택한 항목입니다.

**SelectedItems** – 사용자 상호 작용을 통해 선택된 항목의 목록입니다.

**SelectMultiple** – 사용자가 단일 항목 또는 여러 항목을 선택할 수 있는지 여부입니다.

**IsSearchable** – 사용자가 선택하기 전에 항목을 검색할 수 있는지 선택합니다.

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[Default](properties-core.md)**  – 단일 선택 모드에서 사용자가 변경하기 전의 첫 선택 항목입니다.

**DisplayFields** – 검색에서 반환된 각 항목에 대해 표시되는 필드의 목록입니다.  속성 옵션 탭에서 데이터 창을 통해 구성하는 것이 가장 쉬운 방법입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**InputTextPlaceholder** – 선택된 항목이 없을 경우 최종 사용자에게 표시되는 지침 텍스트입니다.

**OnChange** – 사용자가 선택 항목을 변경할 때 앱이 응답하는 방법입니다.

**OnNavigate** - 사용자가 항목을 클릭할 때 앱이 응답하는 방법입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="example"></a>예
1. 삽입 탭, 컨트롤 메뉴에서 **콤보 상자** 컨트롤을 추가합니다.  
2. 속성 옵션 탭에서 데이터를 클릭합니다.  
3. 데이터 원본, 레이아웃 및 아래의 관련 속성을 선택합니다.
4. 고급 탭에서 **SelectMultiple** 속성을 설정합니다.

    기능적인 **콤보 상자**가 앱에 나타납니다.

    [컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?
