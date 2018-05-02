---
title: '바코드 스캐너 컨트롤: 참조 | Microsoft Docs'
description: 속성 및 예제를 포함한 바코드 스캐너 컨트롤에 관한 정보
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 8cd0c84f508c13e8064b0e5bc93b01024cf22120
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="barcode-scanner-control-experimental-in-powerapps"></a>PowerApps의 바코드 스캐너 컨트롤(실험)
사용자가 장치에서 바코드 스캐너를 사용하여 사진을 촬영할 수 있는 실험적 컨트롤입니다.

## <a name="description"></a>설명
이 컨트롤을 추가하면 사용자는 앱이 실행 중일 때마다 하나 이상의 사진으로 데이터 원본을 업데이트할 수 있습니다.

## <a name="key-properties"></a>주요 속성
**바코드 스캐너** – 둘 이상의 바코드 스캐너를 사용하는 장치에서 앱이 사용하는 바코드 스캐너의 숫자 ID입니다.

## <a name="additional-properties"></a>추가 속성
**[AccessibleLabel](properties-accessibility.md)** – 화면 읽기 프로그램의 레이블입니다.

**[BorderColor](properties-color-border.md)** - 컨트롤의 테두리 색입니다.

**[BorderStyle](properties-color-border.md)** - 컨트롤의 테두리는 **Solid**, **Dashed**, **Dotted**, **None**입니다.

**[BorderThickness](properties-color-border.md)** - 컨트롤의 테두리 굵기입니다.

**Brightness** – 사용자가 이미지에서 인지할 가능성이 높은 조명의 정도를 선택합니다.

**Contrast** – 사용자가 한 이미지에 있는 유사한 색을 얼마나 쉽게 구별할 수 있는지 여부를 선택합니다.

**[DisplayMode](properties-core.md)** – 컨트롤이 사용자 입력을 허용(**편집**)하거나, 데이터만 표시(**보기**)하거나 사용 안 하도록(**사용 안 함**) 설정할지 선택합니다.

**[Height](properties-size-location.md)** – 컨트롤의 위쪽 및 아래쪽 가장자리 사이의 간격입니다.

**[OnSelect](properties-core.md)** – 사용자가 앱을 클릭하거나 탭할 때 앱이 응답하는 방법입니다.

**OnStream** – **Stream** 속성이 업데이트될 때 앱이 응답하는 방법입니다.

**Photo** – 사용자가 촬영 시 캡처된 이미지입니다.

**ShowLiveBarcodeDetection** – 바코드 검색 상태를 나타내기 위해 시각 신호를 표시할지 여부입니다. 노란색 사각형은 검사 중인 영역을 나타냅니다. 직사각형을 가로지르는 녹색 선은 바코드 식별 성공을 나타냅니다.

**Stream** – **StreamRate** 속성에 따라 자동으로 업데이트되는 이미지입니다.

**StreamRate** – **Stream** 속성에서 이미지를 업데이트하는 빈도(밀리초 단위)를 선택합니다.  이 값의 범위는 100(1초의 1/10)에서 3,600,000(1시간)까지입니다.

**Text** - 스캐너가 마지막으로 식별한 바코드 값입니다.

**[Tooltip](properties-core.md)** – 사용자가 마우스로 컨트롤을 가리킬 때 표시되는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 위쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 위쪽 가장자리 사이의 거리입니다.

**Zoom** – 바코스 스캐너의 이미지가 확대되는 비율 또는 PDF 뷰어에서 파일의 보기입니다.

## <a name="related-functions"></a>관련된 함수
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>예
### <a name="add-photos-to-an-image-gallery-control"></a>이미지 갤러리 컨트롤에 사진 추가
1. **바코드 스캐너** 컨트롤을 추가하고 이름을 **Mybarcode 스캐너**로 지정

    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
2. **레이블** 컨트롤을 추가하고 해당 출력을 바코드의 **텍스트**로 설정합니다.  
3. BarcodeType 속성에서 설정된 형식의 바코드입니다.
4. 레이블이 스캔된 바코드를 표시하려고 합니다.


## <a name="accessibility-guidelines"></a>접근성 지침
### <a name="video-alternatives"></a>비디오 대체 항목
* **[Text](properties-core.md)** 가 바코드 스캐너의 **텍스트**로 설정된 **[레이블](control-text-box.md)** 을 추가하는 것이 좋습니다. 바코드 스캐너는 식별된 바코드 값을 표시하지 않으므로 위의 작업을 수행하면 시각 장애가 있는 사용자만이 아니라 모든 사용자가 스캐너에 액세스할 수 있습니다.

### <a name="screen-reader-support"></a>화면 판독기 지원
* **[AccessibleLabel](properties-accessibility.md)** 이 있어야 합니다.

    > [!NOTE]
> 새 바코드가 발견되면 화면 읽기 프로그램이 이를 알립니다. 값은 알리지 않습니다. 바코드가 보기에 있는 동안에는 화면 읽기 프로그램이 동일한 바코드가 아직 식별되고 있음을 5초마다 다시 알립니다.
