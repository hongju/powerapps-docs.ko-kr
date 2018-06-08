---
title: 조회 필드를 사용하여 엔터티 간 관계 만들기 | Microsoft Docs
description: 조회 필드를 사용하여 PowerApps에서 엔터티 간 관계를 만드는 방법에 대한 단계별 지침입니다.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: f1952c2349eb54f2c6348f5abc4dee9a4645348a
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168438"
---
# <a name="create-a-relationship-between-entities"></a>엔터티 간 관계 만들기
한 엔터티의 데이터는 다른 엔터티의 데이터와 자주 관련됩니다. 예를 들어, **Teachers** 엔터티 및 **Class** 엔터티가 있을 수 있으며, **Class** 엔터티에는 클래스를 가르치는 교사를 표시하는 **Teachers** 엔터티에 대한 조회 관계가 있을 수 있습니다. 조회 필드를 사용하여 **Teachers** 엔터티의 데이터를 표시할 수 있습니다. 이는 일반적으로 조회 필드라고 합니다.

## <a name="define-a-relationship"></a>관계 정의
다른 엔터티(또는 엔터티 자체) 간에 여러 형식의 관계를 만들 수 있습니다. 각 엔터티는 둘 이상의 엔터티와 관계가 있을 수 있으며, 각 엔터티는 다른 엔터티에 대해 둘 이상의 관계가 있을 수 있습니다. 몇 가지 일반적인 관계 형식은 다음과 같습니다.

* **다 대 일** - 이 형식의 관계에서 엔터티 A의 각 레코드는 엔터티에 B의 둘 이상의 레코드와 일치할 수 있지만, 엔터티 B의 각 레코드는 엔터티 A의 하나의 레코드와 일치할 수 있습니다. 예를 들어 클래스에는 단일 클래스룸이 있습니다. 이는 관계의 가장 일반적인 형식이며 **조회 필드**로 필드 목록에 표시됩니다.
* **일 대 다**: 이 형식의 관계에서, 엔터티 B의 각 레코드는 엔터티에 A의 둘 이상의 레코드와 일치할 수 있지만, 엔터티 A의 각 레코드는 엔터티 B의 하나의 레코드와만 일치할 수 있습니다. 예를 들어 단일 교사는 많은 클래스를 가르칩니다.
* **다 대 다** - 이 형식의 관계에서 엔터티 A의 각 레코드는 엔터티 B의 둘 이상의 레코드와 일치하거나 또는 그 반대일 수 있습니다. 예를 들어 학생이 많은 클래스에 참석했고 각 클래스에는 여러 학생이 있을 수 있습니다.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>조회 필드 추가(다 대 일 관계)

엔터티를 조회 관계를 추가하려면 **관계** 탭 아래에서 관계를 만들고 관계를 만들려는 엔터티를 지정합니다.

1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 기존 엔터티를 클릭하거나 탭하거나 [새 엔터티를 만듭니다](data-platform-create-entity.md).

3. **관계**를 클릭합니다.

4. **관계 추가**를 클릭하면, 관계를 만들려는 엔터티를 선택하기 위한 새 패널이 열립니다. **관련 엔터티** 드롭다운에서 엔터티를 선택합니다.

    ![다 대 일 관계](./media/data-platform-cds-newrelationship/manytoone-1.png "다 대 일 관계")

5. 엔터티를 선택한 후 조회 필드는 기본 엔터티에 표시되고, 엔터티 이름으로 기본값이 설정되지만(이 예제에서는 Classroom) 필요한 경우 변경할 수 있습니다.

    ![다 대 일 관계](./media/data-platform-cds-newrelationship/manytoone-2.png "다 대 일 관계")

6. **완료**를 클릭하여 엔터티에 관계를 추가한 다음, **엔터티 저장**을 클릭합니다.

    ![다 대 일 관계](./media/data-platform-cds-newrelationship/manytoone-3.png "다 대 일 관계")

## <a name="add-a-one-to-many-relationship"></a>일 대 다 관계 추가

일 대 다 관계를 추가하려면 **관계** 탭 아래에서 관계를 만들고 관계를 만들려는 엔터티를 지정합니다.

1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 기존 엔터티를 클릭하거나 탭하거나 [새 엔터티를 만듭니다](data-platform-create-entity.md).

3. **관계**를 클릭합니다.

4. 아래쪽 화살표를 **관계 추가**의 오른쪽으로 클릭하면, 두 가지 유형의 관계를 선택할 수 있습니다. **일 대 다**를 클릭하면, 관계를 만들려는 엔터티를 선택하기 위한 새 패널이 열립니다. **관련 엔터티** 드롭다운에서 엔터티를 선택합니다.

    ![일 대 다 관계](./media/data-platform-cds-newrelationship/onetomany-1.png "일 대 다 관계")

5. 엔터티를 선택한 후 조회 필드는 기본 엔터티에 표시되고, 엔터티 이름으로 기본값이 설정되지만(이 예제에서는 Class) 필요한 경우 변경할 수 있습니다.

    > [!NOTE]
    > 일 대 다 관계의 경우 조회 필드는 현재 선택한 엔터티가 아닌 관련 엔터티에 생성됩니다. 현재 엔터티를 조회해야 하는 경우 다 대 일 관계를 만드세요.

    ![일 대 다 관계](./media/data-platform-cds-newrelationship/onetomany-2.png "일 대 다 관계")

6. **완료**를 클릭하여 엔터티에 관계를 추가한 다음, **엔터티 저장**을 클릭합니다.

    ![일 대 다 관계](./media/data-platform-cds-newrelationship/onetomany-3.png "일 대 다 관계")

## <a name="add-a-many-to-many-relationship"></a>다 대 다 관계 추가

현재 고급 메뉴를 통해서만 사용 가능합니다. PowerApps 홈 페이지에서 왼쪽 메뉴의 "고급"을 클릭합니다. 관계를 만드는 방법에 대한 자세한 내용은 [N:N 관계 만들기](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships)를 참조하세요.

## <a name="use-a-lookup-field-in-an-app"></a>앱에서 조회 필드 사용
조회 필드를 포함하는 엔터티에서 [자동으로 앱을 만드는](../canvas-apps/data-platform-create-app.md) 경우, 엔터티의 **기본 이름** 필드에서 데이터를 포함하는 **드롭다운** 컨트롤로 표시됩니다.

## <a name="next-steps"></a>다음 단계
* [Common Data Service 데이터베이스를 사용하여 앱 생성](../canvas-apps/data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](../canvas-apps/data-platform-create-app-scratch.md)

