---
title: 공용 데이터 모델 개요 | Microsoft Docs
description: 공용 데이터 모델이 Common Data Service for Apps를 Common Data Service for Analytics에 연결하는 방법을 알아봅니다.
services: ''
suite: powerapps
documentationcenter: na
author: RobertBruckner
manager: lmollico
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/14/2018
ms.author: jdaly
ms.openlocfilehash: 5fb747d94b5af47717debba2341a9914664a27bd
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="common-data-model-overview"></a>공통 데이터 모델 개요

**CDM(공용 데이터 모델)**은 다양한 비즈니스 및 응용 프로그램 도메인에서 일반적으로 사용되는 개념과 활동을 나타내는 표준 엔터티의 오픈 소스 정의입니다. 공용 데이터 모델은 계정, 사업부, 사례, 연락처, 잠재 고객, 영업 기회, 제품 등과 같은 *잘 정의되고 확장 가능한 모듈식* 비즈니스 엔터티뿐 아니라 공급업체, 작업자, 고객 간의 활동이나 서비스 수준 계약 같은 상호 작용 및 관계를 제공합니다. 

Microsoft의 [Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) 및 Common Data Service for Analytics<!-- TODO add link when available  -->는 공용 데이터 모델을 구현합니다. 이러한 서비스는 공용 데이터 모델 정의를 따르는 데이터를 보관합니다. 이러한 서비스를 기반으로 빌드하면 데이터가 어디서 오는지 또는 어디서 사용되는지에 관계없이 패키지에 포함된 응용 프로그램 및 분석 솔루션이 잘 정의된 엔터티 셰이프와 함께 작동하고 데이터를 공유할 수 있습니다. 사용자 지정 기간 업무 앱 및 분석 솔루션은 데이터 공유에 동일한 엔터티를 활용할 수 있으며, 그렇게 함으로써 특정 요구 사항 및 비즈니스 요구 사항을 지원할 수 있습니다. 

Microsoft 및 파트너는 Common Data Service를 기반으로 응용 프로그램을 빌드하고 비즈니스 데이터를 CDM 형태로 저장하기 위해 최선을 다하고 있습니다. *데이터가 CDM 형태로 저장될 때 효율적으로 작동하는 계속 성장 중인 대규모 솔루션 컬렉션*이 있습니다. 다시 말해서 마찰이나 복잡성 없이 신속하게 새 비즈니스 프로세스를 구현하여 비즈니스 운영에 대한 정보를 얻을 수 있습니다. 다음 다이어그램은 공용 데이터 모델 엔터티를 활용하는 Common Data Services 기반의 응용 프로그램을 보여줍니다.

![공용 데이터 모델 엔터티를 활용하는 Common Data Services 기반의 응용 프로그램](media/cdm-overview.png)

공용 데이터 모델은 데이터를 *응용 프로그램 및 배포에서 구조적 및 의미적 일관성*을 갖는 알려진 형식으로 통합하여 데이터 관리 과제를 간소화합니다. 이는 비즈니스 프로세스, 디지털 상호 작용, 제품 원격 분석, 사용자 상호 작용 등에서 수집한 *데이터를 통합 및 구분*하는 데 도움이 됩니다. 

Common Data Service for Apps에 저장된 데이터는 두 서비스를 사용하는 고객을 위해 Common Data Service for Analytics와 *간편하게 자동으로 통합*됩니다. 고객은 이미 갖고 있는 엔터프라이즈 및 트랜잭션 데이터(잠재 고객, 캠페인 정보, 이전 고객 구매 정보 등)로 시작하여 다른 소스(웹 블로그, 제품 원격 분석 등)의 데이터와 결합하여 통합된 그림을 얻을 수 있습니다.

또한 공용 데이터 모델은 *확장 가능*합니다. CDM과 함께 제공되는 사용자 지정 가능한 엔터티에 필드를 추가하거나 고유의 사용자 지정 엔터티를 만들 수 있습니다. CDM 표준은 판매, 마케팅, 운영, 재무, 인력 및 상업에 이르는 비즈니스 프로세스 전체 범위를 아우르는 비즈니스 엔터티에 대한 공통 언어를 정의하고, 고객의 경우 회사의 비즈니스 프로세스 중심에 있는 사람 및 제품 엔터티를 정의합니다. 공용 데이터 모델은 여러 채널, 서비스 구현 및 공급업체에 걸쳐 데이터 상호 운용성을 용이하게 합니다.

공용 데이터 모델 및 Common Data Service는 다음 기능을 통해 풍부하고 생산성 높은 개발 플랫폼을 제공합니다.

- **표준 엔터티 정의** – 공용 데이터 모델은 비즈니스 및 생산성 응용 프로그램에서 가장 일반적으로 사용되는 엔터티를 나타내는 엔터티 정의를 제공합니다. 공용 CDM GitHub 리포지토리[(https://github.com/Microsoft/CDM)](https://github.com/Microsoft/CDM))는 지속적으로 전체 비즈니스 프로세스 환경, 추가적인 수직 산업 데이터 모델 그리고 설문 조사, 검색 엔진, 제품 원격 분석 등의 교차 범위 소스를 아우르는 핵심 엔터티를 통해 개선됩니다.
- **데이터 통합** – 기본 제공 웹 경험으로 Microsoft Excel용 파워 쿼리를 사용하여 기존 시스템에서 데이터를 가져와 시각적으로 변환하고, 온라인 및 온-프레미스 소스의 데이터를 코드와 결합하지 않거나 로우 코드와 결합합니다. Excel 및 Power BI 데이터 변환 기술이 매끄럽게 적용됩니다. [Microsoft Excel용 파워 쿼리를 사용하여 Common Data Service의 엔터티에 데이터 추가](../maker/common-data-service/data-platform-cds-newentity-pq.md)를 참조하세요.
    
    Common Data Service로 데이터를 가져온 후에는 표준 공용 데이터 모델 엔터티에 데이터를 매핑해도 되고, 새 엔터티를 만들어서 매핑해도 됩니다. 기본 데이터 통합 및 매핑 템플릿은 Salesforce 같은 일반 데이터 소스에 대한 연결 작업을 간소화합니다. 이러한 매핑 템플릿은 원하는 대로 사용자 지정하고 확장할 수 있습니다. 다음 스크린샷은 외부 데이터를 가져와서 Microsoft Excel용 파워 쿼리의 표준 엔터티에 매핑하는 방법을 보여줍니다. 
    
    ![외부 데이터를 가져와서 Microsoft Excel용 파워 쿼리의 표준 엔터티에 매핑 ](media/cdm-mapping-entities.png)<br />

- **확장성** – 다른 앱과의 데이터 공유를 중단하지 않고 엔터티를 확장할 수 있습니다.
- **의존성** – 공용 엔터티에 의존할 수 있으므로 엔터티에 바인딩되는 재사용 가능한 구성 요소를 빌드할 수 있습니다. 공용 데이터 모델은 개발 투자를 보호하는 확장성 및 버전 관리를 지원합니다.
- **배포의 엔터티 일관성** – 솔루션이 생산성 플랫폼의 정보를 비즈니스 응용 프로그램의 데이터와 연결할 수 있습니다. 예를 들어 일정 약속 또는 Microsoft Outlook 작업을 영업 기회와 연결할 수 있습니다. 

[Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md)는 공통 데이터 모델을 구현하고, 다음과 같은 비즈니스 응용 프로그램 개발을 허용합니다.

- **패키지 비즈니스 응용 프로그램 활용** – 마케팅, 영업, 서비스, 인력, 재무 및 운영 응용 프로그램을 위한 Dynamics 365와 타사 응용 프로그램은 Common Data Service for Apps를 활용하고/활용하거나 Common Data Service for Apps를 기반으로 빌드됩니다.
- **응용 프로그램을 사용자 지정하고 요구 사항에 대한 기본 확장 빌드** - 사용자 지정자와 개발자는 잘 정의된 응용 프로그램 수명 주기를 사용하여 응용 프로그램 솔루션을 배포합니다. 솔루션은 응용 프로그램 및 확장이 배포되는 방식입니다. [솔루션 소개](../developer/common-data-service/introduction-solutions.md)를 참조하세요.
- **PowerApps를 사용하여 무코드/로우 코드, 모델 기반 및 WYSIWYG 캔버스 앱 빌드** - 패키지 응용 프로그램 또는 타사 응용 프로그램에서 만든/사용하는 것과 동일한 공유 엔터티를 사용하여 추가 독립 실행형 앱을 만듭니다. 참조 항목: 
    - [모델 기반 앱 빌드](../maker/model-driven-apps/model-driven-app-overview.md)
    - [캔버스 앱 빌드](../maker/canvas-apps/getting-started.md) 
- **흐름을 사용하여 비즈니스 프로세스 자동화** - 비즈니스 프로세스 흐름을 사용하여 원하는 결과를 달성하기 위한 스테이지 및 단계 집합을 정의합니다. [Common Data Service를 사용하는 흐름 만들기](/flow/common-data-model-intro)를 참조하세요.
 
예정된 **Common Data Service for Analytics** <!-- TODO add link when available  --> 공개 미리 보기 역시 공통 데이터 모델을 구현하며, 다음을 포함한 표준화된 형식으로 비즈니스 데이터 분석을 지원합니다.

- **표준 데이터 엔터티를 기반으로 하는 패키징되고 사용자 지정된 분석 솔루션** – 과거의 영업 실적을 추적하는 Sales Insights 같은 분석 응용 프로그램은 데이터가 원래 어디서 사용되었는지에 관계없이 일관적인 통찰력을 제공합니다. 데이터 통합 환경에서 다른 소스(예: Salesforce.com)의 데이터를 공통 데이터 모델 엔터티 셰이프에 매핑하기 때문입니다. 이렇게 하면 분석 솔루션이 잠재 고객, 영업 기회 등 잘 정의된 엔터티의 데이터 의미 체계에 집중하도록 간소화됩니다.
- **무코드/로우 코드 파워 쿼리 데이터 통합** – 기본 제공 환경을 사용하여 엔터티를 만들고, 채우고, 변환하고, 보강합니다. 
- **사용자 고유의 Azure 저장소 가져오기** – Azure 데이터 스택을 활용하여 Common Data Service for Analytics에 데이터를 사용할 수 있습니다. 엔터티는 동일한 공통 데이터 모델 형식으로 저장되어 분석 솔루션을 통해 인식됩니다.

