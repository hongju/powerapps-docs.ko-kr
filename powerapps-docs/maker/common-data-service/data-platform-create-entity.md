---
title: 사용자 지정 엔터티 만들기를 위한 빠른 시작 | Microsoft Docs
description: 처음부터 또는 다른 엔터티를 기반으로 사용자 지정 엔터티를 만들기 위한 빠른 시작입니다.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: e22a18bacb258ca46c8f36d647f9ebcc45282929
ms.sourcegitcommit: aa2d0166dccb38100183c093f293233b46f3669d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2018
---
# <a name="quickstart-create-a-custom-entity"></a>빠른 시작: 사용자 지정 엔터티 만들기
귀하의 조직에 관련된 데이터를 저장하는 사용자 지정 엔터티를 만들 수 있습니다. 그런 다음 엔터티를 참조하는 앱을 개발하여 해당 데이터를 표시할 수 있습니다. 엔터티를 만든 다음 [하나 이상의 필드를 만들거나 수정](data-platform-manage-fields.md)하고 [엔터티 간의 관계를 빌드](data-platform-entity-lookup.md)할 수 있습니다.

이 지침에서는 사용자 지정 엔터티를 수동으로 만드는 방법을 보여주며, 파워 쿼리를 사용하여 기존 데이터 기반으로 엔터티를 만들 수도 있습니다. 자세한 내용은 [파워 쿼리를 사용하여 새 엔터티 만들기](data-platform-cds-newentity-pq.md)를 참조하세요.

> [!NOTE]
> 엔터티를 만들기 전에 [엔터티 참조](../../developer/common-data-service/reference/about-entity-reference.md)를 참조하세요. 이러한 엔터티는 계정 및 연락처와 같은 일반적인 시나리오를 설명합니다. 이러한 엔터티 중 하나가 즉시 또는 약간 변경된 후에 요구 사항을 충족하는 경우 해당 엔터티부터 시작하여 약간의 시간을 줄일 수 있습니다.

## <a name="create-an-entity"></a>엔터티 만들기
1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 명령 모음에서 **새 엔터티**를 클릭하거나 탭합니다.
3. **표시 이름** 필드에 나중에 이 엔터티를 참조하는 데 쉽게 인식할 수 있는 이름을 입력합니다. 이는 양식, 차트 및 이 엔터티를 사용하여 만든 다른 개체에도 사용됩니다. 다른 두 필드도 채워진 것을 확인할 수 있습니다.

    * 복수 표시 이름 - PowerApps 또는 Flow의 이 엔터티와 상호 작용할 때 사용되며, Common Data Service WebAPI를 통해 엔터티 이름으로 사용됩니다. 복수 이름은 자동으로 생성되어야 하지만 변경할 수 있습니다.
    * 이름 - 엔터티의 고유한 이름이며, 특수 문자 또는 공백을 포함할 수 없으며 고유해야 합니다. 이름은 또한 환경이 만들어질 때 설정된 접두사를 포함하며, 만든 엔터티가 다른 엔터티 이름과 충돌하여 다른 환경으로 내보내고 가져올 수 있도록 사용됩니다. 이 접두사는 Common Data Service 기본 솔루션에 대한 게시자의 접두사를 업데이트하여 변경할 수 있습니다.

    > [!NOTE]
    > **표시 이름** 필드는 앱에 다르게 표시하도록 언제든지 업데이트될 수 있으며, **이름** 필드는 기존 앱을 중단시킬 수 있으므로 엔터티가 저장된 후에 변경할 수 없습니다.

    ![새 엔터티](./media/data-platform-cds-create-entity/newentitypanel.png "새 엔터티 패널")

4. **다음**을 클릭하면 엔터티 세부 정보 페이지로 이동됩니다. 기본적으로 모든 엔터티는 하나의 필드, "기본 이름"으로 시작하고, 이 필드는 이 엔터티에 대해 조회를 만들 때 사용됩니다. 엔터티에 저장되는 데이터의 이름 또는 기본 설명을 저장하는 데 일반적으로 사용되어야 합니다.

    > [!NOTE]
    > **기본 이름** 필드의 이름 및 표시 이름은 처음으로 엔터티를 저장하기 전에 업데이트할 수 있습니다. 예를 들어 이 필드를 "기본 이름" 대신 "학생 이름"으로 부르려는 경우

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/newentitydetails.png "새 엔터티 세부 정보")

5. 선택 사항: **필드 추가**를 클릭하여 엔터티에 텍스트 필드를 추가합니다. 새 필드 패널에서 필드에 대한 **표시 이름**을 입력하고 데이터 형식을 선택합니다. 자세한 내용은 [엔터티에서 필드 관리](data-platform-manage-fields.md)를 참조하세요.

    ![새 필드](./media/data-platform-cds-create-entity/newfieldpanel-2.png "새 필드 패널")


6. **완료**를 클릭하여 필드를 추가하고, 5단계를 반복하여 추가 필드를 추가합니다.
7. **엔터티 저장**을 클릭하여 엔터티를 저장하고 앱에서 사용할 수 있도록 합니다.

    데이터베이스의 엔터티 목록에 엔터티가 나타납니다. 만든 엔터티를 보기 위해 “기본”에서 “사용자 지정”으로 명령 모음의 필터를 변경할 수 있습니다.

## <a name="system-fields"></a>시스템 필드
모든 엔터티에는 시스템 필드가 있습니다. 이러한 필드는 읽기 전용입니다. 따라서 이러한 필드는 변경 또는 삭제할 수 없으며 값을 할당하지 않습니다. 기본적으로 시스템 필드는 엔터티에 있는 경우에도 필드 목록에 표시되지 않습니다. 모든 필드를 표시하려면 **기본**에서 **모두**로 명령 모음의 필터를 변경할 수 있습니다.

엔터티와 관련된 메타데이터에 대한 자세한 내용은 [엔터티 메타데이터](../../developer/common-data-service/entity-metadata.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
* [엔터티에서 필드 관리](data-platform-manage-fields.md)
* [엔터티 간의 관계 정의](data-platform-entity-lookup.md)
* [Common Data Service 데이터베이스를 사용하여 앱 생성](../canvas-apps/data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다.  이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.

