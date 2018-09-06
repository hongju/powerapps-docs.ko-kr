---
title: 캔버스 앱에 목록 상자, 드롭다운 목록 및 라디오 단추 추가 | Microsoft Docs
description: PowerApps에서 캔버스 앱에 다중 선택 옵션 만들기 또는 구성
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/23/2016
ms.author: lonu
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 71beefdb0c937d69e621d6b02fa000b96c5a3e73
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42861508"
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons-to-a-canvas-app-in-powerapps"></a>PowerApps의 캔버스 앱에 목록 상자, 드롭다운 목록 및 라디오 단추 추가 | Microsoft Docs

PowerApps에는 목록 상자, 드롭다운 목록 및 라디오 단추를 포함하는 캔버스 앱에 대한 다중 선택 및 단일 선택 옵션이 포함되어 있습니다. 이 토픽에서는 이러한 컨트롤을 추가하고 **테이블** 수식을 사용하여 목록을 빌드합니다. 목록에서 항목을 선택하면 다른 컨트롤을 업데이트합니다.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="add-a-list-box"></a>목록 상자 추가

1. **삽입** 탭에서 **컨트롤**을 선택한 다음 **목록 상자**를 선택합니다.  

    ![][2]  

2. **목록 상자** 컨트롤의 이름을 **MyListBox**로 바꿉니다.  

    ![][3]

3. 해당 **[Items](controls/properties-core.md)** 속성을 다음 식으로 설정합니다.  
   ```["circle","triangle","rectangle"]```  <br/>

    디자이너가 다음과 유사하게 표시됩니다.

    ![][4]

4. **삽입** 탭에서 **아이콘**, 원을 차례로 선택하고, **목록 상자** 컨트롤 아래로 이동합니다.

    ![][5]  

5. 삼각형 및 사각형을 추가한 다음, **목록 상자** 컨트롤 아래에 셰이프를 행으로 정렬합니다.

    ![][6]  

6. 다음 셰이프의 **[Visible](controls/properties-core.md)** 속성을 다음 함수로 설정합니다.  

   | 셰이프 | Visible 함수 설정 대상 |
   | --- | --- |
   | 원 |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | 삼각형 |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | 사각형 |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. 만든 항목을 미리 봅니다![][1]. **목록 상자** 컨트롤에서 다른 셰이프를 선택합니다. 선택한 셰이프만 표시됩니다. Esc 키를 누르거나 **X**를 선택하여 화면으로 다시 돌아갑니다.

이 단계에서는 **목록 상자** 컨트롤에서 항목 목록을 만드는 데 식을 사용했습니다. **목록 상자** 컨트롤에서 선택한 항목에 따라 다른 셰이프가 표시됩니다. 이를 비즈니스 내에서 다른 요소에 적용할 수 있습니다. 예를 들어, **목록 상자** 컨트롤을 사용하여 제품 이미지, 제품 설명 등을 표시할 수 있습니다.

## <a name="add-radio-buttons"></a>라디오 단추 추가
1. **홈** 탭에서 **새 화면**을 선택합니다.

2. **삽입** 탭에서 **컨트롤**을 선택한 다음 **라디오**를 선택합니다.

    ![][10]  

3. **라디오** 컨트롤의 이름을 **Choices**로 바꾸고 **[Items](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    필요한 경우 모든 옵션을 표시하도록 컨트롤의 크기를 조정합니다.

4. **삽입** 탭에서 **아이콘**을 선택한 다음 원을 선택합니다.

5. 원의 **[Fill](controls/properties-color-border.md)** 속성을 다음 함수로 설정합니다.  
   ```If(Choices.Selected.Value = "red", RGBA(192, 0, 0, 1), Choices.Selected.Value = "green", RGBA(0, 176, 80, 1), Choices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```  

    이 수식에서 원은 선택한 라디오 단추에 따라 색을 변경합니다.

6. 다음 예와 같이 **라디오** 단추 아래로 원을 이동합니다.

    ![][14]  

7. 만든 항목을 미리 봅니다![][1]. 다른 라디오 단추를 선택하여 원의 색을 변경합니다. Esc 키를 누르거나 **X**를 선택하여 화면으로 다시 돌아갑니다.

## <a name="add-a-drop-down-list"></a>드롭다운 목록 추가
1. 화면을 추가한 다음 **드롭다운** 컨트롤을 추가합니다.

    ![][15]  

2. 컨트롤의 이름을 **DDChoices**로 바꾸고 **[Items](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.<br>
   **["red","green","blue"]**

3. 원을 추가하고 **드롭다운** 컨트롤 아래로 이동한 다음, 원의 **[Fill](controls/properties-color-border.md)** 속성을 다음 수식으로 설정합니다.  
   ```If(DDChoices.Selected.Value = "red", RGBA(192, 0, 0, 1), DDChoices.Selected.Value = "green", RGBA(0, 176, 80, 1), DDChoices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```

4. 만든 항목을 미리 봅니다![][1]. 다른 옵션을 선택하여 원의 색을 변경합니다.

[1]: ./media/add-list-box-drop-down-list-radio-button/preview.png
[2]: ./media/add-list-box-drop-down-list-radio-button/listbox.png
[3]: ./media/add-list-box-drop-down-list-radio-button/renamelistbox.png
[4]: ./media/add-list-box-drop-down-list-radio-button/itemslistbox.png
[5]: ./media/add-list-box-drop-down-list-radio-button/circle.png
[6]: ./media/add-list-box-drop-down-list-radio-button/allshapes.png
[10]: ./media/add-list-box-drop-down-list-radio-button/radiobutton.png
[12]: ./media/add-list-box-drop-down-list-radio-button/itemsradio.png
[14]: ./media/add-list-box-drop-down-list-radio-button/radiocircle.png
[15]: ./media/add-list-box-drop-down-list-radio-button/dropdown.png
