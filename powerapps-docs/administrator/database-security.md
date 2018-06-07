---
title: 환경 보안 구성 | Microsoft Docs
description: 이 항목에서는 환경 보안을 구성하는 방법에 대해 설명합니다.
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: d9bd70acaacbbeda98c14337035a233b7c70c181
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168162"
---
# <a name="configure-environment-security"></a>환경 보안 구성
앱용 CDS(Common Data Service)는 데이터베이스에 대한 보안 액세스를 위해 역할 기반 보안 모델을 사용합니다. 이 항목에서는 앱의 보안을 유지하기 위해 필요한 보안 아티팩트를 만드는 방법을 설명합니다. 사용자 역할은 데이터에 대한 런타임 액세스를 제어하며 환경 관리자 및 환경 작성자가 제어하는 환경 역할과는 별개입니다. 환경 개요는 [환경 개요](environments-overview.md)를 참조하세요.

## <a name="assign-security-roles-to-users"></a>사용자에게 보안 역할 할당
보안 역할은 액세스 수준 및 권한 집합을 통해 데이터에 대한 사용자의 액세스를 제어합니다. 특정 보안 역할에 포함된 액세스 수준 및 사용 권한의 조합은 사용자의 데이터 보기 및 사용자와 해당 데이터의 상호 작용에 대한 제한을 설정합니다.

사용자 또는 보안 그룹을 환경 역할에 할당하기 위해 Environment Admin는 [PowerApps 관리 센터][1]에서 다음 단계를 취할 수 있습니다.

1. 환경 테이블에서 환경을 선택합니다.

    ![](./media/environment-admin/environment-list-new.png)

2. **보안** 탭을 선택합니다.

3. **환경에서 사용자 목록 보기**를 선택하여 사용자가 이미 환경에 있는지 확인합니다.
    
    ![](./media/database-security/security-viewuser.png)

4. 사용자가 없는 경우 PowerApps 관리 센터에서 사용자를 추가할 수 있습니다. 조직에서 사용자의 이메일 주소를 언급하고 **사용자 추가**를 선택하여 사용자를 추가합니다.

    ![](./media/database-security/security-adduser.png)

    몇 분 정도 기다린 후에 환경의 사용자 목록에 사용자가 표시되는지 확인합니다.
  
5. 환경의 사용자 목록에서 사용자를 선택합니다.

    ![](./media/environment-admin/D365-Select-User.png)

6. 사용자에게 역할을 할당합니다.

    ![](./media/environment-admin/D365-Assign-Role.png)

    > [!NOTE]
    > 현재는 사용자에게만 역할을 할당할 수 있습니다. 보안 그룹에도 역할을 할당할 수 있도록 준비 중입니다.

7. **확인**을 선택하여 환경 역할에 대한 할당을 업데이트합니다.

## <a name="predefined-security-roles"></a>미리 정의된 보안 역할
PowerApps 환경에는 앱을 사용하는 데 필요한 최소한의 비즈니스 데이터에 대한 액세스를 제공하는 보안 모범 사례 목표에 맞게 정의된 액세스 수준으로 일반 사용자 작업을 반영하는 미리 정의된 보안 역할이 포함됩니다.

|보안 역할  |*데이터베이스 권한  |설명 |
|---------|---------|---------|
|시스템 관리자     |  만들기, 읽기, 쓰기, 삭제, 사용자 지정, 보안 역할       | 보안 역할 만들기, 수정 및 할당을 포함하여 환경을 사용자 지정하거나 관리하기 위한 모든 권한을 가집니다. 환경의 모든 데이터를 볼 수 있습니다. 자세한 정보: [사용자 지정에 필요한 권한](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|시스템 사용자 지정자     | 만들기(자체), 읽기(자체), 쓰기(자체), 삭제(자체), 사용자 지정         | 환경을 사용자 지정하기 위한 전체 권한을 가집니다. 그러나 작성한 환경 엔터티에 대한 레코드만 볼 수 있습니다. 자세한 정보: [사용자 지정에 필요한 권한](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|환경 작성자     |  없음       | Microsoft Flow를 사용하여 앱, 연결, 사용자 지정 API, 게이트웨이 및 흐름을 포함한 환경과 관련된 새 리소스를 만들 수 있습니다. 그러나 환경 내의 데이터에 액세스할 수 있는 권한은 없습니다. 자세한 정보: [환경 개요](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Common Data Service 사용자     |  읽기, 만들기(자체), 쓰기(자체), 삭제(자체)       | 환경 내에서 앱을 실행하고 자신이 소유한 레코드에 대한 일반적인 작업을 수행할 수 있습니다.        |
|대리자     | 다른 사용자를 대신하여 작업 수행        | 코드가 다른 사용자의 권한으로 실행되거나 다른 사용자를 가장할 수 있습니다.  일반적으로 레코드에 대한 액세스를 허용하기 위해 다른 보안 역할과 함께 사용됩니다. 추가 정보: [다른 사용자 가장](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*권한은 달리 지정되지 않는 한 전역 범위입니다.

- 환경 작성자 역할은 환경 내에 리소스를 만들 수 있을 뿐 아니라 환경에서 빌드한 앱을 조직의 다른 사용자에게 배포할 수 있습니다. 앱을 개별 사용자와 공유할 수 있습니다. 자세한 내용은 [PowerApps에서 앱 공유](../maker/canvas-apps/share-app.md)를 참조하세요.

- 데이터베이스에 연결되는 앱을 만들고 엔터티 및 보안 역할을 만들거나 업데이트해야 하는 사용자의 경우 데이터베이스에 대한 권한이 없는 환경 작성자 역할과 함께 시스템 사용자 지정자 역할이 할당되어야 합니다.

## <a name="create-or-configure-a-custom-security-role"></a>사용자 지정 보안 역할 만들기 또는 구성
앱이 사용자 지정 엔터티를 기반으로 하는 경우 권한을 명시적으로 지정해야만 사용자가 작업할 수 있습니다. 이렇게 하려면 다음 중 하나를 수행하도록 선택할 수 있습니다.
- 기존의 미리 정의된 보안 역할을 확장하여 사용자 지정 엔터티를 기반으로 하는 레코드에 대한 권한을 포함시킵니다.
- 앱 사용자를 위한 권한을 관리할 목적으로 사용자 지정 보안 역할을 만듭니다.

환경에서 여러 앱에 사용 가능한 레코드를 유지할 수도 있으며, 여러 권한으로 데이터에 액세스하려면 여러 보안 역할이 필요할 수 있습니다. 예:
- 일부 사용자(유형 A)는 다른 레코드를 읽고 업데이트하고 첨부해야만 보안 역할에 읽기, 쓰기 및 추가 권한이 부여됩니다.
- 다른 사용자는 유형 A 사용자가 가지고 있는 모든 권한과 더불어 만들기, 추가, 삭제 및 공유 기능을 필요로 하기 때문에 보안 역할이 만들기, 읽기, 쓰기, 추가, 삭제, 할당 및 공유할 수 있습니다.

액세스 및 범위 권한에 대한 자세한 내용은 [보안 역할](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles)을 참조하세요.

1. [PowerApps 관리 센터][1]에서 보안 역할을 업데이트하려는 환경을 선택합니다.

    ![](./media/environment-admin/choose-environment-updated.png)

2. **세부 정보** 탭의 링크를 클릭하면 Dynamics 365 관리 센터에서 환경을 관리할 수 있습니다.

3. 인스턴스(환경과 이름이 같은)를 선택하고 열기를 클릭합니다.

    ![](./media/database-security/glados-instance-list.png)

4. 헤더에서 **설정**을 클릭하고 **보안**을 선택합니다.

    ![](./media/database-security/dyn365-settings-security.png)

5. **보안 역할**을 선택합니다.

    ![](./media/database-security/dyn365-securityroles.png)

6. **새로 만들기**를 클릭합니다.

7. 보안 역할 디자이너에서 읽기, 쓰기 또는 삭제와 같은 작업과 해당 작업을 수행할 범위를 선택합니다.

8. 탭을 선택하고 엔터티를 검색합니다. 예를 들어 사용자 지정 엔터티에 대한 권한을 설정하려면 **사용자 지정 엔터티** 탭을 선택합니다.

9. **읽기, 쓰기, 추가** 권한을 선택합니다.

10. **저장 후 닫기**를 선택합니다.



<!--Reference links in article-->
[1]: https://admin.powerapps.com
