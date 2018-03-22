---
title: 'Power BI 타일 컨트롤: 참조 | Microsoft Docs'
description: 속성 및 예제를 비롯한 Power BI 타일 컨트롤에 관한 정보
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
ms.date: 07/07/2016
ms.author: fikaradz
ms.openlocfilehash: 1f351877e3c05b83b4bd9cfa104a7eb22cef5028
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="power-bi-tile-control-in-powerapps"></a>PowerApps의 Power BI 타일 컨트롤
앱 내부에 있는 [Power BI](https://powerbi.microsoft.com) 타일을 보여주는 컨트롤입니다.

## <a name="description"></a>설명
앱 내부에 있는 **[Power BI 타일](https://docs.microsoft.com/power-bi/service-dashboard-tiles)**을 표시하여 기존 데이터 분석 및 보고를 활용합니다.  옵션 패널의 **데이터** 탭에서 **작업 영역**, **대시보드** 및 **타일**을 설정하여 표시하려는 타일을 선택합니다.

## <a name="sharing-and-security"></a>공유 및 보안
공유되면 PowerApp은 해당 앱에 액세스 권한이 있는 모든 사용자가 액세스하게 됩니다.  하지만 이러한 사용자에게 Power BI 콘텐츠를 표시하려면 타일을 제공하는 대시보드를 Power BI의 사용자와 [공유](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports)해야 합니다.  이를 통해 앱에서 Power BI 콘텐츠에 액세스할 때 Power BI 공유 권한이 존중됩니다.

## <a name="key-properties"></a>주요 속성
**작업 영역** – 타일이 제공되는 Power BI 작업 영역입니다.

**대시보드** – 타일이 제공되는 Power BI 대시보드입니다.

**타일** – 표시하려는 Power BI 타일의 이름입니다.

## <a name="additional-properties"></a>추가 속성
**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다. 기본 동작은 사용자를 타일과 연관된 Power BI 보고서로 안내합니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

## <a name="example"></a>예
1. **삽입** 탭, **컨트롤** 메뉴에서 **Power BI 타일** 컨트롤을 추가합니다.  
2. 옵션 패널의 **데이터** 탭에서 **작업 영역** 설정에 대해 "내 작업 영역"을 선택합니다.  대시보드 목록에서 대시보드를 선택하고 타일 목록에서 타일을 선택합니다.
   
    컨트롤은 Power BI 타일을 렌더링합니다.
   
    [컨트롤을 추가하고 구성](../add-configure-controls.md)하는 방법을 모르시나요?
   
   Power BI가 없나요? [가입](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi)하세요.

