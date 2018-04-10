---
title: 코드로 비즈니스 논리 적용 | Microsoft Docs
description: 개발자가 코드를 사용하여 Common Data Service for Apps에서 비즈니스 논리를 적용하는 방법을 알아봅니다.
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
ms.date: 02/26/2018
ms.author: jdaly
ms.openlocfilehash: 12925c57103b1ecc00dc19205af5f32d165bdc63
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="apply-business-logic-with-code"></a>코드로 비즈니스 논리 적용

가능하다면 요구 사항에 비즈니스 논리 정의가 포함되는 경우 여러 선언적 프로세스 옵션 중 하나를 적용하는 것을 고려해야 합니다. [Dynamics 365 Customer Engagement 사용자 지정 가이드: 프로세스를 통해 사용자 지정 비즈니스 논리 만들기](/dynamics365/customer-engagement/customize/guide-staff-through-common-tasks-processes)

선언적 프로세스가 요구 사항을 충족하지 않는 경우 개발자가 선택할 수 있는 여러 옵션이 있습니다. 이 항목에서는 코드를 작성하는 일반적인 옵션을 소개합니다.

## <a name="create-a-workflow-extension"></a>워크플로 확장 만들기

프로세스 디자이너 내에서 새 옵션을 제공하는 .NET 어셈블리를 작성할 수 있습니다. 이 방법은 워크플로 디자이너를 사용하는 사람들이 조건을 적용하거나 새 작업을 수행할 수 있는 새 옵션을 제공합니다. 그 후에는 개발자가 아닌 사람들이 워크플로 확장을 다시 사용하여 코드의 논리를 적용할 수 있습니다.

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: 사용자 지정 워크플로 작업(워크플로 어셈블리)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies)

## <a name="create-a-plug-in"></a>플러그 인 만들기

데이터 트랜잭션 흐름에 플러그 인하여 서버에 비즈니스 논리를 적용하는 .NET 어셈블리를 작성할 수 있습니다. Common Data Service for Apps 플랫폼을 사용하면 어셈블리의 클래스 내에 정의된 코드를 실행하는 특정 이벤트를 등록할 수 있는 프레임워크가 있습니다. 이 클래스는 [Execute 메서드](/dotnet/api/microsoft.xrm.sdk.iplugin.execute)를 노출하는 특정 인터페이스를 상속합니다. 등록된 이벤트가 발생하면 클래스의 `Execute` 메서드를 호출하여 이벤트에 대한 컨텍스트 데이터를 전달합니다.

개발자는 *플러그 인 등록 도구*를 사용하여 어셈블리를 등록합니다.

`Execute` 메서드 내에서 SDK 어셈블리에 정의된 개체 모델을 사용하여 상황에 맞는 이벤트 데이터를 평가하고 다음을 수행하는 적절한 조치를 취할 수 있습니다.
- 오류를 throw하여 작업을 취소할 것인지 결정
- Execute 메서드에 전달된 컨텍스트 데이터를 변경
- 조직 서비스를 사용하여 프로세스를 자동화하는 추가 작업 수행

### <a name="synchronous-and-asynchronous-plug-ins"></a>동기 및 비동기 플러그 인
플러그 인을 등록하면 트랜잭션 내에서 동기적으로 실행되거나 지연되어 서버에 미치는 영향이 적은 시간에 논리를 적용하는 큐에 전송될 수 있습니다. 이러한 이유로 사람들은 비동기 플러그 인을 선호합니다.

이벤트에 대해 동기적으로 실행되도록 플러그 인을 등록할 때 코드 실행 시기에 대한 옵션이 제공됩니다. 세 가지 단계가 있습니다.

|이벤트  |설명  |
|---------|---------|
|유효성 검사 전|데이터베이스 트랜잭션이 시작되기 전에 발생합니다. 트랜잭션 롤백 시 성능 저하를 피하기 위해 트랜잭션이 시작되기 전에 작업을 취소해야 하는지 여부를 결정하는 비즈니스 논리를 적용할 수 있는 좋은 위치입니다.|
|작업 전|데이터베이스 트랜잭션이 시작된 후 발생합니다. 이 단계에서 작업을 취소하려면 트랜잭션을 롤백해야 합니다.|
|작업 후|주 데이터 작업이 완료된 후 데이터베이스 트랜잭션 내에서 발생합니다. 이전 이벤트에서 적용된 변경 내용을 포함하지만 작업을 취소하는 경우 훨씬 더 큰 페널티가 발생합니다.|

> [!NOTE]
> 동기 플러그 인은 사용할 수 있는 시스템 리소스의 양에 제한이 있습니다. 플러그 인이 임계값을 초과하거나 응답하지 않는 경우 작업을 취소하면 예외가 throw 됩니다.

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: 비즈니스 프로세스를 확장하는 플러그 인 작성](/dynamics365/customer-engagement/developer/write-plugin-extend-business-processes)

### <a name="see-also"></a>참고 항목

[Common Data Service for Apps 개발자 개요](overview.md)
