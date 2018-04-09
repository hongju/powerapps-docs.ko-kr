---
title: 웹 리소스 사용 | Microsoft Docs
description: 개발자가 모델 기반 앱 내에서 웹 리소스를 사용하는 방법을 알아봅니다.
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
ms.openlocfilehash: 56e994929036cc713e7bf7dfc04f46bf991a3530
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="use-web-resources"></a>웹 리소스 사용

이름별로 HTML, JS, CSS, 이미지 및 기타 파일을 요청하고 브라우저에서 액세스할 수 있는 각각의 Common Data Service for Apps 인스턴스 내에 `webresources`라는 가상 폴더가 있습니다. 응용 프로그램을 사용하여 이러한 파일을 업로드하거나 프로그래밍 방식으로 [WebResource 엔터티](../common-data-service/reference/entities/webresource.md) 레코드로 추가할 수 있습니다. [XrmToolBox WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/)는 이러한 레코드 작업을 쉽게 수행할 수 있게 하는 커뮤니티 도구입니다.

이러한 레코드는 해당 콘텐츠에서 상대 경로 이름을 사용하여 서로를 참조할 수 있습니다. 파일을 업로드하고 이름을 요청하는 이 기능은 브라우저의 인증된 세션 내에서 처리되는 파일을 사용하여 웹 응용 프로그램을 만드는 데 필요한 모든 구성 요소를 제공합니다. AJAX 기술을 통해 클라이언트 쪽 코드만 사용하면 양식 또는 대시보드에서 브라우저 창이나 IFrame 내에서 실행할 수 있는 다양한 응용 프로그램을 만들 수 있습니다. 

일반적으로 JavaScript 웹 리소스를 사용하여 양식과 명령에 이벤트 처리기 함수를 추가합니다.

자세한 정보:
- [모델 기반 앱을 사용하여 클라이언트 스크립팅](client-scripting.md)
- [Dynamics 365 고객 관계 개발자 가이드: 웹 리소스](/dynamics365/customer-engagement/developer/web-resources)
