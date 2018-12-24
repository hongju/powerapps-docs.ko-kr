---
title: 캔버스 앱에서 바코드 스캔 | Microsoft Docs
description: UPC 및 Codabar와 같은 다양한 유형의 바코드를 스캔합니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/23/2016
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9b826b66dd1d7d5cb51d464070e087c94dd189b6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849546"
---
# <a name="scan-a-barcode-in-powerapps"></a>PowerApps에서 바코드 스캔

캔버스 앱을 만들고, 카메라가 있는 휴대폰과 같은 디바이스에서 이 앱을 실행하여 여러 유형의 바코드를 스캔합니다. 바코드에 해당하는 숫자는 **레이블** 컨트롤에 표시되며, 해당 데이터를 다양한 [데이터 원본](connections-list.md)에 업로드할 수 있습니다.

PowerApps에 익숙하지 않으면 [시작](getting-started.md)을 참조하세요.

## <a name="known-limitations"></a>알려진 제한 사항

* 바코드의 높이는 1"(2.5cm), 너비는 1.5"(4cm) 이상이어야 합니다.
* 휴대폰을 사용하여 바코드를 스캔하려면 세로 방향으로 잡고 바코드에서 7"(18cm)에서 10"(25cm) 정도 떨어진 위치로 천천히 이동합니다.
* 긴 바코드 유형(예: I2of5 - 15자 이상 포함 가능)은 잘리거나 그렇지 않으면 잘못된 결과(특히 바코드가 명확하게 인쇄되지 않는 경우)가 발생할 수 있습니다.
* iPhone 및 Android 디바이스의 경우 **바코드** 컨트롤의 **Barcode** 속성을 지정할 수 있지만 너비가 고정된 가로 세로 비율로 결정됩니다.
* **바코드** 컨트롤의 **Scanrate** 속성을 **35** 이하로 설정해야 할 수도 있습니다.
* iOS를 실행하는 디바이스에서 메모리 부족을 지연시키려면 **바코드** 컨트롤의 **Height** 속성을 **700**(또는 그 이하), **Scanrate** 속성을 **30**으로 설정합니다.
* 디바이스의 메모리가 부족하여 앱이 중지되면 앱을 다시 시작합니다.

## <a name="create-a-blank-app"></a>빈 앱 만들기
1. [PowerApps에 등록](../signup-for-powerapps.md)한 후 다음 중 *하나*를 수행합니다.

2. 카메라가 있는 장치의 브라우저에서 [PowerApps를 엽니다](https://create.powerapps.com).

3. **빈 캔버스 또는 템플릿으로 시작** 아래에서 **빈 앱** 타일의 **전화 레이아웃**을 클릭하거나 탭합니다.

    ![앱을 처음부터 만들기](./media/scan-barcode/create-from-blank.png)

4. 이전에 PowerApps를 사용하지 않았으면 소개 둘러보기를 통해 앱의 주요 영역에 대해 알아봅니다. 그렇지 않으면 **건너뛰기**를 클릭하거나 탭합니다.

    ![둘러보기 화면 열기](./media/scan-barcode/quick-tour.png)

    > [!NOTE]
   > 나중에 오른쪽 위 모서리의 물음표 아이콘을 클릭하거나 탭한 다음 **소개 둘러보기**를 클릭하거나 탭하면 언제든지 둘러보기를 시작할 수 있습니다.

## <a name="add-a-barcode-control"></a>바코드 컨트롤 추가
1. **삽입** 탭에서 **미디어**, **바코드**를 차례로 클릭하거나 탭합니다.

    ![바코드 스캐너 추가](./media/scan-barcode/add-scanner.png)

2. 컨트롤의 크기를 조정하는 핸들이 있는 선택 상자가 바코드를 둘러싸고 있는지 확인하여 **바코드** 컨트롤이 선택되어 있는지 확인합니다.

    ![선택 상자](./media/scan-barcode/selection-box.png)

3. **홈** 탭에서 **Barcode1**을 클릭하거나 탭한 다음, **이름 바꾸기** 아래에서 **MyScanner**를 입력하거나 붙여넣습니다.

    > [!TIP]
   > 추가한 첫 번째 **바코드** 컨트롤의 이름은 기본적으로 **Barcode1**입니다. 해당 컨트롤을 삭제하고 다른 **바코드** 컨트롤을 추가하면 **Barcode2**라는 이름이 기본적으로 지정됩니다. 수동으로 컨트롤의 이름을 변경하면 수식에서 올바른 이름으로 해당 컨트롤을 참조하도록 합니다.

    ![바코드 컨트롤 이름 바꾸기](./media/scan-barcode/rename-barcode.png)

## <a name="add-a-text-input-control"></a>텍스트 입력 컨트롤 추가
1. **삽입** 탭에서 **텍스트**, **텍스트 입력**을 차례로 클릭하거나 탭합니다.

    **삽입** 탭이 표시되지 않으면 PowerApps 창을 최대화합니다.

    ![텍스트 입력 컨트롤 추가](./media/scan-barcode/add-text-input.png)

2. **MyScanner** 아래에 표시될 때까지 **텍스트 입력** 컨트롤 주위의 선택 상자(크기 조정 핸들 제외)를 아래로 끕니다.

    ![선택 상자가 있는 레이블](./media/scan-barcode/move-input-text.png)

3. **텍스트 입력** 컨트롤을 계속 선택한 상태에서 속성 목록에 **Default**가 표시되는지 확인한 다음, 수식 입력줄에서 **MyScanner.Text**를 입력하거나 붙여넣습니다.

    ![레이블 컨트롤의 Text 속성](./media/scan-barcode/default-text.png)

## <a name="change-the-barcode-type"></a>바코드 유형 변경
1. **삽입** 탭에서 **컨트롤**, **드롭다운**을 차례로 클릭하거나 탭합니다.

    ![드롭다운 목록 추가](./media/scan-barcode/insert-dropdown.png)

2. 화면의 다른 컨트롤 아래에 표시되도록 **드롭다운** 컨트롤을 이동합니다.

    ![드롭다운 목록 이동](./media/scan-barcode/move-dropdown.png)

3. **드롭다운** 컨트롤을 계속 선택한 상태에서 속성 목록에 **Items**가 표시되는지 확인한 다음, 수식 입력줄에서 다음 텍스트 문자열을 입력하거나 붙여넣습니다.<br>
    **[Codabar, Code128, Code39, Ean, I2of5, Upc]**

    ![드롭다운 목록의 Items 속성 설정](./media/scan-barcode/items-property.png)

4. **홈** 탭에서 **드롭다운** 컨트롤의 이름을 **ChooseType**으로 바꿉니다.

    ![드롭다운 목록 이름 바꾸기](./media/scan-barcode/rename-dropdown.png)

5. **MyScanner**를 클릭하거나 탭하여 선택하고, 속성 목록에 **BarcodeType**이 표시되는지 확인한 다음, 수식 입력줄에서 다음 텍스트 문자열을 입력하거나 붙여넣습니다.<br>
    **ChooseType.Selected.Value**

## <a name="test-the-app"></a>앱 테스트
1. F5 키를 눌러 (또는 오른쪽 위 모서리의 재생 단추를 클릭하거나 탭하기) 미리 보기 모드를 엽니다.

    ![미리 보기 모드 열기](./media/scan-barcode/open-preview.png)

2. **레이블** 컨트롤에 바코드의 숫자 구성 요소가 표시될 때까지 바코드를 장치의 카메라에 계속 맞춥니다.

    숫자 구성 요소가 표시되지 않으면 **BarcodeType** 목록에서 다른 옵션을 시도합니다. 올바른 데이터가 여전히 표시되지 않으면 **입력 텍스트** 컨트롤에 올바른 숫자를 입력합니다.

## <a name="next-steps"></a>다음 단계
* [앱을 데이터 원본에 연결](add-data-connection.md)하고, 사용자가 결과를 저장할 수 있도록 **[Patch](functions/function-patch.md)** 함수를 구성합니다.
* **[드롭다운](controls/control-drop-down.md)** 컨트롤을 추가하고, 사용자가 스캔할 바코드의 유형을 선택할 수 있도록 구성합니다.
* **[Slider](controls/control-slider.md)** 컨트롤을 추가하고, 사용자가 **바코드** 컨트롤의 스캔 속도 또는 높이를 조정할 수 있도록 구성합니다.
