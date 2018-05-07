---
title: Dynamics 365 라이선스를 요구하는 제한된 엔터티 | Microsoft Docs
description: Dynamics 365 라이선스를 필요로 하는 앱용 CDS(Common Data Service)에서 제한된 엔터티 목록입니다.
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: cds
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 508f58b48f2dd51bf25f23905cc3513db90ed1ce
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Dynamics 365 라이선스를 요구하는 제한된 엔터티
PowerApps 요금제 1 라이선스만 있는 사용자에 대해 앱과 흐름을 만들려면 앱 작성자는 앱용 CDS(Common Data Service) 내에서 사용할 수 있는 엔터티 대부분을 사용할 수 있습니다. 그러나 일부 엔터티에는 앱 사용자에게 PowerApps 요금제 2 또는 Microsoft Flow 요금제 2를 요구하는 복잡한 비즈니스 논리가 포함됩니다(자세한 내용은 [엔터티 라이선스 요구 사항](data-platform-entity-licenses.md)을 참조합니다). Dynamics 365 제품에 연결된 엔터티의 더 작은 집합은 엔터티 내의 레코드를 만들고 업데이트하고 삭제할 필요가 있는 경우 캔버스 및 모델 기반 앱 사용자에게 해당 Dynamics 365 제품에 대한 라이선스를 요구합니다. 이들은 *제한된* 엔터티라고 합니다.

다음과 같은 이유로 Dynamics 365 라이선스에 엔터티를 제한할 수 있습니다.

* 엔터티는 보통 응용 프로그램 외부에서 사용되지 않는 제품 관련 구성 데이터를 유지 관리하는 데 사용됩니다.
* 엔터티는 Dynamics 365 제품 내에서 사용될 때 특정 방식으로 데이터를 만들고 유지 관리하는 고급 논리와 함께 제공됩니다.

앱 또는 흐름이 엔터티에서 정보를 판독하는 경우 Dynamics 365 라이선스는 필요하지 않으며 적절한 PowerApps 또는 Microsoft Flow 라이선스가 필요한 모든 것입니다. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>작업 만들기, 업데이트 및 삭제를 위한 제한된 엔터티
다음 테이블에서는 엔터티 내에 저장된 데이터를 만들고 업데이트하거나 삭제하는 PowerApps 및 Microsoft Flow 앱 사용자에 대해 제한된 엔터티 및 관련 Dynamics 365 라이선스 요구 사항을 나열합니다. 

|엔터티  |논리적 이름  |라이선스 필요  |
|---------|---------|---------|
실제 |msdyn_actual |Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
계약 비즈니스 프로세스 |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
예약 업무 일지 | msdyn_bookingjournal|Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
예약 설치 메타데이터 | msdyn_bookingsetupmetadata|Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
타임 스탬프 예약 | msdyn_bookingtimestamp|Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
작업 주문 비즈니스 프로세스에 대한 사례 |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
구성 |msdyn_configuration |Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
권리 유형 | 권리 유형 | Dynamics 365 for Customer Service, Enterprise Edition <br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
견적 줄|msdyn_estimateline|Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
견적|msdyn_estimate |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
팩트|msdyn_fact |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
필드 서비스 설정 |msdyn_fieldservicesetting |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
필드 서비스 시스템 작업 |msdyn_fieldservicesystemjob |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
목표 | 목표 | Dynamics 365 for Sales Professional, <br>**또는** Dynamics 365 for Sales, Enterprise Edition, <br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
인시던트 | 인시던트 | Dynamics 365 for Customer Service, Enterprise Edition <br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
인벤토리 저널 |msdyn_inventoryjournal |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
송장 프로세스 |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
여정 | 여정 | Dynamics 365 for Marketing <br> **또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
기술 문서 | 기술 문서 | Dynamics 365 for Customer Service, Enterprise Edition <br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
조직 구성 단위 |msdyn_organizationalunit |Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
제품 인벤토리 |msdyn_productinventory |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
프로젝트 매개 변수|msdyn_projectparameter |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
프로젝트 단계| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
프로젝트 작업 종속성|msdyn_projecttaskdependency |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
프로젝트 작업|msdyn_projecttask |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
프로젝트 팀 구성원|msdyn_projecteam |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
구매 주문 비즈니스 프로세스 | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
리소스 할당 세부 정보(사용되지 않음)|msdyn_resourceassignmentdetail |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
리소스 할당|msdyn_resourceassignment |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
리소스 제한(사용되지 않음) |msdyn_workorderresourcerestriction | Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
규칙 집합 라우팅 | routingrule | Dynamics 365 for Customer Service, Enterprise Edition <br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
보드 설정 예약 |msdyn_scheduleboardsetting |Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
일정 매개 변수 |msdyn_schedulingparameter |Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
SLA| sla | Dynamics 365 for Customer Service, Enterprise Edition <br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
시스템 사용자 스케줄러 설정 |msdyn_systemuserschedulersetting|Dynamics 365 for Field Service <br> **또는** Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
트랜잭션 연결|msdyn_transactionconnection |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
트랜잭션 원본|msdyn_transactionorigin |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
트랜잭션 유형|msdyn_transactiontype |Dynamics 365 for Project Service Automation<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
고유 번호|msdyn_uniquenumber |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
작업 주문 비즈니스 프로세스 |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제
작업 주문 세부 정보 생성 큐(사용되지 않음)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for Field Service<br>**또는** Dynamics 365 고객 참여 계획 <br> **또는** Dynamics 365 요금제

## <a name="licensing"></a>라이선스
PowerApps 및 Dynamics 365 라이선스에 대한 자세한 내용은 [라이선스 개요](../../administrator/pricing-billing-skus.md) 페이지를 참조하십시오.

