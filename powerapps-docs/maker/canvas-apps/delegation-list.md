---
title: 캔버스 앱의 위임 가능한 데이터 원본 | Microsoft Docs
description: 캔버스 앱에서 지원되는 모든 위임 가능한 데이터 원본 목록
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/15/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 98931d4692a61839e0530682bd2d40258c07b7df
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42825766"
---
# <a name="delegable-data-sources-in-canvas-apps"></a>캔버스 앱의 위임 가능한 데이터 원본
[위임 이해](delegation-overview.md) 문서에서 자세히 설명했듯이 위임에서는 PowerApps가 로컬에서 처리하기 위해 데이터를 캔버스 앱으로 이동하기보다는 데이터 처리를 데이터 원본에 위임합니다.

위임은 테이블 형식 데이터 원본에 대해만 지원됩니다. 이 목록은 다음 섹션에 나와 있는 세부 정보와 함께 테이블 형식 데이터 원본 및 위임을 지원하는지 여부를 보여 줍니다.

* Common Data Service - **예**
* SharePoint - **예**
* SQL Server - **예**
* Dynamics 365 - **예**
* Salesforce - **예**
* Dynamics 365 for Operations - 아직 서비스되지 않음
* Dynamics 365 for Financials - 아직 서비스되지 않음
* Dynamics NAV - 아직 서비스되지 않음
* Google Sheets - 아직 서비스되지 않음

더 많은 테이블 형식 데이터 원본과 위임 지원이 지속적으로 추가됩니다.

이 문서는 데이터 원본마다 지원되는 위임의 현재 상태를 나열합니다.

## <a name="prerequisites"></a>필수 조건

* [위임 이해](delegation-overview.md) 문서에 대한 이해

## <a name="list-of-data-sources-and-supported-delegation"></a>데이터 원본 및 지원되는 위임 목록
이 데이터 원본 및 위임 가능한 함수 및 조건자 목록은 PowerApps에서 위임 지원의 현재 상태를 반영하여 주기적으로 업데이트됩니다.

### <a name="top-level-delegable-functions"></a>최상위 위임 가능 함수

| &nbsp; | 일반 데이터 서비스 | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| 평균 |아니요 |아니요 |예 |아니요 |아니요 |
| 필터링 |예 |예 |예 |예 |예 |
| LookUp |예 |예 |예 |예 |예 |
| 최대 |아니요 |아니요 |예 |아니요 |아니요 |
| 최소 |아니요 |아니요 |예 |아니요 |아니요 |
| Search |예<sup>1</sup> |아니요 |예 |예 |예 |
| 정렬 |예 |예 |예 |예 |예 |
| SortByColumns |예 |예 |예 |예 |예 |
| 합계 |아니요 |아니요 |예 |아니요 |아니요 |

<sup>1</sup>문자열 필드만

### <a name="filter-and-lookup-delegable-predicates"></a>Filter 및 LookUp 위임 가능 조건자

| &nbsp; | 일반 데이터 서비스 | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Not |예 |아니요 |예 |예 |예 |
| IsBlank |아니요 |아니요 |예 |예 |아니요 |
| TrimEnds |아니요 |아니요 |예 |아니요 |아니요 |
| Len |아니요 |아니요 |예 |아니요 |아니요 |
| +, - |아니요 |아니요 |예 |아니요 |아니요 |
| <, <=, =, <>, >, >= |예 |예(=만) |예 |예 |예 |
| And(&&), Or(&#124;&#124;), Not(!) |예<sup>2</sup> |예(Not(!) 제외) |예 |예 |예 |
| in |아니요 |아니요 |예 |아니요 |예 |
| StartsWith |아니요 |예 |아니요 |아니요 |아니요 |

<sup>2</sup>연산자만. And/Or/Not 함수는 위임되지 않습니다.
