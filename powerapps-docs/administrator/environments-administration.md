---
title: 환경 관리 | Microsoft Docs
description: PowerApps에서 만들기, 이름 바꾸기, 삭제 및 보안을 포함한 환경 관리
services: powerapps
suite: powerapps
documentationcenter: na
author: manasmams
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: d94ebeeada15f5e7f176b20575f7570c73e28c08
ms.sourcegitcommit: c5e3991e0e4e9f22a1e094d699f35adabfb97c6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="administer-environments-in-powerapps"></a>PowerApps에서 환경 관리
[PowerApps 관리 센터][1]에서 사용자가 만든 환경은 물론, Environment Admin 또는 System Administrator 역할에 추가된 환경을 관리합니다. 관리 센터에서 다음 관리 작업을 수행할 수 있습니다.

* 환경을 만듭니다.
* 환경 이름을 바꿉니다.
* Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거.
* 환경에 대한 Common Data Service 데이터베이스 프로비전.
* 데이터 손실 방지 정책 설정.
* 데이터베이스에 따라 개방 또는 제한된 데이터베이스 보안 정책 설정.
* Azure AD 테넌트 전역 관리자 역할(Office 365 전역 관리자 포함)의 구성원은 테넌트에 만들어진 모든 환경을 관리하고 테넌트 전체 정책을 설정할 수도 있습니다.

## <a name="access-the-powerapps-admin-center"></a>PowerApps 관리 센터에 액세스
PowerApps 관리 센터에 액세스하려면 다음 작업을 수행합니다.

* [admin.powerapps.com][1]으로 직접 이동하거나

* [powerapps.com][2]으로 이동한 다음, 탐색 헤더에서 기어 아이콘을 선택합니다.

    ![](./media/environment-admin/powerapps-gear-dropdown.png)

PowerApps 관리 센터에서 환경을 관리하려면 이러한 역할 중 하나가 있어야 있습니다.

* 환경의 Environment Admin 또는 System Administrator 역할 또는

* Azure AD 또는 Office 365 테넌트의 전역 관리자 역할

또한, 관리 센터에 액세스하려면 PowerApps 요금제 2 또는 Microsoft Flow 요금제 2 라이선스가 필요합니다. 자세한 내용은 [PowerApps 가격 페이지][3]를 참조하세요.

> [!IMPORTANT]
> PowerApps 관리 센터에서 변경한 내용은 [Microsoft Flow 관리 센터][4]에 영향을 미치고 그 반대의 경우도 마찬가지입니다.

## <a name="create-an-environment"></a>환경 만들기
환경을 만드는 방법에 대한 지침은 [빠른 시작: 환경 만들기](create-environment.md)를 참조하세요.

## <a name="view-your-environments"></a>환경 보기
관리 센터를 열면 기본적으로 환경 탭이 나타나고 사용자가 Environment Admin인 환경을 모두 나열합니다(아래 표시).

![](./media/environment-admin/environment-list-new.png)

Azure AD 또는 Office 365 테넌트의 전역 관리자 역할의 멤버인 경우 사용자는 자동으로 해당 환경의 Environment Admin이 되므로, 테넌트의 사용자가 만든 모든 환경이 나타납니다.

## <a name="rename-your-environment"></a>환경 이름 바꾸기
1. [PowerApps 관리 센터][1]를 열고 목록에서 이름을 바꿀 환경을 찾은 다음 클릭하거나 탭합니다.

    ![](./media/environment-admin/environment-list-updated3.png)

2. **세부 정보**를 클릭하거나 탭합니다.

    ![](./media/environment-admin/environment-rename-details-2.png)
3. **이름** 텍스트 상자에 새 이름을 입력한 다음 **저장**을 클릭합니다.

    ![](./media/environment-admin/environment-rename-2.png)

    환경에서 데이터베이스를 만든 경우 이 옵션이 표시되지 않습니다. Dynamics 365 관리 센터에서 **세부 정보** 탭의 링크를 클릭하여 환경의 이름을 바꿀 수 있습니다.

    ![](./media/environment-admin/Delete-D365AdminCenter.png)


## <a name="delete-your-environment"></a>환경 삭제
1. [PowerApps 관리 센터][1]에서 삭제하려는 환경을 클릭하거나 탭합니다.

    ![](./media/environment-admin/environment-list-updated3.png)
2. **세부 정보**를 클릭하거나 탭합니다.

    ![](./media/environment-admin/environment-rename-details-2.png)
3. **환경 삭제**를 클릭하거나 탭하여 환경을 삭제합니다.

    ![](./media/environment-admin/delete-environment-2.png)


## <a name="create-a-common-data-service-database-for-an-environment"></a>환경에 대한 Common Data Service 데이터베이스 만들기
환경에 아직 데이터베이스가 없을 경우 Environment Admin은 다음 단계에 따라 [PowerApps 관리 센터][1]에서 하나 만들 수 있습니다. PowerApps 요금제 2 라이선스가 있는 사용자만 Common Data Service 데이터베이스를 만들 수 있습니다.

1. 환경 테이블에서 환경을 선택합니다.

    ![](./media/environment-admin/choose-environment-updated.png)
2. **세부 정보** 탭을 선택합니다.
3. **데이터베이스 만들기**를 선택합니다.

    ![](./media/environment-admin/Create-DB-From-Details.png)


데이터베이스를 만든 후 보안 모델을 선택합니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

## <a name="manage-security-for-your-environments"></a>환경에 대한 보안 관리

### <a name="environment-permissions"></a>환경 사용 권한
환경에서 Azure AD 테넌트의 모든 사용자는 해당 환경의 사용자입니다. 그러나 권한이 많은 역할을 수행하려면 특정 환경 역할에 추가되어야 합니다. 환경에는 환경 내의 사용 권한에 대한 액세스를 제공하는 두 가지 기본 제공 역할이 있습니다.

* **Environment Admin** 역할(또는 **System Administrator** 역할)은 다음을 포함하는 환경에서 모든 관리 작업을 수행할 수 있습니다.
    * Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거.

    * 환경에 대한 Common Data Service 데이터베이스 프로비전.

    * 환경 내에서 만든 모든 리소스를 보고 관리합니다.

    * 데이터 손실 방지 정책을 설정합니다. 자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.

  > [!NOTE]
  > 환경에 데이터베이스가 있는 경우 **Environment Admin** 역할 대신 **System Administrator** 역할에 사용자를 할당해야 합니다.

* **Environment Maker** 역할은 앱, 연결, 사용자 지정 커넥터, 게이트웨이 및 Microsoft Flow를 사용한 흐름을 포함하는 환경 내에서 리소스를 만들 수 있습니다. 또한 환경에서 빌드한 앱을 조직의 다른 사용자에게 배포할 수 있습니다. 개별 사용자, 보안 그룹 또는 조직의 모든 사용자와 앱을 공유할 수 있습니다. 자세한 내용은 [PowerApps에서 앱 공유](../maker/canvas-apps/share-app.md)를 참조하세요.

사용자 또는 보안 그룹을 환경 역할에 할당하기 위해 Environment Admin는 [PowerApps 관리 센터][1]에서 다음 단계를 취할 수 있습니다.

1. 환경 테이블에서 환경을 선택합니다.

    ![](./media/environment-admin/choose-environment-updated.png)
2. **보안** 탭을 선택합니다.
3. 환경에 생성된 데이터베이스가 없는 경우:

    a. **Environment Admin** 또는 **Environment Maker** 역할을 선택합니다.

    ![](./media/environment-admin/choose-environment-role.png)

    b. Azure Active Directory에서 하나 이상의 사용자 또는 보안 그룹의 이름을 지정하거나, 전체 조직을 추가할지 지정합니다.

    ![](./media/environment-admin/enter-name.png)

    c. **저장**을 선택하여 환경 역할에 대한 할당을 업데이트합니다.

4. 환경에 데이터베이스가 생성된 경우:

    a. Dynamics 365에서 환경 역할을 관리할 링크를 클릭합니다.

    ![](./media/environment-admin/Security-Link-D365.png)

    b. 환경/인스턴스의 사용자 목록에서 사용자를 선택합니다.

    ![](./media/environment-admin/D365-Select-User.png)

    c. 사용자에게 역할을 할당합니다.

    ![](./media/environment-admin/D365-Assign-Role.png)

    d. **확인**을 선택하여 환경 역할에 대한 할당을 업데이트합니다.


> [!NOTE]
> 이러한 환경 역할에 할당된 사용자 또는 그룹은 환경 데이터베이스(있는 경우)에 대해 자동으로 액세스가 제공되지 않으므로 데이터베이스 소유자가 별도로 액세스를 부여해야 합니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.  
>
>

### <a name="database-security"></a>데이터베이스 보안
데이터베이스 스키마를 만들고 수정하며 환경에서 프로비전된 데이터베이스 내에 저장된 데이터베이스 연결하는 기능은 데이터베이스 사용자 역할 및 권한 집합으로 제어합니다. **보안** 탭의 **사용자 역할**과 **권한 집합** 섹션에서 환경 데이터베이스에 대한 사용자 역할과 권한 집합을 관리할 수 있습니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

![](./media/environment-admin/D365-Assign-Role.png)

## <a name="data-policies"></a>데이터 정책
조직의 데이터는 액세스 권한이 없는 대상과 공유되지 않도록 보호해야 합니다. 이 데이터를 보호하기 위해 공유할 수 있는 소비자 서비스 및 커넥터 특정 비즈니스 데이터를 정의하는 정책을 만들고 적용할 수 있습니다. 데이터를 공유할 수 있는 방법을 정의하는 이러한 정책을 DLP(데이터 손실 방지) 정책이라고 합니다. 사용자는 [PowerApps 관리 센터][1]의 **데이터 정책** 섹션에서 환경에 대한 DLP 정책을 관리할 수 있습니다.  자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.

![](./media/environment-admin/data-policies.png)

## <a name="frequently-asked-questions"></a>질문과 대답
### <a name="how-many-environments-can-i-create"></a>몇 개의 환경을 만들 수 있나요?
각 사용자는 라이선스에 따라 최대 2개의 평가판 환경과 2개의 프로덕션 환경을 만들 수 있습니다.

### <a name="how-many-databases-can-i-provision"></a>몇 개의 데이터베이스를 프로비전할 수 있나요?
각 사용자는 라이선스에 따라 2개의 평가판 환경과 2개의 프로덕션 환경에 데이터베이스를 프로비전할 수 있습니다. 사용자는 환경에 **환경 관리자**가 필요합니다.

### <a name="can-i-rename-an-environment"></a>환경 이름을 바꿀 수 있나요?
예, 이 기능은 PowerApps 관리 센터에서 사용 가능합니다. 자세한 내용은 [환경 관리](environments-administration.md#rename-your-environment)를 참조하세요.

### <a name="can-i-delete-an-environment"></a>환경을 삭제할 수 있나요?
예, 이 기능은 PowerApps 관리 센터에서 사용 가능합니다. 자세한 내용은 [환경 관리](environments-administration.md#delete-your-environment)를 참조하세요.

### <a name="as-an-environment-admin-can-i-view-and-manage-all-resources-apps-flows-apis-etc-for-an-environment"></a>Environment Admin은 환경에 대한 모든 리소스(앱, 흐름, API 등)를 보고 관리할 수 있나요?
예, 환경에 대한 앱 및 환경을 볼 수 있는 기능은 PowerApps 관리 센터에서 사용 가능합니다. 자세한 내용은 [앱 보기](admin-view-apps.md)를 참조하세요.

### <a name="which-license-includes-common-data-service"></a>Common Data Service에는 어떤 라이선스가 포함되나요?
PowerApps 요금제 2.  이 라이선스가 포함된 모든 요금제에 대한 자세한 내용은 [PowerApps 가격 페이지][3]를 참조하세요.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://powerapps.microsoft.com/pricing/
[4]: https://admin.flow.microsoft.com
