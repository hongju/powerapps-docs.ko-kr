---
title: 앱용 Common Data Service란 무엇인가요? | Microsoft Docs
description: 앱, 엔터티 및 서버 쪽 논리를 위한 CDS(Common Data Service)에 대한 소개입니다.
author: Mattp123
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: b26f788a782e42125d6397d38b2d946f8188e475
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552832"
---
# <a name="what-is-common-data-service-for-apps"></a>앱용 Common Data Service란 무엇인가요?
앱용 CDS(Common Data Service)를 사용하면 비즈니스 응용 프로그램에서 사용되는 데이터를 안전하게 저장하고 관리할 수 있습니다. 앱용 CDS 내 데이터는 엔터티의 집합 내에 저장됩니다. *엔터티*는 테이블이 데이터베이스 내의 데이터를 저장하는 방법과 유사하게 데이터를 저장하는 데 사용되는 레코드의 집합입니다. 앱용 CDS는 일반적인 시나리오를 다루는 표준 엔터티의 기본 집합을 포함하고 있지만, 조직과 관련된 사용자 지정 엔터티를 만들고 파워 쿼리를 사용하여 데이터로 채울 수도 있습니다. 그런 다음, 앱 작성자는 PowerApps를 사용하여 이 데이터를 사용하는 다양한 응용 프로그램을 빌드할 수 있습니다.

앱용 CDS를 사용하기 위한 계획 구매에 대한 자세한 내용은 [가격 책정 정보](../../administrator/pricing-billing-skus.md)를 참조하세요.

## <a name="why-use-common-data-service-for-apps"></a>앱용 Common Data Service를 사용해야 하는 이유는 무엇인가요?
앱용 CDS 내에서 표준 및 사용자 지정 엔터티는 데이터를 위한 안전한 클라우드 기반 저장소 옵션을 제공합니다. 엔터티를 통해 앱 내에서 사용할 조직 데이터의 비즈니스 중심 정의를 만들 수 있습니다. 엔터티를 사용하는 것이 가장 적합한 방법인지 확신이 들지 않는다면 이러한 이점을 고려해보세요.

* **손쉬운 관리** &ndash; 메타데이터와 데이터는 모두 클라우드에 저장됩니다. 저장 방법에 대한 자세한 내용은 신경쓰지 않아도 됩니다.
* **손쉬운 공유** &ndash; 동료와 데이터를 쉽게 공유할 수 있습니다.&mdash;PowerApps에서 권한을 관리합니다.
* **손쉬운 보안** &ndash; 사용자가 액세스 권한을 부여 받은 경우에만 볼 수 있도록 데이터가 안전하게 저장됩니다. 역할 기반 보안을 통해 조직 내에서 여러 사용자의 엔터티에 대한 액세스를 제어할 수 있습니다.
* **풍부한 메타데이터** &ndash; PowerApps에서 데이터 형식과 관계를 직접 활용합니다. 예를 들어 필드 형식 URL을 정의하면 데이터가 앱 내에서 하이퍼링크로 표시됩니다.
* **논리 및 유효성 검사** &ndash; 데이터 품질을 보장하고 드라이브 프로세스를 추진하기 위해 계산된 필드, 비즈니스 규칙, 워크플로 및 비즈니스 프로세스 흐름을 정의합니다.
* **생산성 도구** &ndash; Microsoft Excel용 추가 기능에서 엔터티를 사용하여 생산성을 높이고 데이터 접근성을 보장할 수 있도록 합니다.

## <a name="interacting-with-entities"></a>엔터티와 상호 작용
앱 개발 시 표준 엔터티, 사용자 지정 엔터티, 또는 두 가지 모두를 사용할 수 있습니다. 앱용 CDS는 기본적으로 표준 엔터티를 제공합니다. 모범 사례에 따라 조직 내의 가장 일반적인 개념 및 시나리오를 파악할 수 있도록 설계되었습니다.

![엔터티 목록을 보여주는 스크린샷.](./media/data-platform-cds-intro/entitylist.png "엔터티 목록")

엔터티의 전체 목록은 [엔터티 참조](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference)를 참조하세요.

고유한 정보를 조직에 저장하기 위해 하나 이상의 사용자 지정 엔터티를 만들어 표준 엔터티의 기능을 확장할 수 있습니다. 자세한 내용은 [사용자 지정 엔터티를 만드는 방법](create-custom-entity.md)을 참조하세요.

## <a name="logic-and-validation"></a>논리 및 유효성 검사
앱용 CDS 내 엔터티는 엔터티 내의 데이터를 만들고 사용하는 각 앱에서 반복적인 코드를 줄이고 데이터 품질을 보장하기 위해 다양한 서버 쪽 논리를 활용하고 유효성 검사를 수행할 수 있습니다.

* **비즈니스 규칙**은 여러 필드 및 엔터티에서 데이터의 유효성을 검사하고, 데이터를 만드는 데 사용되는 앱에 상관 없이 경고 및 오류 메시지를 제공합니다. 자세한 내용은 [비즈니스 규칙 만들기](./data-platform-create-business-rule.md)를 참조하세요.
* **비즈니스 프로세스 흐름**에서는 사용자가 데이터를 일관되게 입력하고 매번 동일한 단계에 따르도록 안내합니다. 비즈니스 프로세스 흐름은 현재 모델 구동 앱에서만 지원됩니다. 자세한 내용은 [비즈니스 프로세스 흐름 개요](/dynamics365/customer-engagement/customize/business-process-flows-overview)를 참조하세요.
* **워크플로**를 사용하면 사용자 상호 작용 없이 비즈니스 프로세스를 자동화할 수 있습니다. 자세한 내용은 [워크플로 개요](/dynamics365/customer-engagement/customize/workflow-processes)를 참조하세요.
* **코드를 사용한 비즈니스 논리**는 고급 시나리오를 지원하여 코드를 통해 직접 응용 프로그램을 확장합니다. 자세한 내용은 [코드로 비즈니스 논리 적용](../../developer/common-data-service/apply-business-logic-with-code.md)을 참조하세요.

## <a name="developer-capabilities"></a>개발자 기능
[PowerApps](https://web.powerapps.com) 포털을 통해 사용할 수 있는 기능 외에도 앱용 CDS에는 메타데이터 및 데이터에 프로그래밍 방식으로 액세스하여 데이터와 상호 작용하면서 엔터티 및 비즈니스 논리를 만들 수 있는 개발자를 위한 기능이 포함되어 있습니다. 자세한 내용은 [앱 개발자를 위한 Common Data Service 개요](../../developer/common-data-service/overview.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
앱용 CDS 사용을 시작하려면:
* [Common Data Service 데이터베이스를 사용하여 앱을 만듭니다](../canvas-apps/data-platform-create-app-scratch.md).
* [사용자 지정 엔터티를 만든](create-custom-entity.md) 다음, [해당 엔터티를 사용하는 앱을 만듭니다](../canvas-apps/data-platform-create-app.md).
* [파워 쿼리를 사용](./data-platform-cds-newentity-pq.md)하여 온라인 또는 온-프레미스 데이터 원본에 연결하고 앱용 CDS로 데이터를 직접 가져옵니다.

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 Microsoft는 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다. 이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 앱 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.
