---
title: 모델 기반 앱에서 클라이언트 스크립팅 사용 | Microsoft Docs
description: 개발자가 클라이언트 쪽 스크립트 및 모델 기반 앱에서 JavaScript를 사용하는 방법을 알아봅니다.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2018
ms.author: jdaly
ms.openlocfilehash: 2d389ae6557944048d8b2d8618379d17aea27557
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
ms.locfileid: "30025544"
---
# <a name="client-scripting-with-model-driven-apps"></a>모델 기반 앱을 사용하여 클라이언트 스크립팅

JavaScript를 사용하는 클라이언트 쪽 스크립팅은 모델 기반 앱에서 양식에 데이터를 표시하기 위한 사용자 지정 비즈니스 프로세스 논리를 적용하는 방법 중 하나이지만, 가장 먼저 선택하지 않아야 합니다. *비즈니스 규칙*은 JavaScript를 알지 못하고 개발자가 아닌 사용자에게 비즈니스 프로세스 논리를 양식에 적용할 수 있는 방법을 제공합니다. 자세한 정보: [Dynamics 365 고객 관계 사용자 지정 가이드: 비즈니스 규칙 및 추천을 만들어 양식에 논리 적용](/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form)

> [!TIP]
> [powerapps.com](http://web.powerapps.com)의 **Common Data Service** 영역 내에서 비즈니스 규칙 디자이너를 찾을 수 있습니다. 엔터티가 표시되면 **비즈니스 규칙** 탭을 찾습니다.

비즈니스 규칙을 사용하여 비즈니스 요구 사항을 달성할 수 없는 경우, 클라이언트 API 개체 모델을 사용하는 클라이언트 스크립팅은 응용 프로그램의 동작을 확장하고 클라이언트에서 자동화를 사용하도록 설정하는 강력한 방법을 제공합니다.

## <a name="resources"></a>리소스

Dynamics 365 고객 관계 개발자 가이드에서 사용할 수 있는 클라이언트 스크립팅용 리소스는 다음과 같습니다.

- [JavaScript를 사용하여 클라이언트 스크립팅](/dynamics365/customer-engagement/developer/clientapi/client-scripting)
- [양식 및 그리드의 이벤트](/dynamics365/customer-engagement/developer/clientapi/events-forms-grids)
- [클라이언트 API 개체 모델 이해](/dynamics365/customer-engagement/developer/clientapi/understand-clientapi-object-model)
- [연습: 첫 번째 클라이언트 스크립트 작성](/dynamics365/customer-engagement/developer/clientapi/walkthrough-write-your-first-client-script)
- [JavaScript 코드 디버깅](/dynamics365/customer-engagement/developer/clientapi/debug-javascript-code)
- [모범 사례: 클라이언트 스크립팅](/dynamics365/customer-engagement/developer/clientapi/client-scripting-best-practices)
- [클라이언트 API 참조](/dynamics365/customer-engagement/developer/clientapi/reference)

