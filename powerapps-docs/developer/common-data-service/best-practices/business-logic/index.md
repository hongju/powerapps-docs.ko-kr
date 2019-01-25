---
title: '개발자: 앱용 Common Data Service의 플러그 인 및 워크플로 개발에 관한 모범 사례 및 지침 | Microsoft Docs'
description: PowerApps의 앱용 Common Data Service 개발자를 위한 플러그 인 및 워크플로 개발에 관한 모범 사례 및 지침.
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
ms.date: 1/15/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 87e7337a4bf62a10647edfd9b6c17bce0a0903bf
ms.sourcegitcommit: 72c97378e96fb54e5d92ec087a59dd0fb1444f99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334020"
---
# <a name="best-practices-and-guidance-regarding-plug-in-and-workflow-development-for-the-common-data-service-for-apps"></a>앱용 Common Data Service의 플러그 인 및 워크플로 개발에 관한 모범 사례 및 지침

이 목록 아래에는 앱용 Common Data Service 내의 플러그 인 및 워크플로 개발에 관한 모든 지침과 모범 사례가 포함되어 있습니다.

|모범 사례  |설명  |
|---------|---------|
|[플러그 인 및 워크플로 작업에 일괄 처리 요청 형식을 사용하지 마세요.](avoid-batch-requests-plugin.md)     |플러그 인 또는 워크플로 작업 컨텍스트 내에서 ExecuteMultipleRequest 또는 ExecuteTransactionRequest 메시지 요청 클래스를 사용하면 안됩니다.         |
|[상태 비저장으로 IPlugin 구현 개발](develop-iplugin-implementations-stateless.md)     |IPlugin를 구현하는 클래스의 멤버는 데이터 불일치 또는 성능 문제가 발생할 수 있는 잠재적인 스레드 안전성 문제에 노출됩니다.         |
|[플러그 인 단계 등록을 복제하지 마세요.](do-not-duplicate-plugin-step-registration.md)     |중복된 플러그 인 등록으로 인해 동일한 메시지/이벤트에서 플러그 인이 여러 번 발생됩니다.         |
|[플러그 인 등록과 필터링 특성 포함](include-filtering-attributes-plugin-registration.md)     |플러그 인 등록 단계에 필터링 특성이 설정되지 않은 경우 플러그 인은 해당 이벤트에 대한 업데이트 메시지가 발생할 때마다 실행됩니다.         |
|[검색 및 RetrieveMultiple 메시지의 플러그 인 등록 제한](limit-registration-plugins-retrieve-retrievemultiple.md)     |검색 및 RetrieveMultiple 메시지 이벤트에 동기 플러그 인 논리를 추가하면 속도가 저하될 수 있습니다.         |
|[사용자 지정 어셈블리 개발 최적화](optimize-assembly-development.md)     |어셈블리 크기가 샌드박스 어셈블리 크기 제약 조건에 가까운 경우, 별도의 플러그 인/사용자 지정 워크플로 작업을 단일 사용자 지정 어셈블리드로 병합하여 성능 및 유지 관리를 향상시키고 플러그 인/사용자 지정 워크플로 작업을 여러 사용자 지정 어셈블리로 이동하는 것을 고려해 보세요.         |
|[플러그 인에서 외부 호스트와 상호 작용할 때 KeepAlive를 false로 설정](set-keepalive-false-interacting-external-hosts-plugin.md)     |HTTP 요청 헤더에서 true로 설정되거나 false로 명시적으로 정의되지 않은 KeepAlive 속성은 플러그 인의 실행 시간을 증가시킬 수 있습니다.         |
|[InvalidPluginExecutionException을 플러그 인 및 워크플로 활동에 사용](use-invalidpluginexecutionexception-plugin-workflow-activities.md)     |플러그 인 또는 워크플로 활동의 컨텍스트 내에서 오류를 발생시키는 경우에는 InvalidPluginExecutionException를 사용합니다.         |

# <a name="see-also"></a>참고 항목
[코드를 사용하여 비즈니스 논리 적용](../../apply-business-logic-with-code.md)<br />
[플러그 인을 사용하여 비즈니스 프로세스 확장](../../plug-ins.md)<br />
[워크플로 확장](../../workflow/workflow-extensions.md)<br />