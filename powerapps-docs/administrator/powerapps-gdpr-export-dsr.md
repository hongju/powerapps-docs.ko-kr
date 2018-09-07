---
title: PowerApps 고객 데이터를 내보내기 위한 DSR(Data Subject Rights) 요청에 응답 | Microsoft Docs
description: PowerApps 고객 데이터를 내보내기 위한 DSR(Data Subject Rights) 요청에 응답하는 방법에 대한 연습입니다.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 59cf670ee4b0aa9f9845a86a1d89bcb64329f2d4
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42856775"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-export-powerapps-customer-data"></a>PowerApps 고객 데이터를 내보내기 위한 DSR(Data Subject Rights) 요청에 응답
“데이터 이식성 권한”을 사용하면 데이터 주체가 다른 데이터 컨트롤러에게 전송될 수 있는 자신의 개인 데이터 복사본을 전자 형식(구조화되고, 일반적으로 사용되고, 컴퓨터에서 읽을 수 있고, 상호 운용 가능한 형식)으로 요청할 수 있습니다.

* 웹 사이트 액세스: [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), [PowerApps 관리 센터](https://admin.powerapps.com/) 및 [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* PowerShell 액세스: PowerApps [앱 작성자 cmdlet](https://go.microsoft.com/fwlink/?linkid=871448), [관리자 cmdlet](https://go.microsoft.com/fwlink/?linkid=871804) 및 [온-프레미스 게이트웨이 cmdlet](https://go.microsoft.com/fwlink/?linkid=872238)

다음은 PowerApps가 특정 사용자에 대해 저장할 수 있는 개인 데이터 유형과 이를 찾고 내보내는 데 사용할 수 있는 환경에 대한 요약입니다.

개인 데이터를 포함하는 리소스 | 웹 사이트 액세스 |   PowerShell 액세스
--- | --- | --
환경 | PowerApps 관리 센터 |  PowerApps cmdlet
환경 권한**   | PowerApps 관리 센터    | PowerApps cmdlet
캔버스 앱  | PowerApps 관리 센터 <br> PowerApps 포털 |    PowerApps cmdlet
캔버스 앱 권한  | PowerApps 관리 센터 <br> PowerApps 포털  | PowerApps cmdlet
게이트웨이 | PowerApps 포털***   | 온-프레미스 게이트웨이 cmdlet
게이트웨이 권한 | PowerApps 포털***   |
사용자 지정 커넥터 | |    앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
사용자 지정 커넥터 권한 | |    앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
연결 | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
연결 권한  | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음
PowerApps 사용자 설정, 사용자 앱 설정 및 알림 | | 앱 작성자: 사용 가능 <br> 관리자: 사용할 수 없음

> ** 앱용 CDS(Common Data Service)가 도입됨에 따라 환경 내에서 데이터베이스를 만드는 경우 환경 권한 및 모델 기반 앱 권한은 앱용 CDS 데이터베이스 인스턴스 내에 레코드로 저장됩니다. 앱용 CDS를 사용하는 사용자에 대한 DSR 요청에 응답하는 방법에 대한 자세한 내용은 [앱용 Common Data Service 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답](common-data-service-gdpr-dsr-guide.md)을 참조하세요.

> *** 관리자는 리소스 소유자가 액세스 권한을 명시적으로 부여받은 경우에만 [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 이 리소스에 액세스할 수 있습니다. 액세스 권한이 부여되지 않은 관리자는 [PowerApps 관리자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)을 이용해야 합니다.

## <a name="prerequisites"></a>필수 조건

### <a name="for-users"></a>사용자의 경우
유효한 PowerApps 라이선스가 있는 사용자는 [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 또는 [앱 작성자 cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)을 사용하여 이 문서에 설명된 사용자 작업을 수행할 수 있습니다.

### <a name="for-admins"></a>관리자의 경우
PowerApps 관리 센터, Microsoft Flow 관리 센터 또는 [PowerApps 관리자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)을 사용하여 이 문서에 설명된 관리 작업을 수행하려면 다음이 필요합니다.

* 유료 PowerApps 요금제 2 라이선스 또는 PowerApps 요금제 2 평가판 라이선스. [http://web.powerapps.com/trial](http://web.powerapps.com/trial)에서 30일 평가판 라이선스를 등록할 수 있습니다. 평가판 라이선스가 만료된 경우 갱신할 수 있습니다.

* 다른 사용자의 리소스를 검색해야 하는 경우 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) 권한. (환경 관리자는 권한이 있는 환경 및 환경 리소스에만 액세스할 수 있습니다.)

## <a name="step-1-export-personal-data-contained-within-environments-created-by-the-user"></a>1단계: 사용자가 만든 환경 내에 포함된 개인 데이터 내보내기

### <a name="powerapps-admin-center"></a>PowerApps 관리 센터
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 특정 사용자가 만든 모든 환경을 내보낼 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. DSR 요청을 통해 사용자가 환경을 만든 경우 **세부 정보** 페이지로 이동하여 세부 정보를 복사한 다음, Microsoft Word와 같은 문서 편집기에 붙여넣습니다.

    ![환경 세부 정보](./media/powerapps-gdpr-export-dsr/environment-details.png)

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-PowerAppsEnvironment** 함수를 사용하여 PowerApps에서 액세스할 수 있는 환경을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
Get-PowerAppsEnvironment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Get-AdminEnvironment** 함수를 사용하여 사용자가 만든 모든 환경을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "7557f390-5f70-4c93-8bc4-8c2faabd2ca0"
Get-AdminEnvironment -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-2-export-the-users-environment-permissions"></a>2단계: 사용자의 환경 권한 내보내기
PowerApps에 ‘역할 할당’으로 저장된 특정 환경의 권한을 사용자에게 할당할 수 있습니다(예: 환경 관리자, 환경 작성자 등). 앱용 CDS가 도입됨에 따라 환경 내에서 데이터베이스를 만드는 경우 역할 할당은 앱용 CDS 데이터베이스 인스턴스 내에 레코드로 저장됩니다. 자세한 내용은 [PowerApps 내에서 환경 관리](environments-administration.md)를 참조하세요.

### <a name="for-environments-without-a-cds-for-apps-database"></a>앱용 CDS 데이터베이스가 없는 환경의 경우

#### <a name="powerapps-admin-center"></a>PowerApps 관리 센터
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 사용자의 환경 권한을 내보낼 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다. 조직 내에서 만들어진 모든 환경을 검토하려면 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)여야 합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. **보안**을 선택합니다.

    해당 환경에 앱용 CDS 데이터베이스가 없으면 **환경 역할**에 대한 섹션이 표시됩니다.

3. **환경 관리자** 및 **환경 작성자**를 각각 둘 다 선택한 다음, 검색 창을 사용하여 사용자 이름을 검색합니다.

    ![환경 역할 페이지](./media/powerapps-gdpr-export-dsr/admin-environment-role-share-page.png)

4. 사용자가 각 역할에 액세스할 수 있는 경우 **사용자** 페이지로 이동하여 세부 정보를 복사한 다음, Microsoft Word와 같은 문서 편집기에 붙여넣습니다.

#### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Get-AdminEnvironmentRoleAssignment** 함수를 사용하여 앱용 CDS 데이터베이스가 없는 모든 환경에서 사용자에 대한 모든 환경 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminEnvironmentRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

> [!IMPORTANT]
>  이 함수는 앱용 CDS 데이터베이스 인스턴스가 없는 환경에서만 작동합니다.
>
>

### <a name="for-environments-with-a-cds-for-apps-database"></a>앱용 CDS 데이터베이스가 있는 환경의 경우
앱용 CDS가 도입됨에 따라 환경 내에서 데이터베이스를 만드는 경우 역할 할당은 앱용 CDS 데이터베이스 인스턴스 내에 레코드로 저장됩니다. 앱용 CDS 데이터베이스 인스턴스에서 개인 데이터를 제거하는 방법에 대한 자세한 내용은 [Common Data Service User personal data removal](https://go.microsoft.com/fwlink/?linkid=871886)(Common Data Service 사용자 개인 데이터 제거)을 참조하세요.
 
## <a name="step-3-export-personal-data-contained-within-canvas-apps-created-by-the-user"></a>3단계: 사용자가 만든 캔버스 앱에 포함된 개인 데이터 내보내기

### <a name="powerapps-portal"></a>PowerApps 포털
사용자는 [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 앱을 내보낼 수 있습니다. 앱을 내보내는 방법에 대한 단계별 지침은 [앱 내보내기](environment-and-tenant-migration.md#exporting-an-app)를 참조하세요.

### <a name="powerapps-admin-center"></a>PowerApps 관리 센터
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 사용자가 만든 앱을 내보낼 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다. 조직 내에서 만들어진 모든 환경을 검토하려면 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)여야 합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. **리소스**를 선택한 다음, **앱**을 선택합니다.

3. 검색 창을 사용하여 이 환경 내에서 사용자가 만든 모든 앱을 가져오는 사용자 이름을 검색합니다.

    ![앱 검색](./media/powerapps-gdpr-export-dsr/search-apps.png)

4. 해당 사용자가 만든 각 앱에 대해 **공유**를 선택하고 자신에게 앱에 대한 **편집 가능** 액세스 권한을 부여합니다.

    ![앱 공유 선택](./media/powerapps-gdpr-export-dsr/select-share.png)

    ![사용자에게 액세스 권한 부여](./media/powerapps-gdpr-export-dsr/grant-access.png)

5. 각 사용자의 앱에 액세스할 수 있으면 [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 앱을 내보낼 수 있습니다. 앱을 내보내는 방법에 대한 단계별 지침은 [앱 내보내기](environment-and-tenant-migration.md#exporting-an-app)를 참조하세요.

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Get-AdminApp** 함수를 사용하여 사용자가 만든 앱을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminApp -Owner $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-4-export-the-users-permissions-to-canvas-apps"></a>4단계: 사용자의 권한을 캔버스 앱으로 내보내기
앱이 사용자와 공유될 때마다 PowerApps는 응용 프로그램에 대한 사용자의 권한(CanEdit 또는 CanUse)을 설명하는 ‘역할 할당’이라는 레코드를 저장합니다. 자세한 내용은 [앱 공유](../maker/canvas-apps/share-app.md#share-an-app)를 참조하세요.

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-RoleAssignment** 함수를 사용하여 액세스할 수 있는 모든 앱에 대한 앱 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
Get-AppRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-center"></a>PowerApps 관리 센터
관리자는 다음 단계에 따라 [PowerApps 관리 센터](https://admin.powerapps.com/)에서 사용자에 대한 앱 역할 할당을 내보낼 수 있습니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com/)에서 조직의 각 환경을 선택합니다. 조직 내에서 만들어진 모든 환경을 검토하려면 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)여야 합니다.

    ![관리 센터 방문 페이지](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. 각 환경에 대해 **리소스**를 선택한 다음, **앱**을 선택합니다.

3. 환경에 있는 각 앱에 대해 **공유**를 선택합니다.

    ![앱 공유 선택](./media/powerapps-gdpr-export-dsr/select-admin-share-nofilter.png)

4. 사용자가 앱에 액세스할 수 있는 경우 앱의 **공유** 페이지로 이동하여 세부 정보를 복사한 다음, Microsoft Word와 같은 문서 편집기에 붙여넣습니다.

    ![앱 공유 관리 페이지](./media/powerapps-gdpr-export-dsr/admin-share-page.png)

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 **Get-AdminAppRoleAssignment** 함수를 사용하여 해당 테넌트의 모든 앱에서 사용자에 대한 모든 앱 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminAppRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-5-export-personal-data-contained-within-connections-created-by-the-user"></a>5단계: 사용자가 만든 연결 내에 포함된 개인 데이터 내보내기
연결은 다른 API 및 SaaS 시스템에 대한 연결을 설정할 때 커넥터와 함께 사용됩니다. 연결을 만든 사용자에 대한 참조가 연결에 포함되므로, 이러한 참조를 모두 제거하기 위해 연결이 삭제될 수 있습니다.

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-Connection** 함수를 사용하여 액세스할 수 있는 모든 연결을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
Get-Connection | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Get-AdminApp** 함수를 사용하여 사용자가 만든 모든 연결을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnection -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-6-export-the-users-permissions-to-shared-connections"></a>6단계: 공유 연결에 대한 사용자의 권한 내보내기

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-ConnectionRoleAssignment** 함수를 사용하여 액세스할 수 있는 모든 연결에 대한 연결 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Get-AdminConnectionRoleAssignment** 함수를 사용하여 사용자에 대한 모든 연결 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-7-export-personal-data-contained-within-custom-connectors-created-by-the-user"></a>7단계: 사용자가 만든 사용자 지정 커넥터 내에 포함된 개인 데이터 내보내기
사용자 지정 커넥터는 기존의 기본 제공 커넥터를 보완하고 다른 API, SaaS 및 사용자 지정 개발 시스템에 대한 연결을 허용합니다.

### <a name="powerapps-app-creator-powershell-cmdlets"></a>PowerApps 앱 작성자 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-Connector** 함수를 사용하여 직접 만든 모든 사용자 지정 커넥터를 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount  
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Get-AdminConnector** 함수를 사용하여 사용자가 만든 모든 사용자 지정 커넥터를 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-8-export-the-users-permissions-to-custom-connectors"></a>8단계: 사용자의 권한을 사용자 지정 커넥터로 내보내기

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-ConnectorRoleAssignment** 함수를 사용하여 액세스할 수 있는 사용자 지정 커넥터에 대한 모든 커넥터 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount  
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Get-AdminConnectorRoleAssignment** 함수를 사용하여 사용자에 대한 모든 사용자 지정 커넥터 역할 할당을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-9-export-powerapps-notifications-user-settings-and-user-app-settings"></a>9단계: PowerApps 알림, 사용자 설정 및 사용자 앱 설정 내보내기
PowerApps는 앱이 사용자와 공유될 경우 및 앱용 CDS 내보내기 작업이 완료될 경우를 포함하여 사용자에게 다양한 유형의 알림을 보냅니다. 사용자의 알림 기록은 [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 내에 표시됩니다.

또한 PowerApps는 사용자가 응용 프로그램을 마지막으로 열거나, 앱을 고정할 경우 등을 포함하여 PowerApps 런타임 및 포털 환경을 전달하는 데 사용되는 다양한 사용자 기본 설정 및 설정도 저장합니다.

### <a name="powershell-cmdlets-for-app-creators"></a>앱 작성자용 PowerShell cmdlet
사용자는 [PowerApps 앱 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)에서 **Get-AdminPowerAppsUserDetails** 함수를 사용하여 고유한 PowerApps 알림, 사용자 설정 및 사용자 앱 설정을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount  
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>관리자용 PowerShell cmdlet
관리자는 [PowerApps 관리자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)에서 **Get-AdminPowerAppsUserDetails** 함수를 사용하여 PowerApps 알림, 사용자 설정 및 사용자 앱 설정을 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json" -UserPrincipalName name@microsoft.com
~~~~

## <a name="step-10-export-personal-data-contained-for-a-user-stored-gateway-or-in-the-users-gateway-permissions"></a>10단계: 사용자가 저장한 게이트웨이에 대해 포함되거나 사용자 게이트웨이 권한에 포함된 개인 데이터 내보내기

### <a name="powerapps-portal"></a>PowerApps 포털
사용자는 다음 단계에 따라 [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 게이트웨이 서비스 내에 저장된 개인 데이터를 내보낼 수 있습니다.

1. [PowerApps 포털](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 테넌트의 기본 환경 내에 있는 **게이트웨이**를 선택한 다음, 액세스할 수 있는 각 게이트웨이에 대한 **세부 정보**를 선택합니다.

    ![게이트웨이 방문 페이지](./media/powerapps-gdpr-export-dsr/gateway-select-details.png)

2. **세부 정보** 페이지에서 게이트웨이 세부 정보에 개인 데이터가 포함된 경우 세부 정보를 복사한 다음, Microsoft Word와 같은 문서 편집기에 붙여넣습니다.

    ![게이트웨이 세부 정보](./media/powerapps-gdpr-export-dsr/gateway-details-drillin.png)

3. **공유**를 선택하고 페이지의 콘텐츠를 복사한 다음, Microsoft Word와 같은 문서 편집기에 붙여넣습니다.

    ![게이트웨이 세부 정보](./media/powerapps-gdpr-export-dsr/gateway-details-share.png)

### <a name="gateway-powershell-cmdlets"></a>게이트웨이 PowerShell cmdlet
개인 게이트웨이를 검색, 관리 및 삭제할 수 있는 PowerShell cmdlet도 있습니다. 자세한 내용은 [온-프레미스 게이트웨이 cmdlet](https://go.microsoft.com/fwlink/?linkid=872238)을 참조하세요.

### <a name="administrators"></a>관리자
조직의 게이트웨이를 관리하는 지침은 [Microsoft PowerApps에 대한 온-프레미스 데이터 게이트웨이 이해](https://docs.microsoft.com/powerapps/maker/canvas-apps/gateway-reference#tenant-level-administration) 문서에서 **테넌트 관리** 섹션을 참조하세요.

## <a name="step-11-export-the-users-personal-data-in-microsoft-flow"></a>11단계: Microsoft Flow에서 사용자의 개인 데이터 내보내기
PowerApps 라이선스에는 항상 Microsoft Flow 기능이 포함되어 있습니다. Microsoft Flow는 PowerApps 라이선스에 포함될 뿐만 아니라 독립 실행형 서비스로도 제공됩니다. Microsoft Flow 서비스를 사용하는 사용자에 대한 DSR 요청에 응답하는 방법에 대한 자세한 내용은 [Microsoft Flow에 대한 GDPR 데이터 주체 요청에 응답](https://go.microsoft.com/fwlink/?linkid=872250)을 참조하세요.

> [!IMPORTANT]
>  관리자는 PowerApps 사용자에 대해 이 단계를 완료하는 것이 좋습니다.
>
>

## <a name="step-12-export-the-users-personal-data-in-cds-for-apps-instances"></a>12단계: 앱용 CDS 인스턴스에서 사용자의 개인 데이터 내보내기
조직 내 사용자는 특정 PowerApps 라이선스를 통해 앱용 CDS 인스턴스를 만들고 앱용 CDS에서 앱을 만들고 빌드할 수 있습니다(사용자가 개별 환경에서 앱용 CDS를 사용해 볼 수 있는 무료 라이선스인 PowerApps 커뮤니티 요금제 포함). 각 PowerApps 라이선스에 포함된 앱용 CDS 기능을 확인하려면 [PowerApps 가격 페이지](https://powerapps.microsoft.com/pricing)를 참조하세요.

앱용 CDS를 사용하는 사용자에 대한 DSR 요청에 응답하는 방법에 대한 자세한 내용은 [앱용 Common Data Service 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답](common-data-service-gdpr-dsr-guide.md)을 참조하세요.

> [!IMPORTANT]
>  관리자는 PowerApps 사용자에 대해 이 단계를 완료하는 것이 좋습니다.
>
>
