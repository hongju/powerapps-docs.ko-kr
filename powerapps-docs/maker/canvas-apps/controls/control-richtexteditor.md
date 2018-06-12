---
title: '서식 있는 텍스트 편집기 컨트롤: 참조 | Microsoft Docs'
description: 속성 및 예제를 포함한 서식 있는 텍스트 편집기 컨트롤에 관한 정보
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/24/2018
ms.author: fikaradz
ms.openlocfilehash: 36fa317a4611c72ab4d2f6ce09e176b14b688a55
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34585092"
---
# <a name="rich-text-editor-control-experimental-in-powerapps"></a>PowerApps의 서식 있는 텍스트 편집기 컨트롤(실험적)
실험적 컨트롤을 사용하면 최종 사용자가 WYSIWYG 편집 영역 내의 텍스트 서식을 지정할 수 있습니다.  출력 형식은 HTML입니다.

## <a name="description"></a>설명
**서식 있는 텍스트 편집기** 컨트롤은 앱 사용자에게 텍스트의 서식을 지정하는 WYSIWYG 편집 영역을 제공합니다.  컨트롤의 입력 및 출력 형식은 HTML입니다.

컨트롤을 사용하면 복사된 서식 있는 텍스트(예: 웹 브라우저 또는 Word에서)를 컨트롤에 붙여넣을 수 있습니다.  

컨트롤의 의도된 용도는 텍스트 서식을 지정하는 것이며 입력 HTML의 무결성을 유지하도록 보장하지 않습니다.  모든 스크립트, 스타일, 개체 및 기타 잠재적으로 손상되는 태그는 편집기에서 제거됩니다.  즉, 서식 있는 텍스트가 PowerApps 외부에서 만들어졌으면 만들어진 제품에서와 동일하게 보일 수 없습니다.

현재 지원되는 기능은 다음과 같습니다.
- 굵게, 기울임꼴, 밑줄
- 텍스트 색, 색 강조
- 텍스트 크기
- 번호 매기기 목록, 글머리 목록
- 하이퍼링크
- 서식 지정 지우기

양식 내에서 컨트롤을 사용하려면 "여러 줄 텍스트 편집" 카드를 선택하고 RTE 컨트롤을 삽입하여 사용자 지정합니다.

## <a name="limitations"></a>제한 사항
컨트롤의 현재 버전은 다음과 같은 임시 제한으로 인해 실험적입니다.
- 컨트롤은 텍스트의 서식을 지정하는 기능을 제한했습니다.  

- 컨트롤은 기본적으로 큰 화면의 브라우저에서 사용하기 위해 만들어졌습니다.  휴대폰에서 컨트롤을 사용하면 어려울 수 있습니다.

- Windows studio 또는 Edge 브라우저를 사용하는 경우 작성 환경에서 알려진 문제입니다.  현재 Chrome에서 웹 스튜디오를 사용하는 것이 좋습니다.


## <a name="key-properties"></a>주요 속성
**[Default](properties-core.md)** – 편집기에 표시된 초기 텍스트 값에 대한 입력 속성입니다.

**HtmlText** – HTML 형식인 서식 있는 결과 텍스트에 대한 출력 속성입니다.



## <a name="additional-properties"></a>추가 속성
**[AccessibleLabel](properties-accessibility.md)** – 화면 읽기 프로그램의 레이블입니다. 첨부 파일의 목적을 설명해야 합니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 파일 추가 및 삭제(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[TabIndex](properties-accessibility.md)** – 다른 컨트롤에 관련된 키보드 탐색 순서입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시할지 또는 숨길지 여부입니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(또는 부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(또는 부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.
