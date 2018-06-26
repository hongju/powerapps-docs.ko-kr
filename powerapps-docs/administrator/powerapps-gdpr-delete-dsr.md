---
title: 고객 데이터를 삭제하기 위한 DSR(Data Subject Rights) 요청에 응답 | Microsoft Docs
description: PowerApps 고객 데이터를 삭제하기 위한 DSR(Data Subject Rights) 요청에 응답하는 방법에 대한 연습입니다.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 495d9976b1daa6e7adb20d97c0840b3a1ba90c4b
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34552694"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-delete-powerapps-customer-data"></a>PowerApps 고객 데이터를 삭제하기 위한 DSR(Data Subject Rights) 요청에 응답

조직의 고객 데이터에서 개인 데이터 제거를 통한 “삭제 권한”은 EU(유럽 연합) GDPR(일반 데이터 보호 규정)의 주요 보호 방법입니다. 개인 데이터 제거에는 시스템 생성 로그 제거가 포함되지만 감사 로그 정보 제거는 포함되지 않습니다.

PowerApps를 통해 사용자는 조직의 일상 업무에 중요한 부분인 기간 업무 응용 프로그램을 빌드할 수 있습니다. 사용자가 조직을 떠나면 사용자가 만든 특정 데이터 및 리소스를 삭제할지 여부를 수동으로 검토하고 결정해야 합니다. 다른 개인 데이터는 사용자 계정이 Azure Active Directory에서 삭제될 때마다 자동으로 삭제됩니다.

다음은 자동으로 삭제되는 개인 데이터와 수동 검토 및 삭제가 필요한 데이터 간의 분석 결과입니다.

수동 검토 및 삭제 필요 |   사용자가 Azure Active Directory에서 삭제될 때 자동으로 삭제됨
--- | ---
환경\** | 게이트웨이
환경 권한\*** | 게이트웨이 권한
캔버스 앱\** | PowerApps 알림
캔버스 앱 권한 | PowerApps 사용자 설정
연결\** | PowerApps 사용자 앱 설정
연결 권한 |
사용자 지정 커넥터\** |
사용자 지정 커넥터 권한 |  

\** 각 리소스에는 개인 데이터를 포함하는 “만든 사람” 및 “수정한 사람” 레코드가 있습니다. 보안상의 이유로 이러한 레코드는 리소스가 삭제될 때까지 보존됩니다.

\*** 앱용 CDS(Common Data Service) 데이터베이스를 포함하는 환경의 경우 환경 권한(환경 작성자 및 관리자 역할에 할당된 사용자)은 해당 데이터베이스에 레코드로 저장됩니다. 앱용 CDS의 사용자에 대한 DSR에 응답하는 방법에 대한 자세한 내용은 [앱용 Common Data Service 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답](common-data-service-gdpr-dsr-guide.md)을 참조하세요.

수동 검토가 필요한 데이터 및 리소스의 경우 PowerApps는 특정 사용자에 대한 개인 데이터를 다시 할당(필요한 경우)하거나 삭제하기 위한 다음과 같은 환경을 제공합니다.

* 웹 사이트 액세스: [PowerApps 사이트](https://web.powerapps.com), [PowerApps 관리 센터](https://admin.powerapps.com/) 및 [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* PowerShell 액세스: [앱 작성자](https://go.microsoft.com/fwlink/?linkid=871448) 및 [관리자](https://go.microsoft.com/fwlink/?linkid=871804)용 PowerApps cmdlet과 [온-프레미스 게이트웨이](https://go.microsoft.com/fwlink/?linkid=872238)용 cmdlet.

다음은 개인 데이터를 포함할 수 있는 각 리소스 유형을 삭제할 수 있는 환경에 대한 분석 결과입니다.

개인 데이터를 포함하는 리소스 | 웹 사이트 액세스 | PowerShell 액세스
--- | --- | ---
환경 | PowerApps 관리 센터 |  PowerApps cmdlet
환경 권한**   | PowerApps 관리 센터 | PowerApps cmdlet
캔버스 앱  | PowerApps 관리 센터 <br> PowerApps| PowerApps cmdlet
캔버스 앱 권한  | PowerApps 관리 센터 | PowerApps cmdlet
연결 | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
연결 권한 | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
사용자 지정 커넥터 | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
사용자 지정 커넥터 권한 | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음

\** 앱용 CDS가 도입됨에 따라 환경 내에서 데이터베이스를 만드는 경우 환경 권한 및 모델 기반 앱 권한은 해당 데이터베이스의 인스턴스 내에 레코드로 저장됩니다. 앱용 CDS의 사용자에 대한 DSR에 응답하는 방법에 대한 자세한 내용은 [앱용 Common Data Service 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답](common-data-service-gdpr-dsr-guide.md)을 참조하세요.

## <a name="prerequisites"></a>필수 조건

### <a name="for-users"></a>사용자의 경우
유효한 PowerApps 라이선스가 있는 사용자는 [PowerApps](https://web.powerapps.com) 또는 [앱 작성자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)을 사용하여 이 문서에 설명된 사용자 작업을 수행할 수 있습니다.

#### <a name="unmanaged-tenant"></a>관리되지 않는 테넌트
[관리되지 않는 테넌트](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover)의 멤버인 경우(즉, Azure AD 테넌트에 전역 관리자가 없는 경우) 개인 데이터를 제거하려면 이 아트에 설명된 단계를 수행할 수 있습니다.  그러나 테넌트에 대한 전역 관리자가 없으므로 아래 [11단계: Azure Active Directory에서 사용자 삭제](#step-11-delete-the-user-from-azure-active-directory)에서 설명된 지침에 따라 테넌트에서 고유한 계정을 삭제해야 합니다.

관리되지 않는 테넌트의 멤버인지 확인하기 위해 다음과 같은 단계를 수행하세요.

1. 브라우저에서 다음과 같은 URL(https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1)을 열고, URL에서 이메일 주소를 바꿉니다.

2. **관리되지 않는 테넌트**의 멤버인 경우 응답에서 `"IsViral": true`이 표시됩니다.
```
{
  ...
  "Login": "foobar@unmanagedcontoso.com",
  "DomainName": "unmanagedcontoso.com",
  "IsViral": true,
  ...
}
```

3. 그렇지 않은 경우 **관리 테넌트**에 속해 있습니다.

### <a name="for-administrators"></a>관리자의 경우
[PowerApps 관리 센터](https://admin.powerapps.com/), Microsoft Flow 관리 센터 또는 [PowerApps 관리자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)을 사용하여 이 문서에 설명된 관리 작업을 수행하려면 다음이 필요합니다.

* 유료 PowerApps 요금제 2 라이선스 또는 PowerApps 요금제 2 평가판 라이선스. [http://web.powerapps.com/trial](http://web.powerapps.com/trial)에서 30일 평가판 라이선스를 등록할 수 있습니다. 평가판 라이선스가 만료된 경우 갱신할 수 있습니다.

* 다른 사용자의 리소스를 검색해야 하는 경우 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) 권한. (환경 관리자는 권한이 있는 환경 및 환경 리소스에만 액세스할 수 있습니다.)

## <a name="step-1-delete-or-reassign-all-environments-created-by-the-user"></a>1단계: 사용자가 만든 모든 환경 삭제 또는 다시 할당
관리자는 사용자가 만든 각 환경에 대한 DSR 삭제 요청을 처리할 때 두 가지 의사 결정을 할 수 있습니다.

1. 조직 내 다른 사용자가 사용하지 않는 환경을 선택적으로 삭제할 수 있습니다.

2. 여전히 필요하다고 판단하는 환경을 삭제하지 않고 자신(또는 조직의 다른 사용자)을 환경 관리자로 추가할 수 있습니다.

> [!IMPORTANT]
> 환경을 삭제하면 환경 내의 모든 앱, 흐름, 연결 등을 비롯한 모든 리소스가 영구적으로 삭제됩니다. 따라서 삭제하기 전에 환경의 콘텐츠를 검토하세요.

### <a name="give-access-to-a-users-environments-from-the-powerapps-admin-center"></a>PowerApps 관리 센터에서 사용자 환경에 대한 액세스 권한 부여
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 특정 사용자가 만든 환경에 대한 관리 액세스 권한을 부여할 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. 사용자가 DSR 요청에서 환경을 만든 경우 **보안**을 선택하고 [환경 관리](environments-administration.md)에 설명된 단계를 계속 진행하여 자신 또는 조직의 다른 사용자에게 관리 권한을 부여합니다.

    ![환경 보안](./media/powerapps-gdpr-delete-dsr/share-environment.png)

### <a name="delete-environments-created-by-a-user-from-the-powerapps-admin-center"></a>PowerApps 관리 센터에서 사용자가 만든 환경 삭제
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 특정 사용자가 만든 환경을 검토하고 삭제할 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. 사용자가 DSR 요청에서 환경을 만든 경우 **삭제**를 선택한 다음 환경 삭제 단계를 계속 진행합니다.

    ![환경 삭제](./media/powerapps-gdpr-delete-dsr/delete-environment.png)

### <a name="give-access-to-a-users-environments-using-powershell"></a>PowerShell을 사용하여 사용자 환경에 대한 액세스 권한 부여
관리자는 [PowerApps 관리자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Set-AdminEnvironmentRoleAssignment** 함수를 사용하여 사용자가 만든 모든 환경에 대한 액세스 권한을 자신(또는 조직 내 다른 사용자)에게 할당할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
$myUserId = $global:currentSession.UserId

#Assign yourself as an admin to each environment created by the user
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Set-AdminEnvironmentRoleAssignment -RoleName EnvironmentAdmin -PrincipalType User -PrincipalObjectId $myUserId

#Retrieve the environment role assignments to confirm
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Get-AdminEnvironmentRoleAssignment
```

> [!IMPORTANT]
> 이 함수는 앱용 CDS에 데이터베이스 인스턴스가 없는 환경에서만 작동합니다.

### <a name="delete-environments-created-by-a-user-using-powershell"></a>PowerShell을 사용하여 사용자가 만든 환경 삭제
 관리자는 [PowerApps 관리자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Remove-AdminEnvironment** 함수를 사용하여 사용자가 만든 모든 환경을 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

# Retrieve all environments created by the user and then delete them
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Remove-AdminEnvironment
```

## <a name="step-2-delete-the-users-permissions-to-all-other-environments"></a>2단계: 다른 모든 환경에 대한 사용자 권한 삭제
PowerApps 서비스에 “역할 할당”으로 저장된 특정 환경의 권한을 사용자에게 할당할 수 있습니다(예: 환경 관리자, 환경 작성자 등).
앱용 CDS가 도입됨에 따라 환경 내에서 데이터베이스를 만드는 경우 이러한 “역할 할당”은 해당 데이터베이스 인스턴스 내에 레코드로 저장됩니다.
자세한 내용은 [환경 관리](environments-administration.md)를 참조하세요.

### <a name="for-environments-without-a-cds-for-apps-database"></a>앱용 CDS 데이터베이스가 없는 환경의 경우

#### <a name="powerapps-admin-center"></a>PowerApps 관리 센터
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 사용자의 환경 권한을 삭제할 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다.

    조직 내에서 만들어진 모든 환경을 검토하려면 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)여야 합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. **보안**을 선택합니다.

    해당 환경에 앱용 CDS 데이터베이스가 없으면 **환경 역할**에 대한 섹션이 표시됩니다.

3. **환경 역할**에서 **환경 관리자** 및 **환경 작성자**를 각각 둘 다 선택한 다음 검색 창을 사용하여 사용자 이름을 검색합니다.

    ![환경 역할 페이지](./media/powerapps-gdpr-delete-dsr/admin-environment-role-share-page.png)

5.  사용자가 한쪽 역할에만 액세스할 수 있는 경우에는 **사용자** 화면에서 해당 권한을 제거하고 **저장**을 선택합니다.

#### <a name="powershell"></a>PowerShell
관리자는 [PowerApps 관리자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Remove-AdminEnvironmentRoleAssignment** 함수를 사용하여 앱용 CDS 데이터베이스가 없는 모든 환경에서 사용자에 대한 모든 환경 역할 할당을 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all environment role assignments for the user for environments without a CDS for Apps instance and delete them
Get-AdminEnvironmentRoleAssignment -UserId $deleteDsrUserId | Remove-AdminEnvironmentRoleAssignment
```

> [!IMPORTANT]
> 이 함수는 앱용 CDS 데이터베이스 인스턴스가 없는 환경에서만 작동합니다.

### <a name="for-environments-with-a-cds-for-apps-database"></a>앱용 CDS 데이터베이스가 있는 환경의 경우
앱용 CDS가 도입됨에 따라 환경 내에서 데이터베이스를 만드는 경우 이러한 “역할 할당”은 해당 데이터베이스 인스턴스 내에 레코드로 저장됩니다. 앱용 CDS의 데이터베이스 인스턴스에서 개인 데이터를 제거하는 방법에 대한 자세한 내용은 Common Data Service 사용자 개인 데이터 제거 문서를 참조하세요.

## <a name="step-3-delete-or-reassign-all-canvas-apps-owned-by-a-user"></a>3단계: 사용자가 소유한 모든 캔버스 앱 삭제 또는 다시 할당

### <a name="reassign-a-users-canvas-apps-using-the-powerapps-admin-powershell-cmdlets"></a>PowerApps 관리자 PowerShell cmdlet을 사용하여 사용자의 캔버스 앱 다시 할당
관리자가 사용자의 캔버스 앱을 삭제하지 않도록 결정하면 [PowerApps 관리자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Set-AdminAppOwner** 함수를 사용하여 사용자가 소유한 앱을 다시 할당할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
$newAppOwnerUserId = "72c272b8-14c3-4f7a-95f7-a76f65c9ccd8"

#find all apps owned by the DSR user and assigns them a new owner
Get-AdminApp -Owner $deleteDsrUserId | Set-AdminAppOwner -AppOwner $newAppOwnerUserId
```

### <a name="delete-a-users-canvas-app-using-the-powerapps-site"></a>PowerApps 사이트를 사용하여 사용자의 캔버스 앱 삭제
사용자는 [PowerApps 사이트](https://web.powerapps.com)에서 앱을 삭제할 수 있습니다. 앱 삭제 방법에 대한 전체 단계는 앱 삭제를 참조하세요.

### <a name="delete-a-users-canvas-app-using-the-powerapps-admin-center"></a>PowerApps 관리 센터를 사용하여 사용자의 캔버스 앱 삭제
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 사용자가 만든 앱을 삭제할 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다.

    조직 내에서 만들어진 모든 환경을 검토하려면 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)여야 합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. **리소스** > **앱**을 선택합니다.

3. 검색 창을 사용하여 이 환경 내에서 해당 사용자가 만든 모든 앱을 가져오는 사용자 이름을 검색합니다.

    ![앱 검색](./media/powerapps-gdpr-delete-dsr/search-apps.png)

4. 사용자가 소유한 각 앱에 대한 **세부 정보**를 선택합니다.

    ![앱 세부 정보 선택](./media/powerapps-gdpr-delete-dsr/select-app-details.png)

5. **삭제**를 선택하여 각 앱을 삭제합니다.

### <a name="delete-a-users-canvas-app-using-the-powerapps-admin-powershell-cmdlets"></a>PowerApps 관리자 PowerShell cmdlet을 사용하여 사용자의 캔버스 앱 삭제
관리자가 사용자가 소유한 모든 캔버스 앱을 삭제하도록 결정하면 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Remove-AdminApp** 함수를 사용하여 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all apps owned by the DSR user and deletes them
Get-AdminApp -Owner "0ecb1fcc-6782-4e46-a4c4-738c1d3accea" | Remove-AdminApp
```

## <a name="step-4-delete-the-users-permissions-to-canvas-apps"></a>4단계: 캔버스 앱에 대한 사용자 권한 삭제
앱이 사용자와 공유될 때마다 PowerApps는 응용 프로그램에 대한 사용자의 권한(CanEdit 또는 CanUse)을 설명하는 “역할 할당”이라는 레코드를 저장합니다. 자세한 내용은 앱 공유 문서를 참조하세요.

> [!NOTE]
> 앱이 삭제될 때 앱의 역할 할당이 삭제됩니다.

> [!NOTE]
> 앱 소유자의 역할 할당을 삭제하려면 앱에 대한 새 소유자를 할당해야 합니다.

### <a name="powerapps-admin-center"></a>PowerApps 관리 센터
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 사용자에 대한 앱 역할 할당을 삭제할 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다.

    조직 내에서 만들어진 모든 환경을 검토하려면 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)여야 합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. 각 환경에서 **리소스** > **앱**를 선택합니다.

3. 환경에 있는 각 앱에 대해 **공유**를 선택합니다.

    ![앱 공유 선택](./media/powerapps-gdpr-delete-dsr/select-admin-share-nofilter.png)

4. 사용자가 앱에 액세스할 수 있는 경우에는 앱의 **공유** 화면에서 해당 권한을 제거하고 **저장**을 선택합니다.

    ![앱 공유 관리 페이지](./media/powerapps-gdpr-delete-dsr/admin-share-page.png)

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Remove-AdminAppRoleAssignmnet** 함수를 사용하여 사용자의 캔버스 앱 역할 할당을 모두 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all app role assignments for the DSR user and deletes them
Get-AdminAppRoleAssignment -UserId $deleteDsrUserId | Remove-AdminAppRoleAssignment
```

## <a name="step-5-delete-connections-created-by-a-user"></a>5단계: 사용자가 만든 연결 삭제
연결은 다른 API 및 SaaS 시스템에 대한 연결을 설정할 때 커넥터와 함께 사용됩니다.  연결을 만든 사용자에 대한 참조가 연결에 포함되므로, 이러한 참조를 모두 제거하기 위해 연결이 삭제될 수 있습니다.

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [앱 작성자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-Connection 함수를 사용하여 모든 연결을 삭제할 수 있습니다.

```
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

### <a name="powershell-cmdlets-for-powerapps-administrators"></a>PowerApps 관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Remove-AdminConnection** 함수를 사용하여 사용자의 모든 연결을 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all connections for the DSR user and deletes them
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection
```

## <a name="step-6-delete-the-users-permissions-to-shared-connections"></a>6단계: 공유 연결에 대한 사용자 권한 삭제

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [앱 작성자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-ConnectionRoleAssignment 함수를 사용하여 공유 연결에 대한 모든 연결 역할 할당을 삭제할 수 있습니다.

```
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```
> [!NOTE]
> 소유자 역할 할당을 삭제하려면 연결 리소스를 삭제해야 합니다.

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Remove-AdminConnectionRoleAssignment** 함수를 사용하여 사용자의 모든 연결 역할 할당을 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all connection role assignments for the DSR user and deletes them
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment
```

## <a name="step-7-delete-custom-connectors-created-by-the-user"></a>7단계: 사용자가 만든 사용자 지정 커넥터 삭제
사용자 지정 커넥터는 기존의 기본 제공 커넥터를 보완하고 다른 API, SaaS 및 사용자 지정 개발 시스템에 대한 연결을 허용합니다. 조직의 다른 사용자에게 사용자 지정 커넥터 소유권을 전송하거나 사용자 지정 커넥터를 삭제할 수 있습니다.

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [앱 작성자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-Connector 함수를 사용하여 모든 사용자 지정 커넥터를 삭제할 수 있습니다.

```
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Remove-AdminConnector** 함수를 사용하여 사용자가 만든 모든 사용자 지정 커넥터를 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all custom connectors created by the DSR user and deletes them
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector
```

## <a name="step-8-delete-the-users-permissions-to-shared-custom-connectors"></a>8단계: 공유된 사용자 지정 커넥터에 대한 사용자 권한 삭제

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [앱 작성자용 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-ConnectorRoleAssignment 함수를 사용하여 공유된 사용자 지정 연결에 대한 모든 커넥터 역할 할당을 삭제할 수 있습니다.

```
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

> [!NOTE]
> 소유자 역할 할당을 삭제하려면 연결 리소스를 삭제해야 합니다.

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Remove-AdminConnectorRoleAssignment** 함수를 사용하여 사용자에 대한 모든 사용자 지정 커넥터 역할 할당을 삭제할 수 있습니다.

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all custom connector role assignments for the DSR user and deletes them
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment
```

## <a name="step-9-delete-the-users-personal-data-in-microsoft-flow"></a>9단계: Microsoft Flow에서 사용자의 개인 데이터 삭제
PowerApps 라이선스에는 항상 Microsoft Flow 기능이 포함되어 있습니다. Microsoft Flow는 PowerApps 라이선스에 포함될 뿐만 아니라 독립 실행형 서비스로도 제공됩니다. Microsoft Flow 서비스를 사용하는 사용자에 대한 DSR에 응답하는 방법에 대한 자세한 내용은 [Microsoft Flow에 대한 GDPR 데이터 주체 요청에 응답](https://go.microsoft.com/fwlink/?linkid=872250)을 참조하세요.

> [!IMPORTANT]
> 관리자는 PowerApps 사용자에 대해 이 단계를 완료하는 것이 좋습니다.

## <a name="step-10-delete-the-users-personal-data-in-instances-of-cds-for-apps"></a>10단계: 앱용 CDS 인스턴스에서 사용자의 개인 데이터 삭제
PowerApps 커뮤니티 요금제를 포함한 특정 PowerApps 라이선스는 조직 내 사용자가 앱용 CDS 인스턴스를 만들고 앱용 CDS에서 앱을 만들고 빌드하는 기능을 제공합니다. PowerApps 커뮤니티 요금제는 사용자가 개별 환경에서 앱용 CDS를 사용해 볼 수 있는 무료 라이선스입니다. 각 PowerApps 라이선스에 포함된 기능에 대해서는 PowerApps 가격 페이지를 참조하세요.

앱용 CDS를 사용하는 사용자에 대한 DSR에 응답하는 방법에 대한 자세한 내용은 [앱용 Common Data Service 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답](common-data-service-gdpr-dsr-guide.md)을 참조하세요.

> [!IMPORTANT]
> 관리자는 PowerApps 사용자에 대해 이 단계를 완료하는 것이 좋습니다.

## <a name="step-11-delete-the-user-from-azure-active-directory"></a>11단계: Azure Active Directory에서 사용자 삭제
위의 단계를 완료하면 최종 단계는 Azure Active Directory에 대한 사용자의 계정을 삭제하는 것입니다.

### <a name="managed-tenant"></a>관리 테넌트
관리 Azure AD 테넌트의 관리자로써 [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)에서 찾을 수 있는 Azure 데이터 주체 요청 GDPR 문서에 설명된 단계에 따라 사용자의 계정을 삭제할 수 있습니다.

### <a name="unmanaged-tenant"></a>관리되지 않는 테넌트
관리되지 않는 테넌트의 멤버인 경우 Azure AD 테넌트에서 계정을 삭제하기 위해 이러한 단계를 수행해야 합니다.

> [!NOTE]
> 관리 또는 관리되지 않는 테넌트의 멤버인지를 감지하는 방법을 보려면 위의 [관리되지 않는 테넌트 섹션](#unmanaged-tenant)을 참조하세요.

1. [직장 및 학교 개인 정보 페이지](https://go.microsoft.com/fwlink/?linkid=87312)로 이동하고 Azure AD 계정으로 로그인합니다.

2. **계정 종료**를 선택하고 Azure AD 테넌트에서 계정을 삭제하는 지침을 따릅니다.

    ![앱 공유 선택](./media/powerapps-gdpr-delete-dsr/close-account.png)
