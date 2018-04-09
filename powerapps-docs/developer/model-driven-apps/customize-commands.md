---
title: 모델 기반 앱을 사용하여 명령 사용자 지정 | Microsoft Docs
description: 모델 기반 앱을 사용하여 명령을 사용자 지정하는 방법을 알아봅니다.
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
ms.date: 03/17/2018
ms.author: jdaly
ms.openlocfilehash: 7ad955ed5858cab69aaf8b2993ae3f98a04147fb
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="customize-commands-with-model-driven-apps"></a>모델 기반 앱을 사용하여 명령 사용자 지정 

양식 또는 목록 명령 모음 내에 나타나는 명령은 사용자 지정할 수 있습니다. 명령은 Office 리본에서 사용되는 XML 스키마를 기반으로 하므로 용어 *리본*이라는 용어가 계속 사용됩니다. 명령을 만들 때 정의할 수 있는 세 가지 요소는 다음과 같습니다.

- *규칙 표시*는 명령 또는 명령 그룹이 표시되는지 여부를 결정하기 위해 양식 또는 목록이 로드될 때 평가됩니다.
- *규칙 사용*은 UI에서 현재 선택된 항목과 같은 다양한 조건에 따라 명령을 사용할 수 있는지 여부를 제어합니다.
- 각 명령에 대한 *작업*은 선택 시 수행할 작업을 알려줍니다. 명령은 URL을 열거나 JavaScript 웹 리소스 내에 정의된 함수를 실행할 수 있습니다.

사용자 지정 명령은 기존 명령에 따라 배치됩니다. 기존 명령 집합에 적용할 변경 내용을 정의하는 *사용자 지정 작업*을 작성해야 합니다. 

명령에 제공되는 디자이너는 없지만, 커뮤니티에서 제공하는 도구가 있습니다. [Ribbon Workbench](http://www.develop1.net/public/rwb/ribbonworkbench.aspx)는 그래픽 인터페이스를 제공하며 명령을 사용자 지정하는 데 사용되는 가장 일반적인 도구입니다.

자세한 정보: [Dynamics 365 고객 관계 개발자 가이드: 명령 및 리본 사용자 지정](/dynamics365/customer-engagement/developer/customize-dev/customize-commands-ribbon)


