---
title: "Microphone 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 마이크 컨트롤에 관한 정보"
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
ms.openlocfilehash: 3ffede0018a371b3c3a4cf4a3a1f9fc8115140de
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="microphone-control-in-powerapps"></a>PowerApps의 마이크 컨트롤
사용자가 사운드를 녹음할 수 있는 컨트롤입니다.

## <a name="description"></a>설명
이 컨트롤을 추가하면 사용자는 앱이 실행 중일 때마다 하나 이상의 사운드로 데이터 원본을 업데이트할 수 있습니다.

## <a name="key-properties"></a>주요 속성
**Mic** – 여러 마이크가 있는 장치의 경우 앱이 사용하는 마이크의 숫자 ID입니다.

**OnStop** – 사용자가 마이크 컨트롤로 녹음을 중지할 때 앱이 응답하는 방식입니다.

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[Color](properties-color-border.md)** – 컨트롤의 텍스트 색입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[DisabledColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 텍스트 색입니다.

**[DisabledFill](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 배경색입니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**[HoverColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 텍스트 색입니다.

**[HoverFill](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 배경색입니다.

**[이미지](properties-visual.md)** – 이미지, 오디오 또는 마이크 컨트롤에 나타나는 이미지의 이름입니다.

**[ImagePosition](properties-visual.md)** – 이미지와 같은 크기가 아닐 경우 컨트롤 또는 화면의 이미지 위치입니다(**채우기**, **맞춤**, **늘이기**, **타일** 또는 **가운데**).

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**OnStart** – 사용자가 마이크 컨트롤로 녹음을 시작할 때 앱이 응답하는 방식입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**[PressedColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 텍스트 색입니다.

**[PressedFill](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 배경색입니다.

**[Reset](properties-core.md)** – 컨트롤을 기본값으로 되돌릴지 여부를 선택합니다.

**[Tooltip](properties-core.md)** – 사용자가 컨트롤을 마우스로 가리킬 때 나타나는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>예
### <a name="add-sounds-to-a-custom-gallery-control"></a>사운드를 사용자 지정 갤러리 컨트롤에 추가
1. **마이크**를 추가하고 이름을 **MyMic**로 지정한 다음, **OnStop** 속성을 다음 서식으로 지정합니다.<br>
   **Collect(MySounds, MyMic.Audio)**
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
   
    **[Collect](../functions/function-clear-collect-clearcollect.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
2. **사용자 지정 갤러리** 컨트롤을 추가하고 **MyMic** 아래로 이동한 다음, **사용자 지정 갤러리** 컨트롤에 대한 **[Items](properties-core.md)** 속성을 **MySounds**로 설정합니다.
3. **사용자 지정 갤러리** 컨트롤에 대한 템플릿에서 **[오디오](control-audio-video.md)** 컨트롤을 추가하고 **Media** 속성을 **ThisItem.Url**로 설정합니다.
4. F5 키를 누르고 녹음을 시작하려면 **MyMic**를 클릭하거나 탭하고, 녹음을 중지하려면 다시 클릭하거나 탭합니다.
5. **사용자 지정 갤러리** 컨트롤에서 녹음을 재생하려면 **[오디오](control-audio-video.md)** 컨트롤의 재생 단추를 클릭하거나 탭합니다.
6. 원하는 만큼 녹음을 추가한 다음 Esc 키를 눌러 기본 작업 영역으로 돌아갑니다.
7. (선택 사항) **사용자 지정 갤러리** 컨트롤에 대한 템플릿에서 **[단추](control-button.md)** 컨트롤을 추가하고 **[OnSelect](properties-core.md)** 속성을 **Remove(MySounds, ThisItem)**로 설정한 다음, F5 키를 누르고 해당 **단추** 컨트롤을 클릭하거나 탭하여 녹음을 제거합니다.

**[SaveData](../functions/function-savedata-loaddata.md)** 함수를 사용하여 녹음을 로컬에서 저장하거나, **[Patch](../functions/function-patch.md)** 함수를 사용하여 데이터 원본을 업데이트합니다.

