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
ms.openlocfilehash: 961f8908014ef9cd85eadacb97a7c1dfc7e52b25
ms.sourcegitcommit: eef2d6d9a9c7f5c8a44b9734817f59dc0eac3ecf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/07/2019
ms.locfileid: "57801000"
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
