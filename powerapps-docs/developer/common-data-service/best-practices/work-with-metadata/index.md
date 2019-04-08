---
title: '개발자: Common Data Service의 메타데이터 사용 시 모범 사례 및 지침 | Microsoft Docs'
description: PowerApps의 Common Data Service 개발자를 위한 메타데이터 사용 시 모범 사례 및 지침입니다.
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2018
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 35e07c87e515759a6e61a0c0a027c190b11bef53
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58358015"
---
# <a name="best-practices-and-guidance-while-working-with-metadata-for-the-common-data-service"></a>Common Data Service의 메타데이터 사용 시 모범 사례 및 지침

이 목록 아래에는 Common Data Service 내에서 메타데이터를 조작하고 사용하는 것과 관련된 모든 지침과 모범 사례가 포함되어 있습니다.


|모범 사례  |설명  |
|---------|---------|
|[게시된 메타데이터 검색](retrieve-published-metadata.md)     |게시되지 않은 메타데이터를 검색하면 요청 자체를 처리하는 데 오버헤드가 추가될 뿐만 아니라 더 느리게 수행하며, 요청자가 기대하지 않은 메타데이터를 반환할 수도 있습니다.         |
|[쿼리 API를 통해 엔터티의 특정 열 검색](retrieve-specific-columns-entity-via-query-apis.md)     |데이터를 검색하기 위해 제출한 쿼리는 모든 열이 아닌 쿼리와 연결된 ColumnSet 인스턴스의 특정 열이 포함되어야 합니다.         |

# <a name="see-also"></a>참고 항목
[코드를 사용하여 메타데이터 작업](../../metadata-services.md)<br />