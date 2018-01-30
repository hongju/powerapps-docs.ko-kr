---
title: "PowerApps의 새로운 기능 | Microsoft Docs"
description: "릴리스 날짜별로 정리된 PowerApps 업데이트"
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/18/2018
ms.author: sharik
ms.openlocfilehash: 5f3336d4cd3ab45f35a3ce93441dd30ffccbaca5
ms.sourcegitcommit: 7d66f33f1419751dd1c758e344cc6d55818a0fd5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="whats-new-in-powerapps"></a>PowerApps의 새로운 기능
알려진 제한 사항에 대한 정보는 [일반적인 문제 및 해결 방법](common-issues-and-resolutions.md)을 참조하세요.

## <a name="jan-18"></a>1월 18일
* iOS 및 Android용 PowerApps에서 이제 Microsoft Authenticator와의 통합을 지원합니다.
* [콤보 상자](controls/control-combo-box.md)는 양식의 [SharePoint 조회 컨트롤](sharepoint-lookup-fields.md)을 대체하며 단일 선택 조회 필드의 새 [데이터 카드](working-with-cards.md) 템플릿은 PowerApps Studio에서 기본적으로 선택됩니다.
* [콤보 상자](controls/control-combo-box.md) 내에 긴 목록의 모든 항목이 향상된 읽기 모드로 표시됩니다.
* [위임할 수 없는 쿼리](delegation-overview.md#non-delegable-limits)에서 최대 2000개의 레코드까지 로컬 레코드 제한 저장소의 크기를 제어합니다. (실험적 기능)

## <a name="jan-5"></a>1월 5일
* Power BI 보고서에서 컨텍스트 데이터를 가져오는 [PowerApps 사용자 지정 시각적 개체(미리 보기 버전)](https://powerapps.microsoft.com/blog/powerbi-powerapps-visual/)를 통합하여 Power BI 보고서 또는 대시보드에서 바로 데이터에 조치를 취합니다.

## <a name="dec-8"></a>12월 8일
1. 규칙의 [조건 템플릿](working-with-rules.md)은 컨트롤(예: **텍스트** 또는 **값**)의 공통 속성을 유추합니다.
2. 규칙 작업을 정의할 때 [**작업 정의** 확인 대화 상자](working-with-rules.md)를 그만 표시합니다.

## <a name="nov-13"></a>11월 13일
1. SharePoint 목록에서 동일한 필드에 대해 여러 값을 선택합니다.
2. SharePoint 목록에서 [첨부 파일을 다운로드하고 봅니다](controls/control-attachments.md).
3. PowerApps를 사용하여 [SharePoint 목록 양식을 사용자 지정합니다](customize-list-form.md).

## <a name="nov-10"></a>11월 10일
* 앱에서 [규칙 이름을 바꾸고](working-with-rules.md) 선택한 컨트롤이 규칙 조건에 들면 규칙을 표시합니다.

## <a name="oct-30"></a>10월 30일
1. 앱의 [모든 규칙 표시](working-with-rules.md)는 선택한 컨트롤을 위한 것만은 아닙니다.
2. 앱 작성자가 가장 많이 요청한 아이콘을 추가합니다.
3. Android 및 iOS 장치용 앱의 성능이 향상되었습니다.

## <a name="sept-20"></a>9월 20일
1. 처음으로 [앱을 저장](save-publish-app.md)하면 기본적으로 2분마다 자동으로 추가적인 변경 사항이 저장됩니다.
2. 식을 작성하지 않고 조건을 설정한 후 PowerApps 캔버스에서 바로 결과를 설계하는 방식으로 손쉽게 조건부 서식에 대한 [규칙을 생성](working-with-rules.md)할 수 있습니다.
3. 컨트롤이 추가되면 표시되는 전체 높이의 데이터 팝업 창을 사용하여 양식, 갤러리 및 데이터 테이블을 더욱 손쉽게 구성할 수 있습니다.
4. 새 앱, 템플릿, 데이터 원본 또는 SharePoint 중 어느 것으로 시작하든 관계없이 앱을 만드는 데 도움을 주는 상황에 맞는 빠른 팁을 확인하세요.

## <a name="sept-6"></a>9월 6일
1. 사용자가 작성한 앱에 대 Power BI에 포함된 대시보드에서 [사용을 추적](app-analytics.md)합니다.
2. **[Split](functions/function-split.md)** 함수를 사용하여 텍스트 문자열을 여러 부분으로 나누려면 구분 기호를 사용합니다.

## <a name="aug-15"></a>8월 15일
1. 조직에서 사용되는 [앱 목록](admin-view-apps.md)을 다운로드합니다.
2. SQL Server에 대한 **Sum**, **Average**, **Min**, **Max** 함수를 위임합니다.

## <a name="july-26"></a>7월 26일
1. 앱 내에 [Power BI 타일](controls/control-power-bi-tile.md)을 표시합니다.
2. 빈 값을 쉽게 대체하면서 다른 값 그대로 두려면 **[Coalesce](functions/function-isblank-isempty.md)** 함수를 사용합니다.
3. 텍스트 문자열이 다른 텍스트 문자열을 끝내는지 테스트하려면 **[EndsWith](functions/function-startswith.md)** 함수를 사용합니다.
4. 수식에 **[And](functions/operators.md)**, **[Or](functions/operators.md)** 또는 **[Not](functions/operators.md)** 연산자를 사용합니다.
