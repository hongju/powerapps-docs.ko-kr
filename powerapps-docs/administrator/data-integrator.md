---
title: 앱용 Common Data Service에 데이터 통합
description: 여러 원본의 데이터를 앱용 Common Data Service에 통합
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 10/15/2018
ms.author: sabinn
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: dfbc420dfb4945cdda635e3cbaadb1acb446753b
ms.sourcegitcommit: ebd39753e2a0b60c1d8c016e38c00dd1accf5d0c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328697"
---
# <a name="integrate-data-into-common-data-service-for-apps"></a>앱용 Common Data Service에 데이터 통합

<!--note from editor: the style guide says not to use "the" in front of Common Data Service for Apps, so I'm removing that.-->

Data Integrator(관리자용)는 앱용 Common Data Service에 데이터를 통합하는 데 사용되는 지점 간 통합 서비스입니다. Dynamics 365 for Finance and Operations, Dynamics 365 for Sales and SalesForce(미리 보기), SQL(미리 보기) 등 여러 원본의 데이터를 앱용 Common Data Service에 통합할 수 있도록 지원합니다. Dynamics 365 for Finance and Operations 및 Dynamics 365 for Sales에 데이터를 통합하는 기능도 지원합니다. 이 서비스는 2017년 7월 이후에 일반 공급되었습니다.  

Microsoft는 Dynamics 365 for Finance and Operations, Dynamics 365 for Sales 등의 자사 앱부터 시작했습니다. 파워 쿼리 또는 M 기반 커넥터의 도움을 받아, 이제 SalesForce(미리 보기) 및 SQL(미리 보기)과 같은 추가 원본을 지원할 수 있으며, 곧 20개 이상의 원본까지 확장할 예정입니다. 

> [!div class="mx-imgBorder"]
> ![대상에 대한 데이터 원본](media/data-integrator/DataIntegratorP2P-new.PNG "대상에 대한 데이터 원본")

## <a name="how-can-you-use-the-data-integrator-for-your-business"></a>어떻게 Data Integrator를 해당 비즈니스에 사용할 수 있을까요?

Data Integrator(관리자용)는 Dynamics 365 for Finance and Operations 및 Dynamics 365 for Sales 간에 직접적인 동기화를 제공하는, 현금에 대한 전망 등의 프로세스 기반 통합 시나리오도 지원합니다. 데이터 통합 기능과 함께 제공되는 현금에 대한 전망 템플릿을 통해 계정, 담당자, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 Finance and Operations 및 Sales 간에 유지되도록 할 수 있습니다. Finance and Operations 및 Sales 간에 데이터 흐름이 진행되는 동안, Sales에서는 판매 및 마케팅 활동을 수행하고 Finance and Operations에서는 재고 관리를 사용하여 주문 이행을 처리할 수 있습니다. 

> [!div class="mx-imgBorder"]
> ![현금에 대한 전망](media/data-integrator/ProspectToCash631.png "현금에 대한 전망")

현금에 대한 전망 통합을 사용하면 Finance and Operations의 풍부한 기능을 사용하여 주문 이행 및 송장 발행의 모든 측면이 수행되는 동시에 판매자가 Dynamics 365 for Sales의 강점을 활용하여 판매 프로세스를 처리 및 모니터링할 수 있습니다. Microsoft Dynamics 365 현금에 대한 전망 통합을 사용하면 두 시스템의 기능을 모두 활용할 수 있습니다. 

비디오: [현금에 대한 전망 통합](https://www.youtube.com/watch?v=AVV9x5x-XCg)을 보세요.

현금에 대한 전망 통합에 대한 자세한 내용은 [현금에 대한 전망 솔루션](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/prospect-to-cash) 관련 설명서를 참조하세요.

Microsoft는 Dynamics 365 for Finance and Operations에 대한 [현장 서비스 통합](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order) 및 [PSA(Project Service Automation) 통합](https://docs.microsoft.com/dynamics365/unified-operations/financials/project-management/psa-integration?toc=/fin-and-ops/toc.json)도 지원합니다.

## <a name="data-integrator-platform"></a>Data Integrator 플랫폼

Data Integrator(관리자용)는 데이터 통합 플랫폼, Dynamics 365 for Finance and Operations, Dynamics 365 for Sales 등의 응용 프로그램 팀이 제공하는 기본 제공 템플릿 및 고객과 파트너가 만든 사용자 지정 템플릿으로 구성됩니다. Microsoft는 다양한 원본으로 확장될 수 있는 응용 프로그램 중립적 플랫폼을 빌드했습니다. 이 플랫폼의 핵심은, 통합 엔드포인트에 대한 연결을 만들고 미리 정의된 매핑이 있는 사용자 지정 가능한 템플릿 중 하나를 선택한 다음, 데이터 통합 프로젝트를 만들고 실행하는 것입니다.  

통합 템플릿은 원본에서 대상으로의 데이터 흐름을 가능하게 하는 미리 정의된 엔터티 및 필드 매핑이 있는 청사진 역할을 합니다. 또한 데이터를 가져오기 전에 변환하는 기능을 제공합니다. 원본 및 대상 앱 간에 스키마가 매우 다른 경우가 많으며, 미리 정의된 엔터티 및 필드 매핑이 있는 템플릿은 통합 프로젝트의 훌륭한 시작점 역할을 합니다.  

> [!div class="mx-imgBorder"]
> ![데이터 통합 플랫폼](media/data-integrator/DIPlatform.PNG "데이터 통합 플랫폼")

## <a name="how-to-set-up-a-data-integration-project"></a>데이터 통합 프로젝트를 설정하는 방법

다음 세 가지 기본 단계가 있습니다.

1. 연결을 만듭니다(데이터 원본에 자격 증명 정보 제공).

2. 연결 집합을 만듭니다(이전 단계에서 만든 연결의 환경 식별).

3. 템플릿을 사용하여 데이터 통합 프로젝트를 만듭니다(하나 이상의 엔터티에 대해 미리 정의된 매핑 만들기 또는 사용).

통합 프로젝트를 만들고 나면 프로젝트를 수동으로 실행하는 옵션이 표시되며, 나중을 위해 일정 기반의 새로 고침도 설정합니다. 이 문서의 나머지 부분에서는 이 세 단계를 확장합니다.

### <a name="how-to-create-a-connection"></a>연결을 만드는 방법

데이터 통합 프로젝트를 만들려면 먼저 Microsoft PowerApps 포털에서 사용하려는 각 시스템에 대한 연결을 프로비전해야 합니다. 이러한 연결을 통합 지점으로 간주하면 됩니다.

**연결을 만들려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 데이터 아래에서 **연결**을 선택한 다음, **새 연결**을 선택합니다.

3. 연결 목록에서 연결을 선택하거나 연결을 검색할 수 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![연결 만들기](media/data-integrator/CreateConnection780.png "연결 만들기")

4. 연결을 선택했으면 **만들기**를 선택합니다. 자격 증명을 입력하라는 메시지가 표시됩니다.

5. 자격 증명을 입력하면 연결 아래에 해당 연결이 나열됩니다.

    > [!div class="mx-imgBorder"] 
    > ![연결 목록](media/data-integrator/CreateConnection1780.png "연결 목록")

> [!NOTE]
> 각 연결을 위해 지정하는 계정이 해당 응용 프로그램의 엔터티에 액세스할 수 있는지 확인하세요. 또한 각 연결을 위한 계정이 다른 테넌트에 있을 수 있습니다. 

### <a name="how-to-create-a-connection-set"></a>연결 집합을 만드는 방법

연결 집합은 두 가지 연결, 연결 환경, 조직 매핑 정보 및 프로젝트 간에 재사용할 수 있는 통합 키의 컬렉션입니다. 개발용 연결 집합을 사용한 후 다른 프로덕션용 연결 집합으로 전환할 수 있습니다. 연결 집합과 함께 저장되는 한 가지 주요 정보는 조직 단위 매핑입니다. 예를 들어 Finance and Operations 법인(또는 회사)과 Dynamics 365 for Sales 조직 또는 비즈니스 단위 간의 매핑입니다. 하나의 연결 집합에 여러 개의 조직 매핑을 저장할 수 있습니다.

**연결 집합을 만들려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 왼쪽 탐색 창에서 **데이터 통합** 탭을 선택합니다.

3. **연결 집합** 탭을 선택하고 **새 연결 집합**을 선택합니다.

4. 연결 집합의 이름을 입력합니다.
  
    > [!div class="mx-imgBorder"] 
    > ![연결 집합 만들기](media/data-integrator/CreateConnectionSet1780.png "연결 집합 만들기")
  
5. 앞에서 만든 연결을 선택하고 적절한 환경을 선택합니다.

6. 다음 연결을 선택하여 단계를 반복합니다(특정 순서 없이 원본 및 대상으로 간주하면 됨).

7. 조직-비즈니스 단위 매핑을 지정합니다(Finance and Operations 및 Sales 시스템 간에 통합하는 경우).
  
    > [!NOTE]
    > 연결 집합마다 여러 개의 매핑을 지정할 수 있습니다.
  
8. 모든 필드에 정보를 입력했으면 **만들기**를 선택합니다.

9. 방금 만든 새 연결 집합이 연결 집합 목록 페이지 아래에 표시됩니다.
    
    > [!div class="mx-imgBorder"] 
    > ![연결 집합 목록](media/data-integrator/CreateConnectionSet2780.png "연결 집합 목록")

연결 집합이 다양한 통합 프로젝트에서 사용할 준비가 되었습니다.

### <a name="how-to-create-a-data-integration-project"></a>데이터 통합 프로젝트를 만드는 방법

프로젝트는 시스템 간에 데이터 흐름을 유지합니다. 프로젝트마다 하나 이상의 엔터티에 대한 매핑이 포함됩니다. 매핑은 각 필드에 매핑되는 필드를 나타냅니다.

**데이터 통합 프로젝트를 만들려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 왼쪽 탐색 창에서 **데이터 통합** 탭을 선택합니다.

3. **프로젝트** 탭에서 오른쪽 위에 있는 **새 프로젝트**를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![프로젝트 만들기](media/data-integrator/CreateNewProject780.png "프로젝트 만들기")

4. 통합 프로젝트의 이름을 입력합니다.

5. 사용 가능한 템플릿 중 하나를 선택하거나 [사용자 고유의 템플릿을 만듭니다](#how-to-customize-or-create-your-own-template). 이 예제에서는 Products 엔터티를 Finance and Operations에서 Sales로 이동합니다.

    > [!div class="mx-imgBorder"] 
    > ![새 프로젝트를 만들기 위한 템플릿 선택](media/data-integrator/CreateNewProjectSelectTemplate780.png "새 프로젝트를 만들기 위한 템플릿 선택")

6. **다음**을 선택하고 앞에서 만든 연결 집합을 선택하거나 [새 연결 집합을 만듭니다](#how-to-create-a-connection-set).

7. 연결 및 환경 이름을 확인하여 올바른 항목을 선택했는지 확인합니다.

    > [!div class="mx-imgBorder"] 
    > ![새 연결 집합 만들기](media/data-integrator/CreateNewProjectSelectConnectionSet780.png "새 연결 집합 만들기")

8. **다음**을 선택하고 법인-비즈니스 단위 매핑을 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![새 법인 매핑 만들기](media/data-integrator/CreateNewProjectLegalEntityMapping780.png "새 법인 매핑 만들기")

9. 다음 화면에서 개인정보처리방침 및 동의를 검토하고 동의합니다.

10. 계속해서 프로젝트를 만든 후 프로젝트를 실행합니다. 그러면 프로젝트가 실행됩니다.

    > [!div class="mx-imgBorder"] 
    > ![프로젝트 실행](media/data-integrator/RunProject780.png "프로젝트 실행")

    이 화면에는 여러 개의 탭(**예약** 및 **실행 기록**)과 단추(**작업 추가**, **엔터티 새로 고침** 및 **고급 쿼리**)가 표시됩니다. 이러한 항목에 대해서는 이 문서의 뒷부분에서 설명합니다.

### <a name="execution-history"></a>실행 기록

실행 기록은 프로젝트 이름, 프로젝트가 실행된 시간의 타임스탬프, 실행 상태와 upsert(업데이트/삽입) 및 오류 수가 포함된 모든 프로젝트 실행 기록을 보여 줍니다.

-   프로젝트 실행 기록의 예입니다.

    > [!div class="mx-imgBorder"] 
    > ![프로젝트 실행 기록](media/data-integrator/ExecutionHistorySuccessFailures4780.png "프로젝트 실행 기록")

-   upsert(업데이트/삽입) 수와 함께 완료 상태를 표시하는 성공적인 실행의 예입니다. Upsert(업데이트/삽입)는 레코드를 업데이트하거나(레코드가 이미 있는 경우) 새 레코드를 삽입하는 논리입니다.

    > [!div class="mx-imgBorder"] 
    > ![실행 성공](media/data-integrator/ExecutionHistorySuccess2780.png "실행 성공")

-   실행 실패의 경우, 드릴다운하여 근본 원인을 확인할 수 있습니다.

    다음은 프로젝트 유효성 검사 오류로 인한 실패의 예입니다. 이 예제에서는 엔터티 매핑에 원본 필드가 누락되어 프로젝트 유효성 검사 오류가 발생합니다.

    > [!div class="mx-imgBorder"] 
    > ![실행 기록 실패](media/data-integrator/ExecutionHistoryFailures3780.png "실행 기록 실패")

-   프로젝트 실행이 ‘오류’ 상태이면 다음 예약된 실행에서 실행이 다시 시도됩니다.

-   프로젝트 실행이 ‘경고’ 상태이면 원본에서 문제를 해결해야 합니다. 다음 예약된 실행에서 실행이 다시 시도됩니다.

    두 경우 모두, 수동으로 ‘실행 다시 실행’을 선택할 수도 있습니다.

### <a name="how-to-set-up-a-schedule-based-refresh"></a>일정 기반의 새로 고침을 설정하는 방법

Microsoft는 현재 다음 두 가지 유형의 실행/쓰기를 지원합니다.

-   수동 쓰기(수동으로 프로젝트 실행 및 새로 고침)

-   일정 기반의 쓰기(자동 새로 고침)

통합 프로젝트를 만들고 나면 수동으로 실행하거나, 일정 기반의 쓰기를 구성하여 프로젝트에 대한 자동 새로 고침을 설정할 수 있는 옵션이 표시됩니다.

**일정 기반의 쓰기를 설정하려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 두 가지 방법으로 프로젝트를 예약할 수 있습니다.<br>

    프로젝트를 선택하고 **예약** 탭을 선택하거나, 프로젝트 목록 페이지에서 프로젝트 이름 옆의 줄임표를 클릭하여 스케줄러를 시작합니다.

    > [!div class="mx-imgBorder"] 
    > ![일정 기반의 쓰기](media/data-integrator/Schedulebasedwrites780.png "일정 기반의 쓰기")

3. **되풀이 간격**을 선택하고, 모든 필드에 정보를 입력했으면 **일정 저장**을 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![일정 기반의 쓰기](media/data-integrator/Schedulebasedwrites1780.png "일정 기반의 쓰기")

빈도를 1분까지 짧게 설정하거나 특정 시간, 일, 주 또는 월 수마다 되풀이되도록 설정할 수 있습니다. 이전 프로젝트 작업을 실행 완료하기 전에는 다음 새로 고침이 시작되지 않습니다.

알림 아래에서 완료되었지만 경고가 발생했거나 오류로 인해 실패한 작업 실행에 대해 경고하는 메일 기반 경고 알림을 옵트인(opt in)할 수 있습니다. 쉼표로 구분된 그룹을 포함하여 여러 명의 수신자를 제공할 수 있습니다.

> [!div class="mx-imgBorder"] 
> ![메일 알림](media/data-integrator/EmailNotification780.png "메일 알림")

> [!NOTE]
> - 현재 특정 시간에 유료 테넌트당 50개의 통합 프로젝트를 예약하는 기능을 지원합니다. 그러나 추가 프로젝트를 만들고 대화형으로 실행할 수 있습니다.
평가판 테넌트의 경우 예약된 프로젝트가 처음 50개 실행을 대상으로만 실행된다는 추가 제한 사항이 있습니다.
> - 항상 실행하도록 프로젝트를 예약할 수 있지만, 이로 인해 앱에 많은 스트레스가 가해지고 결국 전체 성능에 영향을 줄 수 있다는 점을 염두에 두세요. 사용자는 실제 로드 조건에서 프로젝트 실행을 테스트하고 새로 고침 빈도를 줄여 성능을 최적화하는 것이 좋습니다.
프로덕션 환경에서는 테넌트당 5개 이하의 프로젝트를 실행하는 것이 좋습니다.

## <a name="customizing-projects-templates-and-mappings"></a>프로젝트, 템플릿 및 매핑 사용자 지정 

템플릿을 사용하여 데이터 통합 프로젝트를 만듭니다. 템플릿은 데이터 이동을 상용화하여, 비즈니스 사용자 또는 관리자가 원본에서 대상으로 데이터를 빠르게 통합하도록 지원하고 전반적인 부담과 비용을 줄입니다. 비즈니스 사용자 또는 관리자는 Microsoft 또는 파트너가 게시한 즉시 사용 가능한 템플릿으로 시작한 다음, 프로젝트를 만들기 전에 추가로 사용자 지정할 수 있습니다. 프로젝트를 템플릿으로 저장하고 조직과 공유하거나 새 프로젝트를 만들 수 있습니다. 

템플릿은 데이터 흐름의 원본, 대상 및 방향을 제공합니다. 사용자 고유의 템플릿을 사용자 지정하고 만드는 동안 이 점에 유의해야 합니다.  

다음과 같은 방법으로 프로젝트 및 템플릿을 사용자 지정할 수 있습니다.

-   필드 매핑을 사용자 지정합니다.

-   선택한 엔터티를 추가하여 템플릿을 사용자 지정합니다.

### <a name="how-to-customize-field-mappings"></a>필드 매핑을 사용자 지정하는 방법

**연결 집합을 만들려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 필드 매핑을 사용자 지정하려는 프로젝트를 선택하고 원본 및 대상 필드 간의 화살표를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![필드 매핑](media/data-integrator/FieldMapping780.png "필드 매핑")

3. 그러면 매핑 화면으로 이동되며, 여기서 오른쪽 위에 있는 **매핑 추가** 또는 드롭다운 목록의 **기존 매핑 사용자 지정**을 선택하여 새 매핑을 추가할 수 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![필드 매핑 사용자 지정](media/data-integrator/FieldMappingCustomize780.png "필드 매핑 사용자 지정")

4. 필드 매핑을 사용자 지정했으면 **저장**을 선택합니다.

### <a name="how-to-customize-or-create-your-own-template"></a>사용자 고유의 템플릿을 사용자 지정하거나 만드는 방법 

**사용자 고유의 템플릿을 만들려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 새 템플릿의 원본 및 대상과 흐름 방향을 식별합니다.

3. 선택한 원본 및 대상과 흐름 방향에 일치하는 기존 템플릿을 선택하여 프로젝트를 만듭니다.

<!--note from editor: Didn't we create the project in step 3? Step 4 tells us to create the project.-->

4. 적절한 연결을 선택한 후 프로젝트를 만듭니다.

5. 프로젝트를 저장 및/또는 실행하기 전에 오른쪽 위에서 **작업 추가**를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정](media/data-integrator/CustomizeTemplate780.png "템플릿 사용자 지정")

    **작업 추가** 대화 상자가 시작됩니다.

6. 의미 있는 작업 이름을 입력하고 선택한 원본 및 대상 엔터티를 추가합니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정 작업 추가](media/data-integrator/CustomizeTemplateAddtask75.png "템플릿 사용자 지정 작업 추가")

7. 드롭다운 목록에 모든 원본 및 대상 엔터티가 표시됩니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정 작업 추가](media/data-integrator/CustomizeTemplateAddtask175.png "템플릿 사용자 지정 작업 추가")

    이 예제에서는 SalesForce의 User 엔터티를 앱용 Common Data Service의 Users 엔터티에 동기화하는 새 작업이 생성되었습니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정 작업 추가](media/data-integrator/CustomizeTemplateAddtask275.png "템플릿 사용자 지정 작업 추가")

8. 작업을 만들고 나면 새 작업이 나열되며 원래 작업을 삭제할 수 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정 작업 추가](media/data-integrator/CustomizeTemplateAddtask3780.png "템플릿 사용자 지정 작업 추가")

9. 이제 새 템플릿을 만들었습니다. 이 예제에서는 SalesForce의 User 엔터티 데이터를 Common Data Service로 끌어오는 템플릿입니다. **저장**을 선택하여 사용자 지정을 저장합니다.

10. 새 템플릿에 대한 필드 매핑을 사용자 지정하는 단계를 수행합니다. **프로젝트 목록** 페이지에서 이 프로젝트를 실행하거나 프로젝트를 템플릿으로 저장할 수 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정 템플릿으로 저장](media/data-integrator/CustomizeTemplateSaveAsTemplate780.png "템플릿 사용자 지정 템플릿으로 저장")

11. 이름 및 설명을 입력하거나 조직의 다른 사용자와 공유합니다.

    > [!div class="mx-imgBorder"] 
    > ![템플릿 사용자 지정 템플릿으로 저장](media/data-integrator/CustomizeTemplateSaveAsTemplate175.png "템플릿 사용자 지정 템플릿으로 저장")

## <a name="advanced-data-transformation-and-filtering"></a>고급 데이터 변환 및 필터링 

파워 쿼리 지원을 활용하여 이제 원본 데이터의 고급 필터링 및 데이터 변환 기능을 제공합니다. 파워 쿼리를 사용하면 편리하고 매력적이며 코드가 필요 없는 사용자 환경을 통해 데이터 모양을 사용자 요구에 맞게 변경할 수 있습니다. 이 기능은 프로젝트 단위로 사용하도록 설정할 수 있습니다. 

### <a name="how-to-enable-advanced-query-and-filtering"></a>고급 쿼리 및 필터링을 사용하도록 설정하는 방법

**고급 필터링 및 데이터 변환을 설정하려면**

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동합니다.

2. 고급 쿼리를 사용하도록 설정할 프로젝트를 선택하고 **고급 쿼리**를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![고급 쿼리 선택](media/data-integrator/EnablePQ1780.png "고급 쿼리 선택")

3. 고급 쿼리를 사용하도록 설정한 후에는 작업을 취소할 수 없다는 경고가 표시됩니다. **확인**을 선택하여 계속하고 원본 및 대상 매핑 화살표를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![경고](media/data-integrator/EnablePQ275.png "경고")

4. 이제 고급 쿼리 및 필터링을 시작하는 링크가 있는 익숙한 엔터티 매핑 페이지가 표시됩니다.

    > [!div class="mx-imgBorder"] 
    > ![고급 쿼리 및 필터링](media/data-integrator/EnablePQ3780.png "고급 쿼리 및 필터링")

5. **대상 링크**를 선택하여 고급 쿼리 및 필터링 사용자 인터페이스를 시작합니다. 이 인터페이스는 Microsoft Excel 형식의 열에 원본 필드 데이터를 제공합니다.

    > [!div class="mx-imgBorder"] 
    > ![고급 쿼리 및 필터링](media/data-integrator/EnablePQ4780.png "고급 쿼리 및 필터링")

6. 맨 위 메뉴에는 **조건부 열 추가**, **열 복제**, **추출** 등 여러 가지 데이터 변환 옵션이 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![열 추가](media/data-integrator/EnablePQAddColumn75.png "열 추가")

7. 열을 마우스 오른쪽 단추로 클릭하여 **열 제거**, **중복된 항목 제거**, **열 분할** 등의 추가 옵션을 표시할 수도 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![열을 마우스 오른쪽 단추로 클릭](media/data-integrator/EnablePQAddColumn180.png "열을 마우스 오른쪽 단추로 클릭")

8. 각 열을 클릭하고 Excel 형식 필터를 사용하여 필터링할 수도 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![필터링 사용](media/data-integrator/EnablePQFiltering80.png "필터링 사용")

<!--note from editor: I don't see an "otherwise" in the screenshot. I see "else".-->

9. 조건부 열을 사용하여 기본값을 변환할 수 있습니다. 이 작업을 수행하려면 **열 추가** 드롭다운 목록에서 **조건부 열 추가**를 선택하고 새 열의 이름을 입력합니다. **If** 및 **equal to**의 필드와 값을 사용하여 **Then** 및 **Otherwise** 둘 다를 원하는 기본값으로 채웁니다.

    > [!div class="mx-imgBorder"] 
    > ![조건부 열 추가](media/data-integrator/EnablePQDefaultValueTransforms2780.png "조건부 열 추가")

10. *fx* 편집기의 맨 위에 있는 **each** 절을 확인합니다.

    > [!div class="mx-imgBorder"] 
    > ![fx editor](media/data-integrator/EnablePQDefaultValueTransforms2780.png "fx editor")

11. *fx* 편집기에서 **each** 절을 수정하고 **확인**을 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![each 절 수정](media/data-integrator/EnablePQDefaultValueTransforms5780.png "each 절 수정")

<!--note from editor: The sentence that starts with "Additionally" is confusing - not sure where the "same steps" fit in.-->

12. 변경할 때마다 단계를 적용합니다. 오른쪽 창에서 적용된 단계를 볼 수 있습니다(최신 단계를 보려면 맨 아래로 스크롤). 편집해야 하는 경우 단계를 실행 취소할 수 있습니다. 또한 왼쪽 창의 맨 위에 있는 **QrySourceData**를 마우스 오른쪽 단추로 클릭하여 고급 편집기로 이동할 수 있으며, 여기서 동일한 단계로 자동으로 실행되는 M 언어를 볼 수 있습니다.

    > [!div class="mx-imgBorder"] 
    > ![고급 편집기](media/data-integrator/EnablePQDefaultValueTransforms4780.png "고급 편집기")

13. **확인**을 선택하여 고급 쿼리 및 필터링 인터페이스를 닫은 다음, 매핑 작업 페이지에서 새로 만든 열을 원본으로 선택하여 매핑을 적절하게 만듭니다.

    > [!div class="mx-imgBorder"] 
    > ![새 열 선택](media/data-integrator/EnablePQDefaultValueTransforms6780.png "새 열 선택")

파워 쿼리에 대한 자세한 내용은 [파워 쿼리 설명서](https://docs.microsoft.com/power-query/)를 참조하세요.
