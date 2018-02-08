---
title: "환경 개요 | Microsoft Docs"
description: "환경 정의 및 사용 방법"
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
ms.date: 11/01/2016
ms.author: jamesol
ms.openlocfilehash: f8af05b00888891663da975be379211fad79c8a3
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="environments-overview"></a>환경 개요
환경은 PowerApps에서 사용되는 새로운 개념입니다. 간단히 말해 환경은 조직의 비즈니스 데이터, 앱 및 흐름을 저장, 관리 및 공유하기 위한 공간입니다. 또한 각기 다른 역할, 보안 요구 사항 또는 대상 그룹에 따라 앱을 구분하는 컨테이너 기능도 제공합니다. 환경 활용을 선택하는 방식은 해당 조직 및 빌드하려는 앱에 따라 달라집니다. 예:

* 단일 환경에서 앱만 빌드하도록 선택할 수 있습니다.
* 앱의 테스트 및 프로덕션 버전을 그룹화하는 별도 환경을 만들 수 있습니다.
* 회사에서 특정 팀 또는 부서에 따라 각 대상에 대한 관련 데이터 및 앱이 포함된 별도 환경을 만들 수 있습니다.
* 또한 회사 전체의 각 지점마다 별도 환경을 만들 수 있습니다.  

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

* Environment Maker 역할은 앱, 연결, 사용자 지정 커넥터, 게이트웨이 및 Microsoft Flow를 사용한 흐름을 포함하는 환경 내에서 리소스를 만들 수 있습니다.

또한 환경에서 빌드한 앱을 개별 사용자, 보안 그룹과 앱을 공유하여 조직의 다른 사용자에게 배포하거나 조직의 모든 사용자에게 배포할 수 있습니다. 자세한 내용은 [PowerApps에서 앱 공유](share-app.md)를 참조하세요.

이러한 환경 역할에 할당된 사용자 또는 그룹은 환경 데이터베이스(있는 경우)에 대해 자동으로 액세스가 제공되지 않으므로 데이터베이스 소유자가 별도로 액세스를 부여해야 합니다. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.

[PowerApps 관리 센터][1]의 Environment Admin은 사용자 또는 보안 그룹을 두 역할 중 하나에 할당할 수 있습니다. 자세한 내용은 [환경 관리](environments-administration.md)를 참조하세요.

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>기본 환경
단일 기본 환경은 각 테넌트의 PowerApps에서 자동으로 생성되어 해당 테넌트의 모든 사용자에게 공유됩니다. 새 사용자가 PowerApps에 등록할 때마다 기본 환경의 Maker 역할에 자동으로 추가됩니다. 기본 환경은 AAD 테넌트의 기본 지역에서 가장 가까운 지역에 생성됩니다.

> [!NOTE]
> 기본 환경의 Environment Admin 역할에 자동으로 추가되는 사용자는 없습니다. 자세한 내용은 [환경 관리](environments-administration.md)를 참조하세요.
> 
> 

기본 환경 이름은 "{Azure AD 테넌트 이름} (기본값)" 형식입니다.

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="choosing-an-environment"></a>환경 선택
환경의 도입으로 [https://web.powerapps.com](https://web.powerapps.com)에서 새로운 세상을 경험하게 됩니다.  앱, 연결 및 사이트에 표시되는 기타 항목이 선택한 현재 환경에 따라 필터링됩니다.  현재 환경은 헤더의 오른쪽 가장자리 근처에 있는 환경 선택기에 지정됩니다. 다른 환경을 선택하려면 선택기를 클릭하거나 탭하십시오. 사용 가능한 환경 목록이 나타납니다. 들어가려는 환경을 클릭하거나 탭합니다.

다음 조건 중 하나를 충족하는 경우 선택기에 환경이 나타납니다.

* 해당 환경에 대한 Environment Admin 역할의 구성원입니다.
* 해당 환경에 대한 Environment Maker 역할의 구성원입니다.
* 해당 환경의 Environment Admin 또는 Environment Maker가 아니지만 해당 환경 내에서 최소 1개 이상의 앱에 대해 ‘Contributor’ 액세스 권한이 있습니다. 자세한 내용은 [앱 공유](share-app.md)를 참조하세요. 이러한 경우 이 환경에서 앱을 만들 수 없으며 현재 사용자에게 공유된 기존 앱을 수정할 수만 있습니다.

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>환경 만들기
### <a name="who-can-create-environments"></a>누가 환경을 만들 수 있나요?
라이선스에 따라 환경을 만들 수 있는지 여부가 결정됩니다.

| 라이선스 | 환경을 만들 수 있는 경우 |
| --- | --- |
| PowerApps P2 |√ |
| PowerApps P2 평가판 |√ |
| PowerApps P1 |x |
| PowerApps P1 평가판 |x |
| Dynamics 365 플랜 |x |
| Office 365 플랜 |x |
| Dynamics 365 앱 및 팀 플랜 |x |

각 사용자는 최대 2개의 환경을 만들 수 있습니다.

### <a name="where-can-environments-be-created"></a>환경을 어디에 만들 수 있나요?
[PowerApps.com][2] 및 [PowerApps 관리 센터][1]에서 새 환경을 만들 수 있습니다. 환경을 만들면 해당 환경의 Environment Admin 역할에 자동으로 추가됩니다. Environment Admin 또는 Environment Maker 역할의 구성원으로 참여할 수 있는 환경 수는 제한이 없습니다. 자세한 내용은 [환경 관리](environments-administration.md)를 참조하세요.

![](./media/environments-overview/CreateEnvironmentDialog.png)

## <a name="what-will-change-for-powerapps-preview-users"></a>PowerApps 미리 보기 릴리스 사용자에 대한 변경 사항은 무엇인가요?
환경이 도입됨에 따라 PowerApps 미리 보기 릴리스에 참가하는 모든 사용자는 일부 변경된 서비스를 제공받습니다.  다음 표는 미국 사용자와 미국 이외 사용자에게 제공되는 서비스 목록입니다.

| User | 제공되는 서비스 |
| --- | --- |
| Common Data Service 데이터베이스를 만든 미리 보기 릴리스 사용자 |Common Data Service 데이터베이스 미리 보기와 이에 대해 빌드한 모든 앱이 포함된 "{사용자 이름}의 환경"이란 이름의 환경이 표시됩니다.  이 환경의 Environment Maker 또는 Environment Admin 역할 뿐 아니라 해당 데이터베이스의 데이터베이스 소유자로도 추가됩니다. PowerApps가 일반 공급되면 Common Data Service 메타데이터로 업그레이드됩니다. 이 변경의 영향은 Common Data Service 데이터베이스 미리 보기에 대해 이미 빌드한 엔터티 및 앱을 계속 사용할 수 있지만 해당 데이터베이스에서 필드 또는 엔터티를 만들 수는 없다는 것을 의미합니다. 업그레이드된 메타데이터를 포함한 데이터베이스를 사용하여 환경을 만들고 해당 환경에 앱을 마이그레이션하는 방법에 대한 지침이 곧 게시됩니다. <br> Common Data Service 데이터베이스 미리 보기에 대해 빌드된 앱 중 하나라도 사용자 지정 커넥터를 데이터 원본으로 사용하는 경우 모든 사용자 지정 커넥터가 기본 환경으로 마이그레이션되므로 이 환경에서 일시적으로 중단됩니다. 영향을 받는 모든 앱을 복구하려면 이 환경에서 사용자 지정 커넥터를 다시 생성해야 합니다. |
| 미국의 미리 보기 릴리스 사용자 |PowerApps 미리 보기 릴리스 기간 중에 만든 다음 리소스는 사용자 테넌트의 기본 환경에서 사용할 수 있습니다.<br>- 만든 모든 앱(Common Data Service 데이터베이스 미리 보기에 연결된 앱 제외)<br>- 만든 모든 연결 및 사용자 지정 커넥터<br>- 설치한 모든 온-프레미스 데이터 게이트웨이 |
| 미국 이외 지역의 미리 보기 릴리스 사용자 |기본 환경 외에 PowerApps 미리 보기 릴리스 기간 중에 만든 다음 리소스를 포함한 환경이 "(미리 보기의) {Azure AD 테넌트}" 형식의 이름을 표시됩니다.<br>- 만든 모든 앱(Common Data Service 데이터베이스 미리 보기에 연결된 앱 제외)<br>- 만든 모든 연결 및 사용자 지정 커넥터<br>- 설치한 모든 온-프레미스 데이터 게이트웨이<br>이 환경의 Environment Maker 역할에 추가됩니다. |

*미리 보기 릴리스 사용자*는 GA(일반 공급) 전에 Microsoft PowerApps를 사용한 사용자입니다.

PowerApps가 GA(일반 공급)에 들어간 이후 2주 뒤에 미리 보기 콘텐츠를 포함하는 환경은 읽기 전용으로 표시됩니다(기본 환경 제외). 모든 기존 앱과 흐름은 이 환경에서 계속 작동하지만 새로운 앱과 흐름을 만들 수는 없습니다. 이러한 환경의 사용자는 콘텐츠를 기본 환경 또는 다른 사용자 지정 환경으로 마이그레이션하는 것이 좋습니다. 마이그레이션 프로세스에 대한 자세한 내용은 이번주에 게시될 다음 블로그에서 [Common Data Service 기능 공지 블로그][3]를 참조하세요.

### <a name="example-environments-for-a-preview-user-in-us"></a>미국의 미리 보기 릴리스 사용자를 위한 예제 환경
![](./media/environments-overview/USuser1.png)

### <a name="example-environments-for-a-preview-user-not-in-us"></a>미국 이외 지역의 미리 보기 릴리스 사용자를 위한 예제 환경
![](./media/environments-overview/non-USuser1.png)

## <a name="managing-environments-for-your-organization"></a>조직을 위한 환경 관리
환경 도입과 함께 직접 만들거나 Environment Admin 역할에 추가된 모든 환경을 관리할 수 있는 PowerApps 관리 센터를 선보입니다. 관리 센터에서 사용자는 다음을 포함하여 환경에 관한 모든 관리 작업을 수행할 수 있습니다.

* Environment Admin 또는 Environment Maker 역할에서 사용자나 그룹을 추가 또는 제거.  자세한 내용은 [환경 관리](environments-administration.md)를 참조하세요.
* 환경에 대한 Common Data Service 데이터베이스 프로비전. 자세한 내용은 [ Common Data Service 데이터베이스 만들기](create-database.md)를 참조하세요.
* 데이터 손실 방지 정책 설정. 자세한 내용은 [데이터 손실 방지 정책](prevent-data-loss.md)을 참조하세요.
* 데이터베이스에 따라 개방 또는 제한된 데이터베이스 보안 정책 설정. 자세한 내용은 [데이터베이스 보안 구성](database-security.md)을 참조하세요.
* Azure AD 테넌트 전역 관리자 역할(Office 365 전역 관리자 포함)의 구성원은 PowerApps 관리 센터에서 테넌트에 만들어진 모든 환경을 관리하고 테넌트 전체 정책을 설정할 수도 있습니다.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga
