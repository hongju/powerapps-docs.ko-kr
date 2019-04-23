---
title: '개발자: Common Data Service에 대한 모범 사례 및 지침 | Microsoft Docs'
description: PowerApps의 Common Data Service 개발자를 위한 모범 사례 및 지침입니다.
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
ms.date: 01/07/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c89042e1f94e6f891bfdc255c38f72929c27cb1e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61528369"
---
# <a name="best-practices-and-guidance-for-the-common-data-service"></a>Common Data Service에 대한 모범 사례 및 지침

Common Data Service는 개발자가 고도로 사용자 지정되고 맞춤화된 환경을 빌드할 수 있도록 확장 가능한 프레임워크입니다. Common Data Service를 사용자 지정, 확장 또는 통합하는 동안 개발자는 확립된 지침과 모범 사례를 알고 있어야 합니다. 

이 섹션 내에서 식별한 문제와 그 영향에 대해 알아보고 해결하기 위한 지침을 이해합니다. 작업을 특정 방식으로 수행해야 하는 이유와 향후 잠재적인 문제를 방지하는 방법에 대한 백그라운드를 다루겠습니다. 이는 사용자 환경의 가용성, 지원성 및 성능에 도움이 될 수 있습니다. 지침 설명서는 개발자 및 관리 가이드 내의 기존 정보를 지원합니다.

# <a name="targeted-customization-types"></a>대상이 지정된 사용자 지정 형식
설명서는 다음 사용자 지정 형식을 대상으로 합니다.

- 사용자 지정 워크플로 작업 및 플러그 인
- Common Data Service 데이터 작업
- Common Data Service를 확장하는 통합

# <a name="sections"></a>섹션
각 지침 문서에는 다음 섹션의 대부분 또는 전부가 포함됩니다.

- 제목 - 지침 설명
- 범주 - 지침을 따르지 않아 영향을 받는 하나 이상의 영역
- 잠재적 영향 - 지침에 따르지 않으므로써 환경에 영향을 미치는 위험 수준(높음, 중간 또는 낮음)
- 증상 - 지침을 따르지 않았음을 나타내는 징후
- 지침 - 예제를 포함할 수도 있는 권장 사항
- 문제가 되는 패턴 - 지침을 따르지 않는 설명 또는 예제
- 추가 정보 - 더 광범위한 보기를 위한 세부 정보 지원
- 참고 항목 - 문서에 언급된 항목에 대해 자세히 알 수 있는 참조 사항

# <a name="categories"></a>범주
각 지침 문서는 다음 범주 중 하나 이상으로 분류됩니다.

- 사용 – 특정 API, 패턴 또는 구성의 부적절한 사용
- 디자인 - 사용자 지정의 디자인 결함
- 성능 - 메모리 관리, CPU 사용률, 네트워크 트래픽 또는 사용자 환경과 같은 영역에서 성능에 부정적인 영향을 줄 수 있는 사용자 지정 또는 패턴
- 보안 – 런타임 환경에서 악용될 수 있는 사용자 지정의 잠재적인 취약점
- 업그레이드 준비 - 실패한 버전 업그레이드 위험을 증가시킬 수 있는 사용자 지정 또는 패턴
- 온라인 마이그레이션 - 온라인 마이그레이션이 실패할 위험을 증가시킬 수 있는 사용자 지정 또는 패턴
- 유지 관리 – 변경하는 데 필요한 개발자 노력의 양, 필요한 변경의 빈도 또는 회귀 발생 가능성을 불필요하게 증가시키는 사용자 지정
- 지원 가능성 – 제거된 API의 사용 또는 금지된 기술의 구현을 포함하여 게시된 지원 가능성 명령문의 경계를 벗어나는 사용자 지정 또는 패턴
