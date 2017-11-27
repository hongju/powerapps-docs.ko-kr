---
title: "API 커넥터 개발 | Microsoft Docs"
description: "API를 설명하고, 인증 유형을 지정하고, 트리거 및 작업을 빌드하고, 테스트합니다."
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
ms.openlocfilehash: 68a0be6c6be91ff5b89b3e06aecc242f987a4cf4
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="develop-an-api-connector-powerapps"></a>API 커넥터 개발(PowerApps)
커넥터를 빌드하기 위한 프로세스에는 여러 단계가 포함됩니다. 시작하려면 [PowerApps](https://web.powerapps.com/)에서 페이지의 오른쪽 위에 있는 **설정** 단추(기어 아이콘)를 클릭하거나 탭합니다. 그런 다음, **사용자 지정 커넥터**를 클릭하거나 탭합니다.

![API 커넥터 찾기](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>API 설명
API 커넥터는 HTTP API의 인터페이스를 정의하기 위해 [OpenAPI 표준](https://swagger.io/)을 사용하여 설명됩니다. 기존 OpenAPI 파일로 빌드를 시작하거나, OpenAPI 파일을 자동으로 생성하는 [Postman Collection](https://www.getpostman.com/docs/collections)을 가져올 수 있습니다. 

![API 다이어그램 정의](./media/api-connectors-dev/build-your-api-updated.png)

이러한 API 설명 중 하나로 시작하는 경우 마법사의 메타데이터 필드는 자동으로 채워집니다. 이러한 항목은 언제든지 편집할 수 있습니다.  

## <a name="build-security"></a>보안 빌드
사용자 서비스에서 지원하는 인증 유형을 선택하고, 서비스와 클라이언트 간 적절한 ID 흐름을 사용 가능하게 하도록 추가 세부 사항을 제공합니다. 

![보안 다이어그램](./media/api-connectors-dev/security.png)

커넥터 보안에 대해 [자세히 알아보세요](register-custom-api.md).

## <a name="build-triggers-and-actions"></a>트리거 및 작업 빌드
1. 커넥터에 대한 트리거 및 작업을 빌드하려면 **정의** 탭으로 전환합니다. 
   
    ![정의 다이어그램](./media/api-connectors-dev/definition.png)
2. 마법사를 사용하여 새 작업을 추가하거나 스키마 및 기존 작업에 대한 응답을 편집할 수 있습니다. 각 작업에 대한 **General** 속성을 사용하여 커넥터에 대한 최종 사용자 환경을 제어할 수 있습니다. 아래 링크를 사용하여 다양한 유형의 작업에 대해 자세히 알아보세요.
   
   * [트리거](https://flow.microsoft.com/documentation/customapi-webhooks)(PowerApps에서는 보이지 않음)
   * [작업](register-custom-api.md)
     
     Microsoft Flow의 고급 기능을 구현하려면 [API 커넥터에 대한 OpenAPI 확장](https://flow.microsoft.com/documentation/customapi-how-to-swagger/)을 참조하세요. 
3. 마지막으로, **커넥터 만들기**를 클릭하거나 탭하여 API 커넥터를 등록합니다.

마법사에서 사용할 수 없는 추가 기능은 [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com)으로 문의하세요.

## <a name="test-the-connector"></a>커넥터 테스트
제출하기 전에 API 커넥터를 하나 이상의 방법으로 테스트합니다. 

* API 커넥터 [테스트 마법사](https://flow.microsoft.com/blog/new-updates-custom-api/)를 사용하면 각 작업을 호출하여 기능 및 응답 스키마를 확인할 수 있습니다.
* Microsoft Flow를 위한 디자이너에서 API 커넥터를 사용하여 흐름을 시각적으로 빌드할 수 있습니다. 이 테스트 방법을 통해 커넥터의 사용자 인터페이스 기능 및 특징을 시각화할 수 있습니다.
* PowerApps Studio에서 수식 입력줄을 사용하여 각 작업을 호출하고, 화면에 컨트롤에 대한 응답을 바인딩할 수 있습니다.

이 토픽에서는 개요를 제공합니다. 자세한 내용은 [사용자 지정 커넥터의 등록 및 사용](register-custom-api.md)을 참조하세요.

