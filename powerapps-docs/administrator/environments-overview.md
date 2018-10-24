---
title: 환경 개요 | Microsoft Docs
description: PowerApps의 환경 및 사용 방법 알아보기
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 08/29/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: e160098075b78a0a4de98da9c9915d0bef26d183
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297331"
---
# <a name="environments-overview"></a>환경 개요
환경은 조직의 비즈니스 데이터, 앱 및 흐름을 저장, 관리 및 공유하는 공간입니다. 또한 각기 다른 역할, 보안 요구 사항 또는 대상 그룹에 따라 앱을 구분하는 컨테이너 기능도 제공합니다. 환경 활용을 선택하는 방식은 해당 조직 및 빌드하려는 앱에 따라 달라집니다. 예:

* 단일 환경에서 앱만 빌드하도록 선택할 수 있습니다.
* 앱의 테스트 및 프로덕션 버전을 그룹화하는 별도 환경을 만들 수 있습니다.
* 회사에서 특정 팀 또는 부서에 따라 각 대상에 대한 관련 데이터 및 앱이 포함된 별도 환경을 만들 수 있습니다.
* 또한 회사 전체의 각 지점마다 별도 환경을 만들 수 있습니다.  
* [PowerApps 미리 보기 프로그램](preview-environments.md)에 참여하여 예정된 PowerApps 기능에 대한 초기 액세스를 가져옵니다.

## <a name="environment-scope"></a>환경 범위
각 환경은 Azure AD 테넌트 아래 만들어지고 사용자는 각 테넌트 내에서 해당 리소스에만 액세스할 수 있습니다. 또한 환경은 미국 같은 지리적 위치에 바인딩됩니다. 환경에서 앱을 만들면 해당 앱은 해당 지리적 위치의 데이터 센터에만 라우팅됩니다. 연결, 게이트웨이, Microsoft Flow를 사용한 흐름 등을 포함하는 환경에서 만드는 모든 항목도 환경 위치에 바인딩됩니다.

모든 환경에는 앱에 대한 저장소를 제공하는 0개 또는 1개의 Common Data Service 데이터베이스가 있습니다. 환경에 대한 데이터베이스를 만드는 기능은 PowerApps에 대해 구입한 라이선스와 환경 내의 사용자 권한에 따라 달라집니다. 자세한 내용은 [가격 정보](pricing-billing-skus.md)를 참조하세요.

환경에서 앱을 만들 때 해당 앱은 연결, 게이트웨이, 흐름, Common Data Service 데이터베이스를 포함한 동일한 환경 내에서도 배포된 데이터 원본을 연결하는 것만 허용됩니다.  예를 들어, 'Test' 및 'Dev'라는 두 가지 환경을 만들고 각 환경에서 Common Data Service 데이터베이스를 만들었다고 가정해 보겠습니다. 'Test' 환경에서 앱을 만들면 해당 앱은 'Test' 데이터베이스에만 연결할 수 있고 'Dev' 데이터베이스에는 연결할 수 없습니다.

환경 간에 리소스를 이동하는 프로세스도 있습니다. 자세한 내용은 [리소스 마이그레이션](environment-and-tenant-migration.md)을 참조하세요.

![](./media/environments-overview/Environments.png)

## <a name="environment-permissions"></a>환경 사용 권한
환경에는 환경 내의 사용 권한에 대한 액세스를 제공하는 두 가지 기본 제공 역할이 있습니다.

* Environment Admin 역할은 다음을 포함하는 환경에서 모든 관리 작업을 수행할 수 있습니다.

    * Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거

    * 환경에 대한 Common Data Service 데이터베이스 프로비전

    * 환경 내에서 만든 모든 리소스 보기 및 관리

    * 데이터 손실 방지 정책을 설정합니다. 자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.

    환경에서 데이터베이스를 만든 후에는 Environment Admin 역할 대신 System Administrator 역할을 사용할 수 있습니다.

* Environment Maker 역할은 앱, 연결, 사용자 지정 커넥터, 게이트웨이 및 Microsoft Flow를 사용한 흐름을 포함하는 환경 내에서 리소스를 만들 수 있습니다.

또한 환경에서 빌드한 앱을 개별 사용자, 보안 그룹과 앱을 공유하여 조직의 다른 사용자에게 배포하거나 조직의 모든 사용자에게 배포할 수 있습니다. 자세한 내용은 [PowerApps에서 앱 공유](../maker/canvas-apps/share-app.md)를 참조하세요.

이러한 환경 역할에 할당된 사용자 또는 그룹은 환경 데이터베이스(있는 경우)에 대해 자동으로 액세스가 제공되지 않으므로 데이터베이스 소유자가 별도로 액세스를 부여해야 합니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

[PowerApps 관리 센터][1]의 Environment Admin은 사용자 또는 보안 그룹을 두 역할 중 하나에 할당할 수 있습니다. 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>기본 환경
단일 기본 환경은 각 테넌트의 PowerApps에서 자동으로 생성되어 해당 테넌트의 모든 사용자에게 공유됩니다. 새 사용자가 PowerApps에 등록할 때마다 기본 환경의 Maker 역할에 자동으로 추가됩니다. 기본 환경은 AAD 테넌트의 기본 지역에서 가장 가까운 지역에 생성됩니다.

> [!NOTE]
> 기본 환경의 Environment Admin 역할에 자동으로 추가되는 사용자는 없습니다. 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.
>
>

기본 환경 이름은 "{Azure AD 테넌트 이름} (기본값)" 형식입니다.

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="production-and-trial-environments"></a>프로덕션 및 평가판 환경
여러 목적을 위한 환경을 만들 수 있습니다. 평가판 환경은 Common Data Service 경험을 사용하여 환경 및 데이터베이스를 시험하는 용도로 사용됩니다. 일정 기간 후에 만료됩니다. 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.

## <a name="choosing-an-environment"></a>환경 선택
환경의 도입으로 [https://web.powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 새로운 세상을 경험하게 됩니다.  앱, 연결 및 사이트에 표시되는 기타 항목이 선택한 현재 환경에 따라 필터링됩니다.  현재 환경은 헤더의 오른쪽 가장자리 근처에 있는 환경 선택기에 지정됩니다. 다른 환경을 선택하려면 선택기를 클릭하거나 탭하십시오. 사용 가능한 환경 목록이 나타납니다. 들어가려는 환경을 클릭하거나 탭합니다.

다음 조건 중 하나를 충족하는 경우 선택기에 환경이 나타납니다.

* 해당 환경에 대한 Environment Admin 역할의 구성원입니다.
* 해당 환경에 대한 Environment Maker 역할의 구성원입니다.
* 해당 환경의 Environment Admin 또는 Environment Maker가 아니지만 해당 환경 내에서 최소 1개 이상의 앱에 대해 ‘Contributor’ 액세스 권한이 있습니다. 자세한 내용은 [앱 공유](../maker/canvas-apps/share-app.md)를 참조하세요. 이러한 경우 이 환경에서 앱을 만들 수 없으며 현재 사용자에게 공유된 기존 앱을 수정할 수만 있습니다.

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>환경 만들기
### <a name="who-can-create-environments"></a>누가 환경을 만들 수 있나요?
라이선스에 따라 환경을 만들 수 있는지 여부가 결정됩니다.

| 라이선스 | 환경을 만들 수 있는 경우 |
| --- | --- |
| PowerApps P2 |√ (2개의 프로덕션 및 2개의 평가판 환경)|
| PowerApps P2 평가판 |√ (두 개의 평가판 환경)|
| PowerApps P1 |x |
| PowerApps P1 평가판 |x |
| Dynamics 365 플랜 |x |
| Office 365 플랜 |x |
| Dynamics 365 앱 및 팀 플랜 |x |


### <a name="where-can-environments-be-created"></a>환경을 어디에 만들 수 있나요?
[PowerApps.com][2] 및 [PowerApps 관리 센터][1]에서 새 환경을 만들 수 있습니다. 환경을 만들면 사용자는 해당 환경의 Environment Admin 역할에 자동으로 추가됩니다. Environment Admin 또는 Environment Maker 역할의 구성원으로 참여할 수 있는 환경 수는 제한이 없습니다. 환경에 대한 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요. 환경을 만드는 방법에 대한 지침은 [환경 만들기](create-environment.md)를 참조하세요.

![](./media/environments-overview/CreateEnvironmentDialog-New.png)


## <a name="managing-environments-for-your-organization"></a>조직을 위한 환경 관리
PowerApps 관리 센터에서 사용자가 만든 환경은 물론, Environment Admin 역할에 추가한 환경을 관리할 수 있습니다. 관리 센터에서 사용자는 다음을 포함하여 환경에 관한 모든 관리 작업을 수행할 수 있습니다.

* Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거.  자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.
* 환경에 대한 Common Data Service 데이터베이스 프로비전. 자세한 내용은 [ Common Data Service 데이터베이스 만들기](create-database.md)를 참조하세요.
* 데이터 손실 방지 정책 설정. 자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.
* 데이터베이스에 따라 개방 또는 제한된 데이터베이스 보안 정책 설정. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.
* Azure AD 테넌트 전역 관리자 역할(Office 365 전역 관리자 포함)의 구성원은 PowerApps 관리 센터에서 테넌트에 만들어진 모든 환경을 관리하고 테넌트 전체 정책을 설정할 수도 있습니다.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga
