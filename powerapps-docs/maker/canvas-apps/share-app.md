---
title: 캔버스 앱 공유 | Microsoft Docs
description: 다른 사용자에게 캔버스 앱을 실행하거나 수정할 수 있는 권한을 부여하여 앱 공유
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 11/28/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 34cf740bb029440480618a180ac45bc094c061d5
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58357279"
---
# <a name="share-a-canvas-app-in-powerapps"></a>PowerApps에서 캔버스 앱 공유

비즈니스 요구를 해결하는 캔버스 앱을 빌드한 후에 조직의 어떤 사용자가 앱을 실행하고 수정하며 심지어 다시 공유할 수 있는지 지정합니다. 이름으로 각 사용자를 지정하거나, Azure Active Directory의 보안 그룹을 지정합니다. 모든 사용자가 앱의 이점을 누리는 경우 조직 전체가 실행할 수 있도록 지정합니다.

> [!IMPORTANT]
> 공유 앱이 예상 대로 작동에 관리 해야 데이터 원본 또는 앱을 기준으로 하는와 같은 원본에 대 한 권한을 [Common Data Service](#common-data-service) 하거나 [Excel](share-app-data.md)합니다. 또한, 앱이 종속된 [기타 리소스](share-app-resources.md)(예: 흐름, 게이트웨이 또는 연결)도 공유해야 합니다.

## <a name="prerequisites"></a>필수 조건

앱을 공유하려면 로컬이 아닌 클라우드에 저장한 다음, 앱을 게시해야 합니다.

- 사용자가 앱의 기능에 대해 알고 목록에서 쉽게 찾을 수 있도록 앱에 의미 있는 이름을 지정하고 명료한 설명을 제공합니다. PowerApps Studio의 **파일** 메뉴에서 **앱 설정**을 선택하고 이름을 지정한 다음, 설명을 입력하거나 붙여넣습니다.

- 변경 사항을 적용할 때마다 다른 사용자가 해당 변경 사항을 보길 원한다면 저장하고 앱을 다시 게시합니다.

## <a name="share-an-app"></a>앱 공유

1. [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인한 다음, 왼쪽 가장자리 근처에서 **앱**을 선택합니다.

    ![앱 목록 표시](./media/share-app/file-apps.png)

1. 해당 아이콘을 선택 하 여 공유 하려는 앱을 선택 합니다.

    ![앱 선택](./media/share-app/select-app.png)

1. 배너를 선택 **공유**합니다.

    ![공유 화면 열기](./media/share-app/banner-share.png)

1. 지정 이름 또는 별칭으로 사용자 또는 보안 그룹과 앱을 공유 하려는 Azure Active Directory에서 합니다.

    - 조직 전체 앱을 실행 합니다 (하지만 수정 하거나 공유)를 허용 하려면 입력 **Everyone** 공유 패널에서 합니다.
    - 별칭, 친숙 한 이름 또는 조합 된 목록을 사용 하 여 앱을 공유할 수 있습니다 (예를 들어 **Jane Doe &lt; jane.doe@contoso.com>**) 항목은 세미콜론으로 구분 하는 경우. 둘 이상의 명 동일한 이름을 갖지만 다른 별칭을 찾을 수 있는 첫 번째 사용자 목록에 추가 됩니다. 도구 설명에는 이름이 나 별칭을 이미 권한이 또는 확인할 수 없는 경우 표시 됩니다. 
    
    ![사용자 및 공동 소유자를 지정 합니다.](./media/share-app/share-everyone.png)

    > [!NOTE]
    > 조직 외부 사용자 또는 그룹 또는 조직에서 배포 그룹을 사용 하 여 앱을 공유할 수 없습니다.

1. 편집한 (실행 외에도 해당), 공유 앱을 공유 하는 사용자는 선택 허용 하려는 경우는 **공동 소유자** 확인란 합니다.

    권한을 부여할 수 없습니다 **공동 소유자** 보안 권한을 그룹화 하는 경우 있습니다 [솔루션 내에서 앱을 만든](add-app-solution.md)합니다.
    
    > [!NOTE]
    > 권한에 관계 없이 직원 동시에 앱을 편집할 수 있습니다. 하나의 사용자가 편집을 위해 앱을 열면 다른 사용자가 실행할 수 있지만 편집할 수는 없습니다.

1. 앱 사용자가 액세스 권한을 해야 하는 데이터에 연결 하는 경우를 지정 합니다.

    예를 들어, 앱은 Common Data Service 데이터베이스의 엔터티에 연결할 수 있습니다. 이러한 앱을 공유 하는 경우 공유 패널 해당 엔터티에 대 한 보안을 관리 하 라는 메시지를 표시 합니다.

    ![사용 권한 설정](./media/share-app/set-permissions.png)

    엔터티에 대 한 보안을 관리 하는 방법에 대 한 자세한 내용은 참조 하세요. [엔터티 권한 관리](share-app.md#manage-entity-permissions) 이 항목의에서 뒷부분에 있습니다.

1. 사람들이 앱을 선택 찾을 수 있도록 하려는 경우는 **새 사용자에 게 메일 초대를 보내려면** 확인란 합니다.

1. 공유 패널의 맨 아래에서 선택 **공유**합니다.

    모든 앱을 공유한 사용자가에서 실행할 수 PowerApps Mobile에서 모바일 장치에서 또는 AppSource [Dynamics 365](https://home.dynamics.com) 브라우저에서 합니다. 공동 소유자를 편집 하 고 앱을 공유할 수 [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)합니다.

    전자 메일 초대를 보낼 경우 초대에 대 한 링크를 선택 하 여 실행할 수 앱을 공유한 모든 사용자.

    - 사용자가 모바일 장치에서 링크를 선택 하는 경우 앱이 PowerApps Mobile에서 열립니다.
    - 사용자가 데스크톱 컴퓨터에서 링크를 선택 하는 경우 앱이 브라우저에서 열립니다.

    공동 소유자는 초대를 받을 PowerApps Studio 편집을 위해 앱을 열면 다른 링크를 가져옵니다.

해당 이름을 선택 하 고 다음이 단계 중 하나를 수행 하 여 사용자 또는 보안 그룹에 대 한 권한을 변경할 수 있습니다.

- 실행할 앱 있지만 더 이상 편집 하거나 공유할 공동 소유자를 허용 하려면 선택을 취소 합니다 **공동 소유자** 확인란 합니다.
- 해당 사용자 또는 그룹을 사용 하 여 앱을 공유를 중지 하려면 제거 (x) 아이콘을 선택 합니다.

## <a name="security-group-considerations"></a>보안 그룹 고려 사항

- 보안 그룹과 앱을 공유한 경우 그룹의 기존 회원 및 가입하는 모든 회원이 해당 그룹에 지정된 사용 권한을 받습니다. 그룹을 떠난 사람은 액세스 권한이 있는 다른 그룹에 속하거나, 개인으로 사용 권한이 부여되지 않는 한 해당 사용 권한을 잃게 됩니다.
- 보안 그룹의 모든 구성원은 앱에 대해 전체 그룹과 동일한 권한을 갖습니다. 하지만 해당 그룹의 한 명 또는 그 이상의 회원에게 더 많은 사용 권한을 지정하여 더 많은 액세스를 허용할 수 있습니다. 예를 들어, 앱을 실행 하는 보안 그룹 권한을 제공할 수 있습니다 하지만 해당 그룹에 속한 사용자 B를 제공할 수도 **공동 소유자** 권한. 보안 그룹의 모든 구성원은 앱을 실행할 수 있지만 사용자 B만 편집할 수 있습니다. 보안 그룹 A를 제공 하는 경우 **공동 소유자** 권한 및 앱을 실행 하려면 사용자 B 권한을 해당 사용자 여전히 앱을 편집할 수 있습니다.

## <a name="manage-entity-permissions"></a>엔터티 사용 권한 관리

### <a name="common-data-service"></a>Common Data Service

Common Data Service에 따라 앱을 만드는 경우 사용자가 앱을 공유 하는 엔터티 또는 엔터티는 앱 사용에 대 한 적절 한 권한이 있는지 확인 해야 합니다. 특히, 해당 사용자는 관련 레코드를 삭제 하 고 만들기, 읽기, 쓰기 등의 작업을 수행할 수 있는 보안 역할에 속해야 합니다. 대부분의 경우 사용자가 앱을 실행 해야 하는 정확 하 게 사용 권한이 있는 하나 이상의 사용자 지정 보안 역할을 만들려고 합니다. 그런 다음 적절 하 게 각 사용자에 게 역할을 할당할 수 있습니다.

> [!NOTE]
> 이 문서의 작성 시점 현재 보안 그룹이 아니라 개별 사용자에 게 보안 역할을 할당할 수 있습니다.

#### <a name="prerequisite"></a>필수 조건

다음 두 절차를 수행 하려면 있어야 **시스템 관리자에 게** Common Data Service 데이터베이스에 대 한 권한.

#### <a name="create-a-security-role"></a>보안 역할 만들기

1. 공유 패널에서 선택 **사용 권한을 설정** 아래에서 **데이터 권한을**를 선택한 후는 **보안 역할** 링크.

    ![보안 역할 열기](media/share-app/security-roles.png)

1. **모든 역할**에서 **새로 만들기**를 선택한 다음, 만들려는 역할에 대한 이름을 입력하거나 붙여 넣습니다.

    ![보안 역할 만들기](media/share-app/new-role.png)

1. 앱에서 사용하는 엔터티를 찾을 수 있도록 하나 이상의 탭을 선택한 다음, 보안 역할을 부여하려는 사용 권한을 선택합니다.

    예를 들어이 그래픽을 표시 하는 합니다 **핵심 레코드** 탭에는 **계정** 엔터티와이 보안 역할이 할당 된 사용자 수 만들기, 읽기, 쓰기 및 해당 엔터티의 레코드를 삭제 .

    ![사용 권한 지정](media/share-app/grant-access.png)

1. **저장 후 닫기**를 선택합니다.

#### <a name="assign-a-user-to-a-role"></a>역할에 사용자 할당

1. 공유 패널에서 선택 **사용 권한을 설정** 아래에서 **데이터 권한을**를 선택한 후는 **사용자** 링크.

    ![사용자 링크](media/share-app/open-users.png)

1. 오른쪽 위 모서리에서 역할에 할당하려는 사용자의 이름을 입력하거나 붙여넣고 검색 아이콘을 선택합니다.

    ![사용자 검색](media/share-app/search-users.png)

1. 검색 결과에서 원하는 결과를 가리켜 나타나는 확인란을 선택합니다.

1. 위쪽 배너에서 **역할 관리**를 선택합니다.

1. 나타나는 대화 상자에서 확인란을 선택 **Common Data Service 사용자** 및 사용자에 게 필요한 앱에 대 한 역할을 선택 하 고 **확인 합니다.**

    ![역할에 사용자 할당](media/share-app/assign-users.png)

### <a name="common-data-service-previous-version"></a>Common Data Service(이전 버전)

이전 버전의 Common Data Service를 기반으로 하는 앱을 공유 하는 경우 서비스에 대 한 런타임 권한을 별도로 공유 해야 있습니다. 이 작업을 수행할 수 있는 권한이 없으면 환경 관리자를 참조 하세요.
