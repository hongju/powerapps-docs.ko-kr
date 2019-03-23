---
title: 캔버스 앱에서 종속 드롭 다운 목록 만들기 | Microsoft Docs
description: PowerApps에서 캔버스 앱에서 다른 드롭다운 목록을 필터링 하는 드롭다운 목록을 만듭니다.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e00c81f25de9a764e8f6d963ff94f3c0ffe052a2
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58357256"
---
# <a name="create-dependent-drop-down-lists-in-a-canvas-app"></a>캔버스 앱에서 종속 드롭 다운 목록 만들기

종속 (또는 연속) 드롭 다운 목록을 만들면 사용자 목록을 다른 목록의 필터 옵션에 옵션을 선택 합니다. 대부분의 조직에서는 종속 목록 양식을 더 효율적으로 작성할 수 있도록 만듭니다. 예를 들어, 사용자 국가 또는 도시 목록을 필터링 할 지역을 선택할 수 또는 사용자 코드만 해당 범주에 표시할 범주를 선택할 수 있습니다.

모범 사례로, 사용자가 앱을 사용 하 여 업데이트 하는 데이터 원본에서 별도의 목록 (예: 국가/지역 및 도시) "부모" 및 "자식"의 값에 대 한 데이터 원본을 만듭니다. 이 방법을 사용 하는 경우 둘 이상의 앱에서 동일한 부모 및 자식 데이터를 사용할 수 있습니다 하 고 앱을 사용 하는 앱을 다시 게시 하지 않고도 해당 데이터를 업데이트할 수 있습니다. 컬렉션 또는 정적 데이터를 사용 하 여 동일한 결과 수행할 수 있지만 엔터프라이즈 시나리오에 권장 되지 않습니다.

이 항목의 시나리오의 경우 저장에 대 한 직원 제출 문제는 **인시던트** 양식을 통해 목록입니다. 뿐만 아니라 저장소의 위치를 지정 하는 직원 인시던트가 발생 한 뿐만 아니라 해당 위치 내의 부서입니다. 모든 위치에서 동일한 부서를 따라서에 **위치** 목록 하면 직원이 부서는 부서 없는 위치를 지정할 수 없습니다.

이 항목에서는 SharePoint 목록을 데이터 원본으로 사용 하 여 있지만 모든 테이블 형식 데이터 원본에 동일한 방식으로 작동 합니다.

## <a name="create-data-sources"></a>데이터 원본 만들기

A **위치** 목록에서는 각 위치에서 부서를 보여 줍니다.

| Location | Department |
|----------------|------------------|
| Eganville      | 빵집           |
| Eganville      | 배달             |
| Eganville      | 생성          |
| Renfrew        | 빵집           |
| Renfrew        | 배달             |
| Renfrew        | 생성          |
| Renfrew        | Pharmacy         |
| Renfrew        | 꽃           |
| Pembroke       | 빵집           |
| Pembroke       | 배달             |
| Pembroke       | 생성          |
| Pembroke       | 꽃           |

**인시던트** 연락처 정보 및 각 인시던트에 대 한 정보 목록을 보여 줍니다. 으로 날짜 열을 만듭니다는 **날짜** 열에 있지만 다른 열을 만들 **한 줄 텍스트** 구성을 단순화 하 고 방지 하기 위해 열 [위임](./delegation-overview.md) 에서 경고 PowerApps입니다.

| 첫 번째 이름 | 성 | 전화 번호     | Location | Department | 설명       | Date      |
|------------|-----------|------------------|----------------|------------|-------------------------|-----------|
| Tonya       | Cortez   | (206) 555 - 1022 | Eganville      | 생성    | 문제가 했습니다...   | 2/12/2019 |
| Moses     | Laflamme     | (425) 555 - 1044 | Renfrew        | 꽃     | 문제를 경험 했습니다... | 2/13/2019 |

기본적으로 사용자 지정 SharePoint 목록에 포함 된 **제목** 열 이름을 바꾸거나 제거할 수 없습니다 및 목록에서 항목을 저장 하기 전에 데이터를 포함 해야 합니다. 데이터를 필요 하지 않습니다 있도록 열을 구성 합니다.

1. 오른쪽 위 모서리에서 기어 아이콘을 선택 하 고 선택한 **설정을 나열 합니다.** 합니다.
1. 에 **설정을** 페이지에서 **Title** 열 목록에서.
1. 아래 **이 열이 정보가 필요**를 선택 **No**합니다.

무시 해도 해당 변경 후 합니다 **제목** 하거나 열 수 있습니다 [제거](https://support.office.com/article/edit-a-list-column-in-sharepoint-online-77130c2e-76d1-4f80-af8b-4c6f47b264b8) 다른 열을 하나 이상 있으면 기본 보기에서.

## <a name="open-the-form"></a>폼을 엽니다

1. 엽니다는 **인시던트** 목록 및 선택한 **PowerApps** > **양식 사용자 지정**합니다.

    > [!div class="mx-imgBorder"]
    > ![인시던트 목록 열기를 선택한 다음 PowerApps > 양식 사용자 지정 합니다. ](./media/dependent-drop-down-lists/open-form.png "인시던트 목록 열기를 선택한 다음 PowerApps > 양식 사용자 지정 합니다.")

    PowerApps Studio 기본 양식을 사용 하 여 브라우저 탭이 열립니다.

1. (선택 사항) 에 **필드** 창 위로 마우스를 가져가고 합니다 **제목** 필드에서 나타나고 다음을 선택 하는 줄임표 (...)를 선택 **제거**합니다.

    닫은 경우 합니다 **필드** 창에서 열 수 있습니다 다시 선택 하 여 **SharePointForm1** 왼쪽된 탐색 모음과 선택한 다음, **필드를 편집** 합니다 에**속성** 오른쪽 창의 탭 합니다.

1. (선택 사항) 제거 하는 이전 단계를 반복 합니다 **첨부 파일** 폼에서 필드입니다.

    추가한 필드만 된 폼이 나타납니다.

    > [!div class="mx-imgBorder"]
    > ![제목 및 첨부 파일 필드가 없는 형성](./media/dependent-drop-down-lists/default-form.png)

## <a name="replace-the-controls"></a>컨트롤 대체

1. 에 **필드** 창 옆에 있는 아래쪽 화살표를 선택 **위치**합니다.

    닫은 경우 합니다 **필드** 창에서 열 수 있습니다 다시 선택 하 여 **SharePointForm1** 왼쪽된 탐색 모음과 선택한 다음, **필드를 편집** 합니다 에**속성** 오른쪽 창의 탭 합니다.

1. 엽니다는 **컨트롤 형식과** 목록 및 선택한 **허용 되는 값**합니다.

    > [!div class="mx-imgBorder"]
    > ![허용 되는 값](./media/dependent-drop-down-lists/change-control.png)

    입력된 메커니즘을 변경 하는 **드롭다운** 제어 합니다.

1. 이러한 단계를 반복 합니다 **부서** 카드.

## <a name="add-the-locations-list"></a>위치 목록에 추가

1. 선택 **뷰** > **데이터 원본** > **데이터 원본 추가**합니다.

1. 또는 SharePoint 연결을 만들려면 선택한 다음이 포함 된 사이트를 지정 합니다 **위치** 목록입니다.

1. 목록에 대 한 확인란을 선택 하 고 선택한 **Connect**합니다.

    > [!div class="mx-imgBorder"]
    > ![데이터 창](./media/dependent-drop-down-lists/select-list.png)

    연결 표시 목록 합니다 **인시던트** 목록, 폼 기반, 및 **위치** 목록 위치와 부서 형태로 식별할 수 있습니다.

    > [!div class="mx-imgBorder"]
    > ![SharePoint 데이터 원본](./media/dependent-drop-down-lists/data-sources.png)

## <a name="unlock-the-cards"></a>카드를 잠금 해제

1. 선택 합니다 **위치** 카드를 선택 합니다 **고급** 오른쪽 창에서 탭을 선택 합니다 **속성을 변경 하려면 잠금 해제**합니다.

1. 에 대 한 이전 단계를 반복 합니다 **부서** 카드.

## <a name="rename-the-controls"></a>컨트롤 이름 바꾸기

컨트롤의 이름을 바꾸면 보다 쉽게 식별할 수 있습니다 및 예제는 쉽게 수행할 수 있습니다. 기타 모범 사례를 검색 하려면 다음을 검토 합니다 [코딩 표준 및 지침 백서](https://aka.ms/powerappscanvasguidelines)합니다.

1. 에 **위치** 카드를 선택 합니다 **드롭다운** 컨트롤입니다.

1. 오른쪽 창의 위쪽에 입력 하거나 붙여넣기 하 여 선택한 컨트롤의 이름을 **ddLocation**합니다.

    > [!div class="mx-imgBorder"]
    > ![컨트롤 이름 바꾸기](./media/dependent-drop-down-lists/rename-control.png)

1. 이전 두 단계를 반복 합니다 **부서** 카드의 이름을 바꾸려면 합니다 **드롭다운** 컨트롤을 **ddDepartment**합니다.

## <a name="configure-the-locations"></a>위치를 구성 합니다.

1. 설정 된 **항목** 속성을 **ddlocation** 을 다음이 수식으로:

    `Distinct(Locations, Location)`

1. (선택 사항) Alt 키를 누른 채 엽니다 **ddLocation**는 세 위치 목록에 표시 되는지 확인 합니다.

## <a name="configure-the-departments"></a>부서를 구성 합니다.

1. 선택 **ddDepartment** 한 후에 **속성** 선택 오른쪽 창의 탭 **에 따라 달라 집니다.**

1. 아래 **컨트롤을 부모**, 되도록 **ddLocation** 위 목록에 표시 및 **결과** 아래 목록에 나타납니다.

    > [!NOTE]
    > 문자열에는 데이터 행의 실제 ID에 일치 하지 않으려는 경우 선택 **ID** of **결과**합니다.

1. 아래 **일치 필드**를 선택 **위치** 위쪽 목록에서 선택 **위치** 을 선택 하 고 아래쪽 목록에서 **적용**합니다.

    > [!div class="mx-imgBorder"]
    > ![링크에 따라 달라 집니다.](./media/dependent-drop-down-lists/depends-on.png)

    합니다 **항목** 속성을 **ddDepartment** 이 수식으로 설정 됩니다.

    `Filter(Locations, Location = ddLocation.Selected.Result)`

    항목을 필터링 하는이 수식을 **ddDepartment** 사용자가의 선택에 따라 **ddLocation**합니다. 이러한 구성은 부서 "자식" 목록으로의 "부모" 위치에 대 한 데이터를 반영 하는지 확인 합니다 **위치** SharePoint 목록의 지정 합니다.

1. 에 **속성** 탭의 오른쪽 창에 있는 목록을 연 다음 **값**를 선택한 후 **부서**합니다.

    이 단계에서 옵션에 표시할 텍스트를 설정 합니다 **부서** 열의 합니다 **위치** SharePoint 목록의 합니다.

    > [!div class="mx-imgBorder"]
    > ![부서 값](./media/dependent-drop-down-lists/dept-value.png)

## <a name="test-the-form"></a>형식 테스트

Alt 키를 누른 채로 위치 목록을 열고, 하는 동안에 하나를 선택 부서 목록을 열고 하나를 선택 합니다.

위치와 부서 목록에서 정보를 반영 합니다 **위치** SharePoint 목록.

> [!div class="mx-imgBorder"]
> ![위치 목록, Pembroke,으로 Renfrew에서 선택을 변경를 열고 학부의 목록](./media/dependent-drop-down-lists/dropdowns.gif)

## <a name="save-and-open-the-form-optional"></a>저장 하 고 (선택 사항) 양식을 엽니다

1. 엽니다는 **파일** 메뉴를 선택한 후 **저장할** > **SharePoint에 게시** > **SharePoint에게시**.

1. 왼쪽 위 모퉁이에서 뒤로 화살표를 선택한 다음, **SharePoint로 돌아가기**를 선택합니다.

1. 명령 모음에서 **새로 만들기**를 선택하여 사용자 지정된 양식을 엽니다.

## <a name="faq"></a>FAQ

**데이터가 보이지 않는 경우: 소스 모두 비어 있거나 잘못 된 데이터입니다.**
이러한 방법 중 하나로 컨트롤에 대 한 올바른 필드를 표시 하는 여부를 확인 합니다.

- 드롭다운 목록을 선택한 다음 선택 합니다 **값** 속성에는 **속성** 오른쪽 창의 탭 합니다.

    > [!div class="mx-imgBorder"]
    > ![변경 드롭다운](./media/dependent-drop-down-lists/drop-down-display-field.png)

- 콤보 상자를 선택 하 고의 기본 텍스트를 표시 하려는 필드를 확인 합니다.

    > [!div class="mx-imgBorder"]
    > ![변경 콤보 상자](./media/dependent-drop-down-lists/combo-box-display-field.png)

**내 자식 드롭다운 목록에서 중복 항목을 포함 합니다.**
이 증상을 사용 하 여 때문일 가능성이 큽니다.는 **조회** SharePoint에서 열 또는 **선택** PowerApps의 함수입니다. 중복을 제거 하려면 래핑하는 **Distinct** 제대로 반환 데이터에 대 한 함수입니다. 자세한 정보: [Distinct 함수](functions/function-distinct.md)

## <a name="known-limitations"></a>알려진 제한 사항

이 구성은에서 사용할 수 있습니다 **드롭다운** 컨트롤 뿐만 **콤보 상자** 하 고 **목록 상자** 한 번에 하나의 선택 영역을 사용할 수 있는 컨트롤입니다. 사용할 수 없습니다는 **종속** 다중 선택을 허용 된다면 이러한 컨트롤 중 하나에 대 한 구성 합니다. 옵션 집합을 사용 하 여 공통 데이터 서비스 작업에 대 한이 방법은 권장 되지 않습니다.

합니다 **종속** 정적 데이터 또는 컬렉션 구성을 지원 하지 않습니다. 종속 드롭 다운 목록에서 이러한 소스를 구성 하려면 수식 입력줄에 직접 식을 편집 합니다. 또한 PowerApps는 데이터의 일치 하는 모든 테이블이 없는 SharePoint의 두 선택 필드를 사용 하 여 지원 하지 않습니다 하 고 정의할 수 없습니다 **일치 필드** 이 UI 내에서.