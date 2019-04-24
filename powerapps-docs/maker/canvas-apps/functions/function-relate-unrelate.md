---
title: 연관 및 함수를 연관 해제할 | Microsoft Docs
description: 참조 된 관계에 대 한 구문과 예를 들어, 정보 및 PowerApps에서 함수를 연관 해제
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/22/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4b2c6b9518e987ef17f2ff2b50987568c8a0b69f
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61527527"
---
# <a name="relate-and-unrelate-functions-in-powerapps"></a>PowerApps에서 함수의 연결을 해제와 관련 된

연결 및에 일 대 다 또는 다 대 다 관계를 통해 두 엔터티 레코드의 연결을 해제 합니다.

## <a name="description"></a>설명

합니다 **관련** 함수에서 Common Data Service에 일 대 다 또는 다 대 다 관계를 통해 두 개의 레코드를 연결 합니다. 합니다 **Unrelate** 함수는 프로세스를 반대로 하 고 링크를 제거 합니다.

1 대 다 관계에 대 한 많은 엔터티에 외래 키 필드 한 엔터티의 레코드를 가리키는 **관련** 한 엔터티의 특정 레코드를 가리키도록이 필드를 설정 하는 동안 **Unrelate** 이 필드를 설정 *빈*합니다. 필드가 이미 설정 되어 있으면 시기 **관련** 는 호출 기존 링크가 새 링크를 위해 손실 됩니다. 합니다. 사용 하 여이 필드를 설정할 수도 있습니다는 [ **패치** ](function-patch.md) 함수 또는 **[편집 양식](../controls/control-form-detail.md)** ; 사용 하지 않고는 **관련**  함수입니다.

다 대 다 관계에 대 한 레코드를 연결 하는 시스템은 숨겨진된 조인 테이블을 유지 합니다. 이 조인 테이블을 직접 액세스할 수 없습니다. 수-일대다 프로젝션 통해서만 읽고 통해 설정 합니다 **관련** 하 고 **Unrelate** 함수입니다. 모두 관련된 엔터티에 외래 키를 있습니다.

첫 번째 인수에 지정 된 엔터티에 대 한 데이터 변경 내용을 반영 하도록 새로 고칠 수는 있지만 두 번째 인수에 지정 된 엔터티에 대 한 데이터가 없습니다. 사용 하 여 새로 고칠 데이터 수동으로 해야 합니다 **[새로 고침](function-refresh.md)** 작업의 결과 표시 하려면 함수.

이러한 함수를 되지 만들거나 레코드를 삭제 합니다. 이러한만 연결 하거나 이미 존재 하는 두 레코드의 연결을 해제 합니다.

이러한 함수를 사용할 수 있습니다 에서만 [동작 수식](../working-with-formulas-in-depth.md)합니다.

> [!NOTE]
> 이러한 함수는 미리 보기 기능을 일부 이며 해당 동작은 경우에만 사용할 수는 **관계형 데이터, 옵션 집합 및 CDS에 대 한 기타 새로운 기능** 기능이 사용 하도록 설정 합니다. 새 앱에 대해 기본적으로 사용 하도록 설정 되는 응용 프로그램 수준 설정입니다. 이 기능 스위치를 찾기 위해 엽니다는 **파일** 메뉴를 선택 **앱 설정**를 선택한 후 **고급 설정**. 여러분의 피드백은 매우 소중합니다. [PowerApps 커뮤니티 포럼](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To)에 의견을 남겨주세요.

## <a name="syntax"></a>구문

**Relate**( *Entity1RelatedTable*, *Entity2Record* )

* *Entity1RelatedTable* -필수 항목입니다. 레코드에 대해 *Entity1*, 목차 *Entity2* 에 일 대 다 또는 다 대 다 관계를 통해 관련 레코드.
* *Entity2Record* -필수 항목입니다. 합니다 *Entity2* 레코드 관계에 추가 합니다.

**Unrelate**( *Entity1RelatedTable*, *Entity2Record* )

* *Entity1RelatedTable* -필수 항목입니다. 레코드에 대해 *Entity1*, 목차 *Entity2* 에 일 대 다 또는 다 대 다 관계를 통해 관련 레코드.
* *Entity2Record* -필수 항목입니다. 합니다 *Entity2* 관계에서 제거할 레코드입니다.

## <a name="examples"></a>예

고려해 야는 **제품** 에 표시 된 대로 다음과 같은 관계를 사용 하 여 엔터티를 [PowerApps 포털 엔터티 뷰어](../../common-data-service/create-edit-entities-portal.md):

| 관계 표시 이름 | 관련된 엔터티 | 관계 유형 |
| --- | --- |
| 제품 예약 | 예약 | 1 대 다 |
| 제품 &harr; 연락처 | 연락처 | 다 대 다 |

**제품** 하 고 **예약** 1 대 다를 통해 관련 된 관계입니다.  첫 번째 레코드를 연결 하는 **예약** 의 첫 번째 레코드를 사용 하 여 엔터티를 **제품** 엔터티:

`Relate( First( Products ).Reservations, First( Reservations ) )`

이러한 레코드 간의 관계를 제거 합니다.

`Unrelate( First( Products ).Reservations, First( Reservations ) )`

순식간에 만든 또는 제거 하거나 레코드를 레코드 간의 관계만 수정 되었습니다.

**제품** 하 고 **연락처** 다 대 다를 통해 관련 된 관계입니다.  첫 번째 레코드를 연결 하는 **연락처** 의 첫 번째 레코드를 사용 하 여 엔터티를 **제품** 엔터티:

`Relate( First( Products ).Contacts, First( Contacts ) )`

으로 다 대 다 관계는 대칭도 수행할 수 있는이 반대 방향에서:

`Relate( First( Contacts ).Products, First( Products ) )`

이러한 레코드 간의 관계를 제거 합니다.

`Unrelate( First( Products ).Contacts, First( Contacts ) )`

또는:

`Unrelate( First( Contacts ).Products, First( Products ) )`

다음과 같이 해당 연습을 사용 하 여 앱을 사용 하 여 이러한 엔터티에 대 한 이러한 작업 정확 하 게 않습니다 **갤러리** 하 고 **콤보 상자** 관련된 레코드를 선택 하는 컨트롤입니다.

이 예제에서는 사용자 환경에 설치 되 고 샘플 데이터에 따라 달라 집니다. 어느 [샘플 데이터를 포함 하 여 평가판 환경을 만들](../../model-driven-apps/overview-model-driven-samples.md#get-sample-apps) 또는 [기존 환경에 샘플 데이터 추가](../../model-driven-apps/overview-model-driven-samples.md#install-or-uninstall-sample-data)합니다.

### <a name="one-to-many"></a>1 대 다

#### <a name="relate-function"></a>**관련** 함수

보기 및 제품과 관련 된 예약을 다시 할당 하기 위한 간단한 앱을 먼저 만들어야 합니다.

1. 만들기는 [비어 있는 상태에서 태블릿 앱](../data-platform-create-app-scratch.md)합니다.

1. **보기**에서 **데이터 원본**을 선택합니다.

1. 에 **데이터** 창 **데이터 원본 추가** > **Common Data Service** > **제품**  >  **연결**합니다.  

    제품 엔터티가 로드 위의 샘플 데이터의 일부입니다.

     ![데이터 원본으로 제품 엔터티를 추가 합니다.](media/function-relate-unrelate/products-connect.png)

1. 에 **삽입** 탭에서 추가 빈 세로 **[갤러리](../controls/control-gallery.md)** 제어 합니다.

1. 방금 추가한 컨트롤 라고 보장 **Gallery1**, 이동 고 화면 왼쪽에 맞게 크기를 조정 합니다.

1. 에 **속성** 탭에서 **Gallery1**의 **항목** 속성을 **제품** 고 **레이아웃** 를 **이미지 및 제목**합니다.

    ![ProductsGallery 구성](media/function-relate-unrelate/products-gallery.png)

1. **Gallery1**, 되어 있는지 확인 합니다 **레이블** 컨트롤 이름이 **Title1**를 설정한 후 해당 **텍스트** 속성을  **ThisItem.Name**합니다.

    ![Gallery1에 레이블을 구성합니다](media/function-relate-unrelate/products-title.png)

1. 화면에 다음 항목을 삽입 하지 않으려면 선택 **Gallery1**합니다.  추가할 두 번째 빈 세로 **갤러리** 컨트롤을 확인 하 라고 하는 **Gallery2**합니다.

    **Gallery2** 사용자가 어떤 제품에 대 한 예약 알아보겠습니다 **Gallery1**합니다.

1. 이동 및 크기 조정 **Gallery2** 화면의 오른쪽 위 사분면에 맞게 합니다.

1. (선택 사항) 파란색 추가 **레이블을** 컨트롤 위의 **Gallery2**처럼 다음 그림을 보여 줍니다.

1. 수식 입력줄에서 설정 합니다 **항목** 속성을 **Gallery2** 에 **Gallery1.Selected.Reservations**합니다.

    ![Gallery2 항목 구성](media/function-relate-unrelate/reservations-gallery.png)

1. 속성 창에서 설정할 **Gallery2**의 **레이아웃** 하 **Title**합니다.

    ![Gallery2 레이아웃을 구성 합니다.](media/function-relate-unrelate/reservations-gallery-right.png)

1. **Gallery2**, 추가 **[콤보 상자](../controls/control-combo-box.md)** 제어, 이름이 있는지 확인 **ComboBox1**를 이동 다음 및 차단을 방지 하도록 크기를 조정 합니다 다른 컨트롤과 **Gallery2**합니다.

1. 에 **속성** 탭에서 **ComboBox1**의 **항목** 속성을 **제품**합니다.

    ![제품에 Items 속성 설정](media/function-relate-unrelate/reservations-combo-right.png)

1. 아래로 스크롤하여 합니다 **속성** 탭 및 설정 **ComboBox1**의 **다중 선택을 허용** 속성을 **해제**합니다.

    ![Off로 다중 선택 허용 하는 설정](media/function-relate-unrelate/reservations-singleselect-right.png)

1. 수식 입력줄에 설정할 **ComboBox1**의 **DefaultSelectedItems** 속성을 **ThisItem.' 제품 예약 '** 합니다.

    ![DefaultSelectedItems ReserveCombo에 대 한 설정](media/function-relate-unrelate/reservations-combo.png)

1. **Gallery2**설정 **NextArrow2**의 **OnSelect** 속성을 다음이 수식:

    ```powerapps-dot
    Relate( ComboBox1.Selected.Reservations, ThisItem )
    ```

    현재 예약 변경에서 사용자가 선택한 제품에는 사용자가이 아이콘을 선택 하면 **ComboBox1**합니다.

    ![NextArrow2 구성](media/function-relate-unrelate/reservations-relate.png)

1. F5 키를 눌러 미리 보기 모드에서 앱을 테스트 합니다.

이 앱을 사용 하 여 사용자는 다른 제품 중 하나에서 예약을 이동할 수입니다. 제품 중 하나에서 예약을 사용자의 다른 제품을 선택할 수 **ComboBox1** 선택한 후 **NextArrow2** 해당 예약을 변경 합니다.

![일대다 앱에서 관련 함수를 보여 줍니다.](media/function-relate-unrelate/reservations-reassign.gif)

#### <a name="unrelate-function"></a>**연결을 해제** 함수

이 시점에서 다른 한 레코드에서 관계를 이동할 수 있습니다 하지만 관계를 완전히 제거할 수 없습니다. 사용할 수는 **Unrelate** 함수를 예약 레코드를 모든 제품에서 연결을 끊습니다.

1. **보기**에서 **데이터 원본**을 선택합니다.

1. 에 **데이터** 창 **데이터 원본 추가** > **Common Data Service** > **예약**  >  **연결**합니다.

1. **Gallery2**로 설정 된 **OnSelect** 수식 **NextArrow2** 을 다음이 수식으로:

    ```powerapps-dot
    If( IsBlank( ComboBox1.Selected ),
        Unrelate( Gallery1.Selected.Reservations, ThisItem ),
        Relate( ComboBox1.Selected.Reservations, ThisItem )
    );
    Refresh( Reservations )
    ```
    ![올바른 아이콘 구성](media/function-relate-unrelate/reservations-relate-unrelate.png)

1. 복사본 **Gallery2** 를 선택 하 고 Ctrl + C를 눌러 클립보드

1. 중복을 붙여 넣습니다 **Gallery2** 동일한 Ctrl + V를 눌러 화면 및 다음 화면의 오른쪽 아래 사분면으로 이동 합니다.

1. (선택 사항) 위의 레이블을 추가 하는 경우 **Gallery2**를 해당 레이블에 대해 이전 두 단계를 반복 합니다.

1. 중복 되도록 **Gallery2** 이름은 **Gallery2_1**를 설정한 후 해당 **항목** 속성을 다음이 수식:

    ```powerapps-dot
    Filter( Reservations, IsBlank( 'Product Reservation' ) )
    ```

    위임 경고가 표시 되지만이 예제의 데이터의 작은 크기를 사용 하 여 중요 하지 않습니다.

    ![Gallery2_1의 Items 속성 설정](media/function-relate-unrelate/reservations-lost.png)

이러한 변경으로 사용자의 선택을 취소할 수 **ComboBox1** 해당 제품을 예약 하지 않은 경우 연락처입니다. 제품을 예약 하지 않은 대화 상대의 나타나지 **Gallery2_1** 사용자 제품에 각 연락처를 할당할 수 있습니다.

   ![일대다 앱의 함수에서에서의 연결을 해제 및 관계를 보여 줍니다.](media/function-relate-unrelate/reservations-lostandfound.gif)

### <a name="many-to-many"></a>다 대 다

#### <a name="create-a-many-to-many-relationship"></a>다 대 다 관계 만들기

샘플 데이터를 다 대 다 관계를 포함 하지 않습니다 하지만 제품 엔터티와 연락처 간의 하나를 만들어야 합니다. 사용자는 각 제품 둘 이상의 연락처 및 둘 이상의 제품에 각 연락처에 연결 될 수 있습니다.

1. [이 페이지](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)를 선택 **데이터** 왼쪽 탐색 모음에서 선택한 후 **엔터티**합니다.

    ![엔터티 목록 열기](media/function-relate-unrelate/entity-list.png)

1. 모든 엔터티를 포함 하도록 엔터티에 필터를 변경 합니다.

    기본적으로 샘플 엔터티 표시 되지 않습니다.

    ![엔터티에 필터를 제거 합니다.](media/function-relate-unrelate/entity-all.png)

1. 오픈 아래로 스크롤하여 합니다 **제품** 엔터티와 선택 **관계**합니다.

    ![Product 엔터티에 대 한 관계 탭](media/function-relate-unrelate/entity-relationships.png)

1. 선택 **관계 추가** > **다 대 다**합니다.

    ![다 대 다 관계 추가](media/function-relate-unrelate/entity-manytomany.png)

1. 선택 된 **연락처** 관계에 대 한 엔터티.

    ![연락처 엔터티를 선택 합니다.](media/function-relate-unrelate/entity-contact.png)

1. 선택 **수행** > **엔터티 저장**합니다.

    ![제품 엔터티에 대 한 관계의 목록](media/function-relate-unrelate/entity-done.png)

#### <a name="relate-and-unrelate-contacts-with-one-or-more-products"></a>서로 연결 하 고 하나 이상의 제품을 사용 하 여 연락처의 연결을 해제합니다

이 항목의 앞부분에서 만든과 유사한 다른 앱을 만들어야 하지만 새 앱에는 다 대 다 관계를 제공 합니다. 각 연락처 하나만 대신 여러 제품을 예약할 수 있습니다.

1. 태블릿에 대 한 새 앱을 만듭니다 **Gallery1** 으로 [첫 번째 절차](#one-to-many) 이 항목에서 설명 합니다.

1. 다른 빈 세로 추가 **갤러리** 컨트롤을 확인 하 라는 **Gallery2**, 다음 화면의 오른쪽 위 모서리에 이동 합니다.

    이 항목의 뒷부분에 나오는 추가 된 **콤보 상자** 제어할 **Gallery2**합니다.

1. 수식 입력줄에 설정할 **Gallery2**의 **항목** 속성을 **Gallery1.Selected.Contacts**합니다.

    ![ContactsGallery 구성](media/function-relate-unrelate/contacts-gallery.png)

1. 에 **속성** 탭에서 **레이아웃** 하 **이미지 및 제목**합니다.

    ![ContactsGallery 구성](media/function-relate-unrelate/contacts-gallery-right.png)

1. **Gallery2**, 되어 있는지 확인 합니다 **레이블** 컨트롤 이름이 **Title2**를 설정한 후 해당 **텍스트** 속성을  **ThisItem. '전체 이름'** 합니다.

    이 절차를 완료 하는 제품에 연락처를 할당할 때까지 해당 컨트롤에 텍스트가 표시 됩니다.

    ![연락처 이름 표시](media/function-relate-unrelate/contacts-title.png)

1. 삭제할 **NextArrow2**, 삽입을 **취소** 아이콘을 이름이 있는지 확인 하 고 **icon1**.

1. 설정 된 **취소할** 아이콘 **OnSelect** 속성을 다음이 수식: 

    ```powerapps-dot
    Unrelate( Gallery1.Selected.Contacts, ThisItem )
    ```

    ![구성 취소 아이콘](media/function-relate-unrelate/contacts-unrelate.png)

1. **보기**에서 **데이터 원본**을 선택합니다.

1. 에 **데이터** 창 **데이터 원본 추가** > **Common Data Service** > **연락처**  >  **연결**합니다.

1. 아래 **Gallery2**, 추가 **콤보 상자** 제어, 이름이 있는지 확인 **ComboBox1**를 설정한 후 해당 **항목** 속성**연락처**합니다.

    ![콤보 상자 항목 속성 구성](media/function-relate-unrelate/contacts-combo.png)

1. 에 **속성** 탭에서 **다중 선택을 허용** 하 **해제**합니다.

    ![콤보 상자 레이아웃 속성 구성](media/function-relate-unrelate/contacts-combo-right.png)

1. 삽입 된 **추가** 아이콘을 설정 하 고 해당 **OnSelect** 속성을 다음이 수식: 

    ```powerapps-dot
    Relate( Gallery1.Selected.Contacts, ComboBox1.Selected )
    ```

    ![구성 추가 아이콘](media/function-relate-unrelate/contacts-relate.png)

이 앱을 사용 하 여 사용자가 이제 자유롭게 관련를 일련의 연락처에는 각 제품의 연결을 해제 합니다.

- 제품에 연락처를 추가 하려면 화면 맨 아래에 있는 콤보 상자에서 연락처를 선택 하 고 다음을 선택 합니다 **추가** 아이콘입니다.
- 제품에서 연락처를 제거 하려면 선택 합니다 **취소** 해당 연락처에 대 한 아이콘입니다.

    다를 달리 다 대 다 관계를 사용 하면 여러 제품을 사용 하 여 동일한 연락처를 연결할 수 있습니다.

![다 대 다 앱의 함수에서에서의 연결을 해제 및 관계를 보여 줍니다.](media/function-relate-unrelate/contacts-relate-unrelate.gif)

#### <a name="in-reverse-relate-and-unrelate-products-with-multiple-contacts"></a>반대로:와 관련 된 여러 연락처가 있는 제품의 연결을 해제

다 대 다 관계는 대칭적입니다. 연락처에 제품을 추가 하 고 다음 어느 쪽에서 관계 모양을 표시할 두 개의 화면 간에 대칭 이동 하도록 예제를 확장할 수 있습니다.

1. 설정 합니다 **OnVisible** 속성을 **Screen1** 에 **(제품)를 새로 고침**합니다.

    1 대 다 또는 다 대 다 관계의 첫 번째 인수 엔터티의 데이터에만 업데이트 하는 경우는 **관련** 또는 **Unrelate** 호출 새로 고쳐집니다. 두 번째는이 앱의 화면 간의 대칭 이동 하려는 경우에 수동으로 새로 고칠 수 없습니다.

    ![새로 고침 함수 OnVisible 속성을 설정 합니다.](media/function-relate-unrelate/contacts-refresh.png)

1. 중복 **Screen1**합니다.

    중복 이름은 **Screen1_1** 연락처 쪽에서 관계를 확인 하기 위한 기초를 형성 하 고 있습니다.

    ![화면 복제](media/function-relate-unrelate/contacts-duplicate.png)

1. 역방향 뷰를 만들려면의 컨트롤에는 이러한 수식을 변경할 **Screen1_1**:

    - Screen1_1.OnVisible = `Refresh( Contacts )`
    - Gallery1_1.Items = `Contacts`
    - Title1_1.Text = `ThisItem.'Full Name'`
    - Label1_1.Text = `"Selected Contact Products"`
    - Gallery2_1.Items = `Gallery1_1.Selected.Products`
    - Title2_1.Text = `ThisItem.Name`
    - Icon1_1.OnSelect = `Unrelate( Gallery1_1.Selected.Products, ThisItem )`
    - ComboBox1_1.Items = `Products`
    - Icon2_1.OnSelect = `Relate( Gallery1_1.Selected.Products, ComboBox1_1.Selected )`

    결과 이전 화면 매우 유사 하지만 관계를 수반 합니다 **연락처** 쪽입니다.

    ![연락처를 사용 하 여 시작 하는 다 대 다 관계 표시](media/function-relate-unrelate/reverse-screen.png)

1. 삽입을 **화살표 스핀** 아이콘 집합과 해당 **OnSelect** 속성을 **Navigate (Screen1, None)** 합니다.  동일한 작업을 수행할 **Screen1** 수식을 사용 하 여 **Navigate (Screen1_1, None)** 합니다.

    ![화면 간 탐색 추가](media/function-relate-unrelate/reverse-navigate.png)

이 새 화면을 사용 하 여 사용자 수 제품에 연락처를 추가 다음 연락처의 보기로 대칭 이동 및 연결된 된 제품을 참조 하세요. 관계는 대칭 및 두 개의 화면 간에 공유 됩니다.

![어느 한 쪽에서 다 대 다 관계를 보여 줍니다.](media/function-relate-unrelate/contacts-reverse.gif)
