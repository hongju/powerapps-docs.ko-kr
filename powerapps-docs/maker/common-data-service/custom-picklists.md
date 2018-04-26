---
title: 옵션 집합 만들기를 위한 빠른 시작 | Microsoft Docs
description: 이 빠른 시작에서 옵션 집합을 만듭니다.
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: e31bec33a90a962e302e2bc92c0f2a676ce1a4cc
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-create-an-option-set"></a>빠른 시작: 옵션 집합 만들기

옵션 집합을 통해 다른 응용 프로그램의 선택 목록 또는 선택 필드라고도 하는 데이터 일관성을 유지하기 위해 앱 내의 사용자에 대한 고정된 값의 드롭다운 목록을 포함할 수 있습니다. 엔터티와 마찬가지로, 표준 옵션 집합과 앱 내에서 사용하기 위해 사용자 지정 옵션 집합을 만드는 기능이 있습니다.

두 가지 방법으로 옵션 집합을 만들 수 있습니다. 포털 내의 옵션 집합 목록에서 또는 필드를 만드는 동안 엔터티 내에서 직접 만들 수 있습니다. 엔터티를 만드는 방법에 대한 자세한 내용은 [엔터티 만들기](data-platform-create-entity.md)를 참조하세요.

## <a name="creating-an-option-set-while-adding-a-field"></a>필드를 추가하는 동안 옵션 집합 만들기

1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 기존 엔터티를 클릭하거나 탭하거나 [새 엔터티를 만듭니다](data-platform-create-entity.md).

3. **필드 추가**를 클릭하여 엔터티에 새 필드를 추가합니다.

4. 새 필드 패널에서 필드에 대한 **표시 이름**을 입력하면 **이름**은 자동으로 채워지고 필드에 대한 고유 이름으로 사용됩니다. **표시 이름**은 이 필드를 사용자에게 표시할 때 사용되며, **이름**은 식과 수식에서 앱을 빌드할 때 사용됩니다.

    ![새 필드](./media/data-platform-cds-create-entity/newfieldpanel.png "새 필드 패널")

5. **데이터 형식** 드롭다운을 클릭하고 **옵션 집합** 또는 **다중 선택 옵션 집합**을 선택합니다.

6. **옵션 집합** 드롭다운을 클릭하고 **새 옵션 집합**을 선택합니다.

    > [!NOTE]
    > 기존 옵션 집합을 엔터티에 사용할 수 있는 경우 새로 만들지 않고 이 목록에서 선택할 수 있습니다.

    ![옵션 집합 목록](./media/data-platform-cds-newoptionset/fieldpanel-1.png "옵션 집합 목록")

7. 옵션 집합을 만들기 위한 새 패널이 열립니다. **표시 이름** 및 **이름**은 필드 이름의 기본값이지만 필요한 경우 변경할 수 있습니다. **새 항목 추가**를 클릭하여 옵션 목록 만들기를 시작합니다. 모든 항목을 만들 때까지 이 단계를 반복합니다.

    ![새 옵션 집합](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "새 옵션 집합")

8. 항목을 입력한 후 **저장**을 클릭하여 옵션 집합을 만듭니다.

    ![새 옵션 집합](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "새 옵션 집합")

9. **완료**를 클릭하여 필드 창을 닫은 다음, **엔터티 저장**을 클릭하여 Common Data Service에 엔터티를 저장합니다.

    > [!NOTE]
    > 이 필드에 대한 **기본값**으로 항목 중 하나를 선택할 수 있으며 사용자가 엔터티에 새 레코드를 만드는 경우 기본적으로 선택됩니다.

    ![새 필드](./media/data-platform-cds-newoptionset/fieldpanel-2.png "새 필드 패널")

## <a name="creating-an-option-set-from-the-option-set-list"></a>목록 집합 목록에서 옵션 집합 만들기

1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **옵션 집합**을 클릭하거나 탭합니다.

    ![옵션 집합](./media/data-platform-cds-newoptionset/optionsetlist.png "옵션 집합 목록")

2. **새 옵션 집합**을 클릭합니다.

3. 옵션 집합을 만드는 새 패널이 열리고, **표시 이름** 및 **이름**을 입력합니다. **새 항목 추가**를 클릭하여 옵션 목록 만들기를 시작합니다. 모든 항목을 만들 때까지 이 단계를 반복합니다.

    ![옵션 집합 만들기](./media/data-platform-cds-newoptionset/optionset-create.png "옵션 집합 만들기")

4. 항목을 입력한 후 **저장**을 클릭하여 옵션 집합을 만듭니다.

    ![새 옵션 집합](./media/data-platform-cds-newoptionset/optionset-create-values.png "새 옵션 집합")

5. 이제 엔터티에 새 필드를 만들어 이 옵션 집합을 사용할 수 있습니다.

## <a name="global-and-local-option-sets"></a>전역 및 로컬 옵션 집합

기본적으로 옵션 집합은 여러 엔터티 간에 다시 사용할 수 있도록 하는 전역 옵션 집합으로 만들어집니다. **자세히 보기** 옵션 아래에서 새 옵션 집합을 만들 때 옵션 집합을 **로컬**로 만들도록 선택할 수 있습니다. 이 옵션은 옵션 집합 목록을 통해서가 아닌 필드를 추가하는 동안 옵션 집합을 만들 때만 사용 가능합니다. 로컬 옵션 집합은 만들어진 엔터티 및 필드에서만 사용될 수 있으며 다른 엔터티에서 다시 사용할 수 없습니다. 이 방법은 로컬 옵션 집합에 대한 특정 요구 사항이 있는 고급 사용자에게만 권장됩니다.

> [!IMPORTANT]
> 로컬 또는 전역으로 옵션 집합이 만들어지면 변경할 수 없습니다.