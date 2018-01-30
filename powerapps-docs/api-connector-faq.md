---
title: "API 커넥터 FAQ | Microsoft Docs"
description: "요구 사항, 트리거 및 다른 영역에 관한 질문에 대한 답변을 찾습니다."
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
ms.openlocfilehash: b945f2775e26327557255a75f18e87a638a9fe66
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="api-connector-faq-powerapps"></a>API 커넥터 FAQ(PowerApps)
## <a name="requirements"></a>요구 사항
**Q:** ISV가 아닌 경우에도 여전히 커넥터를 빌드할 수 있나요?

**A:** 커넥터를 공개적으로 릴리스하려면 기본 서비스를 소유하거나 API 사용에 관한 명시적 권한이 있어야 합니다.

**Q:** REST API 없이 커넥터를 빌드할 수 있나요?

**A:** 아니요. API 커넥터를 빌드하려면 안정적인 HTTP REST API를 지원해야 합니다.

**Q:** 지원되는 인증 유형은 무엇인가요?

**A:** 다음과 같은 인증 표준을 지원합니다.

* OAuth2.0(Azure Active Directory 포함)
* API 키
* 기본 인증

## <a name="triggers"></a>트리거
**Q:** 웹후크 없이 트리거를 빌드할 수 있나요? 

**A:** Microsoft Flow 및 Logic Apps를 위한 API 커넥터를 사용하면 웹후크 기반 트리거만 빌드할 수 있습니다. 다른 형태의 구현이 필요한 경우 API에 대한 자세한 내용과 함께 [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com)에 문의하세요.

## <a name="miscellaneous"></a>기타
**Q:** 내 API는 동적 호스트를 사용합니다. 이를 OpenAPI에서 구현하려면 어떻게 할까요?

**A:** API 커넥터 기능은 동적 호스트를 지원하지 않습니다. 개발 및 테스트 목적을 위한 정적 호스트를 사용하십시오. 제출하는 동안 동적 구현에 대해 Microsoft 담당자에게 문의하십시오.

**Q:** Postman Collection V2를 지원합니까?

**A:** 아니요, 현재 Postman V2는 지원되지 않습니다.

**Q:** OpenAPI 3.0을 지원합니까?

**A:** 아니요, 현재 OpenAPI 2.0이 지원되는 유일한 버전입니다.

