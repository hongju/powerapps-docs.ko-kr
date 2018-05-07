---
title: 엔터티 내 사용자 지정 필드 관리 | Microsoft Docs
description: 앱용 CDS의 엔터티에서 사용자 지정 필드를 만들고, 읽고, 업데이트하고, 삭제하는 방법에 대한 연습입니다.
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.component: cds
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: ff522ee5d5614888c6cc0fcfb1e7d6658a36c6ae
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="manage-custom-fields-in-an-entity"></a>엔터티 내 사용자 지정 필드 관리
모든 엔터티 내 하나 이상의 사용자 지정 필드를 만들고 업데이트할 수 있습니다. 사용자 지정 필드를 만들려면 필드의 이름, 필드의 표시 이름, 포함할 데이터 형식 등과 같은 속성 집합을 지정해야 합니다. 자세한 내용은 [엔터티 특성 메타데이터](../../developer/common-data-service/entity-attribute-metadata.md)를 참조하세요.

> [!NOTE]
> 모든 엔터티에는 레코드가 마지막으로 업데이트된 날짜 및 업데이트한 사람을 나타내는 필드와 같은 시스템 필드가 있습니다. 또한 표준 엔터티에는 표준(기본값) 필드가 있습니다. 시스템 필드 또는 표준 필드를 수정하거나 삭제할 수 없습니다. 사용자 지정 필드를 만들 경우 이러한 기본 제공 필드를 기반으로 기능을 제공해야 합니다.

## <a name="create-a-field"></a>필드 만들기
1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 기존 엔터티를 클릭하거나 탭하거나 [새 엔터티를 만듭니다](data-platform-create-entity.md).

3. **필드 추가**를 클릭하여 엔터티에 새 필드를 추가합니다.

4. 새 필드 패널에서 필드에 대한 **표시 이름**을 입력하면 **이름**은 자동으로 채워지고 필드에 대한 고유 이름으로 사용됩니다. **표시 이름**은 이 필드를 사용자에게 표시할 때 사용되며, **이름**은 식과 수식에서 앱을 빌드할 때 사용됩니다.

    > [!NOTE]
    > **표시 이름** 필드는 앱에 다르게 표시하도록 언제든지 업데이트될 수 있으며, **이름** 필드는 기존 앱을 중단시킬 수 있으므로 엔터티가 저장된 후에 변경할 수 없습니다.

    ![새 필드](./media/data-platform-cds-create-entity/newfieldpanel.png "새 필드 패널")

5. 필드의 **데이터 형식**을 선택합니다. 이는 정보가 저장되는 방식과 앱에서 표시되는 방법을 제어합니다. 예를 들어 텍스트는 10진수 또는 URL에 따라 다르게 저장됩니다. 사용 가능한 데이터 형식의 자세한 내용은 [엔터티 특성 메타데이터](../../developer/common-data-service/entity-attribute-metadata.md)를 참조하세요.

    메시지가 나타나면 사용자가 지정한 데이터 형식에 대한 추가 정보를 지정합니다. 데이터 형식에 따라 서로 다른 필드가 표시됩니다. 옵션 집합 또는 다중 선택 옵션 집합 형식의 필드를 만드는 경우 **새 옵션 집합**을 선택하고 필드를 만드는 동안 새 옵션 집합을 만들 수 있습니다. 자세한 내용은 [옵션 집합 만들기](custom-picklists.md)를 참조하세요.

    ![새 필드](./media/data-platform-cds-create-entity/newfieldpanel-2.png "새 필드 패널")


7. **필수** 아래에서 앱의 필수로 이 필드를 권장하려는 경우 확인란을 선택합니다. Common Data Service에 대한 모든 연결을 통해 하드 적용을 제공하지 않습니다. 필드가 채워지는지 확인해야 하는 경우 [비즈니스 규칙](data-platform-create-business-rule.md)을 만듭니다.

8. **검색 가능** 아래에서 이 필드를 보기, 차트, 대시보드 및 고급 찾기에 사용할 수 있도록 하려면 확인란을 선택합니다. 대부분의 경우에서 이 확인란을 선택해야 합니다.

9. **완료**를 클릭하거나 탭하여 필드 패널을 닫고 엔터티로 돌아옵니다. 각 추가 필드에 대해 3~9단계를 반복할 수 있습니다.
   
    > [!IMPORTANT]
    > 엔터티에 대한 변경 내용을 저장할 때까지 필드는 저장 및 만들어지지 않습니다.

10. **엔터티 저장**을 클릭하거나 탭하여 변경 내용을 마무리하고 Common Data Service에 저장합니다.

    작업이 성공적으로 완료될 때 알림을 받습니다. 작업이 실패할 경우 오류 메시지가 발생한 문제 및 해결 방법을 표시합니다.

## <a name="create-a-calculated-or-roll-up-field"></a>계산됨 또는 롤업 필드 만들기
계산됨 필드를 통해 비즈니스 프로세스에 사용되는 수동 계산을 자동화할 수 있습니다. 예를 들어 한 영업 직원은 확률을 곱한 기회에서 예상된 수익을 기반으로 하는 기회에 대해 가중된 수익을 알아야 할 수 있습니다. 또는 주문이 $500보다 많은 경우 자동으로 할인을 적용하려고 합니다. 계산된 필드는 단순한 수학 작업 또는 더 크거나 그렇지 않은 경우와 같은 조건부 작업의 결과 및 기타 작업에서 발생하는 값을 포함할 수 있습니다. 계산된 필드는 다음 데이터 형식을 사용하여 만들 수 있습니다.

* 한 줄 텍스트
* 옵션 집합
* 두 가지 옵션
* 정수
* 10진수
* 통화
* 날짜 및 시간

지원되는 식의 형식 및 예제에 대한 자세한 내용은 [계산된 필드 정의](/dynamics365/customer-engagement/customize/define-calculated-fields)를 참조하세요.

## <a name="update-or-delete-a-field"></a>필드 업데이트 또는 삭제
1. [powerapps.com](https://web.powerapps.com)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭한 다음, 엔터티를 클릭하거나 탭합니다.
2. 선택한 엔터티에 대한 필드 목록에서 필드를 클릭하거나 탭한 후 다음 단계 중 하나를 따르십시오.
   
   * 필드의 하나 이상의 속성을 변경합니다.
   * 필드의 오른쪽 모서리 옆의 줄임표(...)를 클릭하거나 탭한 다음 **삭제**를 클릭하거나 탭하여 필드를 삭제합니다.

3. 변경 내용을 제출하려면 **엔터티 저장**을 클릭하거나 탭합니다.
   
    > [!IMPORTANT]
    > 브라우저에서 다른 페이지를 열거나 브라우저를 종료하기 전에 저장하지 않으면 변경 내용이 손실됩니다.

    작업이 성공적으로 완료될 때 알림을 받습니다. 작업이 실패할 경우 오류 메시지가 발생한 문제 및 해결 방법을 표시합니다.

## <a name="best-practices-and-restrictions"></a>모범 사례 및 제한 사항
필드를 만들고 수정할 때 유의할 사항:

* 시스템의 필드 또는 필드 값은 수정하거나 삭제할 수 없습니다.
* 표준 엔터티에서 표준(기본값) 필드를 수정 또는 삭제하는 작업, 데이터가 필요한 필드를 추가하는 작업, 또는 해당 엔터티에 의존하는 앱이 중단될 수 있는 모든 변경 작업은 수행할 수 없습니다.
* 사용자 지정 엔터티에서 해당 엔터티에 의존하는 모든 앱이 중단되지 않을 변경 작업인지 확인해야 합니다.
* 각 사용자 지정 필드마다 엔터티 내 고유한 이름을 지정해야 하고, 필드를 후에는 필드 이름을 변경할 수 없습니다.

## <a name="next-steps"></a>다음 단계
* [엔터티 간의 관계 정의](data-platform-entity-lookup.md)
* [비즈니스 규칙 만들기](data-platform-create-business-rule.md)
* [엔터티를 사용하여 앱 만들기](../canvas-apps/data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다.  이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.

