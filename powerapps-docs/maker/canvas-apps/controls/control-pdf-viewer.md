---
title: 'PDF 뷰어 컨트롤: 참조 | Microsoft Docs'
description: 속성 및 예제를 비롯한 PDF 뷰어 컨트롤에 관한 정보
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8d3add2ccb460e11211baa993c61902856c8f083
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833724"
---
# <a name="pdf-viewer-control-experimental-in-powerapps"></a>PowerApps의 PDF 뷰어 컨트롤(실험)
PDF 파일의 콘텐츠를 표시하는 실험적 컨트롤입니다.

## <a name="description"></a>설명
이 형식의 컨트롤을 추가하고, **Document** 속성을 표시하려는 파일의 URL(큰따옴표로 묶은)로 설정하여 PDF 파일에 있는 텍스트, 그래픽 및 기타 콘텐츠를 표시합니다.

## <a name="limitations"></a>제한 사항
PowerApps의 보안 아키텍처로 인해 PDF 뷰어는 HTTP가 아닌 HTTPS 링크만을 지원합니다.  
PDF 문서가 제한적인 CORS 설정을 사용하는 서버에 존재하는 경우 앱 내에서 볼 수 없습니다.  이 문제를 해결하려면 PDF 문서를 호스팅하는 서버에서 powerapps.com에서 오는 CORS(교차 원본 요청)를 허용해야 합니다.

PowerApps에서 문서를 열 수 없는 경우 외부 브라우저에서 문서를 여는 옵션은 최종 사용자에게 표시됩니다.  이 옵션은 모든 외부 문서에 대한 컨트롤 메뉴에서 사용할 수 있습니다.

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

**[PaddingBottom](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 아래쪽 가장자리 사이의 거리입니다.

**[PaddingLeft](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 왼쪽 가장자리 사이의 거리입니다.

**[PaddingRight](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 오른쪽 가장자리 사이의 거리입니다.

**[PaddingTop](properties-size-location.md)** – 컨트롤의 텍스트와 해당 컨트롤의 위쪽 가장자리 사이의 거리입니다.

**Page** – 표시하려고 하는 페이지 수입니다.

**PageCount** -문서의 페이지 수입니다.

**[PressedBorderColor](properties-color-border.md)** – 사용자가 컨트롤을 탭하거나 클릭하는 경우 컨트롤의 테두리 색입니다.

**ShowControls** - 오디오 또는 비디오 플레이어에서 재생 단추, 볼륨 슬라이더 등을 표시하는지 및 펜 컨트롤에서 그리기, 삭제 및 지우기 아이콘 등을 표시하는지 여부입니다.

**[Tooltip](properties-core.md)** – 사용자가 마우스로 컨트롤을 가리킬 때 표시되는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

**Zoom** – 카메라의 이미지 확대 비율 또는 PDF 뷰어의 파일 보기입니다.

## <a name="example"></a>예

다음 예와 같이 **PDF 뷰어** 컨트롤을 추가하고 **Document** 속성을 PDF 파일의 URL(큰따옴표로 묶인)로 설정합니다.

  **"https://blog.mozilla.org/security/files/2015/05/HTTPS-FAQ.pdf"**

    The control shows the PDF file.

    Don't know how to [add and configure a control](../add-configure-controls.md)?

## <a name="accessibility-guidelines"></a>접근성 지침

**PDF 뷰어**가 여전히 실험 단계에 있기 때문에 PDF 문서의 일부 접근성 기능이 지원되지 않습니다. 따라서 사용자가 외부 응용 프로그램에서 문서를 열 수 있으려면 **ShowControls**를 **true**로 설정해야 합니다.

[WCAG 2.0](https://www.w3.org/TR/WCAG-TECHS/pdf.html) 및 [PDF/UA](https://www.pdfa.org/pdfua-the-iso-standard-for-universal-accessibility/) 표준을 사용하여 접근성 있는 PDF 문서를 만드는 방법을 알아봅니다.

### <a name="screen-reader-support"></a>화면 판독기 지원
* PDF 문서에 제목이 없는 경우 **[레이블](control-text-box.md)** 을 통해 제목을 추가하는 것이 좋습니다. 제목은 **PDF 뷰어** 바로 앞에 배치할 수 있습니다.
