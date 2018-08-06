---
title: 캔버스 앱 공유 | Microsoft Docs
description: 다른 사용자에게 캔버스 앱을 실행하거나 수정할 수 있는 권한을 부여하여 앱 공유
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/11/2018
ms.author: anneta
ms.openlocfilehash: eaea8049b573b619881ae0a2b6ecb2618e4bf192
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39470641"
---
# <a name="share-a-canvas-app-in-powerapps"></a>PowerApps에서 캔버스 앱 공유

비즈니스 요구를 해결하는 캔버스 앱을 빌드한 후에 조직의 어떤 사용자가 앱을 실행하고 수정하며 심지어 다시 공유할 수 있는지 지정합니다. 이름으로 각 사용자를 지정하거나, Azure Active Directory의 보안 그룹을 지정합니다. 모든 사용자가 앱의 이점을 누리는 경우 조직 전체가 실행할 수 있도록 지정합니다.

> [!IMPORTANT]
> 공유 앱이 예상대로 작동하려면 앱이 기반한 데이터 원본(예: [앱용 Common Data Service](#common-data-service-for-apps) 또는 [Excel](share-app-data.md))에 대한 사용 권한도 관리해야 합니다. 또한, 앱이 종속된 [기타 리소스](share-app-resources.md)(예: 흐름, 게이트웨이 또는 연결)도 공유해야 합니다.

## <a name="prerequisites"></a>필수 조건

앱을 공유하려면 로컬이 아닌 클라우드에 저장한 다음, 앱을 게시해야 합니다.

- 사용자가 앱의 기능에 대해 알고 목록에서 쉽게 찾을 수 있도록 앱에 의미 있는 이름을 지정하고 명료한 설명을 제공합니다. PowerApps Studio의 **파일** 메뉴에서 **앱 설정**을 선택하고 이름을 지정한 다음, 설명을 입력하거나 붙여넣습니다.

- 변경 사항을 적용할 때마다 다른 사용자가 해당 변경 사항을 보길 원한다면 저장하고 앱을 다시 게시합니다.

## <a name="share-an-app"></a>앱 공유

1. [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인한 다음, 왼쪽 가장자리 근처에서 **앱**을 선택합니다.

    ![앱 목록 표시](./media/share-app/file-apps.png)

1. 공유하려는 앱에 대한 줄임표(...)를 선택한 다음, **공유**를 선택합니다.

    ![공유 화면 열기](./media/share-app/ellipsis-share.png)

1. Azure Active Directory에서 앱을 공유하려는 사용자 또는 보안 그룹을 지정합니다.

    > [!NOTE]
    > 조직의 메일 그룹, 또는 조직 외부의 사용자나 그룹과는 앱을 공유할 수 없습니다.

    ![사용자 지정](./media/share-app/share-list.png)

    전체 조직과 앱을 공유하여 앱을 실행하도록 할 수도 있지만 이 경우 수정하거나 공유할 수는 없습니다.

1. (선택 사항) 사용자가 앱을 찾을 수 있도록 이메일 초대 보내기 확인란을 선택합니다.

    초대에는 사용자가 앱을 실행하도록 선택할 수 있는 링크가 포함되어 있습니다.

    - 사용자가 데스크톱 컴퓨터에서 링크를 선택하는 경우 앱이 [Dynamics 365](http://home.dynamics.com)로 열립니다.
    - 사용자가 모바일 장치에서 링크를 선택하는 경우 앱이 PowerApps Mobile에서 열립니다.

    사용자에게 앱을 수정할 수 있는 사용 권한을 부여한 경우 PowerApps Studio에서 편집할 수 있도록 앱을 열 수 있는 별도의 링크도 포함됩니다.

    초대를 보낼지 여부와 상관 없이 사용자는 [Dynamics 365](http://home.dynamics.com)의 AppSource에서 앱을 실행할 수 있습니다. **편집 가능** 사용 권한이 있는 사용자는 [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 내에서도 앱을 편집할 수 있습니다.

1. 각 사용자 또는 보안 그룹에 대한 사용 권한을 지정한 다음, **저장**을 선택합니다.

    - **사용 가능**: 사용자가 앱을 실행할 수 있지만 공유할 수는 없습니다.
    - **편집 가능**: 사용자가 앱을 실행하고 수정할 수 있으며 사용자 지정된 버전을 다른 사용자와 공유할 수 있습니다.

        ![사용 권한 지정](./media/share-app/edit-use.png)

    사용자 또는 보안 그룹에 대한 사용 권한을 변경하려면 사용자 또는 그룹에게 이미 있는 사용 권한 옆의 아래쪽 화살표를 선택한 다음, 다른 사용 권한을 지정합니다.

    사용자 또는 그룹에 대한 모든 사용 권한을 제거하려면 해당 사용자 또는 그룹에 대한 **x** 아이콘을 선택합니다.

## <a name="security-group-considerations"></a>보안 그룹 고려 사항

- 보안 그룹과 앱을 공유한 경우 그룹의 기존 회원 및 가입하는 모든 회원이 해당 그룹에 지정된 사용 권한을 받습니다. 그룹을 떠난 사람은 액세스 권한이 있는 다른 그룹에 속하거나, 개인으로 사용 권한이 부여되지 않는 한 해당 사용 권한을 잃게 됩니다.
- 보안 그룹의 모든 구성원은 앱에 대해 전체 그룹과 동일한 권한을 갖습니다. 하지만 해당 그룹의 한 명 또는 그 이상의 회원에게 더 많은 사용 권한을 지정하여 더 많은 액세스를 허용할 수 있습니다. 예를 들어 보안 그룹 A에 **사용 가능** 권한을 제공할 수 있지만 해당 그룹에 속한 사용자 B에게 **편집 가능** 권한을 제공할 수 있습니다. 보안 그룹의 모든 구성원은 앱을 실행할 수 있지만 사용자 B만 편집할 수 있습니다. 보안 그룹 A에 **편집 가능** 권한을, 사용자 B에게 **사용 가능** 권한을 제공할 경우, 해당 사용자는 여전히 앱을 편집할 수 있습니다.

## <a name="manage-entity-permissions"></a>엔터티 사용 권한 관리

### <a name="common-data-service-for-apps"></a>앱용 Common Data Service

앱용 Common Data Service에 기반하여 앱을 만드는 경우 앱을 실행하는 사용자가 앱을 실행할 엔터티에 대한 적절한 사용 권한을 갖고 있는지도 확인해야 합니다. 특히, 이러한 사용자는 관련 기록 만들기, 읽기, 쓰기 및/또는 삭제 등의 작업을 수행할 수 있는 보안 역할에 속해 있어야 합니다. 이 환경의 데이터베이스에 대한 **시스템 관리자** 또는 **시스템 사용자 지정자** 사용 권한이 있는 경우 사용자 지정 역할을 만든 다음, 사용자를 추가할 수 있습니다.

#### <a name="create-a-security-role"></a>보안 역할 만들기

1. [PowerApps에 로그인](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)하고 공유하려는 앱과 같은 환경에 있는지 확인합니다.

1. 오른쪽 위 모서리에 있는 기어 아이콘을 클릭하고 **고급 사용자 지정**을 선택합니다.

    ![고급 사용자 지정 창 열기](media/share-app/advanced-customizations.png)

1. **보안 역할** 링크를 선택합니다.

    ![보안 역할 열기](media/share-app/security-roles.png)

1. **모든 역할**에서 **새로 만들기**를 선택한 다음, 만들려는 역할에 대한 이름을 입력하거나 붙여 넣습니다.

    ![보안 역할 만들기](media/share-app/new-role.png)

1. 앱에서 사용하는 엔터티를 찾을 수 있도록 하나 이상의 탭을 선택한 다음, 보안 역할을 부여하려는 사용 권한을 선택합니다.

    예를 들어 이 그림은 **핵심 레코드** 탭에 나타나는 계정 엔터티에서 보안 역할이 레코드를 만들고, 읽고, 쓰고, 삭제할 수 있음을 보여 줍니다.

    ![사용 권한 지정](media/share-app/grant-access.png)

1. **저장 후 닫기**를 선택합니다.

#### <a name="assign-a-user-to-a-role"></a>역할에 사용자 할당

1. 이전 절차의 설명대로 **고급 사용자 지정** 창을 열고 **사용자** 링크를 선택합니다.

    ![사용자 링크](media/share-app/open-users.png)

1. 오른쪽 위 모서리에서 역할에 할당하려는 사용자의 이름을 입력하거나 붙여넣고 검색 아이콘을 선택합니다.

    ![사용자 검색](media/share-app/search-users.png)

1. 검색 결과에서 원하는 결과를 가리켜 나타나는 확인란을 선택합니다.

1. 위쪽 배너에서 **역할 관리**를 선택합니다.

1. 대화 상자가 나타나면 **Common Data Service 사용자**와 사용자가 앱에 필요한 역할에 대한 확인란을 선택하고 **확인**을 선택합니다.

    ![역할에 사용자 할당](media/share-app/assign-users.png)

### <a name="common-data-service-previous-version"></a>Common Data Service(이전 버전)

이전 버전의 Common Data Service에 기반한 앱을 공유하는 경우 해당 서비스에 대한 런타임 권한을 별도로 공유해야 합니다. 이 작업을 수행할 수 있는 권한이 없으면 환경 관리자에게 문의하세요.