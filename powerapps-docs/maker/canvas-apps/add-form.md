---
title: 테이블의 레코드 표시, 편집 또는 추가 | Microsoft Docs
description: 폼을 사용하여 데이터 원본에 테이블의 레코드를 표시, 편집 또는 추가합니다.
services: ''
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/06/2017
ms.author: sharik
ms.openlocfilehash: c21a9350445365065b1a0cdbe91484f446ac6a81
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="show-edit-or-add-a-record-from-a-table-in-powerapps"></a>PowerApps에서 테이블의 레코드 표시, 편집 또는 추가
레코드의 모든 필드를 표시하려면 **[폼 표시](controls/control-form-detail.md)** 컨트롤을 추가하고 구성합니다. 레코드의 모든 필드를 편집하고(또는 레코드를 추가) 변경 내용을 데이터 원본에 다시 저장하려면 **[폼 편집](controls/control-form-detail.md)** 컨트롤을 추가하고 구성합니다.

## <a name="prerequisites"></a>필수 조건

* PowerApps에서 [컨트롤을 추가하고 구성](add-configure-controls.md)하는 방법을 알아봅니다.
* 이 자습서에 대한 샘플 데이터를 포함하는 [이 Excel 파일](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)을 다운로드합니다.
* Excel 파일을 비즈니스용 OneDrive와 같은 [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 업로드합니다.
* 새로운 또는 기존 앱에서 Excel 파일의 **FlooringEstimates** 테이블에 [연결을 추가](add-data-connection.md)합니다.
* 기존 앱을 사용하는 경우 [화면을 추가](add-screen-context-variables.md)합니다.

## <a name="add-a-form-and-show-data"></a>폼 추가 및 데이터 표시
1. **[드롭다운](controls/control-drop-down.md)** 컨트롤을 추가하고 이름을 **ChooseProduct**로 바꾼 다음 **[Items](controls/properties-core.md)** 속성을 다음 값으로 설정합니다.

    **FlooringEstimates.Name**

    > [!NOTE]
> 컨트롤을 추가하거나, 이름을 바꾸거나, 속성을 설정하는 방법을 잘 모르는 경우 [컨트롤 추가 및 제어](add-configure-controls.md)를 참조하세요.

    목록은 데이터 원본에서 바닥재 제품의 이름을 표시합니다.

2. **폼 편집** 컨트롤을 추가하고, **ChooseProduct** 아래로 이동한 다음, 화면 대부분을 가리도록 폼 크기를 조정합니다.

    ![양식 추가](./media/add-form/add-a-form.png)

    > [!NOTE]
> 이 토픽에서는 **폼 편집** 컨트롤을 설명하지만, 유사한 원칙이 **폼 표시** 컨트롤에도 적용됩니다.

3. 폼의 **[DataSource](controls/control-form-detail.md)** 속성을 **FlooringEstimates**로, 폼의 **[Item](controls/control-form-detail.md)** 속성을 다음 수식으로 설정합니다.

   **First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))**

   이 수식은 폼 구성을 완료한 후 사용자가 **ChooseProduct**에서 선택한 해당 레코드를 표시하도록 지정합니다.

4. **데이터** 창에서 각 필드의 확인란을 클릭하거나 탭하여 표시합니다.

    > [!NOTE]
> **데이터** 창이 닫히면 왼쪽 창에서 폼을 선택한 다음 오른쪽 창에서 **데이터**를 클릭하거나 탭하여 엽니다.

    ![양식에 필드 표시](./media/add-form/checkbox.png)

5. **데이터** 창에서 **이름** 항목을 목록의 맨 위로 끕니다.

    ![카드 이동](./media/add-form/drag-field.png)

    **폼 편집** 컨트롤에 변경 내용이 반영됩니다.

    ![위쪽에 이름](./media/add-form/move-card-form.png)

## <a name="set-the-card-type-for-a-field"></a>필드에 대한 카드 유형 설정
1. 선택된 폼을 사용하여 **데이터** 창에서 **가격**에 대한 카드 선택기를 클릭하거나 탭합니다.

    ![카드 선택기 선택](./media/add-form/price-card2.png)

2. 아래로 스크롤한 다음, 필드를 읽기 전용으로 만드는 **텍스트 보기** 옵션을 클릭하거나 탭합니다.

    ![보기 텍스트 ](./media/add-form/view-text.png)

    폼에 변경 내용이 반영됩니다.

    ![읽기 전용 번호](./media/add-form/read-only.png)  

## <a name="edit-form-only-save-changes"></a>(폼 편집에만) 변경 내용 저장
1. 왼쪽 창에서 폼을 선택한 다음, 줄임표(...)를 클릭하거나 탭합니다.

   ![폼 선택](./media/add-form/select-form.png)

2. **이름 바꾸기**를 클릭하거나 탭한 다음, 폼의 이름을 **EditForm**으로 바꿉니다.

3. **[단추](controls/control-button.md)** 컨트롤을 추가하고 **[Text](controls/properties-core.md)** 속성을 **저장**로 설정합니다.

    ![저장 단추 추가](./media/add-form/save-button.png)  

4. **저장** 단추의 **[OnSelect](controls/properties-core.md)** 속성을 다음 수식으로 설정합니다.

   **SubmitForm(EditForm)**

5. 오른쪽 위 모서리 근처에 있는 재생 단추를 선택하여 미리 보기 모드를 엽니다(또는 F5 키 누름).

    ![미리 보기 모드 열기](./media/add-form/open-preview.png)

6. 제품의 이름을 변경한 다음, 만든 **저장** 단추를 클릭하거나 탭합니다.

    **[SubmitForm](functions/function-form.md)** 함수는 폼을 구성한 데이터 원본에 변경 내용을 저장합니다.

7. (선택 사항) 미리 보기를 닫으려면 닫기 아이콘을 선택합니다(또는 Esc 키 누름).

    ![미리 보기 닫기](./media/add-form/close-preview.png)

## <a name="next-steps"></a>다음 단계
[폼](working-with-forms.md), 및 [수식](working-with-formulas.md)을 사용한 작업에 대한 자세한 내용을 알아봅니다.
