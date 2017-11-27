---
title: "제한 사항 및 구성 | Microsoft Docs"
description: "PowerApps에 대한 제한 사항 및 구성 값"
services: 
suite: PowerApps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: PowerApps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2017
ms.author: sharik
ms.openlocfilehash: 337f3fc00fe52e0008190e2144f21f40d1632f52
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="limits-and-configuration-in-microsoft-powerapps"></a>Microsoft PowerApps의 제한 사항 및 구성
이 항목에는 PowerApps에 대한 현재 제한 사항 및 구성 세부 정보에 대한 정보가 포함됩니다.

## <a name="requests"></a>요청
이러한 제한은 보내는 단일 요청 각각에 적용됩니다.

| 이름 | 제한 |
| --- | --- |
| 시간 제한 |180초 |
| 재시도 횟수 |4 |

**참고**: 재시도 값은 달라질 수 있습니다. 특정 오류 조건의 경우 재시도하지 않는 것이 좋습니다.

## <a name="ip-addresses"></a>IP 주소
PowerApps의 요청은 앱이 위치한 [환경](environments-overview.md)의 지역에 따라 다른 IP 주소를 사용합니다. PowerApps 시나리오에 사용할 수 있는 정규화된 도메인 이름을 게시하지 않습니다.

이 항목의 뒷부분에서 지정된 IP 주소에서 앱(예: SQL API 또는 SharePoint API)을 통해 연결된 API의 호출이 비롯됩니다.

예를 들어, Azure SQL Database에 대한 IP 주소를 허용 목록에 추가해야 하는 경우 이러한 주소를 사용합니다.

| 지역 | 아웃바운드 IP |
| --- | --- |
| 아시아 |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| 오스트레일리아 |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| 캐나다 |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| 유럽 |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| 인도 |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| 일본 |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| 미국 |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| 미국(초기 액세스) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

## <a name="required-services"></a>필수 서비스
이 목록은 PowerApps Studio에서 설명하는 사용법에 대한 모든 서비스를 식별합니다. 네트워크는 이러한 서비스를 차단하지 **않아야** 합니다.

| 도메인 | 프로토콜 | 사용 |
| --- | --- | --- |
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |커넥터 런타임/API |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph - 사용자 정보를 가져오는 경우(예: 프로필 사진) |
| gallery.azure.com |https |샘플 및 템플릿 앱 |
| *.azure-apim.net |https |API 허브 - 각 로캘에 대해 다른 하위 도메인 |
| *.powerapps.com |https |WebAuth + 포털 |
| *.azureedge.net |https |WebAuth |
| *.blob.core.windows.net |https |Blob 저장소 |
| vortex.data.microsoft.com |https |원격 분석 |

