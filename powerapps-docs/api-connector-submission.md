---
title: "API 커넥터로 인증을 위한 제출 | Microsoft Docs"
description: "커넥터를 인증하면 Microsoft Flow, PowerApps 및 Logic Apps의 모든 사용자가 사용할 수 있습니다."
services: 
suite: powerapps
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 265fde7b8ce5d5521c53af35a2274409523282fe
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="submit-for-certification-as-an-api-connector-powerapps"></a>API 커넥터로 인증을 위한 제출(PowerApps)
타사 인증 과정의 일부로, 게시하기 전에 커넥터를 검토합니다. 커넥터를 인증하면 Microsoft Flow, PowerApps 및 Logic Apps의 모든 사용자가 사용할 수 있습니다. 다음은 인증에 대한 조건 및 단계입니다.

## <a name="criteria"></a>조건
| 기능 | 세부 정보 | 필수 또는 권장 |
| --- | --- | --- |
| 비즈니스용 SaaS(Software as a Service) 앱 |Microsoft Flow, PowerApps 및 Logic Apps에 적합한 비즈니스 사용자 시나리오 |필수 |
| 인증 형식 |사용자 API는 OAuth2, API 키 또는 기본 인증을 지원해야 함 |필수 |
| 지원 |고객이 도움을 받을 수 있는 지원 연락처를 제공해야 함 |필수 |
| 가용성/작동 시간 |앱은 최소 99.9%의 작동 시간이 있어야 합니다. |권장 |

## <a name="submitting-your-connector"></a>커넥터 제출
간단한 3단계로 Microsoft Flow, PowerApps 및 Logic Apps에 대한 커넥터를 인증합니다.

1. **지명**
   
   * [지명을 제출](https://go.microsoft.com/fwlink/?linkid=848754)
   * 사용자는 상호 비공개 규약 및 파트너 계약을 받게 됩니다. 계약서에 서명하면 계속 진행됩니다.
   * 사용자의 앱이 조건을 충족하는지 확인합니다. 승인되면 온보딩을 위한 지침과 함께 알려드립니다.
2. **검토**
   
    검토를 위해 지명 담당자에게 다음 정보를 제출합니다. 추가 정보가 필요한 경우 자세한 설명을 알려드리겠습니다.
   
   * 사용자의 API를 설명하는 OpenAPI 파일
   * icon.png 파일(230px 정사각형 내에 ~160px 로고, 색이 지정된 배경에 흰색이 좋음)
   * 브랜드 색 16진수(아이콘 파일에서 색이 지정된 배경과 일치)
   * 유효성 검사를 위한 테스트 계정
   * 지원 연락처
3. **게시**
   
    커넥터 기능 및 콘텐츠를 확인한 후 모든 제품 및 지역에서 배포를 위한 커넥터를 스테이징하게 됩니다. 
   
    기본적으로 모든 커넥터는 “프리미엄”으로 게시됩니다. 앱이 Azure에서 빌드된 경우, 커넥터가 Office 365 Enterprise 계획의 모든 사용자가 사용할 수 있는 “표준” 커넥터로 나열되도록 지원할 수 있습니다. 자세한 내용은 지명 담당자에게 문의하세요.

