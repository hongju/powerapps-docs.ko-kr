---
title: "사용자 지정 엔터티 만들기 | Microsoft Docs"
description: "처음부터 또는 다른 엔터티를 기반으로 사용자 지정 엔터티를 만듭니다."
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
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: 5d927e84144da8e3b011bb4e4a7ac107aedac74f
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="create-a-custom-entity"></a>사용자 지정 엔터티 만들기
귀하의 조직에 관련된 데이터를 저장하는 사용자 지정 엔터티를 만들 수 있습니다. 그런 다음 엔터티를 참조하는 앱을 개발하여 해당 데이터를 표시할 수 있습니다.

엔터티를 만드는 데에는 다음 두 가지 방법이 있습니다.

* 처음부터 엔터티를 만듭니다. 기본적으로 엔터티는 [네 개의 시스템 필드와 레코드 제목 필드](data-platform-create-entity.md#system-and-record-title-fields)만 포함합니다.
* 해당 엔터티의 필드와 설정은 복사하지만 데이터는 복사하지 않고 다른 엔터티를 기반으로 하는 엔터티를 만듭니다.

두 경우 모두 Microsoft PowerApps는 자동으로 데이터를 저장하고 보안에 도움이 됩니다. 엔터티를 만든 다음 [하나 이상의 필드를 만들거나 수정](data-platform-manage-fields.md)하고 [엔터티 간의 관계를 빌드](data-platform-entity-lookup.md)할 수 있습니다.

**참고:** 엔터티를 만들기 전에 [표준 엔터티 목록](data-platform-intro.md#standard-entities)을 참조하세요. 이러한 엔터티는 계정 및 연락처와 같은 일반적인 시나리오를 설명합니다. 이러한 엔터티 중 하나가 즉시 또는 약간 변경된 후에 요구 사항을 충족하는 경우 해당 엔터티부터 시작하여 약간의 시간을 줄일 수 있습니다.

## <a name="create-an-entity"></a>엔터티 만들기
1. 1. [powerapps.com](https://web.powerapps.com)에서 **Common Data Service** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.
2. 데이터베이스를 만들지 않은 경우 하나를 만들어야 합니다. 자세한 내용은 [ Common Data Service 데이터베이스 만들기](create-database.md)를 참조하세요.
3. 오른쪽 위 모서리 근처에서 **새 엔터티**를 클릭하거나 탭합니다.
4. **엔터티 이름** 필드에 엔터티에 대한 이름을 입력합니다. 엔터티를 만든 후에는 이름을 변경할 수 없으므로 이름이 명확하고 의미 있도록 합니다. 앱을 개발할 때 수식에서 이 이름으로 엔터티를 참조하게 됩니다.
5. 표시 이름과 엔터티에 대한 설명(선택 사항)을 지정한 후 **다음**을 클릭하거나 탭합니다.
6. 선택 사항: **제목** 필드의 값을 데이터에 대해 더욱 의미 있는 값으로 바꿉니다.
7. **만들기**를 클릭하거나 탭하여 엔터티를 만듭니다.

데이터베이스의 엔터티 목록에 엔터티가 나타납니다. 목록 맨 위에 엔터티를 표시하려면 열 머리글 **형식**을 클릭하거나 탭합니다. 엔터티는 형식에 따라 정렬되며 모든 사용자 지정 엔터티가 모든 표준 엔터티 위로 나타납니다.

## <a name="system-fields-and-the-record-title-field"></a>시스템 필드 및 레코드 제목 필드
모든 엔터티에는 5개의 시스템 필드가 있습니다. 이러한 필드는 읽기 전용입니다. 따라서 이러한 필드는 변경 또는 삭제할 수 없으며 값을 할당하지 않습니다.

| 표시 이름 | 시스템 필드 이름 | 데이터 형식 | 설명 |
| --- | --- | --- | --- |
| ID입니다. |시스템 필드 이름 |Big Integer |레코드에 대한 고유 식별자입니다. |
| 작성자 |CreatedByUser |텍스트 |레코드를 만든 사용자입니다. |
| 레코드 생성 날짜 |CreatedOnDateTime |DateTime |레코드를 생성한 날짜와 시간입니다. |
| 마지막으로 수정한 사람입니다. |LastModifiedByUser |텍스트 |가장 최근에 레코드를 수정한 사용자입니다. |
| 레코드 수정 날짜 |LastModifiedDateTime |DateTime |레코드를 수정한 최근 날짜와 시간입니다. |

엔터티를 처음부터 만든 경우 **제목**으로 이름이 지정된 사용자 지정 필드 또한 포함됩니다. 이 필드는 레코드의 **제목** 필드로 설정됩니다. **제목** 필드 값은 앱에서 해당 레코드를 사용할 때의 레코드에 관한 사용자에게 친숙한 식별자입니다. 어떤 필드가 **제목** 필드가 될지 변경할 수 있지만 모든 엔터티가 하나의 **제목** 필드를 가져야 합니다.

## <a name="next-steps"></a>다음 단계
* [엔터티에서 필드 관리](data-platform-manage-fields.md)
* [엔터티 간의 관계 정의](data-platform-entity-lookup.md)
* [Common Data Service 데이터베이스를 사용하여 앱 생성](data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다.  이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.

