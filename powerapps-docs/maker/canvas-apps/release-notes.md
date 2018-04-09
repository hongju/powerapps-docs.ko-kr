---
title: PowerApps의 새로운 기능 | Microsoft Docs
description: 릴리스 날짜별로 정리된 PowerApps 업데이트
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: 83a04905de797cb25012a05244dfae59ef54c5ae
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="whats-new-in-powerapps"></a>PowerApps의 새로운 기능
알려진 제한 사항에 대한 정보는 [일반적인 문제 및 해결 방법](common-issues-and-resolutions.md)을 참조하세요.

> [!NOTE]
> 릴리스는 며칠 동안 배포됩니다. 새 기능 또는 업데이트된 기능이 즉시 나타나지 않을 수 있습니다.

## <a name="mar-21"></a>3월 21일
1. 데이터 모델로 시작하여 Common Data Service의 핵심 비즈니스 데이터와 프로세스의 모양을 모델로 하여 양식, 뷰 및 기타 구성 요소를 작성하는 [모델 기반 앱](../model-driven-apps/model-driven-app-overview.md)을 만듭니다. 모델 기반 앱은 여러 장치에서 반응하는 우수한 UI를 자동으로 생성합니다.
2. 환경에서 Common Data Service의 최신 버전에서 [데이터베이스를 만듭니다](../../administrator/create-database.md).
3. 앱용 Common Data Service는 이제 다음을 포함합니다.

    - **추가 데이터 형식**은 더 복잡한 엔터티 정의를 지원하고 더 풍부한 환경을 제공합니다. (캔버스 및 모델 기반 앱에 적용됩니다.)
    - PowerApps 사이트에서 직접 앱용 Common Data Service에 [엔터티를 만들고 사용자 지정합니다](../common-data-service/data-platform-create-entity.md). **새로 고친 환경**은 향상된 성능과 더 친숙한 UI 및 옵션 집합의 인라인 만들기 등의 유용한 기능을 포함합니다. (캔버스 및 모델 기반 앱에 적용됩니다.) 
    - 앱용 Common Data Service에 입력된 데이터의 유효성을 검사하기 위한 **서버 쪽 비즈니스 규칙**을 만듭니다. (캔버스 및 모델 기반 앱에 적용됩니다.)
    - PowerApps 사이트에서 직접 앱용 Common Data Service 엔터티에 **계산된 필드 및 롤업 필드**를 만듭니다. (캔버스 및 모델 기반 앱에 적용됩니다.)  
    - 개발자는 앱용 Common Data Service SDK(**소프트웨어 개발 키트**)를 사용하여 Common Data Service에 대한 코드 기반 사용자 지정을 만들 수 있습니다. 
    - 고급 사용자는 새 **OData Web API**를 통해 앱용 Common Data Service에 저장된 데이터에 액세스할 수 있습니다. 
    - **파워 쿼리**를 사용하여 Common Data Service로 [데이터를 가져옵니다](../common-data-service/data-platform-cds-newentity-pq.md). 웹에서 파워 쿼리를 사용하여 여러 원본에서 앱용 Common Data Service로 데이터를 직접 가져옵니다.

## <a name="mar-5"></a>3월 5일
1. SharePoint 목록에 [첨부 파일](controls/control-attachments.md)을 추가(및 삭제)합니다.
2. 외부 [PDF](controls/control-pdf-viewer.md) 파일을 웹 브라우저에서 엽니다. (실험적 기능)

## <a name="feb-12"></a>2월 12일
* 포함된 [비디오](controls/control-audio-video.md) 및 [오디오](controls/control-audio-video.md) 재생에 대한 볼륨 컨트롤이 이제 인라인으로 제공됩니다. 재생을 음소거하려면, 단추를 클릭하거나 탭하는 대신 이제 볼륨 컨트롤을 사용하여 볼륨을 줄여야 합니다.

## <a name="feb-7"></a>2월 7일
1. [카메라](controls/control-camera.md) 및 [바코드 스캐너](controls/control-barcodescanner.md) 컨트롤에서 확대/축소, 밝기 및 대비 속성을 제거했습니다.
2. [텍스트 입력](controls/control-text-input.md) 컨트롤의 [지우기] 단추가 사용자 입력에 할당된 공간을 제한하는 문제를 해결했습니다. 이러한 수정으로 인해, 텍스트 입력 컨트롤의 [지우기](controls/control-text-input.md#additional-properties) 속성은 Microsoft Edge(최신 버전) 및 Internet Explorer 11 웹 브라우저에서만 지원됩니다.
3. [멀티미디어](add-images-pictures-audio-video.md) 컨트롤에 접근성 개선 사항이 추가되었습니다.

## <a name="jan-31"></a>1월 31일
1. [비디오](controls/control-audio-video.md) 컨트롤에 선택 캡션을 추가합니다.
2. [PDF 뷰어](controls/control-pdf-viewer.md) 컨트롤에서 오류 처리 기능이 향상되었습니다.

## <a name="jan-18"></a>1월 18일
1. iOS 및 Android용 PowerApps에서 이제 Microsoft Authenticator와의 통합을 지원합니다.
2. [콤보 상자](controls/control-combo-box.md)는 양식의 [SharePoint 조회 컨트롤](sharepoint-lookup-fields.md)을 대체하며 단일 선택 조회 필드의 새 [데이터 카드](working-with-cards.md) 템플릿은 PowerApps Studio에서 기본적으로 선택됩니다.
3. [콤보 상자](controls/control-combo-box.md) 내에 긴 목록의 모든 항목이 향상된 읽기 모드로 표시됩니다.
4. [위임할 수 없는 쿼리](delegation-overview.md#non-delegable-limits)에서 최대 2000개의 레코드까지 로컬 레코드 제한 저장소의 크기를 제어합니다. (실험적 기능)

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
