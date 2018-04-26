---
title: PowerApps와 모델 기반 앱 빌드에 대한 개요 | Microsoft Docs
description: PowerApps 앱과 함께 사용하는 엔터티를 만들고 구성하기 위한 단계별 지침입니다.
documentationcenter: na
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 1b9ee344192d84933d25a3208d2feb0873a298c1
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="overview-of-building-a-model-driven-app"></a>모델 기반 앱 빌드에 대한 개요

모델 기반 앱 디자인은 앱 개발에 대해 구성 요소에 중점을 두는 방법입니다. 모델 기반 앱 디자인에는 코드가 필요하지 않으며 앱을 단순하거나 매우 복잡하게 만들 수 있습니다.  디자이너 앱 레이아웃을 완전히 제어하는 캔버스 앱 개발과 달리, 모델 기반 앱을 사용하면 레이아웃의 대부분은 주로 사용자가 앱에 추가하는 구성 요소에 따라 지정되거나 결정됩니다. 

![샘플 모델 기반 앱](media/model-driven-app-overview/model-app-sample.png)

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

모델 기반 앱 디자인은 다음과 같은 이점을 제공합니다.
- 다양한 구성 요소 중심의 코드 없는 디자인 환경 
- 데스크톱에서 모바일에 이르는 다양한 장치 간에 유사한 UI로 복잡한 응답성이 뛰어난 앱 생성
- Dynamics 365 고객 참여 플랫폼에서 사용할 수 있는 것과 유사한 디자인 기능 
- 앱을 솔루션으로 배포 가능
 
## <a name="the-approach-to-model-driven-app-making"></a>모델 기반 앱을 만들기 위한 방법
기본적인 수준에서 모델 기반 앱 만들기는 3가지 핵심 영역으로 이루어져 있습니다.

- 비즈니스 데이터의 모델링 
- 비즈니스 프로세스의 정의 
- 앱의 작성

### <a name="modeling-business-data"></a>비즈니스 데이터의 모델링
비즈니스 데이터를 모델링하려면 앱에서 필요한 데이터가 무엇인지와 해당 데이터가 어떻게 다른 데이터와 관련되는지를 결정합니다. 디자이너가 코드를 작성하지 않고 응용 프로그램을 사용자 지정할 수 있도록 모델 기반 디자인은 메타데이터 기반 아키텍처를 사용합니다. 메타데이터란 “데이터에 대한 데이터”를 의미하며 시스템에 저장된 데이터의 구조를 정의합니다. [자습서: PowerApps에 구성 요소가 있는 사용자 지정 엔터티 만들기](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>비즈니스 프로세스의 정의
일관된 비즈니스 프로세스를 정의하고 강화하는 것은 모델 기반 앱 디자인에서 중요한 요소입니다. 일관된 프로세스로 인해 앱 사용자는 일련의 수동 단계를 수행해야 함을 기억하기보다 자신의 작업에 집중할 수 있습니다. 프로세스는 간단하거나 복잡할 수 있으며 시간이 지나면서 자주 변경될 수 있습니다. 프로세스를 만들려면 **고급**을 선택하여 [솔루션 탐색기](#advanced-model-driven-app-making)를 엽니다. 다음으로, 솔루션 탐색기의 왼쪽 탐색 창에서 **프로세스**를 선택한 다음, **새로 만들기**를 선택합니다. 자세한 내용: [비즈니스 논리 작업](#working-with-business-logic)  

### <a name="composing-the-model-driven-app"></a>모델 기반 앱 작성
데이터를 모델링하고 프로세스를 정의한 후, 앱 디자이너를 사용하여 필요한 구성 요소를 선택 및 구성하여 앱을 빌드합니다.

![앱 디자이너](media/model-driven-app-overview/app-designer.png)

## <a name="model-driven-app-components-and-designers"></a>모델 기반 앱 구성 요소 및 디자이너
잘 디자인된 모델 기반 앱은 완성된 앱의 모양 및 기능을 빌드하기 위해 디자이너가 선택한 여러 구성 요소로 구성되어 있습니다. 디자이너가 앱을 만드는 데 사용한 구성 요소 및 구성 요소 속성이 메타데이터가 됩니다. 이러한 각 구성 요소가 어떻게 앱 디자인과 관련되는지 이해하기 위해 *데이터*, *UI*, *논리* 및 *시각화*범주로 분리하였습니다. 

### <a name="data"></a>데이터
이러한 구성 요소는 앱이 기반으로 하는 데이터를 결정합니다.


|구성 요소  |설명  |디자이너  |
|---------|---------|---------|
|엔터티     |연락처 계정과 같이 추적하는 속성이 있는 항목입니다. 많은 표준 엔터티를 사용할 수 있습니다. 비시스템 표준 엔터티(프로덕션 엔터티)를 사용자 지정하거나 처음부터 사용자 정의 엔터티를 만들 수 있습니다.     | [!INCLUDE [powerapps](../../includes/powerapps.md)] 엔터티 디자이너        |
|필드     | 엔터티와 연결된 속성입니다. 필드는 입력하거나 선택할 수 있는 데이터의 형식을 결정하는 데이터 형식에 의해 정의됩니다. 텍스트, 숫자, 날짜 및 시간, 통화 또는 조회(다른 엔터티와의 관계를 만듦)를 예로 들 수 있습니다. 필드는 일반적으로 폼, 보기 및 검색에 사용됩니다.        | [!INCLUDE [powerapps](../../includes/powerapps.md)] 엔터티 디자이너   |
|관계     | 엔터티 관계는 엔터티가 서로 어떻게 연결될 수 있는지를 정의합니다. 1:N(일 대 다), N:1(다 대 일) 및 N:N(다 대 다) 형식의 관계가 있습니다. 예를 들어 엔터티에 조회 필드를 추가하면 두 엔터티 간에 새로운 1:N 관계가 생성되어 해당 조회 필드를 폼에 배치할 수 있습니다.   | [!INCLUDE [powerapps](../../includes/powerapps.md)] 엔터티 디자이너        |
|옵션 설정 필드     | 이는 사용자에게 미리 결정된 옵션 집합을 제공하는 특수한 필드 형식입니다. 각 옵션에는 숫자 값 및 레이블이 있습니다. 폼에 추가하면 이 필드는 사용자가 옵션을 선택하도록 컨트롤을 표시합니다.  사용자가 하나의 옵션만 선택할 수 있는 옵션 집합과 둘 이상을 선택할 수 있는 다중 선택 옵션으로 두 가지 종류의 옵션 집합이 있습니다.  | [!INCLUDE [powerapps](../../includes/powerapps.md)] 옵션 집합 디자이너     |

### <a name="ui"></a>UI
이러한 구성 요소는 사용자가 앱과 어떻게 상호 작용하는지를 결정합니다. 

|구성 요소  |설명  |디자이너  |
|---------|---------|---------|
|앱     | 앱에 대한 구성 요소, 속성, 클라이언트 유형 및 URL과 같은 응용 프로그램 기본 항목을 결정합니다.      | 앱 디자이너   |
|사이트 맵     | 앱에 대한 탐색을 지정합니다.        | 사이트 맵 디자이너        |
|폼     | 조직에서 엔터티에 대해 추적하는 항목과 일치하는 주어진 엔터티에 대한 데이터 입력 필드의 집합입니다. 예를 들어 사용자의 입력 관련 정보가 요청된 특정 재주문 날짜와 함께 고객의 이전 주문을 추적하는 데이터 입력 필드의 집합입니다.        | 폼 디자이너        |
|보기     | 보기는 특정 엔터티에 대한 레코드 목록이 응용 프로그램에 표시되는 방법을 정의합니다. 보기는 표시할 열, 각 열의 너비, 정렬 동작 및 기본 필터를 정의합니다.   |  뷰 디자이너       |

![앱 디자이너 및 폼 디자이너](media/model-driven-app-overview/app-and-form-designers.png)

### <a name="logic"></a>논리
앱이 갖게 되는 비즈니스 프로세스, 규칙 및 자동화를 결정합니다. [!INCLUDE [powerapps](../../includes/powerapps.md)] 결정권자는 프로세스 또는 규칙의 형식에 적용되는 디자이너를 사용합니다. 


|논리의 형식  |설명  |디자이너  |
|---------|---------|---------|
|비즈니스 프로세스 흐름     | 사용자에게 표준 비즈니스 프로세스를 안내하는 온라인 프로세스입니다. 예를 들어 모든 사람이 동일한 방식으로 고객 서비스 요청을 처리하거나, 직원들이 주문을 제출하기 전에 송장에 대한 승인을 얻도록 하려는 경우비즈니스 프로세스를 사용합니다.        | 비즈니스 프로세스 흐름 디자이너        |
|워크플로     |  워크플로는 사용자 인터페이스 없이 비즈니스 프로세스를 자동화합니다. 디자이너는 워크플로를 사용하여 사용자 상호 작용이 필요하지 않은 자동화를 시작합니다.       | 워크플로 디자이너        |
|작업    |  작업은 워크플로에서 직접 수동으로 사용자 지정 작업과 같은 작업을 호출할 수 있는 프로세스의 유형입니다.       |  프로세스 디자이너       |
|비즈니스 규칙     | 필드 요구 사항 설정, 필드 숨기기 또는 데이터 유효성 검사와 같은 규칙이나 권장 사항 논리를 폼에 적용하는 데 사용합니다. 앱 디자이너는 빠르게 변경되고 일반적으로 사용되는 규칙을 구현하고 유지하기 위해 간단한 인터페이스를 사용합니다.         |  비즈니스 규칙 디자이너       |
|흐름     | 흐름은 앱 및 서비스 간에 자동화된 워크플로를 만들어 알림 받기, 파일 동기화, 데이터 수집 등의 작업을 수행할 수 있는 클라우드 기반 서비스입니다.        | Microsoft Flow        |

![워크플로, 작업 및 비즈니스 프로세스 흐름 디자이너](media/model-driven-app-overview/designer-mash.png)

### <a name="visualizations"></a>시각화
앱에서 가능한 데이터 시각화 및 보고의 유형을 결정합니다.


|구성 요소  |설명  |디자이너  |
|---------|---------|---------|
|차트     | 폼에서 뷰 내에 표시하거나 대시보드에 추가할 수 있는 단일 그래픽 시각화입니다.        | 차트 디자이너        |
|대시보드     | 작업 가능한 비즈니스 데이터에 대한 개요를 제공하는 하나 이상의 그래픽 시각화에 대한 시작점으로 작동합니다.        | 대시보드 디자이너        |
|Embedded Power BI     | 앱에 포함된 Power BI 타일 및 대시보드를 추가합니다. Power BI는 비즈니스 인텔리전스 정보를 제공하는 클라우드 기반 서비스입니다.        |  차트 디자이너, 대시보드 디자이너 및 Power BI의 조합       |

![샘플 대시보드](media/model-driven-app-overview/dashboard-designer.png)

### <a name="advanced-model-driven-app-making"></a>고급 모델 기반 앱 만들기
솔루션 탐색기는 고급 모델 기반 앱 빌드에 사용되는 포괄적인 도구입니다. 솔루션 탐색기 내에서 도구의 왼쪽에 있는 탐색 창을 사용하여 모든 앱 구성 요소로 구성된 계층 구조를 탐색할 수 있습니다.

![솔루션 탐색기](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

솔루션 탐색기를 열려면 [!INCLUDE [powerapps](../../includes/powerapps.md)]의 왼쪽 창에서 **모델 기반**을 선택합니다.

  ![모델 기반 선택](media/model-driven-app-overview/app-type-picker-mod.png)

그런 다음, **고급** 탭을 선택합니다. 

## <a name="model-driven-app-development-resources"></a>모델 기반 앱 개발 리소스
모델 기반 앱 개발에 대한 자세한 내용은 다음 항목을 참조하세요.
### <a name="modeling-your-data"></a>데이터 모델링
- [앱 디자이너를 사용하여 사용자 지정 비즈니스 앱 디자인](https://docs.microsoft.com/dynamics365/customer-engagement/customize/design-custom-business-apps-using-app-designer)
- [양식 만들기 및 설계](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-design-forms)
- [뷰 만들기 또는 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-views)  

### <a name="modeling-and-composing-your-app"></a>앱 모델링 및 작성
- [엔터티 만들기 또는 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entities)
- [관계 만들기 및 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entity-relationships) 
- [필드 만들기 및 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-fields)
- [전역 옵션 집합 만들기 및 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-global-option-sets)

### <a name="working-with-business-logic"></a>비즈니스 논리 작업
- [비즈니스 프로세스 흐름 개요](https://docs.microsoft.com/dynamics365/customer-engagement/customize/business-process-flows-overview)
- [워크플로 프로세스를 사용하여 프로세스를 자동화](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)
- [작업 개요](https://docs.microsoft.com/dynamics365/customer-engagement/customize/actions)
- [논리를 적용하는 비즈니스 규칙 및 권장 사항 만들기](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form)

### <a name="using-visualizations-in-your-app"></a>앱에서 시각화 사용
- [시스템 차트 만들기 또는 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-system-chart)
- [대시보드 만들기 또는 편집](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-dashboards)


### <a name="distributing-your-app"></a>앱 배포
[솔루션 만들기](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-solution)

## <a name="next-steps"></a>다음 단계
[빠른 시작: 사용자 지정 엔터티 만들기](../common-data-service/data-platform-create-entity.md)

[자습서: PowerApps에 구성 요소가 있는 사용자 지정 엔터티 만들기](../common-data-service/create-custom-entity.md)

