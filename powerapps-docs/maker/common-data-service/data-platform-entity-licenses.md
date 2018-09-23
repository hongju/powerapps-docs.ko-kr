---
title: 엔터티에 대한 라이선스 요구 사항| Microsoft Docs
description: 앱용 CDS(Common Data Service) 내의 엔터티에 대한 라이선스 요구 사항의 설명입니다.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 4350f7141adf0fbce3e74271d6aff48c18c857e2
ms.sourcegitcommit: 2bcc36916f0c591466eb3e007c2d30b99f2315c6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40009262"
---
# <a name="license-requirements-for-entities"></a>엔터티에 대한 라이선스 요구 사항
PowerApps 요금제 1 또는 Microsoft Flow 요금제 1 라이선스가 있는 사용자에 대해 앱 및 흐름을 만들려면 앱 작성자는 앱용 CDS(Common Data Service) 내에서 사용할 수 있는 엔터티 대부분(사용자 지정 엔터티 및 CDS의 일부인 엔터티 포함)을 사용할 수 있습니다. 경우에 따라 엔터티는 복잡한 비즈니스 논리를 포함하거나 앱 사용자에게 특정 라이선스를 취득하도록 요구하는 Dynamics 365 응용 프로그램에 연결됩니다. 


|엔터티    |설명    |요구 사항    |
|---------|---------|---------|
|복잡한 비즈니스 논리를 지닌 엔터티   | 이들은 복잡한 서버측 비즈니스 로직을 사용하는 엔터티입니다. 예를 들어, 실시간 워크플로 또는 코드 플러그인을 사용하는 엔터티.       |  [PowerApps 요금제 2](https://powerapps.microsoft.com/pricing/) 또는 [Flow 요금제 2](https://flow.microsoft.com/pricing/)        |
|제한된 엔터티  |  이는 앱용 Common Data Service에는 표준이 아니지만 Dynamics 365 고객 참여 응용 프로그램 또는 타사 솔루션에는 포함된 엔터티입니다. 예를 들어 기술 문서, 목표 및 권리 유형 엔터티.     |  [Dynamics 365 요금제](https://dynamics.microsoft.com/pricing/)      | 


> [!NOTE]
> 이러한 엔터티를 사용하는 앱 및 흐름은 앱 또는 흐름 개발자나 제작자가 아닌 앱 및 흐름 사용자에게 적절하게 라이선스를 취득하도록 요구합니다.

## <a name="entities-with-complex-business-logic"></a>복잡한 비즈니스 논리를 지닌 엔터티
다음과 같은 복잡한 서버측 논리를 포함하는 엔터티는 이러한 엔터티를 사용하는 앱 또는 흐름 사용자에게 PowerApps 요금제 2 또는 Microsoft Flow 요금제 2 라이선스를 취득하도록 요구합니다.

* 코드 플러그 인(자세한 내용은 [플러그 인 개발](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development) 참조)
* 실시간 워크플로(자세한 내용은 [워크플로 프로세스](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes) 참조)

    > [!NOTE]
    >  실시간 워크플로로 변환되는 워크플로만 실시간 및 동기적으로 간주됩니다. 백그라운드에서 실행되는 워크플로는 적절한 PowerApps 요금제로 계속 사용할 수 있으며 추가 라이선스를 요구하지 않습니다.

엔터티에 복잡한 비즈니스 논리를 추가했는지 여부를 알려면 사용자 환경에서 구성된 워크플로 및 플러그 인 어셈블리 목록을 검토합니다. Dynamics 365 응용 프로그램을 설치한 후 서버측 논리를 포함할 수 있는 엔터티 목록의 경우 [PowerApps 요금제 2 라이선스가 필요한 복잡한 엔터티](data-platform-complex-entities.md)를 참조하세요.  

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>복잡한 비즈니스 논리를 추가하는 경우 영향을 주는 라이선스 요구 사항
앱 작성자는 앱용 CDS 내에서 엔터티에 코드 플러그 인 및 실시간 워크플로를 추가할 수 있지만 그렇게 하면 이미 배포된 앱의 사용자에 대한 라이선스 요구 사항을 변경할 수 있습니다. 앱 작성자는 엔터티에 복잡한 비즈니스 논리를 추가하는 경우 조심해야 하며 먼저 엔터티를 사용하는 앱을 확인하고 이러한 앱 사용자가 적절한 라이선스가 있는지 확인해야 합니다.

## <a name="restricted-entities"></a>제한된 엔터티
Dynamics 365 응용 프로그램의 기능에 연결된 특정 엔터티는 해당 엔터티 내의 레코드를 만들고 업데이트하거나 삭제하려는 경우 앱 사용자에게 해당 응용 프로그램에 대한 해당 라이선스를 취득하도록 요구합니다. 제한된 엔터티의 전체 목록에 대해서는 [Dynamics 365 라이선스를 요구하는 제한된 엔터티](data-platform-restricted-entities.md)를 참조합니다.

## <a name="licensing-examples"></a>라이선스 예제
Barb과 Isaac은 앱용 CDS를 사용하여 PowerApps에서 앱을 만들어 해당 데이터를 저장합니다.

Barb은 다음 두 개의 캔버스 앱을 만듭니다.

* 앱 1 &ndash; 관련 정보를 저장하는 사용자 지정 엔터티 함께 연락처 엔터티 사용
* 앱 2 &ndash; 제한된 엔터티인 인시던트 엔터티와 함께 연락처 엔터티 사용

Isaac은 다음 두 가지 모델 기반 앱을 만듭니다.

* 앱 3 &ndash; 관련 정보를 저장하는 사용자 지정 엔터티 함께 연락처 엔터티 사용
* 앱 4 &ndash; 제한된 엔터티인 인시던트 엔터티와 함께 연락처 엔터티 사용

Barb과 Isaac은 다음의 라이선스가 필요합니다.
* Barb은 앱용 CDS를 사용하여 캔버스 앱을 만들려면 PowerApps 요금제 1 라이선스가 필요합니다. 데이터베이스 또는 사용자 지정 엔터티 만들어야 할 경우는 PowerApps 요금제 2 라이선스가 필요합니다.

* Isaac은 모델 기반 앱을 빌드하려면 PowerApps 요금제 2 라이선스가 필요합니다.

앱 사용자는 다음의 라이선스가 필요합니다.
* 앱이 비즈니스 논리 또는 제한된 엔터티가 있는 모든 엔터티를 포함하지 않기 때문에 앱 1 사용자는 PowerApps 요금제 1 또는 요금제 2 라이선스가 필요합니다.

* 앱이 제한된 엔터티를 포함하기 때문에 앱 2 사용자는 Dynamics 365 for Customer Service, Enterprise Edition 라이선스(또는 Dynamics 365 또는 Dynamics 365 Customer Engagement 요금제)가 필요합니다.

* 모델 기반 앱이므로 앱 3 사용자는 PowerApps 요금제 2 라이선스가 필요합니다.

* 앱이 제한된 엔터티를 포함하기 때문에 앱 4 사용자는 Dynamics 365 for Customer Service, Enterprise Edition 라이선스(또는 Dynamics 365 또는 Dynamics 365 Customer Engagement 요금제)가 필요합니다.

    Dynamics 365 for Customer Service 요금제는 사용자가 모델 기반 앱을 실행할 수 있는 PowerApps 요금제 2 라이선스를 포함합니다.

이제 Isaac과 Barb 모두가 해당 앱에서 사용하는 사용자 지정 엔터티에 Isaac이 실시간 워크플로를 추가하는 경우 어떻게 되는지 살펴보겠습니다.

Barb과 Isaac은 다음의 라이선스가 필요합니다.
* Barb은 앱용 CDS를 사용하여 캔버스 앱을 만들려면 여전히 PowerApps 요금제 1 라이선스가 필요합니다.

* Isaac은 모델 기반 앱을 빌드하려면 여전히 PowerApps 요금제 2 라이선스가 필요합니다.

앱 사용자는 다음의 라이선스가 필요합니다.
* 앱이 실시간 워크플로가 있는 엔터티를 포함하므로 이제 앱 1 사용자는 PowerApps 요금제 2 라이선스가 필요합니다.

* 앱이 제한된 엔터티를 포함하기 때문에 앱 2 사용자는 여전히 Dynamics 365 for Customer Service, Enterprise Edition 라이선스(또는 Dynamics 365 또는 Dynamics 365 Customer Engagement 요금제)가 필요합니다. 

* 모델 기반 앱이므로 앱 3 사용자는 여전히 PowerApps 요금제 2 라이선스가 필요합니다.

* 앱이 제한된 엔터티를 포함하기 때문에 앱 4 사용자는 여전히 Dynamics 365 for Customer Service, Enterprise Edition 라이선스(또는 Dynamics 365 또는 Dynamics 365 Customer Engagement 요금제)가 필요합니다.

    Dynamics 365 for Customer Service 요금제는 사용자가 모델 기반 앱을 실행할 수 있는 PowerApps 요금제 2 라이선스를 포함합니다.

이러한 변경의 영향을 받는 유일한 앱은 전에 PowerApps 요금제 1 라이선스를 필요했지만 지금은 복잡한 비즈니스 논리가 있는 엔터티를 포함하므로 PowerApps 요금제 2 라이선스가 필요한 앱 1입니다. 

## <a name="more-about-licensing"></a>라이선스에 대한 추가 정보
PowerApps 및 Dynamics 365 라이선스에 대한 자세한 내용은 [라이선스 개요](../../administrator/pricing-billing-skus.md)를 참조하십시오.
