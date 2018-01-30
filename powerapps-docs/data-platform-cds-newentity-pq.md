---
title: "파워 쿼리를 사용하여 CDS(Common Data Service)에서 새 엔터티 만들기 | Microsoft Docs"
description: "파워 쿼리를 사용하여 CDS에서 새 엔터티를 만들기 위한 단계별 지침입니다."
services: 
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: 18f580c06412968b27a279a526b562e27cb89e26
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="create-new-entities-in-the-common-data-service-cds-using-power-query"></a>파워 쿼리를 사용하여 CDS(Common Data Service)에서 새 엔터티 만들기
**파워 쿼리**의 통합을 사용하여 비즈니스 앱 개발자는 다양한 데이터 원본에서 CDS(Common Data Service)에 새 엔터티를 만들 수 있습니다.

**Common Data Service**를 통해 사용자는 표준 및 사용자 지정 엔터티 집합 내에서 데이터를 안전하게 저장하고 관리할 수 있습니다. *엔터티*는 데이터베이스 내의 테이블과 유사한 데이터를 저장하는 데 사용되는 필드의 집합입니다. 데이터가 Common Data Service에 저장되면 **Microsoft PowerApps**를 사용하여 저장된 데이터를 사용하는 다양한 응용 프로그램을 빌드할 수 있습니다.

**파워 쿼리** 통합으로 PowerApps를 사용하는 비즈니스 앱 개발자는 관계형 데이터베이스(SQL Server, IBM DB2 등)와 같은 온-프레미스 데이터 원본, Excel, 액세스 및 텍스트 파일과 같은 외부 데이터 원본뿐만 아니라 Salesforce, Azure SQL Database 및 Data Warehouse, Web API, OData 피드 및 더 많은 원본과 같은 온라인 서비스의 데이터를 기반으로 하는 **Common Data Service**에 새 엔터티를 만들 수 있습니다. 연결할 수 있는 다양한 데이터 원본 외에도 **파워 쿼리**를 사용하여 Common Data Service에 로드하기 전에 데이터를 필터링, 변환 및 결합할 수 있습니다.

![데이터의 새 엔터티](media/data-platform-cds-newentity-pq/data-platform-cds-pq-01.jpg)

## <a name="enabling-the-cds-new-entities-from-power-query-feature"></a>파워 쿼리 기능에서 CDS 새 엔터티를 사용하도록 설정
이 기능은 PowerApps 테넌트에서 사용할 수 있지만 기본적으로 켜져 있지 않습니다. [web.powerapps.com](https://aka.ms/pqocds)에서 활성화할 수 있습니다.

> [!NOTE]
> 사용자가 만든 데이터베이스에만 새 사용자 정의 엔터티를 만들 수 있습니다.

PowerApps 포털에서 다음 단계를 수행하여 이 기능을 활성화합니다.

1. 왼쪽 탐색 창에서 **Common Data Service > 엔터티** 탭으로 이동합니다.

2. **엔터티** 목록에서 **새 엔터티** 드롭다운을 선택합니다.

3. 드롭다운 메뉴에 나타나는 목록에서 다음 그림에 나와 있는 것처럼 **데이터의 새 엔터티(기술 미리 보기)**를 선택합니다.
   
    ![데이터의 새 엔터티](media/data-platform-cds-newentity-pq/data-platform-cds-pq-02.jpg)
4. 메뉴에서 **데이터의 새 엔터티(기술 미리 보기)**를 선택하면 다음 그림에 나와 있는 것처럼 이 기술 미리 보기에서 사용할 수 있는 커넥터의 목록과 함께 대화 상자가 나타납니다.
   
   ![사용 가능한 커넥터](media/data-platform-cds-newentity-pq/data-platform-cds-pq-03.jpg)
5. 사용하려는 커넥터를 선택하면 다음 단계로 계속하여 데이터 원본 연결 세부 정보 및 자격 증명을 지정하고, 가져올 테이블을 선택하는 등의 작업을 수행할 수 있습니다. **쿼리 편집기**에도 액세스할 수 있으므로(**탐색기** 보기에서 **편집** 단추 사용) CDS로 데이터를 가져오기 전에 필터 또는 데이터 변환 단계를 적용할 수 있습니다.
   
    ![](media/data-platform-cds-newentity-pq/data-platform-cds-pq-04.jpg)

## <a name="adjust-load-settings-and-other-behavior"></a>로드 설정 및 기타 동작 조정
이전 섹션의 단계를 완료하고 **파워 쿼리**를 사용하여 CDS에서 새 엔터티를 만드는 데 데이터 원본을 사용할 준비가 되면 새로 고침 동작 및 엔터티 관련 설정(예: 표시 이름, 기본 키 및 기타)과 같은 추가 로드 설정을 조정할 수 있습니다.

![](media/data-platform-cds-newentity-pq/data-platform-cds-pq-05.jpg)

이러한 단계가 완료되고 **로드**를 선택하면 CDS에서 새 사용자 지정 엔터티를 만들게 됩니다. 특정 엔터티에 대한 **엔터티** 메뉴에 액세스하여 초기 로드 이후에 쿼리를 편집할 수도 있습니다.

이 기능에 대해 매우 기대하고 있으며 사용자의 의견을 기다리고 있습니다. 이 기능에 대한 [제안 및 의견을 보내주세요](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).

