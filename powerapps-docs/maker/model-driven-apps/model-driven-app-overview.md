---
title: PowerApps와 모델 기반 앱 빌드에 대한 개요 | Microsoft Docs
description: PowerApps 앱과 함께 사용하는 엔터티를 만들고 구성하기 위한 단계별 지침입니다.
documentationcenter: na
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 08/09/2018
ms.author: matp
ms.openlocfilehash: f6434e6a9248586c05fa0b56b8934d910af3087a
ms.sourcegitcommit: 2a61989be5880fede31510c5dab1593a6f42a741
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "39723849"
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>PowerApps의 모델 기반 앱이란?

모델 기반 앱 디자인은 앱 개발에 대해 구성 요소에 중점을 두는 방법입니다. 모델 기반 앱 디자인에는 코드가 필요하지 않으며 앱을 단순하거나 매우 복잡하게 만들 수 있습니다.  디자이너 앱 레이아웃을 완전히 제어하는 캔버스 앱 개발과 달리, 모델 기반 앱을 사용하면 레이아웃의 대부분은 주로 사용자가 앱에 추가하는 구성 요소에 따라 지정되거나 결정됩니다. 

![샘플 모델 기반 앱](media/model-driven-app-overview/model-app-sample.png)

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
일관된 비즈니스 프로세스를 정의하고 강화하는 것은 모델 기반 앱 디자인에서 중요한 요소입니다. 일관된 프로세스로 인해 앱 사용자는 일련의 수동 단계를 수행해야 함을 기억하기보다 자신의 작업에 집중할 수 있습니다. 프로세스는 간단하거나 복잡할 수 있으며 시간이 지나면서 자주 변경될 수 있습니다. 프로세스를 만들려면 PowerApps.com 모델 기반 영역에서 ![설정](media/powerapps-gear.png) > **고급 사용자 지정** > **솔루션 탐색기 열기**를 선택합니다. 다음으로, 솔루션 탐색기의 왼쪽 탐색 창에서 **프로세스**를 선택한 다음, **새로 만들기**를 선택합니다. 자세한 정보: [비즈니스 프로세스 흐름 개요](/flow/business-process-flows-overview) 및 [앱용 Common Data Service를 사용하여 비즈니스 논리 적용](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>모델 기반 앱 작성
데이터를 모델링하고 프로세스를 정의한 후, 앱 디자이너를 사용하여 필요한 구성 요소를 선택 및 구성하여 앱을 빌드합니다.

![앱 디자이너](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>다음 단계

[첫 번째 모델 기반 앱 빌드](build-first-model-driven-app.md)

[모델 기반 앱 구성 요소 이해](model-driven-app-components.md)

