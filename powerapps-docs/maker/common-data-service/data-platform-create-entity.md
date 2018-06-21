---
title: 사용자 지정 엔터티를 만드는 빠른 시작 | Microsoft Docs
description: 이 빠른 시작에서는 PowerApps에서 사용자 지정 엔터티를 만드는 방법을 알아봅니다.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: ecbdc81b2688ee9aabf5e0df6416212957ca2642
ms.sourcegitcommit: 222df368f1f35e9357b0b1adf0e69d7206d8126e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298495"
---
# <a name="quickstart-create-a-custom-entity"></a>빠른 시작: 사용자 지정 엔터티 만들기
PowerApps에서 *엔터티*는 추적하려는 정보를 회사 이름, 위치, 제품, 메일 및 전화 등의 속성을 포함하는 레코드의 형태로 정의합니다. 그런 다음, 엔터티를 참조하는 앱을 개발하여 해당 데이터를 표시할 수 있습니다. PowerApps는 조직 내에서 일반적인 시나리오를 다루도록 표준 "기본 제공" 엔터티를 제공하지만 조직에 관련된 데이터를 저장하는 사용자 지정 엔터티를 만들어야 하는 경우가 있을 수 있습니다.

이 빠른 시작에서는 회사가 판매하는 제품에 대한 등급 및 설명을 표시하는 앱을 만드는 데 사용할 수 있는 제품 검토라는 사용자 지정 엔터티를 만드는 방법을 알아봅니다.

## <a name="prerequisites"></a>필수 조건
이 빠른 시작을 수행하려면 다음 항목이 필요합니다.
* PowerApps 요금제 2 또는 Microsoft Flow 요금제 2 라이선스. 또는 [평가판 PowerApps 계획 2](https://web.powerapps.com/signup?redirect=marketing&email=)에 등록할 수 있습니다.
* 앱용 Common Data Service 내에서 시스템 관리자 또는 시스템 사용자 지정자 보안 역할입니다.

## <a name="sign-in-to-powerapps"></a>PowerApps에 로그인
[https://web.powerapps.com](https://web.powerapps.com)에서 PowerApps에 로그인합니다.

## <a name="create-an-entity"></a>엔터티 만들기
1. 탐색 창에서 **데이터**를 클릭하거나 탭하여 확장한 다음, **엔터티**를 클릭하거나 탭합니다.

    ![엔터티 및 세부 정보 목록](./media/data-platform-cds-create-entity/entitylist.png "엔터티 목록")

2. 명령 모음에서 **새 엔터티**를 클릭하거나 탭합니다.

    엔터티를 만들기 전에 사용 가능한 표준 엔터티의 설명에 대한 [엔터티 참조](../../developer/common-data-service/reference/about-entity-reference.md)를 확인합니다. 이러한 엔터티는 일반적인 시나리오를 다룹니다. 이러한 엔터티 중 하나가 있는 그대로 또는 약간 변경된 후에 요구 사항을 충족하는 경우 해당 엔터티부터 시작하여 시간을 줄일 수 있습니다. 

3. **새 엔터티** 패널에서 **표시 이름** 상자에 **제품 검토**를 입력한 다음, 필요에 따라 설명을 입력합니다(설명은 다른 사람이 이 엔터티를 사용하는 경우 유용함). 패널의 다른 필드는 아래 설명한 것과 같이 채워집니다. 완료하면 **다음**을 클릭합니다.

    * **복수 표시 이름** - 이 필드는 표시 이름을 입력하면 채워지지만 필요에 따라 변경할 수 있습니다. 복수 표시 이름은 Common Data Service WebAPI에서 엔터티의 이름이며, PowerApps 또는 Flow에서 이 엔터티와 상호 작용할 때 사용됩니다.
    * **이름** - 이 필드도 표시 이름을 입력하면 채워집니다. 접두사는 환경이 만들어질 때 설정되었으며, 만든 엔터티가 다른 엔터티 이름과 충돌하지 않고 다른 환경으로 내보내고 가져올 수 있도록 합니다. Common Data Service 기본 솔루션에 대한 게시자의 접두사를 업데이트하여 이 접두사를 변경할 수 있습니다. 기존 앱을 중단되지 않도록 유지하기 위해 엔터티를 저장한 후 이름을 변경할 수 없습니다.
     
    ![새 엔터티](./media/data-platform-cds-create-entity/newentitypanel.png "새 엔터티 패널")

4. 엔터티 세부 정보 페이지에서 **기본 이름** 필드를 클릭하거나 탭하여 **기본 이름** 패널을 연 다음, **표시 이름** 상자에서 **기본 이름**을 **제품 검토**로 바꿉니다. **이름** 상자에서 **PrimaryName**을 **ProductReview**로 바꾼 다음, **완료**를 클릭하거나 탭합니다.
 
    기본적으로 모든 엔터티는 다른 엔터티와의 관계를 설정할 때 조회 필드에 사용되는 기본 이름 필드를 포함합니다. 일반적으로 기본 이름 필드는 엔터티에 저장되는 데이터의 이름 또는 기본 설명을 저장합니다. 처음으로 엔터티를 저장하기 전에 기본 이름 필드의 이름 및 표시 이름을 업데이트할 수 있습니다.

    ![엔터티 세부 정보](./media/data-platform-cds-create-entity/newentitydetails.png "새 엔터티 세부 정보")

5. 엔터티에 필드를 추가하려면 다음을 수행합니다.
 
    a. 명령 모음에서 **필드 추가**를 클릭하거나 탭하여 **필드 속성** 패널을 엽니다.

    b. **표시 이름** 상자에 **검토 날짜**를 입력합니다.

    c. **데이터 형식** 드롭다운 목록에서 **날짜만**을 선택합니다.

    d. **필수** 확인란을 클릭하거나 탭합니다.
    
    e. **완료**를 클릭하거나 탭합니다.
     
    자세한 내용은 [엔터티에서 필드 관리](data-platform-manage-fields.md)를 참조하세요.

    ![새 필드](./media/data-platform-cds-create-entity/newfieldpanel-2.png "새 필드 패널")

6. 이전 단계를 반복하여 다음 구성으로 3개의 필드를 더 추가합니다.
    * **표시 이름** = 제품 등급, **데이터 형식** = 정수, **필수** 확인란 클릭하거나 탭
    * **표시 이름** = 검토자 이름, **데이터 형식** = 텍스트
    * **표시 이름** = 검토자 설명, **데이터 형식** = 텍스트

    완료되면 엔터티 세부 정보 페이지에 다섯 개의 필드가 나열됩니다.

    ![필드 목록](./media/data-platform-cds-create-entity/addedfields.png "필드 목록")

    모든 엔터티에는 읽기 전용 시스템 필드가 있습니다. 기본적으로 시스템 필드는 엔터티에 있는 경우에도 필드 목록에 표시되지 않습니다. 모든 필드를 표시하려면 **기본**에서 **모두**로 명령 모음의 필터를 변경합니다. 엔터티와 관련된 메타데이터에 대한 자세한 내용은 [엔터티 메타데이터](../../developer/common-data-service/entity-metadata.md)를 참조하세요.

7. **엔터티 저장**을 클릭하여 엔터티를 저장하고 앱에서 사용할 수 있도록 합니다.

    제품 검토 엔터티는 데이터베이스의 엔터티 목록에 표시되어야 합니다. 표시되지 않는 경우 **기본**에서 **사용자 지정**으로 명령 모음의 필터를 변경합니다.

    ![필터](./media/data-platform-cds-create-entity/filter.png "필터 선택")

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 특정 회사에서 판매된 각 제품에 대한 등급 및 설명을 표시하는 앱을 만드는 데 사용할 수 있는 제품 검토라는 사용자 지정 엔터티를 만드는 방법을 알아봤습니다. 다음으로 각 제품을 수신하는 검토 및 설명과 연결할 수 있도록 엔터티 간의 관계를 정의하는 방법을 알아봅니다(이 경우 표준 제품 엔터티와 사용자 지정 하는 제품 검토 엔터티 간).

> [!div class="nextstepaction"]
> [관계 만들기](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>개인 정보 취급 방침
Microsoft PowerApps 공통 데이터 모델을 통해 Microsoft는 사용자 지정 엔터티 및 필드 이름을 진단 시스템에 수집 및 저장합니다. 이 정보는 고객을 위한 공통 데이터 모델을 향상하기 위해 사용합니다. 앱 작성자가 만드는 엔터티 및 필드 이름은 Microsoft PowerApps 커뮤니티에서 공통된 시나리오를 이해하고 조직에 관련된 스키마와 같은 서비스의 표준 엔터티 범위의 격차를 확인하는 데 도움을 줍니다. 이러한 엔터티와 연결된 데이터베이스 테이블의 데이터는 Microsoft에 의해 액세스되거나 사용되지 않고 데이터베이스가 프로비전되는 영역 외부에서 복제되지 않습니다. 단, 사용자 지정 엔터티 및 필드 이름은 지역에 걸쳐 복제될 수 있고 데이터 보존 정책에 따라 삭제될 수 있습니다. Microsoft는 [보안 센터](https://www.microsoft.com/trustcenter/Privacy/default.aspx)에서 더 자세히 설명한 것과 같이 개인 정보 보호를 위해 노력합니다.
