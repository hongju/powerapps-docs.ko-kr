---
title: "그림 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 그림 컨트롤에 관한 정보"
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
ms.openlocfilehash: 6a7c60755f5623803d20bec4ec9881108b1116c6
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="add-picture-control-in-powerapps"></a>PowerApps의 그림 컨트롤 추가
사진을 촬영하거나 로컬 장치에서 이미지를 로드 합니다.

## <a name="description"></a>설명
이 컨트롤을 통해 사용자는 사진을 촬영하거나 본인의 장치에서 이미지 파일을 업로드하고 이 콘텐츠로 데이터 원본을 업데이트할 수 있습니다. 모바일 장치에서 사용자에게 사진을 촬영하거나 이미 사용 가능한 이미지 중에서 선택할지 묻는 장치의 선택 대화 상자가 표시됩니다.

이 컨트롤은 2개의 컨트롤로 구성된 복합 컨트롤입니다.  1회 누르거나 탭하여 로드된 이미지를 보여주는 외부 컨트롤을 선택합니다.  다시 누르거나 탭하여 내부 레이블 컨트롤을 선택합니다.

## <a name="outer-control-properties"></a>외부 컨트롤 속성
이러한 속성은 외부 컨트롤에 적용됩니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[DisabledFill](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 배경색입니다.

**Error** -이미지를 업로드하는 중에 문제가 있어 이 속성이 적절한 오류 문자열이 포함됩니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**Media** – 오디오 또는 비디오 컨트롤에서 재생하는 클립에 대한 식별자입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[PressedFill](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 배경색입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="inner-text-properties"></a>내부 텍스트 속성
이러한 속성은 기본적으로 "탭 하거나 클릭 그림을 추가하려면" 라고 표시하는 내부 레이블 컨트롤에 적용 됩니다.  이 내부 컨트롤을 선택하려면 **그림 추가** 컨트롤 창을 누르거나 탭합니다.

**[Align](properties-text.md)** - 컨트롤의 가로 가운데를 기준으로 한 텍스트의 위치입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisabledColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 텍스트 색입니다.

**[Font](properties-text.md)** – 텍스트가 표시되는 글꼴의 제품군 이름입니다.

**[FontWeight](properties-text.md)** - 컨트롤의 텍스트 굵기입니다. **Bold**, **Semibold**, **Normal** 또는 **Lighter**로 설정합니다.

**[HoverColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 텍스트 색입니다.

**[Italic](properties-text.md)** - 컨트롤의 텍스트를 기울임꼴로 설정할지 여부를 선택합니다.

**[OnChange](properties-core.md)** – 사용자가 컨트롤의 값을 변경할 때(예: 슬라이더 조절) 앱이 응답하는 방식입니다.

**[Padding](properties-size-location.md)** – 가져오기 또는 내보내기 단추의 텍스트와 단추의 가장자리 사이의 간격입니다.

**[PressedColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 텍스트 색입니다.

**[Size](properties-text.md)** -컨트롤에 표시되는 텍스트의 글꼴 크기입니다.

**[Strikethrough](properties-text.md)** - 컨트롤에 표시되는 텍스트 중앙에 선을 표시할지 여부를 선택합니다.

**[Text](properties-core.md)** – 컨트롤에 표시되는 텍스트 또는 사용자가 컨트롤에 입력하는 텍스트입니다.

**[Underline](properties-text.md)** – 컨트롤에 표시되는 텍스트 아래에 선을 표시할지 여부를 선택합니다.

**[VerticalAlign](properties-text.md)** – 컨트롤의 세로 가운데를 기준으로 한 텍스트의 위치입니다.

## <a name="related-functions"></a>관련된 함수
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>예
### <a name="add-images-to-an-image-gallery-control"></a>이미지 갤러리 컨트롤에 이미지 추가
1. **이미지 추가** 컨트롤에서 세 번 클릭합니다.
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. **열기** 대화 상자에서 이미지 파일을 클릭하거나 탭한 다음, **열기**를 클릭하거나 탭합니다.
3. **[단추](control-button.md)** 컨트롤을 추가하고 **그림 추가** 컨트롤에서 이동하고 **[단추](control-button.md)** 컨트롤에 대한 **[OnSelect](properties-core.md)** 속성을 이 수식으로 설정합니다.<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    **[Collect](../functions/function-clear-collect-clearcollect.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
4. **이미지 갤러리** 컨트롤을 추가하고 **[Items](properties-core.md)** 속성을 **MyPix**로 설정합니다.
5. F5 키를 누르고 **[단추](control-button.md)** 컨트롤을 클릭하거나 탭합니다.
   
    **그림 추가** 컨트롤의 이미지가 **이미지 갤러리** 컨트롤에 나타납니다. 이미지가 **Image gallery** 컨트롤에서 가로 세로 비율이 **[이미지](control-image.md)**와 동일하지 않을 경우, **[Image](control-image.md)** 컨트롤의 **[ImagePosition](properties-visual.md)** 속성을 **Fit**로 설정합니다.
6. **그림 추가** 컨트롤을 클릭하거나 탭하고 다른 이미지 파일을 클릭하거나 탭하고, **열기**를 클릭하거나 탭한 다음, 사용자가 추가한 **[단추](control-button.md)** 컨트롤을 클릭하거나 탭합니다.
   
    두 번째 이미지가 **이미지 갤러리** 컨트롤에 나타납니다.
7. (선택 사항) 이전 단계를 1회 이상 반복한 다음, Esc 키를 눌러 기본 작업 영역으로 돌아갑니다.

**[SaveData](../functions/function-savedata-loaddata.md)** 함수를 사용하여 이미지를 로컬에서 저장하거나, **[Patch](../functions/function-patch.md)** 함수를 사용하여 데이터 원본을 업데이트합니다.

