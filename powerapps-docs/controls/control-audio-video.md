---
title: "오디오 및 동영상 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯하여 오디오 및 동영상 컨트롤에 관한 정보"
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
ms.openlocfilehash: a79ef2ff58667b5a2516056f29845330745e5936
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="audio-and-video-controls-in-powerapps"></a>PowerApps의 오디오 및 동영상
오디오 파일, 동영상 파일 또는 YouTube의 동영상을 재생하는 컨트롤입니다.

## <a name="description"></a>설명
**오디오** 컨트롤은 파일에서 사운드 클립, **[마이크](control-microphone.md)** 컨트롤에서 녹음 또는 동영상 파일에서 오디오 트랙을 재생합니다. **동영상** 컨트롤은 선택 자막을 사용하는 URL을 지정한 경우 파일 또는 YouTube에서 동영상 클립을 재생합니다.

## <a name="key-properties"></a>주요 속성
**Loop** – 재생을 마치는 즉시 오디오 또는 동영상 클립이 자동으로 시작할지 여부를 선택합니다.

**Media** – 오디오 또는 동영상 컨트롤이 재생하는 클립에 대한 식별자입니다.

**ShowControls** - 오디오 또는 비디오 플레이어에서 재생 단추, 볼륨 슬라이더 등을 표시하는지 및 펜 컨트롤에서 그리기, 삭제 및 지우기 아이콘 등을 표시하는지 여부입니다.

## <a name="additional-properties"></a>추가 속성
**AutoPause** – 사용자가 다른 화면으로 이동하는 경우 오디오 또는 비디오 클립을 자동으로 일시 중지할지 여부입니다.

**AutoStart** - 사용자가 해당 컨트롤이 포함된 화면으로 이동할 때 오디오 또는 비디오 컨트롤에서 클립을 자동으로 재생할지 여부입니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**ClosedCaptionsUrl** – 비디오 컨트롤만 해당합니다.  WebVTT 형식인 선택 자막 파일의 URL입니다.  비디오 및 캡션 URL은 모두 HTTPS여야 합니다. 비디오 및 캡션 파일을 모두 호스팅하는 서버는 CORS를 사용하도록 설정되어야 합니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[Image](properties-visual.md)** – 이미지, 오디오 또는 마이크 컨트롤에 표시되는 이미지의 이름입니다.

**[ImagePosition](properties-visual.md)** – 이미지와 같은 크기가 아닌 경우 컨트롤 또는 화면에 있는 이미지의 위치입니다(**채우기**, **맞춤**, **늘이기**, **타일** 또는 **가운데**).

**OnEnd** - 오디오 또는 동영상 클립이 재생을 마칠 때 앱이 응답하는 방식입니다

**OnPause** - 사용자가 오디오 또는 동영상 컨트롤이 재생하는 클립을 일시 중지할 때 앱이 응답하는 방식입니다.

**OnStart** – 사용자가 마이크 컨트롤로 녹음을 시작할 때 앱이 응답하는 방식입니다.

**Paused** – 미디어 재생 컨트롤이 현재 일시 중지되면 *True*이고 그렇지 않으면 *false*입니다.

**[Reset](properties-core.md)** – 컨트롤이 기본값으로 되돌아가는지 여부입니다.

**Start** – 오디오 또는 동영상 클립의 재생 여부를 선택합니다.

**StartTime** – 클립이 재생을 시작할 때 오디오 또는 동영상 클립의 시작 후 시간입니다.

**Time** – 미디어 컨트롤의 현재 위치입니다.

**[Tooltip](properties-core.md)** – 사용자가 마우스로 컨트롤을 가리킬 때 표시되는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="related-functions"></a>관련된 함수
[**First**( *TableName* )](../functions/function-first-last.md)

## <a name="examples"></a>예
### <a name="play-an-audio-or-video-file"></a>오디오 또는 동영상 파일 재생
1. **파일** 메뉴에서 **미디어**를 클릭하거나 탭하고 **동영상** 또는 **오디오**를 클릭하거나 탭한 다음, **찾아보기**를 클릭하거나 탭합니다.
2. 사용하려는 파일로 이동하여 클릭하거나 탭한 다음, **열기**를 클릭하거나 탭합니다.
3. Esc 키를 눌러 기본 작업 영역으로 돌아가 **오디오** 또는 **비디오** 컨트롤을 추가하고 **Media** 속성을 사용자가 추가한 파일로 설정합니다.

    [컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?
4. F5 키를 누르고 사용자가 추가한 컨트롤의 재생 단추를 클릭하거나 탭하여 클립을 재생합니다.

    > [!TIP]
> **동영상** 컨트롤의 재생 단추는 컨트롤을 마우스로 가리킬 때 나타납니다.
5. 기본 작업 영역으로 돌아가려면 Esc 키를 누릅니다.

### <a name="play-a-youtube-video"></a>YouTube 동영상을 재생합니다
1. **동영상** 컨트롤을 추가하고 **Media** 속성을 YouTube 동영상의 URL(큰따옴표로 묶인)로 설정합니다.
2. F5 키를 누르고 **동영상** 컨트롤의 재생 단추를 클릭하거나 탭하여 클립을 재생합니다.
3. 기본 작업 영역으로 돌아가려면 Esc 키를 누릅니다.
