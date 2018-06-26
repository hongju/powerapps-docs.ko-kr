---
title: 새로운 기능 | Microsoft Docs
description: 릴리스 날짜별로 정리된 PowerApps 업데이트
documentationcenter: na
author: AFTOwen
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 05/21/2018
ms.author: anneta
ms.openlocfilehash: ef4360dda5d4003ff91389af78958052bbb1e052
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34851710"
---
# <a name="whats-new-in-powerapps"></a>PowerApps의 새로운 기능
> [!IMPORTANT]
> **릴리스 정보 발표**<br>
> PowerApps에서 예정되거나 최근에 릴리스된 기능에 대해 알고 있습니까?<br>
[릴리스 정보를 봅니다](https://docs.microsoft.com/en-us/business-applications-release-notes/april18/powerapps/overview). 모든 세부 정보를 처음부터 끝까지 캡처했으므로 계획에 사용할 수 있습니다.

알려진 제한 사항에 대한 정보는 [일반적인 문제 및 해결 방법](common-issues-and-resolutions.md)을 참조하세요.

> [!NOTE]
> 릴리스는 며칠 동안 배포됩니다. 새 기능 또는 업데이트된 기능이 즉시 나타나지 않을 수 있습니다.

## <a name="may-30"></a>5월 30일
1. [서식 있는 텍스트 편집기 컨트롤](controls/control-richtexteditor.md)(실험적) - 최종 사용자가 WYSIWYG 편집 영역 내의 텍스트 서식을 지정할 수 있습니다. 

## <a name="may-21"></a>5월 21일
1. 앱 사용자가 업그레이드된 Apps용 CDS(Common Data Service) 환경에 현재 사용할 수 있는 **Excel 파일에서 데이터 가져오기** 및 **데이터 내보내기** 기능을 사용하여 로컬로 저장된 Excel 또는 CSV 파일에서 데이터를 가져오고 내보낼 수 있습니다. 
1. 앱 사용자가 PowerApps용 Excel 추가 기능을 사용하여 Apps용 CDS 내에 저장된 데이터를 만들고, 업데이트하고, 삭제하기 위해 [Excel에서 엔터티를 열](../common-data-service/data-platform-excel-addin.md) 수 있습니다. 
1. Apps용 CDS에 연결된 Power BI Desktop을 사용하여 [Power BI 보고서를 만들고 게시](../common-data-service/data-platform-powerbi-connector.md)합니다. 

## <a name="april-23"></a>4월 23일
* Internet Explorer의 SharePoint 사용자 지정 목록 양식 내에 [첨부 파일](controls/control-attachments.md)을 다운로드합니다.

## <a name="april-9"></a>4월 9일
* 웹 브라우저의 앱에서 잘라내기(Ctrl+X), 복사(Ctrl+C) 및 붙여넣기(Ctrl+V) 컨트롤&mdash;컨트롤의 스타일, 수식 및 속성 포함&mdash;.

## <a name="march-21"></a>3월 21일
1. 데이터 모델로 시작하여 앱용 Common Data Service의 핵심 비즈니스 데이터와 프로세스의 모양을 모델로 하여 양식, 뷰 및 기타 구성 요소를 작성하는 [모델 기반 앱](../model-driven-apps/model-driven-app-overview.md)을 만듭니다. 모델 기반 앱은 여러 장치에서 뛰어난 반응 속도를 제공하는 우수한 UI를 자동으로 생성합니다.
2. 환경에서 앱용 CDS의 최신 버전에서 [데이터베이스를 만듭니다](../../administrator/create-database.md).
3. 이제 앱용 CDS에는 다음이 포함됩니다.
    - **추가 데이터 형식**은 더 복잡한 엔터티 정의를 지원하고 더 풍부한 환경을 제공합니다. (캔버스 및 모델 기반 앱에 적용됩니다.)
    - PowerApps 사이트에서 직접 앱용 CDS에 [엔터티를 만들고 사용자 지정합니다](../common-data-service/data-platform-create-entity.md). **새로 고친 환경**은 향상된 성능과 더 친숙한 UI 및 옵션 집합의 인라인 만들기 등의 유용한 기능을 포함합니다. (캔버스 및 모델 기반 앱에 적용됩니다.)
    - 앱용 CDS에 입력된 데이터의 유효성을 검사하기 위한 **서버 쪽 비즈니스 규칙**을 만듭니다. (캔버스 및 모델 기반 앱에 적용됩니다.)
    - PowerApps 사이트에서 직접 앱용 CDS 엔터티에 **계산된 필드 및 롤업 필드**를 만듭니다. (캔버스 및 모델 기반 앱에 적용됩니다.)  
    - 개발자는 앱용 CDS SDK(**소프트웨어 개발 키트**)를 사용하여 앱용 CDS에 대한 코드 기반 사용자 지정을 만들 수 있습니다.
    - 고급 사용자는 새 **OData Web API**를 통해 앱용 CDS에 저장된 데이터에 액세스할 수 있습니다.
    - **파워 쿼리**를 사용하여 앱용 CDS로 [데이터를 가져옵니다](../common-data-service/data-platform-cds-newentity-pq.md). 웹에서 파워 쿼리를 사용하여 여러 원본에서 앱용 CDS로 데이터를 직접 가져옵니다.

## <a name="march-5"></a>3월 5일
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
