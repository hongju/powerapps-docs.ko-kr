---
title: PowerApps 엔터프라이즈 배포 관리 | MicrosoftDocs
description: PowerApps 엔터프라이즈 배포 관리에 대한 백서를 확인합니다.
ms.custom: ''
ms.date: 08/09/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 83200632-a36b-4401-ba41-952e5b43f939
caps.latest.revision: 31
author: jimholtz
ms.author: jimholtz
manager: kvivek
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: ce8daad960834c2965e2a5432ccaf2a3f515e503
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42857497"
---
# <a name="administering-a-powerapps-enterprise-deployment"></a>PowerApps 엔터프라이즈 배포 관리

PowerApps는 Microsoft의 고생산성 애플리케이션 개발 플랫폼입니다.  이 플랫폼은 Microsoft에서 판매, 서비스, 필드 서비스, 마케팅 및 탤런트용 Dynamics 365를 자체적으로 빌드하는 데 사용됩니다.  즉, 이러한 애플리케이션은 플랫폼에서 기본적으로 빌드됩니다.   엔터프라이즈 고객은 동일한 기술을 사용하여 자체 비즈니스 애플리케이션의 사용자 지정 라인을 빌드할 수도 있습니다.  조직 내의 개별 사용자와 팀은 코드가 없거나 코드가 적은 개인 또는 팀 생산성 애플리케이션을 빌드할 수도 있습니다. 

다운로드 가능한 [PowerApps 엔터프라이즈 배포 관리](https://aka.ms/powerappsadminwhitepaper) 백서를 확인합니다.

이 백서는 PowerApps 플랫폼에 빌드된 애플리케이션을 계획, 보안, 배포 및 지원을 담당하는 엔터프라이즈 애플리케이션 관리자를 대상으로 합니다.  이 백서의 목표는 현재 사용자 환경의 상태, 개발 및 배포 중인 애플리케이션을 사전에 계획하는 방법과 마지막으로 배포를 관리하기 위한 일상적인 관리 작업을 처리하는 방법을 이해하는 데 도움을 주는 것입니다.
이 백서에서는 주요 개념, 플랫폼 아키텍처 및 필요한 의사 결정에 대해 설명합니다.  가능한 경우 플랫폼을 사용하는 사용자의 성공적인 배포와 높은 생산성을 보장하기 위해 조직에 대한 모범 사례를 개발할 수 있도록 지원합니다.

PowerApps 플랫폼은 PowerBI 및 Microsoft Flow도 포함하는 대규모 Microsoft Power 플랫폼의 일부로 앱 및 데이터 커넥터용 Common Data Service의 공통 인프라를 활용합니다. 이러한 기능은 Microsoft Azure 클라우드 서비스에서 빌드되고 활용됩니다.  PowerApps 플랫폼에서 빌드된 애플리케이션에는 Azure 클라우드 서비스가 포함되어 개별 생산성에서 비즈니스 애플리케이션의 엔터프라이즈 업무상 중요한 라인으로 확장할 수 있습니다.

![Microsoft Power 플랫폼](media/ms-power-platform.png "Microsoft Power 플랫폼")
