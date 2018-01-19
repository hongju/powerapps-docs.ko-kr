---
title: "첨부 파일 컨트롤: 참조 | Microsoft Docs"
description: "첨부 파일 컨트롤에 대한 속성 및 예제를 포함한 정보"
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
ms.date: 09/29/2017
ms.author: fikaradz
ms.openlocfilehash: 2fd5db380eead5403d4cc7d927da5a24aa24abc9
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="attachments-control-in-powerapps"></a>PowerApps의 첨부 파일 컨트롤
사용자가 파일을 자신의 장치에 다운로드하도록 해주는 컨트롤입니다.  업로드 기능은 곧 제공됩니다.

## <a name="description"></a>설명
**첨부 파일** 컨트롤을 사용하면 데이터 원본에 저장된 파일을 열 수 있습니다.

## <a name="key-properties"></a>주요 속성
**[Items](properties-core.md)** – 다운로드할 수 있는 파일을 설명하는 소스입니다.

**MaxAttachments** – 컨트롤에 허용되는 파일의 최대 수입니다.

**OnAttach** – 사용자가 새 첨부 파일을 추가할 때 앱이 응답하는 방식입니다.

**OnRemove** – 사용자가 기존 첨부 파일을 삭제할 때 앱이 응답하는 방식입니다.

**[OnSelect](properties-core.md)** – 사용자가 첨부 파일을 클릭할 때 앱이 응답하는 방식입니다.

## <a name="additional-properties"></a>추가 속성
**AddAttachmentText** – 새 첨부 파일을 추가하는 데 사용되는 단추의 레이블 텍스트입니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**NoAttachmentsText** – 표시할 첨부 파일이 없는 경우 사용자에게 표시할 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시할지 또는 숨길지 여부입니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(또는 부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(또는 부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.


## <a name="example"></a>예
1. SharePoint 목록을 데이터 원본으로 사용하여 데이터에서 앱을 만듭니다.  또는 앱에 양식을 추가하고 SharePoint 목록을 데이터 원본으로 설정합니다.

2. 왼쪽의 트리 뷰에서 **Form** 컨트롤을 선택합니다.

3. 오른쪽의 옵션 패널에 있는 속성 탭에서 **데이터**를 클릭합니다.

4. **필드**에서 **첨부 파일** 필드를 사용하도록 설정합니다.

    SharePoint 목록과 연결된 첨부 파일 필드가 양식에 표시됩니다.

[컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?
