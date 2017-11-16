---
title: "PDF 뷰어 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 비롯한 PDF 뷰어 컨트롤에 관한 정보"
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
ms.openlocfilehash: 51b0045bd8b5e83f754c4d68e1dfe63566371ae1
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="pdf-viewer-control-in-powerapps"></a>PowerApps의 PDF 뷰어
PDF 파일의 내용을 표시하는 컨트롤입니다.

## <a name="description"></a>설명
이 형식의 컨트롤을 추가하고, **Document** 속성을 표시하려는 파일의 URL(큰따옴표로 묶은)로 설정하여 PDF 파일에 있는 텍스트, 그래픽 및 기타 콘텐츠를 표시합니다.

## <a name="key-properties"></a>주요 속성
**Document** – PDF 파일의 URL(큰따옴표로 묶은)입니다.

## <a name="additional-properties"></a>추가 속성
**ActualZoom** - 컨트롤의 실제 확대/축소이며, **Zoom** 속성으로 요청된 확대/축소와 다를 수 있습니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**CurrentFindText** – 사용 중인 현재 검색어입니다.

**CurrentPage** – 실제로 표시되는 PDF 파일의 페이지 번호입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[DisabledBorderColor](properties-color-border.md)** – 컨트롤의 **[DisplayMode](properties-core.md)** 속성이 **Disabled**로 설정된 경우 컨트롤의 테두리 색입니다.

**[Fill](properties-color-border.md)** - 컨트롤의 배경색입니다.

**FindNext** – 문서에서 **FindText**의 다른 인스턴스를 찾습니다.

**FindPrevious** – 문서에서 **FindText**의 이전 인스턴스를 찾습니다.

**FindText** – 문서에서 찾을 검색어입니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[HoverBorderColor](properties-color-border.md)** – 사용자가 해당 컨트롤에 마우스 포인터를 올려두는 경우 컨트롤의 테두리 색입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**OnStateChange** – 컨트롤의 상태가 변할 때 앱이 응답하는 방식입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 하단 가장자리 사이의 거리입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 왼쪽 가장자리 사이의 거리입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 오른쪽 가장자리 사이의 거리입니다.

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 상단 가장자리 사이의 거리입니다.

**Page** – 표시하려고 하는 페이지 수입니다.

**PageCount** -문서의 페이지 수입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**ShowControls** - 오디오 또는 동영상 플레이어에서 재생 단추, 볼륨 슬라이더 등을 표시할지, 그리고 펜 컨트롤이 그리기, 삭제 및 지우기 아이콘 등을 표시할지 여부를 선택합니다.

**[Tooltip](properties-core.md)** – 사용자가 컨트롤을 마우스로 가리킬 때 나타나는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

**Zoom** – 카메라의 이미지가 확대되는 비율 또는 PDF 뷰어에서 파일의 보기입니다.

## <a name="example"></a>예
* 다음 예와 같이 **PDF 뷰어** 컨트롤을 추가하고 **Document** 속성을 PDF 파일의 URL(큰따옴표로 묶인)로 설정합니다.<br>
  **"http://www.who.int/gho/publications/world_health_statistics/EN_WHS2015_TOC.pdf?ua=1"**
  
    컨트롤은 PDF 파일을 보여줍니다.
  
    [컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?

