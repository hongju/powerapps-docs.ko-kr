---
title: 공통 데이터 모델을 사용한 개발 | Microsoft Docs
description: 공통 데이터 모델을 사용하여 앱과 솔루션을 개발하는 방법에 대한 정보를 제공합니다.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 6e99fbe13d9b6e3acdd0cfdd08662676a321471c
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332093"
---
# <a name="how-to-use-the-common-data-model"></a>공통 데이터 모델을 사용하는 방법

**CDM(공통 데이터 모델)** 을 사용하면 일반적으로 사용되는 개념 및 활동을 나타내는 형식으로 데이터를 저장할 수 있으며, 데이터를 쿼리하고 재사용하며 해당 형식을 사용하는 다른 비즈니스 및 응용 프로그램과도 상호 운용할 수 있도록 광범위하게 사용되고 이해됩니다. 모든 원격 컨트롤에서 사용할 수 있도록 AA 배터리의 크기와 모양을 알고 있는 것과 마찬가지로 CDM은 *연락처*(예)의 크기와 모양을 정의합니다. 따라서 응용 프로그램 개발자 및 비즈니스 파트너는 해당 데이터를 처리하는 방법을 알고 민첩성과 신뢰성을 바탕으로 앱을 빌드(또는 상호 운용)할 수 있습니다. 그리고, CDM은 표준 엔터티의 오픈 소스 정의이므로 관심 있는 개발자 커뮤니티는 스키마 정의를 쉽게 이해하고 참여할 수 있습니다.

현재 CDM은 Dynamics 및 PowerApps를 지원하며 Power BI의 데이터 준비 기능을 통해 Azure Data Lake에서 스키마된 파일을 만드는 앱용 CDS(Common Data Service) 내에서 사용되고 있습니다.

![앱용 CDS를 사용하는 공통 데이터 모델](media/cdm-with-cds.png)

다음과 같은 방법으로 앱용 CDM 및 CDS를 사용할 수 있습니다.

-   **CDM 형식으로 데이터를 안전하게 저장 및 관리**: 앱용 CDS를 사용하여 CDM 형식으로 데이터를 안전하게 저장하고 관리할 수 있습니다. 이렇게 하면 Dynamics, Powerapps, Flow 또는 Power BI와 같은 Microsoft 앱 및 서비스 또는 고유의 사용자 지정 응용 프로그램에서 해당 데이터를 액세스하여 사용할 수 있습니다.

-   **사용자 지정 CDM 엔터티 만들기**: CDM은 확장 가능하므로 조직과 관련된 CDM에 아직 없는 모든 엔터티를 만들고 **파워 쿼리**를 사용하여 해당 엔터티를 기존 데이터로 채울 수 있습니다. 이렇게 하면 CDM의 이점을 활용하고 비즈니스에 맞게 조정할 수 있습니다.

-   **사용자 고유의 리포지토리 만들기**: **CDM(공통 데이터 모델)** 스키마를 준수하는 데이터 리포지토리를 빌드하고 Microsoft 데이터 커넥터를 사용하여 해당 데이터 원본에 연결할 수 있습니다. 이를 통해 데이터의 출처나 저장 위치에 상관없이 CDM 데이터를 사용하거나 공유하는 사용자 지정 LOB(기간 업무) 응용 프로그램을 빌드할 수 있습니다.

-   **Power BI를 통해 신속하게 인사이트 파생 및 배포**: Power BI에서 고급 데이터 준비 서비스를 사용하여 CDM 데이터 저장소(예: 앱용 CDS에 입력한 데이터)에 액세스하여 보고서 및 대시보드를 만든 다음, CDM 데이터를 조직의 개인 및 그룹에 대한 사용자 지정 인사이트로 자동으로 가져오는 보고서 생성 앱을 만듭니다.

-   **Power BI에서 사용자 지정이지만 조직 전체 보고서 생성**: 조직 및 그 이상의 사용자를 위해 Power BI 작업 영역에 배치할 수 있는 사용자 지정 보고서를 자동으로 생성하는 앱을 사용할 수 있습니다.

Microsoft가 여러 파트너 및 실무 전문가와 함께 CDM을 지속적으로 확장함에 따라, 의료 산업과 같은 새로운 산업은 CDM 및 이를 지원하는 플랫폼의 혜택을 활용할 수 있게 될 것입니다.

## <a name="data-integration-and-power-query-online"></a>데이터 통합 및 파워 쿼리 온라인

현재 CDM을 지원하는 두 플랫폼 모두 파워 쿼리 온라인을 통해 데이터 통합 환경을 제공하므로 사용자가 다양한 소스에서 데이터를 가져와서 필요한 경우 변환한 다음, 표준 CDM 엔터티에 매핑하거나 사용자 지정 엔터티를 만들 수 있습니다. 파워 쿼리 온라인은 Excel 및 Power BI Desktop 내의 파워 쿼리와 동일한 시각적 개체에서 셀프 서비스 데이터 준비 환경을 활용하므로 기존 사용자도 신속하게 증가시킬 수 있습니다.

![CDM의 엔터티를 사용하여 데이터 매핑](media/cdm-map-entities.png)

## <a name="common-data-service-for-apps"></a>앱용 Common Data Service

앱용 CDS를 사용하면 비즈니스 논리, 보안 및 통합 기능이 기본 제공되는 CDM을 사용하여 앱을 시작할 수 있습니다. 플랫폼을 통해 다음을 수행할 수 있습니다.

-   **패키지 비즈니스 응용 프로그램 활용**: 많은 Microsoft Dynamics 솔루션과 많은 타사 응용 프로그램이 앱용 CDS를 기반으로 빌드(또는 적어도 활용)되었습니다. 데이터가 CDM에 있으면 패키지된 해당 응용 프로그램을 활용할 수 있습니다.

-   **사용자 지정 솔루션에 대한 액세스 권한 확보**: CDM 형식으로 데이터를 이해하고 사용하는 개발자가 만든 확장 및 완벽한 응용 프로그램의 에코 시스템이 존재합니다. 자세한 내용은 [솔루션 소개](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions)를 참조하세요.

CDM은 의도와 상관없이 데이터를 공통 형식으로 저장하여 보다 쉽게 사용, 공유 및 분석할 수 있도록 합니다.

**앱용 CDS에 대한 리소스**

-   [앱용 CDS란?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)

-   [파워 쿼리를 사용하여 앱용 CDS의 엔터티에 데이터 추가](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-cds-newentity-pq)

-   [솔루션 소개](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions)

-   [모델 기반 앱 빌드](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview)

-   [캔버스 앱 빌드](https://docs.microsoft.com/powerapps/maker/canvas-apps/getting-started)

-   [앱용 CDS를 사용하는 흐름 만들기](https://docs.microsoft.com/flow/common-data-model-intro)

