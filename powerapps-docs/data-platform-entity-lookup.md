---
title: "조회 필드를 통한 엔터티 관계 | Microsoft Docs"
description: "조회 필드를 사용하여 엔터티 간의 관계를 만듭니다."
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: kfend
ms.openlocfilehash: 1aff4df6e314f50a67aff6a08298d3d7aa4a9cfa
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="build-a-relationship-between-entities"></a>엔터티 간 관계 빌드
한 엔터티의 데이터는 다른 엔터티의 데이터와 자주 관련됩니다. 예를 들어, **고객** 엔터티 및 **주문** 엔터티, 및 **주문** 엔터티에는 주문을 한 고객을 표시하는 **고객** 엔터티에 대한 조회 관계가 있을 수 있습니다. 조회 필드를 사용하여 주문한 고객에 대한 **고객** 엔터티의 데이터를 표시할 수 있습니다. 자세한 내용은 [엔터티 관계 및 조회 필드](https://docs.microsoft.com/en-us/common-data-service/entity-reference/relationships)를 참조하세요.

## <a name="define-a-relationship"></a>관계 정의
다른 엔터티(또는 엔터티 자체) 간에 여러 형식의 관계를 만들 수 있습니다. 각 엔터티는 둘 이상의 엔터티와 관계가 있을 수 있으며, 각 엔터티는 다른 엔터티에 대해 둘 이상의 관계가 있을 수 있습니다. 몇 가지 일반적인 관계 형식은 다음과 같습니다.

* **보통** - 이 형식의 관계는 두 엔터티 간에 존재합니다.
* **자체** - 이 형식의 관계는 엔터티와 자체 사이에 존재합니다.
* **일대일** - 이 형식의 관계에서, 엔터티 A의 각 레코드는 엔터티 B의 하나의 레코드와만 일치하거나 또는 그 반대일 수 있습니다. 현재 릴리스의 Common Data Service는 사용자 지정 엔터티에 대해 이 형식의 관계를 지원하지 않습니다.
* **일 대 다** - 이 형식의 관계에서 엔터티 A의 각 레코드는 엔터티에 B의 둘 이상의 레코드와 일치할 수 있지만, 엔터티 B의 각 레코드는 엔터티 A의 하나의 레코드와 일치할 수 있습니다.
* **다 대 다** - 이 형식의 관계에서 엔터티 A의 각 레코드는 엔터티 B의 둘 이상의 레코드와 일치하거나 또는 그 반대일 수 있습니다. 현재 릴리스의 Common Data Service는 이 형식의 관계를 지원하지 않습니다.

## <a name="add-a-lookup-relation"></a>조회 관계 추가
엔터티를 조회 관계를 추가하려면 **관계** 탭 아래에서 관계를 만들고 관계를 만들려는 엔터티를 지정합니다.

1. [powerapps.com](https://web.powerapps.com)에서 **Common Data Service** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 누릅니다.
2. 엔터티 목록에서 엔터티를 클릭하거나 탭하여 해당 필드를 표시합니다. 목록 위의 검색 창에서 하나 이상의 문자를 입력하여 목록을 필터링할 수 있습니다.
3. 화면 위쪽 근처에서 **관계**를 클릭하거나 누릅니다. 이 탭에서는 엔터티에 대한 모든 관계를 표시합니다. **새 관계**를 클릭합니다.
4. **관계 만들기** 페이지에서 관계 만들고, 이름 및 표시 이름을 지정하려는 관련된 엔터티를 지정합니다.
5. **저장**을 클릭하거나 탭하여 변경 내용을 커밋합니다. 동일한 이름을 가진 조회 필드가 자동으로 생성됩니다.

## <a name="use-a-lookup-field-in-an-app"></a>앱에서 조회 필드 사용
조회 필드를 포함하는 엔터티에서 [자동으로 앱을 만드는](data-platform-create-app.md) 경우, 참조된 엔터티의 **기본 키** 필드에서 데이터를 포함하는 축소된 상태의 **드롭다운** 컨트롤로 표시됩니다. 두 필드가 확장될 때 드롭다운에서 확인하려면 PrimaryId 필드 및 선택한 두 번째 필드를 조회 관계와 관련된 엔터티의 **기본 조회** 필드 그룹에 추가해야 합니다.

## <a name="delete-a-record-with-a-lookup-relation"></a>조회 관계가 있는 레코드 삭제
엔터티 A가 엔터티 B에 대한 조회 관계를 포함하는 경우:

* 제한 없이 엔터티 A에서 모든 레코드를 삭제할 수 있습니다.
* 엔터티 B의 레코드가 엔터티 A의 하나 이상의 레코드와 일치하는 경우, 엔터티 B의 레코드를 삭제하기 전에 엔터티 A에서 일치하는 모든 레코드를 삭제해야 합니다.

**참고**: 엔터티 B가 엔터티 A에 대한 부모 관계가 있는 표준 엔터티이고 엔터티 A에서 레코드를 삭제하는 경우, 엔터티 B에 있는 모든 일치된 레코드도 삭제됩니다.

필드를 삭제하는 방법에 대한 정보는 [필드 관리](data-platform-manage-fields.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
* [Common Data Service 데이터베이스를 사용하여 앱 생성](data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](data-platform-create-app-scratch.md)

