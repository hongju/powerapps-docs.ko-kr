---
title: "카메라 컨트롤: 참조 | Microsoft Docs"
description: "속성 및 예제를 포함한 카메라 컨트롤에 관한 정보"
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
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: a3a724ad42082962ec8aea4e616f1d75aa7299ec
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="camera-control-in-powerapps"></a>PowerApps의 카메라 컨트롤
사용자가 장치에서 카메라를 사용하여 사진을 촬영할 수 있는 컨트롤입니다.

## <a name="description"></a>설명
이 컨트롤을 추가하면 사용자는 앱이 실행 중일 때마다 하나 이상의 사진으로 데이터 원본을 업데이트할 수 있습니다.

## <a name="key-properties"></a>주요 속성
**Camera** – 여러 카메라가 있는 장치의 경우 앱이 사용하는 카메라의 숫자 ID입니다.

## <a name="additional-properties"></a>추가 속성
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

**Stream** – **StreamRate** 속성에 따라 자동으로 업데이트되는 이미지입니다.

**StreamRate** – **Stream** 속성에서 이미지를 업데이트하는 빈도(밀리초 단위)를 선택합니다.  이 값의 범위는 100(1초의 10분의 1)에서 3,600,000(1시간)입니다.

**[Tooltip](properties-core.md)** – 사용자가 컨트롤을 마우스로 가리킬 때 나타나는 설명 텍스트입니다.

**[Visible](properties-core.md)** – 컨트롤을 표시하거나 숨길지 여부를 선택합니다.

**[Width](properties-size-location.md)** – 컨트롤의 왼쪽 및 오른쪽 가장자리 사이의 간격입니다.

**[X](properties-size-location.md)** – 컨트롤의 왼쪽 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 왼쪽 가장자리 사이의 거리입니다.

**[Y](properties-size-location.md)** – 컨트롤의 상단 가장자리와 해당 부모 컨테이너(부모 컨테이너가 없는 경우 화면)의 상단 가장자리 사이의 거리입니다.

**Zoom** – 카메라의 이미지가 확대되는 비율 또는 PDF 뷰어에서 파일의 보기입니다.

## <a name="related-functions"></a>관련된 함수
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>예
### <a name="add-photos-to-an-image-gallery-control"></a>이미지 갤러리 컨트롤에 사진 추가
1. **카메라** 컨트롤을 추가하고 이름을 **MyCamera**로 지정한 다음 **[OnSelect](properties-core.md)** 속성을 다음 수식으로 설정합니다.<br>
   **Collect(MyPix, MyCamera.Photo)**
   
    [컨트롤을 추가, 이름을 지정하고, 구성](../add-configure-controls.md)하는 방법을 모르시나요?
   
    **[Collect](../functions/function-clear-collect-clearcollect.md)** 함수 또는 [다른 함수](../formula-reference.md)에 대해 더 알고 싶으신가요?
2. F5 키를 누른 뒤 **MyCamera**를 클릭하거나 터치하여 사진을 촬영합니다.
3. **[이미지 갤러리](control-gallery.md)** 컨트롤을 추가한 다음 **[이미지](control-image.md)** 컨트롤, 템플릿 및 **이미지 갤러리** 컨트롤 자체의 크기를 화면에 맞게 조정합니다.
4. **이미지 갤러리** 컨트롤의 **[Items](properties-core.md)** 속성을 이 식으로 설정합니다.<br>**MyPix.Url**.
5. 갤러리에서 **이미지** 컨트롤의 **[Items](properties-visual.md)** 속성을 이 식으로 설정합니다.<br>
   **ThisItem.Url**
   
    사용자가 촬영한 사진이 **이미지 갤러리** 컨트롤에 나타납니다.
6. 원하는 만큼 사진을 찍은 다음 Esc를 눌러 기본 작업 영역으로 돌아갑니다.
7. (선택 사항) **이미지 갤러리** 컨트롤의 **이미지** 컨트롤에서 **OnSelect** 속성을 **Remove(MyPix, ThisItem)**로 설정하고 F5를 누른 다음 사진을 클릭하거나 탭하여 제거합니다.

**[SaveData](../functions/function-savedata-loaddata.md)** 함수를 사용하여 사진을 로컬에서 저장하거나, **[Patch](../functions/function-patch.md)** 함수를 사용하여 데이터 원본을 업데이트합니다.

