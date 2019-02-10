---
title: 앱용 CDS(Common Data Service) 데이터베이스 만들기 | Microsoft Docs
description: 앱용 CDS(Common Data Service) 데이터베이스 만드는 방법을 연습합니다.
services: powerapps
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 02/01/2019
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: f7b5fb27e5b135239e1fe2306f7c431d6d1e6aae
ms.sourcegitcommit: 676cfa415f67e2e8fcfcf30fab83fc118a6f3210
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55558752"
---
# <a name="create-a-common-data-service-for-apps-database"></a>앱용 CDS(Common Data Service) 데이터베이스 만들기
앱용 CDS(Common Data Service)를 데이터 저장소로 사용하여 데이터베이스를 만들고 앱을 빌드할 수 있습니다. 사용자 고유의 사용자 지정 엔터티를 만들거나 미리 정의된 엔터티를 사용할 수 있습니다. 데이터베이스를 만들려면 먼저 환경을 만들거나 기존 환경에 **환경 관리자**로 할당되어야 합니다. 또한 적절한 라이선스를 할당 받아야 합니다. 앱용 CDS 사용을 위한 계획 구매에 대한 자세한 내용은 [가격 책정 정보](pricing-billing-skus.md)를 참조하세요.

다양한 방법으로 데이터베이스를 만들 수 있습니다.

* PowerApps 관리 센터에서
* powerapps.com의 **엔터티** 창에서

## <a name="create-a-database-in-the-admin-center"></a>관리 센터에서 데이터베이스 만들기
1. [관리 센터](https://admin.powerapps.com)의 왼쪽 탐색 창에서 **환경**을 클릭합니다.
    
2. 데이터베이스를 만들려는 환경을 선택합니다.
    
    ![](./media/create-database/environment-list-new.png)

3. **세부 정보** 탭에서 **데이터베이스 만들기**를 클릭합니다. 
    
    ![](./media/create-database/Create-DB-From-Details.png)

4. 통화 및 데이터베이스를 선택하여 데이터베이스 만들기를 계속 진행합니다. 
    
    ![](./media/create-database/DB-Choose-options.png)

## <a name="create-a-database-in-the-entities-pane-of-powerapps"></a>PowerApps의 엔터티 창에서 데이터베이스 만들기
1. [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.

2. **데이터베이스 만들기**를 클릭하여 데이터베이스를 만듭니다.

    ![](./media/create-database/Create-DB-From-Entities.png)

## <a name="security-model-for-the-databases"></a>데이터베이스의 보안 모델
데이터베이스가 만들어지면 환경 역할이 할당된 사용자는 계속해서 해당 권한이 유지됩니다.  
    이제 **환경 관리자** 역할을 갖고 있는 사용자에게 **시스템 관리자** 역할이 할당됩니다. **환경 작성자** 역할을 갖고 있는 사용자는 계속해서 동일한 역할을 보유합니다.

미리 정의된 역할에 추가 사용자를 할당하거나 [사용자 정의 역할][1]을 만들 수 있습니다. 자세한 내용은 [데이터베이스 보안](database-security.md)을 참조하세요.

> [!NOTE]
> 데이터베이스를 만드는 즉시, 환경 관리자 또는 환경 작성자 역할에 할당된 모든 보안 그룹이 더 이상 적용되지 않습니다. 현재 AAD 보안 그룹은 데이터베이스에서 권한을 할당할 수 없습니다.


## <a name="license-and-security-permissions"></a>라이선스 및 보안 권한
데이터베이스를 만들려면 선택된 환경에서 관리자여야 하며 적절한 라이선스를 할당 받아야 합니다. 환경에서 **보안** 탭을 사용하여 다른 사용자에 대한 보안 권한을 구성할 수 있습니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다.  이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.


<!--Reference links in article-->
[1]: https://technet.microsoft.com/library/dn531130.aspx
