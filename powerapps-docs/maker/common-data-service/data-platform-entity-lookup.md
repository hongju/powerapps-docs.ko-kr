---
title: 조회 필드를 사용하여 엔터티 간 관계 만들기 | Microsoft Docs
description: 조회 필드를 사용하여 PowerApps에서 엔터티 간의 관계를 만드는 방법에 대한 단계별 지침입니다.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 02/21/2019
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-relationship-between-entities"></a>두 엔터티 간 관계 만들기
한 엔터티의 데이터는 다른 엔터티의 데이터와 관련이 있는 경우가 많습니다. 예를 들어 **교사** 엔터티와 **수업** 엔터티가 있을 수 있으며 **수업** 엔터티에는 교사가 수업을 가르치는 교사를 표시하기 위해 **교사** 엔터티와 조회 관계가 있을 수 있습니다. 조회 필드를 사용하여 **교사** 엔터티의 데이터를 표시할 수 있습니다. 일반적으로 조회 필드라고 합니다.

## <a name="define-a-relationship"></a>관계 정의
한 엔터티에서 다른 엔터티로(또는 엔터티와 자체 간) 여러 유형의 관계를 만들 수 있습니다. 각 엔터티는 둘 이상의 엔터티와 관계를 가질 수 있으며 각 엔터티에는 다른 엔터티에 대 둘 이상의 관계가 있을 수 있습니다. 몇 가지 일반적인 관계 유형은 다음과 같습니다.

* **다대일** - 이러한 유형의 관계에서는 엔터티 A의 각 레코드가 엔터티 B에서 둘 이상의 레코드와 일치할 수 있지만 엔터티 B의 각 레코드는 엔터티 A의 레코드 한 개만 일치할 수 있습니다. 예를 들어 수업에는 하나의 교실이 있습니다. 가장 일반적인 관계 유형이며 필드 목록에 **조회 필드**로 표시됩니다.
* **일대다** - 이러한 유형의 관계에서는 엔터티 B의 각 레코드가 엔터티 A에서 둘 이상의 레코드와 일치할 수 있지만 엔터티 A의 각 레코드는 엔터티 B의 레코드 한 개만 일치할 수 있습니다. 예를 들어 하나의 교사가 여러 수업을 가르집니다.
* **다대다** - 이러한 유형의 관계에서 엔터티 A의 각 레코드는 엔터티 B에서 둘 이상의 레코드와 일치할 수 있으며 그 반대의 경우도 마찬가지입니다. 예를 들어 학생들은 많은 수업에 참석하고 각 수업에는 학생이 여러 명이 있을 수 있습니다.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>조회 필드 추가(다대일 관계)

엔터티에 대한 조회 관계를 추가하려면 **관계** 탭 아래에 관계를 작성하고 관계가 생성될 엔터티를 지정합니다.

1. [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 기존 엔터티 클릭 또는 탭 또는 [새 엔터티 만들기](data-platform-create-entity.md)

3. **관계**를 클릭합니다.

4. **관계 추가**를 클릭하면 관계를 만들려는 엔터티를 선택할 수 있는 새 패널이 열립니다. **관련 엔터티** 드롭다운에서 엔터티를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![다대일 관계](./media/data-platform-cds-newrelationship/manytoone-1.png "다대일 관계")

5. 엔터티를 선택한 후 조회 필드는 기본 엔터티에 표시되며, 엔터티 이름(이 예에서는 교실)은 기본적으로 지정되지만 필요한 경우 변경할 수 있습니다.

    ![다대일 관계](./media/data-platform-cds-newrelationship/manytoone-2.png "다대일 관계")

6. **완료**를 클릭하여 엔터티에 관계를 추가한 다음 **엔터티** 저장을 클릭합니다.

    > [!div class="mx-imgBorder"] 
    > ![다대일 관계](./media/data-platform-cds-newrelationship/manytoone-3.png "다대일 관계")

## <a name="add-a-one-to-many-relationship"></a>일대다 관계 추가

일대다 관계를 추가하려면 **관계** 탭 아래에 관계를 작성하고 관계가 생성될 엔터티를 지정합니다.

1. [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 기존 엔터티 클릭 또는 탭 또는 [새 엔터티 만들기](data-platform-create-entity.md)

3. **관계**를 클릭합니다.

4. **관계 추가**의 오른쪽에 있는 아래쪽 화살표를 클릭하면 이 두 유형의 관계를 선택할 수 있습니다. **일대다**를 클릭하면 관계를 만들려는 엔터티를 선택할 수 있는 새 패널이 열립니다. **관련 엔터티** 드롭다운에서 엔터티를 선택합니다.

    ![일대다 관계](./media/data-platform-cds-newrelationship/onetomany-1.png "일대다 관계")

5. 엔터티를 선택한 후 조회 필드는 기본 엔터티에 표시되며, 엔터티 이름(이 예에서는 수업)은 기본적으로 지정되지만 필요한 경우 변경할 수 있습니다.

    > [!NOTE]
    > 일대다 관계의 경우 조회 필드는 현재 선택한 엔터티가 아니라 관련 엔터티에 생성 될 것입니다. 현재 엔터티에 대한 조회가 필요한 경우 다대다 관계를 만듭니다.

    > [!div class="mx-imgBorder"] 
    > ![일대다 관계](./media/data-platform-cds-newrelationship/onetomany-2.png "일대다 관계")

6. **완료**를 클릭하여 엔터티에 관계를 추가한 다음 **엔터티** 저장을 클릭합니다.

    > [!div class="mx-imgBorder"] 
    > ![일대다 관계](./media/data-platform-cds-newrelationship/onetomany-3.png "일대다 관계")

## <a name="add-a-many-to-many-relationship"></a>다대다 관계 추가

현재 이 고급 메뉴를 통해서만 사용할 수 있습니다. PowerApps 홈페이지에서 왼쪽 메뉴의 "고급"을 클릭합니다. 관계를 만드는 방법에 대한 자세한 내용은 [N:N 관계 만들기](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships)를 참조하십시오.

## <a name="use-a-lookup-field-in-an-app"></a>앱에서 조회 필드 사용
조회 필드가 포함된 엔터티에서 [자동으로 앱을 만들면](../canvas-apps/data-platform-create-app.md) 엔터티의 **기본 이름** 필드에 있는 데이터를 포함하는 **드롭다운** 컨트롤로 표시됩니다.

## <a name="add-1n-and-nn-relationships-for-canvas-apps"></a>캔버스 앱에 대해 1:N 및 N:N 관계 추가
**관계** 함수를 사용하여 앱용 Common Data Service(CDS)에서 일대다 또는 다대다 관계를 통해 두 레코드를 연결합니다. 추가 정보: [PowerApps의 관계 및 관계 해제 함수](../canvas-apps/functions/function-relate-unrelate.md)

## <a name="next-steps"></a>다음 단계
* [Common Data Service 데이터베이스를 사용하여 앱 생성](../canvas-apps/data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 새로 만들기](../canvas-apps/data-platform-create-app-scratch.md)

