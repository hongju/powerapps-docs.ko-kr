---
title: 표시, 편집 또는 캔버스 앱에서 레코드를 추가 합니다. | Microsoft Docs
description: 캔버스 앱 양식을 사용하여 데이터 원본에 테이블의 레코드를 표시, 편집 또는 추가합니다.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/06/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e94aa48ed3fba1b4591e196e3b81d3fb0f76666f
ms.sourcegitcommit: 5c098a62f66a2f33418967fdce9363bd529e0fc1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58581027"
---
# <a name="show-edit-or-add-a-record-in-a-canvas-app"></a>표시, 편집 또는 캔버스 앱에서 레코드를 추가 합니다.

캔버스 앱을 추가 하 고 구성 된 **[표시](controls/control-form-detail.md)** form 컨트롤 추가 및 구성할 수도 있습니다는 레코드의 모든 필드를 표시 하는 **[편집](controls/control-form-detail.md)** 레코드를 추가 하 고 다시 데이터 소스에 변경 내용을 저장 하는 양식 컨트롤을 레코드의 모든 필드를 편집 합니다.

## <a name="prerequisites"></a>필수 조건

- PowerApps에서 [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아봅니다.
- 이 자습서에 대한 샘플 데이터를 포함하는 [이 Excel 파일](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)을 다운로드합니다.
- Excel 파일을 비즈니스용 OneDrive와 같은 [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 업로드합니다.
- 휴대폰에 대 한 앱을 열거나 만듭니다 [연결 추가](add-data-connection.md) 에 **FlooringEstimates** Excel 파일에서 테이블입니다.

    태블릿 앱에 폼을 추가할 수 있지만 기본적으로이 폼 세 개의 열에는 때문에이 항목에서는 일치 하지 않습니다.

- 기존 앱을 열면 [화면 추가](add-screen-context-variables.md) 되도록 합니다.

## <a name="add-a-form-and-show-data"></a>폼 추가 및 데이터 표시
1. 빈 화면에서 추가 **[드롭다운](controls/control-drop-down.md)** 제어 하 고 이름을 **ChooseProduct**합니다.

    > [!NOTE]
   > 컨트롤을 추가하거나, 이름을 바꾸거나, 속성을 설정하는 방법을 잘 모르는 경우 [컨트롤 추가 및 제어](add-configure-controls.md)를 참조하세요.

1. 에 **속성** 오른쪽 창의 탭 설정 **항목** 하 `FlooringEstimates` 및 **값** 에 `Name`입니다.

    ![폼의 Items 속성 설정](./media/add-form/items-property.png)

    목록은 데이터 원본에서 바닥재 제품의 이름을 표시합니다.

1. 추가 **편집** form 컨트롤을 아래로 이동 **ChooseProduct**, 대부분의 화면에 맞게 폼 크기를 조정 합니다.

    ![양식 추가](./media/add-form/add-a-form.png)

    > [!NOTE]
   > 에 대해 설명 합니다 **편집** 폼 컨트롤, 하지만 비슷한 원칙에 적용 합니다 **표시** form 컨트롤입니다.

1. 폼의 설정 **[DataSource](controls/control-form-detail.md)** 속성을 **FlooringEstimates** 고 **[항목](controls/control-form-detail.md)** 속성 이 수식은 다음과 같습니다.

    `First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))`

   이 수식은 폼 구성을 완료한 후 사용자가 **ChooseProduct**에서 선택한 해당 레코드를 표시하도록 지정합니다.

1. 에 **속성** 선택 오른쪽 창의 탭 **필드를 편집할**합니다.

    ![필드 편집](./media/add-form/edit-fields.png)

1. **필드** 창에서 **필드 추가**를 선택하고, 각 필드에 대한 확인란을 선택한 다음, **추가**를 선택합니다.

    ![필드 추가](./media/add-form/add-fields.png)

1. 옆의 줄임표 (...)를 선택 **추가 필드**를 선택 **모두 축소**를 끌어서 놓습니다 **이름** 목록의 맨 위로 이동 합니다.

    ![필드 이동](./media/add-form/move-field.png)

    합니다 **편집** 양식 컨트롤에 변경 내용이 반영 합니다.

    ![폼이 표시](./media/add-form/show-form1.png)

## <a name="set-the-card-type-for-a-field"></a>필드에 대한 카드 유형 설정
1. 에 **필드** 창 확장 합니다 **가격** 아래쪽 화살표를 선택 하 여 필드입니다.

1. 엽니다는 **컨트롤 형식과** 목록 및 선택한 **슬라이더 편집**합니다.

    ![슬라이더 편집](./media/add-form/edit-slider.png)

    폼에는 **가격** 필드를 **슬라이더** 컨트롤 대신를 **텍스트 입력** 컨트롤입니다.

1. (선택 사항) 컨트롤을 변경 하려면 동일한 프로세스를 수행 합니다 **개요** 필드를 **여러 줄 텍스트 편집** 제어 합니다.

## <a name="edit-form-only-save-changes"></a>(폼 편집에만) 변경 내용 저장

1. 폼의 이름을 **EditForm**합니다.

1. **[단추](controls/control-button.md)** 컨트롤을 추가하고 이 수식에 **[OnSelect](controls/properties-core.md)** 속성을 설정합니다.

   `SubmitForm(EditForm)`

1. F5 키를 눌러 미리 보기를 열려면 제품의 이름을 변경 하 고 사용자가 만든 단추를 선택 합니다.

    합니다 **[SubmitForm](functions/function-form.md)** 함수는 데이터 원본에 변경 내용을 저장 합니다.

1. (선택 사항) Esc 키를 눌러 (또는 오른쪽 위 모서리의 닫기 아이콘을 선택 하 여) 미리 보기를 닫습니다.

## <a name="next-steps"></a>다음 단계
[폼](working-with-forms.md), 및 [수식](working-with-formulas.md)을 사용한 작업에 대한 자세한 내용을 알아봅니다.
