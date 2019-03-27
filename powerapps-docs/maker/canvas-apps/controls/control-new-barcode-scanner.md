---
title: '바코드 스캐너 컨트롤: 참조 | Microsoft Docs'
description: 속성 및 바코드 스캐너 컨트롤에 대 한 예제를 포함 한 정보
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/25/2018
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1e41ec8d228e62c22354d77777a8390bfd442f8c
ms.sourcegitcommit: 212d397284c431f5989dc7b39549e2fc170d447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58491595"
---
# <a name="barcode-scanner-control-for-canvas-apps"></a>캔버스 앱에 대 한 바코드 스캐너 컨트롤

바코드, QR 코드 및 Android 또는 iOS 장치에서 데이터 행렬 코드를 검색합니다. 웹 브라우저에서 지원 되지 않습니다.

## <a name="description"></a>설명

컨트롤에는 Android 또는 iOS 장치에서 네이티브 스캐너를 엽니다. 스캐너는 바코드, QR 코드를 또는 행렬 데이터 코드를 표시 하는 경우에 자동으로 검색 합니다. 컨트롤을 웹 브라우저에서 검색을 지원 하지 않습니다.

컨트롤 QR 코드, 데이터 행렬 코드 및 이러한 유형의 바코드를 지원합니다.

- UPC A
- UPC E
- EAN 8
- EAN 13
- 39 코드
- 코드 128
- ITF
- PDF 417

## <a name="key-properties"></a>주요 속성

**값** – 가장 최근에 검색 한 코드의 텍스트 값을 포함 하는 속성을 출력 합니다.

**텍스트** -스캐너를 활성화 하는 단추에 나타나는 텍스트입니다.

**OnScan** – 바코드를 스캔 했습니다 때 앱이 응답 하는 방법입니다.

## <a name="additional-properties"></a>추가 속성

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**FlashlightEnabled** 는 손전등은 스캐너 열릴 때 자동으로 사용 되는지 여부를-합니다.

**[높이](properties-size-location.md)**  – 스캐너를 활성화 하는 단추의 높이입니다.

**[Tooltip](properties-core.md)** – 사용자가 마우스로 컨트롤을 가리킬 때 표시되는 설명 텍스트입니다.

**형식** -가장 최근에 성공한 검색에서 검색 된 코드의 형식입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[너비](properties-size-location.md)**  – 스캐너를 활성화 하는 단추의 너비입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="accessibility-guidelines"></a>접근성 지침
에 대 한 동일한 지침이 합니다 **[단추](control-button.md)** 에 적용될지를 제어 합니다 **바코드 스캐너** 검색을 시작 하는 단추가 이기 때문에 제어 합니다.

### <a name="visual-alternatives"></a>시각 신호
* 바코드 스캐너에는 검색 결과 표시 하지 않는 단추입니다. 검색 결과를 표시 하는 것이 좋습니다.는 **[레이블을](control-text-box.md)** 제어 합니다. 레이블 설정 **[텍스트](properties-core.md)** 속성을 바코드 스캐너 **값** 속성입니다. 레이블 설정 **[Live](properties-accessibility.md)** 속성을 **정중** 화면 읽기 프로그램 사용자에 대 한 알림을 변경 되도록 합니다. 이 변경은 visual 수에 관계 없이 누구나 액세스할 수 있는 스캔 한 값을 만듭니다.

* 시각적 및 화물 차 장애가 있는 사용자는 한 바코드에 카메라를 가리키지 선호할 수 있습니다. 와 같은 다른 형태의 입력을 추가 하는 것이 좋습니다.는 **[텍스트 입력](control-text-input.md)** 바코드를 입력 하는 사용자에 대 한 제어 합니다.
