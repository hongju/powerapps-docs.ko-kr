---
title: "환경 관리 | Microsoft Docs"
description: "PowerApps에서 만들기, 이름 바꾸기, 삭제 및 보안을 포함한 환경 관리"
services: 
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/11/2017
ms.author: jamesol
ms.openlocfilehash: 1eeb79d0c109181ae75b86a78cecdb4babe058ab
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="environments-administration-in-powerapps"></a>PowerApps의 환경 관리
[PowerApps 관리 센터][1]에서 사용자가 만든 환경은 물론, 환경 관리자 역할에 추가한 환경을 관리합니다. 관리 센터에서 다음 관리 작업을 수행할 수 있습니다.

* 환경을 만듭니다.
* 환경 이름을 바꿉니다.
* Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거.
* 환경에 대한 Common Data Service 데이터베이스 프로비전.
* 데이터 손실 방지 정책 설정.
* 데이터베이스에 따라 개방 또는 제한된 데이터베이스 보안 정책 설정.
* Azure AD 테넌트 전역 관리자 역할(Office 365 전역 관리자 포함)의 구성원은 테넌트에 만들어진 모든 환경을 관리하고 테넌트 전체 정책을 설정할 수도 있습니다.

## <a name="access-the-powerapps-admin-center"></a>PowerApps 관리 센터에 액세스
PowerApps 관리 센터에 액세스하려면 다음 작업을 수행합니다.

* [admin.powerapps.com][1]으로 직접 이동하거나 또는
* [powerapps.com][2]으로 이동한 다음, 탐색 헤더에서 기어 아이콘을 선택합니다.
  
    ![](./media/environment-admin/powerapps-gear-dropdown.png)

PowerApps 관리 센터에서 환경을 관리하려면 이러한 역할 중 하나가 있어야 있습니다.

* 해당 환경에 대한 Environment Admin 역할 또는
* Azure AD 또는 Office 365 테넌트의 전역 관리자 역할

또한, 관리 센터에 액세스하려면 PowerApps 요금제 2 또는 Flow 요금제 2도 필요합니다. 자세한 내용은 [PowerApps 가격 페이지][3]를 참조하세요.

**중요**: PowerApps 관리 센터에서 적용한 변경 사항은 [Flow 관리 센터][4], 그리고 그 반대로 영향을 미칩니다.

## <a name="create-an-environment"></a>환경 만들기
먼저, 클릭 **+ 새 환경**을 클릭하여 대화 상자를 열고 환경을 만듭니다.

![](./media/environment-admin/new-environment-button.png)

그다런 음, 다음 정보를 입력합니다.

| 속성 | 설명 |
| --- | --- |
| 환경 이름 |환경의 이름을 입력합니다. |
| 지역 |환경을 호스팅할 위치를 선택합니다. 사용자에게 가장 가까운 위치를 사용하는 것이 좋습니다. 예를 들어 앱 사용자가 런던에 있는 경우 유럽 위치를 선택합니다. 앱 사용자가 뉴욕에 있는 경우 미국을 선택합니다. 지원되는 환경 영역 목록은 [지원되는 영역](regions-overview.md) 목록을 참조하세요. |
| 이 환경에 대한 데이터베이스 만들기 |이 환경에 대한 Common Data Service 데이터베이스를 만들려면 이 확인란을 선택합니다. 환경의 모든 사용자에 열려 있거나 데이터베이스 역할로 제한하도록 데이터베이스를 구성할 수 있습니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요. |

![](./media/environment-admin/new-environment-updated.png)

마지막으로 **환경 만들기**를 선택합니다.

새 환경이 환경 테이블에 나타납니다.

> [!NOTE]
> 환경을 만들면 사용자는 해당 환경의 Environment Admin 역할에 자동으로 추가됩니다.
> 
> 

## <a name="view-your-environments"></a>환경 보기
관리 센터를 열면 기본적으로 환경 탭이 나타나고 사용자가 Environment Admin인 환경을 모두 나열합니다(아래 표시).

![](./media/environment-admin/environment-list-updated.png)

Azure AD 또는 Office 365 테넌트의 전역 관리자 역할의 멤버인 경우 사용자는 자동으로 해당 환경의 Environment Admin이 되므로, 테넌트의 사용자가 만든 모든 환경이 나타납니다.

## <a name="rename-your-environment"></a>환경 이름 바꾸기
1. [PowerApps 관리 센터][1]를 열고 목록에서 이름을 바꿀 환경을 찾은 다음 클릭하거나 탭합니다.
   
    ![](./media/environment-admin/environment-list-updated3.png)
2. **세부 정보**를 클릭하거나 탭합니다.
   
    ![](./media/environment-admin/environment-rename-details-2.png)
3. **이름** 텍스트 상자에 새 이름을 입력한 다음 **저장**을 클릭합니다.
   
    ![](./media/environment-admin/environment-rename-2.png)

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
2. **데이터베이스** 탭을 선택합니다.
3. **데이터베이스 만들기**를 선택합니다.
   
    ![](./media/environment-admin/database-tab.png)
   
    데이터베이스가 프로비저닝되면 다음 확인 메시지가 나타납니다.
   
    ![](./media/environment-admin/database-tab-success.png)

데이터베이스를 만든 후 보안 모델을 선택합니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

## <a name="manage-security-for-your-environments"></a>환경에 대한 보안 관리
### <a name="environment-permissions"></a>환경 사용 권한
환경에서 Azure AD 테넌트의 모든 사용자는 해당 환경의 사용자입니다. 그러나 권한이 많은 역할을 수행하려면 특정 환경 역할에 추가되어야 합니다. 환경에는 환경 내의 사용 권한에 대한 액세스를 제공하는 두 가지 기본 제공 역할이 있습니다.

* **Environment Admin** 역할은 다음을 포함하는 환경에서 모든 관리 작업을 수행할 수 있습니다.
  
  o   Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거
  
  o   환경에 대한 Common Data Service 데이터베이스 프로비전
  
  o   환경 내에서 만든 모든 리소스 보기 및 관리
  
  o    데이터 손실 방지 정책 설정 자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.
* **Environment Maker** 역할은 앱, 연결, 사용자 지정 커넥터, 게이트웨이 및 Microsoft Flow를 사용한 흐름을 포함하는 환경 내에서 리소스를 만들 수 있습니다. 또한 환경에서 빌드한 앱을 조직의 다른 사용자에게 배포할 수 있습니다. 개별 사용자, 보안 그룹 또는 조직의 모든 사용자와 앱을 공유할 수 있습니다. 자세한 내용은 [PowerApps에서 앱 공유](share-app.md)를 참조하세요.

사용자 또는 보안 그룹을 환경 역할에 할당하기 위해 Environment Admin는 [PowerApps 관리 센터][1]에서 다음 단계를 취할 수 있습니다.

1. 환경 테이블에서 환경을 선택합니다.
   
    ![](./media/environment-admin/choose-environment-updated.png)
2. **보안** 탭에서 **환경 역할**을 선택합니다.
3. **Environment Admin** 또는 **Environment Maker** 역할을 선택합니다.
   
    ![](./media/environment-admin/choose-environment-role.png)
4. Azure Active Directory에서 하나 이상의 사용자 또는 보안 그룹의 이름을 지정하거나, 전체 조직을 추가할지 지정합니다.
   
    ![](./media/environment-admin/enter-name.png)
5. **저장**을 선택하여 환경 역할에 대한 할당을 업데이트합니다.

사용자 또는 그룹에 대한 모든 사용 권한을 제거하려면 해당 사용자 또는 그룹에 대한 **x** 아이콘을 클릭하거나 탭합니다.

> [!NOTE]
> 이러한 환경 역할에 할당된 사용자 또는 그룹은 환경 데이터베이스(있는 경우)에 대해 자동으로 액세스가 제공되지 않으므로 데이터베이스 소유자가 별도로 액세스를 부여해야 합니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.  
> 
> 

### <a name="database-security"></a>데이터베이스 보안
데이터베이스 스키마를 만들고 수정하며 환경에서 프로비전된 데이터베이스 내에 저장된 데이터베이스 연결하는 기능은 데이터베이스 사용자 역할 및 권한 집합으로 제어합니다. **보안** 탭의 **사용자 역할**과 **권한 집합** 섹션에서 환경 데이터베이스에 대한 사용자 역할과 권한 집합을 관리할 수 있습니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

![](./media/environment-admin/database-security.png)

> [!NOTE]
> Environment Admin은 환경 데이터베이스에 대한 사용자 역할과 권한 집합을 만들고 관리할 수 있는 액세스 권한이 없습니다. 이 권한은 **데이터베이스 소유자** 사용자 역할의 멤버로 국한됩니다.  
> 
> 

## <a name="data-policies"></a>데이터 정책
조직의 데이터는 액세스 권한이 없는 대상과 공유되지 않도록 보호해야 합니다. 이 데이터를 보호하기 위해 공유할 수 있는 소비자 서비스 및 커넥터 특정 비즈니스 데이터를 정의하는 정책을 만들고 적용할 수 있습니다. 데이터를 공유할 수 있는 방법을 정의하는 이러한 정책을 DLP(데이터 손실 방지) 정책이라고 합니다. 사용자는 [PowerApps 관리 센터][1]의 **데이터 정책** 섹션에서 환경에 대한 DLP 정책을 관리할 수 있습니다.  자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.

![](./media/environment-admin/data-policies.png)

## <a name="frequently-asked-questions"></a>질문과 대답
### <a name="how-many-environments-can-i-create"></a>몇 개의 환경을 만들 수 있나요?
각 사용자는 최대 2개의 환경을 만들 수 있습니다.

### <a name="how-many-databases-can-i-provision"></a>몇 개의 데이터베이스를 프로비전할 수 있나요?
각 사용자는 최대 2개의 데이터베이스를 프로비전할 수 있습니다.

### <a name="can-i-rename-an-environment"></a>환경 이름을 바꿀 수 있나요?
예, 이 기능은 PowerApps 관리 센터에서 사용 가능합니다. 자세한 내용은 [환경 관리](environments-administration.md#rename-your-environment)를 참조하세요.

### <a name="can-i-delete-an-environment"></a>환경을 삭제할 수 있나요?
예, 이 기능은 PowerApps 관리 센터에서 사용 가능합니다. 자세한 내용은 [환경 관리](environments-administration.md#delete-your-environment)를 참조하세요.

### <a name="as-an-environment-admin-can-i-view-and-manage-all-resources-apps-flows-apis-etc-for-an-environment"></a>Environment Admin은 환경에 대한 모든 리소스(앱, 흐름, API 등)를 보고 관리할 수 있나요?
예, 환경에 대한 앱 및 환경을 볼 수 있는 기능은 PowerApps 관리 센터에서 사용 가능합니다. 자세한 내용은 [앱 보기](admin-view-apps.md)를 참조하세요.

### <a name="which-license-includes-common-data-service"></a>Common Data Service에는 어떤 라이선스가 포함되나요?
PowerApps 요금제 2.  이 라이선스가 포함된 모든 요금제에 대한 자세한 내용은 [PowerApps 가격 페이지][3]를 참조하세요.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Common Data Service는 환경 외부에서 사용할 수 있나요?
아니요. Common Data Service에는 환경이 필요합니다.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://powerapps.microsoft.com/pricing/
[4]: https://admin.flow.microsoft.com
