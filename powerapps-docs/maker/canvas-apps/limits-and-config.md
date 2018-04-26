---
title: 시스템 요구 사항, 제한 및 구성 값 | Microsoft Docs
description: PowerApps에 대한 시스템 요구 사항, 제한 및 구성 값
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: PowerApps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/07/2018
ms.author: sharik
ms.openlocfilehash: 5cd2fdf5150d008f905e4c5c8177e6331545848e
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="system-requirements-limits-and-configuration-values"></a>시스템 요구 사항, 제한 및 구성 값
이 항목은 장치 플랫폼 및 웹 브라우저 요구 사항뿐만 아니라 PowerApps에 대한 제한 사항 및 구성 값을 포함합니다.

## <a name="supported-platforms-for-running-apps-using-the-powerapps-app"></a>PowerApps 앱을 사용하여 앱을 실행하는 데 지원되는 플랫폼
| **필요한 최소 사항** | **권장** |
| --- | --- |
| iOS 9.3 이상 |최소 2GB의 RAM이 있는 iOS 10 이상 |
| Android 5 이상 |최소 4GB의 RAM이 있는 Android 7 이상 |
| Windows 8.1 이상(PC만 해당) |최소 8GB의 RAM이 있는 Windows 10 Fall Creators Update|

## <a name="supported-browsers-for-running-apps"></a>앱 실행에 지원되는 브라우저
| **브라우저** | **운영 체제** |
| --- | --- |
| Google Chrome(최신 버전)<br>(권장) |Windows 7 SP1, 8.1 및 10 <br>Android 5 이상 <br>iOS 8 이상<br>macOS |
| Microsoft Edge(최신 버전)<br>(권장) |Windows 10 |
| Microsoft Internet Explorer 11(호환성 보기 해제) |Windows 7 SP1, 8.1 및 10 |
| Mozilla Firefox(최신 버전) |Windows 7 SP1, 8.1 및 10 <br> Android 5 이상 <br>iOS 8 이상 <br>macOS |
| Apple Safari(최신 버전) |iOS 8 이상 <br>macOS |

## <a name="supported-browsers-for-powerapps-studio-for-web"></a>웹용 PowerApps Studio에 대해 지원되는 브라우저
| **브라우저** | **운영 체제** |
| --- | --- |
| Google Chrome(최신 버전)<br>(권장) |Windows 7 SP1, 8.1 및 10 <br>macOS |
| Microsoft Edge(최신 버전)<br>(권장) |Windows 10 |
| Microsoft Internet Explorer 11(호환성 보기 해제) |Windows 7 SP1, 8.1 및 10 |

## <a name="request-limits"></a>요청 제한
이러한 제한은 보내는 단일 요청 각각에 적용됩니다.

| 이름 | 제한 |
| --- | --- |
| 시간 제한 |180초 |
| 재시도 횟수 |4 |

> [!NOTE]
> 재시도 값은 달라질 수 있습니다. 특정 오류 조건의 경우 재시도가 필요하지 않습니다.

## <a name="ip-addresses"></a>IP 주소
PowerApps의 요청은 앱이 위치한 [환경](../../administrator/environments-overview.md)의 지역에 따라 다른 IP 주소를 사용합니다. PowerApps 시나리오에 사용할 수 있는 정규화된 도메인 이름을 게시하지 않습니다.

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
