---
title: "Common Data Service 데이터베이스 만들기 | Microsoft Docs"
description: "Common Data Service 데이터베이스를 만듭니다."
services: powerapps
documentationcenter: na
author: nimakms
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: a2224d97c9cfc1261e43f7d30c8d8bdd2dd6e86b
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="create-a-common-data-service-database"></a>Common Data Service 데이터베이스 만들기
Common Data Service를 데이터 저장소로 사용하여 데이터베이스를 만들고 앱을 빌드할 수 있습니다. 사용자 고유의 사용자 지정 엔터티를 만들거나 미리 정의된 엔터티를 사용할 수 있습니다. 데이터베이스를 만들려면 먼저 환경을 만들거나 관리자 권한으로 기존 환경에 할당해야 합니다. 또한 적절한 라이선스를 할당 받아야 합니다. Common Data Service 사용을 위한 계획 구매에 대한 자세한 내용은 [가격 책정 정보](pricing-billing-skus.md)를 참조하세요.

세 가지 방법으로 데이터베이스를 만들 수 있습니다.

* 관리 센터에서
* powerapps.com의 **홈** 창에서
* powerapps.com의 **엔터티** 창에서

## <a name="create-a-database-in-the-admin-center"></a>관리 센터에서 데이터베이스 만들기
1. [관리 센터](https://admin.powerapps.com)의 왼쪽 탐색 창에서 **환경**을 클릭합니다.
2. 환경을 선택하거나 필요한 경우 새 환경을 만듭니다.
3. **데이터베이스** 탭에서 **데이터베이스 만들기**를 클릭합니다. 기본적으로 데이터베이스는 개방형 액세스 모드에서 만들어집니다.
4. 보안을 적용하려는 경우 **액세스 제한**을 선택합니다.

## <a name="create-a-database-in-the-home-pane-of-powerappscom"></a>powerapps.com의 홈 창에서 데이터베이스 만들기
1. [powerapps.com](https://web.powerapps.com)의 왼쪽 탐색 창에서 **홈**을 클릭합니다.
2. **Microsoft Common Data Service 사용** 섹션에서 **데이터베이스 만들기** 또는 **시작**이라는 이름의 단추를 찾습니다. 단추의 이름은 라이선스 및 사용 권한 할당에 따라 달라집니다. 현재 환경에서 데이터베이스를 만들도록 허용되지 않을 수 있습니다.

### <a name="create-database-in-current-environnmet"></a>현재 환경에서 데이터베이스 만들기
1. **데이터베이스 만들기**를 클릭합니다.
2. 대화 상자에서 보안을 적용하려는 경우 **데이터베이스에 대한 액세스 제한** 확인란을 선택합니다.
3. **내 데이터베이스 만들기**를 클릭합니다.

### <a name="get-started-by-creating-a-new-environment"></a>새 환경을 만들어 시작
1. **시작**을 클릭합니다.
2. 대화 상자에서 **새 환경 만들기**를 클릭하여 새 환경 및 데이터베이스 만들기를 시작합니다.
3. **환경 이름** 필드에 고유한 이름을 입력합니다. **지역** 필드에서 적절한 영역을 선택합니다.
4. 보안을 적용하려는 경우 **데이터베이스에 대한 액세스 제한** 확인란을 선택합니다.
5. **만들기**를 클릭합니다.

## <a name="create-a-database-in-the-entities-pane-of-powerappscom"></a>powerapps.com의 엔터티 창에서 데이터베이스 만들기
1. [powerapps.com](https://web.powerapps.com)에서 **Common Data Service** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.
2. **시작**을 클릭합니다. 데이터베이스는 개방형 액세스 모드에서 만들어집니다.

## <a name="open-and-restricted-databases"></a>개방형 및 제한된 데이터베이스
기본적으로 데이터베이스는 개방형 액세스 모드에서 만들어집니다. 이 모드에서 엔터티에 대한 액세스의 보안은 적용되지 않습니다. 환경 관리자는 액세스 제한 모드로 데이터베이스를 설정할 수 있습니다. 이 모드에서 엔터티에 대한 액세스의 보안은 사용 권한 집합 및 역할에 따라 적용됩니다.

1. [관리 센터](https://admin.powerapps.com)의 왼쪽 탐색 창에서 **환경**을 클릭합니다.
2. 환경을 선택합니다.
3. **데이터베이스** 탭에서 다음 단계 중 하나를 수행합니다.
   * 보안을 적용하려면 **액세스 제한**을 선택합니다.
   * 보안을 사용하지 않으려면 **개방형 액세스**를 선택합니다.

## <a name="license-and-security-permissions"></a>라이선스 및 보안 권한
데이터베이스를 만들려면 선택된 환경에서 관리자여야 하며 적절한 라이선스를 할당 받아야 합니다. 환경에서 **보안** 탭을 사용하여 다른 사용자에 대한 보안 권한을 구성할 수 있습니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md) 및 [보안 모델](https://docs.microsoft.com/en-us/common-data-service/entity-reference/security-model)을 참조하세요.

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다.  이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.

