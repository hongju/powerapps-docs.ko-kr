---
title: PowerShell 지원(미리 보기) | Microsoft Docs
description: 다양한 PowerShell cmdlet에 대한 설명 및 cmdlet을 설치 및 실행하는 방법에 대한 연습
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 01/18/2019
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 0152296adbe01abae2b831576c312a43d1f2a2b8
ms.sourcegitcommit: 3ce7c17f90f87756a072210c8abfbd93733a6d4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2019
ms.locfileid: "54397770"
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerApps에 대한 PowerShell 지원(미리 보기)
최근에 앱 작성자 및 관리자용 PowerShell cmdlet 미리 보기가 제공되면서 [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 또는 [PowerApps 관리 센터](https://admin.powerapps.com)에서 현재는 수동으로만 가능한 다양한 모니터링 및 관리 작업을 자동화할 수 있습니다.

## <a name="cmdlets"></a>Cmdlet
[Cmdlet](https://docs.microsoft.com/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)은 Windows PowerShell 환경에서 명령을 실행하는 PowerShell 스크립트 언어로 작성된 함수입니다. 이러한 PowerApps cmdlet을 실행하면 웹 브라우저에서 관리 포털을 통해 이동하지 않고도 비즈니스 애플리케이션 플랫폼과 상호 작용할 수 있습니다. 이러한 cmdlet을 다른 PowerShell 함수와 결합하여 워크플로를 최적화할 수 있는 복잡한 스크립트를 작성할 수 있습니다. 테넌트의 관리자가 아닌 경우에도 cmdlet을 계속 사용할 수 있지만 소유한 리소스로 제한됩니다. 'Admin'이라는 단어로 시작하는 cmdlet은 관리 사용자 계정으로 사용하도록 디자인되었습니다.

cmdlet은 PowerShell 갤러리에서 두 개의 별도 모듈로 제공됩니다. 
- [관리자](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.1)
- [Maker](https://www.powershellgallery.com/packages/Microsoft.PowerApps.PowerShell/1.0.1) 

## <a name="installation"></a>설치
앱 작성자용 PowerShell cmdlet을 실행하려면 다음을 수행합니다.

1. 관리자 권한으로 PowerShell을 실행합니다.

   > [!div class="mx-imgBorder"] 
   > ![관리자 권한으로 PowerShell 실행](media/open-powershell-as-admin75.png "관리자 권한으로 PowerShell 실행")

2. 다음 명령을 사용하여 필요한 모듈을 가져옵니다.

    ```
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber
    ```
3. 리포지토리의 *InstallationPolicy* 값 변경을 허용하라는 메시지가 표시되면 'A'를 입력하고 각 모듈에 대해 **Enter**를 눌러[A] Yes를 승인합니다.

   ![InstallationPolicy 값 허용](media/accept-installationpolicy-value75.png "InstallationPolicy 값 허용")

4. 명령에 액세스하기 전에 다음 명령을 사용하여 자격 증명을 제공하는 옵션이 있습니다. cmdlet을 계속 사용하기 위해 다시 로그인하기 전에 이러한 자격 증명을 새로 고치는 데는 최대 8시간이 걸립니다.

    ```
    # This call opens prompt to collect credentials (Azure Active Directory account and password) used by the commands 
    Add-PowerAppsAccount
    ```

    ```
    # Here is how you can pass in credentials (avoiding opening a prompt)
    $pass = ConvertTo-SecureString "password" -AsPlainText -Force
    Add-PowerAppsAccount -Username foo@bar.com -Password $pass
    ```

## <a name="powerapps-cmdlets-for-app-creators-preview"></a>앱 작성자용 PowerApps cmdlet(미리 보기)

### <a name="prerequisite"></a>필수 조건
유효한 PowerApps 라이선스를 보유한 사용자는 이러한 cmdlet으로 작업을 수행할 수 있지만, 이러한 사용자는 함께 만들거나 자신과 공유된 리소스(예: 앱, 흐름 등)에만 액세스할 수 있습니다.

### <a name="cmdlet-list---maker-cmdlets"></a>Cmdlet 목록 - 작성자 Cmdlet
> [!NOTE]
> 충돌을 방지하기 위해 적절한 접두사를 추가하기 위해 최신 릴리스의 일부 cmdlet 함수 이름을 업데이트했습니다. 변경된 사항에 대한 개요는 아래 표를 참조하세요.

| 용도 | Cmdlet |
| --- | --- |
| 환경 읽기 | Get-PowerAppEnvironment *(이전의 Get-PowerAppsEnvironment)* <br> Get-FlowEnvironment |
| 캔버스 앱 읽기, 업데이트 및 삭제 | Get-PowerApp *(이전의 Get-App)* <br> Remove-PowerApp *(이전의 Remove-App)* <br> Publish-PowerApp *(이전의 Publish-App)* <br> Set-AppDisplayName *(이전의 Set-PowerAppDisplayName)*<br> Get-PowerAppVersion *(이전의 Get-AppVersion)* <br> Restore-PowerAppVersion *(이전의 Restore-AppVersion)* |
| 캔버스 앱 권한 읽기, 업데이트 및 삭제 | Get-PowerAppRoleAssignment *(이전의 Get-AppRoleAssignment)* <br> Set-PowerAppRoleAssignment *(이전의 Set-AppRoleAssignment)* <br> Remove-PowerAppRoleAssignment *(이전의previously Remove-AppRoleAssignment)* |
| 흐름 읽기, 업데이트 및 삭제 | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow |
| 흐름 권한 읽기, 업데이트 및 삭제 | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole |
| 흐름 승인 읽기 및 응답 | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest |
| 연결 읽기 및 삭제 | Get-PowerAppConnection *(이전의 Get-Connection)* <br> Remove-PowerAppConnection *(이전의 Remove-Connection)* |
| 연결 권한 읽기, 업데이트 및 삭제 | Get-PowerAppConnectionRoleAssignment *(이전의 Get-ConnectionRoleAssignment)* <br> Set-PowerAppConnectionRoleAssignment *(이전의 Set-ConnectionRoleAssignment)* <br> Remove-PowerAppConnectionRoleAssignment *(이전의 Remove-ConnectionRoleAssignment)* |
| 커넥터 읽기 및 삭제 | Get-PowerAppConnector *(이전의 Get-Connector)* <br> Remove-PowerAppConnector *(이전의 Remove-Connector)* |
| 사용자 지정 커넥터 권한 읽기, 업데이트 및 삭제 | Get-PowerAppConnectorRoleAssignment *(이전의 Get-ConnectorRoleAssignment)* <br> Set-PowerAppConnectorRoleAssignment *(이전의 Set-ConnectorRoleAssignment)* <br> Remove-PowerAppConnectorRoleAssignment *(이전의 Remove-ConnectorRoleAssignment)* |

## <a name="powerapps-cmdlets-for-administrators-preview"></a>관리자용 PowerApps cmdlet(미리 보기)

### <a name="prerequisite"></a>필수 조건
관리자 cmdlet에서 관리 작업을 수행하려면 다음이 필요합니다.

* 유료 PowerApps 요금제 2 라이선스 또는 PowerApps 요금제 2 평가판 라이선스. [http://web.powerapps.com/trial](http://web.powerapps.com/trial)에서 30일 평가판 라이선스를 등록할 수 있습니다. 평가판 라이선스가 만료된 경우 갱신할 수 있습니다.

* 다른 사용자의 리소스를 검색해야 하는 경우 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) 권한. (환경 관리자는 권한이 있는 환경 및 환경 리소스에만 액세스할 수 있습니다.)

### <a name="cmdlet-list---admin-cmdlets"></a>Cmdlet 목록 - 관리자 Cmdlet

| 용도 | Cmdlet
| --- | ---
| 앱 데이터베이스용 환경 및 Common Data Service 읽기, 업데이트 및 삭제 | New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> Get-AdminPowerAppEnvironment *(이전의 Get-AdminEnvironment)* <br> Remove-AdminPowerAppEnvironment *(이전의 Remove-AdminEnvironment)* <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations |
| CDS 데이터베이스 삭제 | Remove-LegacyCDSDatabase **\*새로 만들기\*** | 
| 환경 읽기, 업데이트 및 삭제 권한 <br><br> *이러한 cmdlet은 현재 앱용 CDS(Common Data Service) 데이터베이스가 없는 환경에서만 작동합니다.* | Get-AdminPowerAppEnvironmentRoleAssignment *(이전의 Get-adminenvironmentroleassignment)* <br> Set-AdminPowerAppEnvironmentRoleAssignment *(이전의 Set-AdminEnvironmentRoleAssignment)* <br> Remove-AdminPowerAppEnvironmentRoleAssignment *(이전의 Remove-AdminEnvironmentRoleAssignment)* |
| 캔버스 앱 읽기, 업데이트 및 제거 | Get-AdminPowerApp *(이전의 Get-AdminApp)* <br> Remove-AdminPowerApp *(이전의 Remove-AdminApp)* <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent |
| 캔버스 앱 권한 읽기, 업데이트 및 삭제 | Get-AdminPowerAppRoleAssignment *(이전의 Get-AdminAppRoleAssignment)* <br> Remove-AdminPowerAppRoleAssignment *(이전의 Remove-AdminAppRoleAssignment)* <br> Set-AdminPowerAppRoleAssignment *(이전의 Set-AdminAppRoleAssignment)* <br> Set-AdminPowerAppOwner *(이전의 Set-AdminAppOwner)* |
| 흐름 읽기, 업데이트 및 삭제 | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow <br> Remove-AdminFlowApprovals |
| 흐름 권한 읽기, 업데이트 및 삭제 | Get-AdminFlowOwnerRole <br> Set-AdminFlowOwnerRole <br> Remove-AdminFlowOwnerRole |
| 연결 읽기 및 삭제 | Get-AdminPowerAppConnection *(이전의 Get-AdminConnection)* <br> Remove-AdminPowerAppConnection *(이전의 Remove-AdminConnection)* |
| 연결 권한 읽기, 업데이트 및 삭제 | Get-AdminPowerAppConnectionRoleAssignment *(이전의 Get-AdminConnectionRoleAssignment)* <br> Set-AdminPowerAppEnvironmentConnectionRoleAssignment *(이전의 Set-AdminConnectionRoleAssignment)* <br> Remove-AdminPowerAppConnectionRoleAssignment *(이전의 Remove-AdminConnectionRoleAssignment)* |
| 사용자 지정 커넥터 읽기 및 삭제 | Get-AdminPowerAppConnector *(이전의 Get-AdminConnector)* <br> Remove-AdminPowerAppConnector *(이전의 Remove-AdminConnector)* |
| 사용자 지정 커넥터 권한 읽기, 업데이트 및 삭제 | Get-AdminPowerAppConnectorRoleAssignment *(이전의 Get-AdminConnectorRoleAssignment)*<br> Set-AdminPowerAppConnectorRoleAssignment *(이전의 Set-AdminConnectorRoleAssignment)* <br> Remove-AdminPowerAppConnectorRoleAssignment *(이전의 Remove-AdminConnectorRoleAssignment)* |
| 사용자의 PowerApps 사용자 설정, 사용자 앱 설정 및 알림 읽기 | Get-AdminPowerAppsUserDetails |
| 사용자에게 표시되지 않는 사용자의 Microsoft 흐름 설정을 읽고 삭제하지만 흐름 실행을 지원합니다. | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails |
| 조직에 대한 데이터 손실 방지 정책 만들기, 읽기, 업데이트 및 삭제 | Get-AdminDlpPolicy *(이전의 Get-AdminApiPolicy)* <br> New-AdminDlpPolicy *(이전의 Add-AdminApiPolicy)* <br> Remove-AdminDlpPolicy *(이전의 Remove-AdminApiPolicy)* <br> Set-AdminDlpPolicy *(이전의 Set-AdminApiPolicy)* <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup <br/>Add-CustomConnectorToPolicy<br/> Remove-CustomConnectorFromPolicy|

## <a name="tips"></a>팁

- Get-Help 'CmdletName'을 사용하여 예제 목록을 가져옵니다.

     ![Get-Help 명령](media/get-help-cmdlet.png "Get-Help 명령")

- 입력 태그에 가능한 옵션을 순환하려면 cmdlet 이름 뒤에 대시(-) 문자를 입력한 후 탭 키를 클릭합니다.

예제 명령:

```
Get-Help Get-AdminPowerAppEnvironment
Get-Help Get-AdminPowerAppEnvironment -Examples
Get-Help Get-AdminPowerAppEnvironment -Detailed
```

## <a name="operation-examples"></a>작업 예제

다음은 신규 및 기존 PowerApps cmdlet을 사용하는 방법을 보여주는 몇 가지 일반적인 시나리오입니다.

- [환경 명령](#environments-commands)
- [PowerApps 명령](#powerapps-commands)
- [흐름 명령](#flow-commands)
- [API 연결 명령](#api-connection-commands)
- [DLP(데이터 손실 방지) 정책 명령](#data-loss-prevention-dlp-policy-commands)

### <a name="environments-commands"></a>환경 명령

이러한 명령을 사용하여 테넌트 환경의 세부 정보를 가져오고 업데이트합니다.

#### <a name="display-a-list-of-all-environments"></a>모든 환경의 목록 표시

```
Get-AdminPowerAppEnvironment
```

테넌트 전체에서 각 환경 목록을 세부 정보(예: 환경 이름(guid), 표시 이름, 위치, 작성자 등)와 함께 반환합니다.

#### <a name="display-details-of-your-default-environment"></a>기본 환경의 세부 정보 표시

```
Get-AdminPowerAppEnvironment –Default
```

테넌트의 기본 환경에 대한 세부 정보만 반환합니다.

#### <a name="display-details-of-a-specific-environment"></a>특정 환경의 세부 정보 표시

```
Get-AdminPowerAppEnvironment –EnvironmentName ‘EnvironmentName’
```

**참고**: *EnvironmentName* 필드는 *DisplayName*과 다른 고유한 식별자입니다(다음 이미지의 출력에서 첫 번째와 두 번째 필드 참조).

![Get-AdminEnvironment 명령](media/get-adminenvironment.png "Get-AdminEnvironment 명령")

### <a name="powerapps-commands"></a>PowerApps 명령

이러한 작업은 테넌트의 PowerApps 데이터를 읽고 수정하는 데 사용됩니다.

#### <a name="display-a-list-of-all-powerapps"></a>모든 PowerApps의 목록 표시

```
Get-AdminPowerApp
```

테넌트의 모든 PowerApps 목록을 각 세부 정보(예: 애플리케이션 이름(guid), 표시 이름, 작성자 등)와 함께 반환합니다.

#### <a name="display-a-list-of-all-powerapps-that-match-the-input-display-name"></a>입력 표시 이름과 일치하는 모든 PowerApps 목록 표시

```
Get-AdminPowerApp 'DisplayName'
```

표시 이름과 일치하는 테넌트의 모든 PowerApps 목록을 반환합니다. 

**참고**: 공백이 포함된 입력된 값 주위에 따옴표(”)를 사용합니다.

#### <a name="feature-an-application"></a>애플리케이션 기능

```
Set-AdminPowerAppAsFeatured –AppName 'AppName'
```

주요 애플리케이션이 그룹화되고 PowerApps 모바일 플레이어의 목록 맨 위로 푸시됩니다.

**참고**: 환경과 마찬가지로 *AppName* 필드는 *DisplayName*과 다른 고유한 식별자입니다. 표시 이름에 따라 작업을 수행하려면 일부 함수를 통해 파이프라인을 사용할 수 있습니다(다음 함수 참조).

#### <a name="make-an-application-a-hero-app-using-the-pipeline"></a>파이프라인을 사용하여 애플리케이션을 Hero 앱으로 만듭니다.

```
Get-AdminPowerApp 'DisplayName' | Set-AdminPowerAppAsHero
```

Hero 앱은 PowerApps 모바일 플레이어 목록의 위쪽에 표시됩니다. Hero 앱은 하나만 있을 수 있습니다.

파이프라인(두 cmdlet 사이에 ‘|’ 문자로 표시)은 첫 번째 cmdlet의 출력을 가져와서 두 번째 입력 값으로 전달합니다. 이 함수는 파이프라인 기능을 수용하도록 작성된 것으로 가정합니다.

**참고**: 앱은 히어로로 바뀌기 전에 이미 추천 앱이어야 합니다.

#### <a name="display-the-number-of-apps-each-user-owns"></a>각 사용자가 소유한 앱의 수 표시

```
Get-AdminPowerApp | Select –ExpandProperty Owner | Select –ExpandProperty displayname | Group
```

네이티브 PowerShell 함수를 PowerApps cmdlet과 결합하여 데이터를 더 많이 조작할 수 있습니다. 여기서 Select 함수를 사용하여 Get-AdminApp 개체에서 Owner 특성(개체)을 격리합니다. 그런 다음, 출력을 다른 Select 함수로 파이프라이닝하여 owner 개체의 이름을 격리합니다. 마지막으로, 두 번째 Select 함수 출력을 Group 함수로 전달하면 각 소유자의 앱 수를 포함하는 좋은 테이블을 반환합니다.

![Get-AdminPowerApp 명령](media/get-adminpowerapp.png "Get-AdminPowerApp 명령")

#### <a name="display-the-number-of-apps-in-each-environment"></a>각 환경의 앱 수 표시

```
Get-AdminPowerApp | Select -ExpandProperty EnvironmentName | Group | %{ New-Object -TypeName PSObject -Property @{ DisplayName = (Get-AdminPowerAppEnvironment -EnvironmentName $_.Name | Select -ExpandProperty displayName); Count = $_.Count } }
```

![Get-AdminPowerApp 명령](media/get-adminpowerapp-environment.png "Get-AdminPowerApp 명령")

#### <a name="download-powerapps-user-details"></a>PowerApps 사용자 세부 정보 다운로드

```
Get-AdminPowerAppsUserDetails -OutputFilePath '.\adminUserDetails.txt' –UserPrincipalName ‘admin@bappartners.onmicrosoft.com’
```

위의 명령은 지정된 텍스트 파일에 PowerApps 사용자 세부 정보(사용자 주체 이름을 통해 입력된 사용자에 대한 기본 사용 정보)를 저장합니다. 해당 이름이 있는 기존 파일이 없으면 새 파일을 만들고, 이미 존재하면 텍스트 파일을 덮어씁니다.

#### <a name="set-logged-in-user-as-the-owner-of-a-powerapp"></a>로그인한 사용자를 PowerApp의 소유자로 설정

```
Set-AdminPowerAppOwner –AppName 'AppName' -AppOwner $Global:currentSession.userId –EnvironmentName 'EnvironmentName'
```

PowerApp의 소유자 역할을 현재 사용자로 변경하고 원래 소유자를 "볼 수 있음" 역할 형식으로 바꿉니다.

**참고**: AppName 및 EnvironmentName 필드는 표시 이름이 아닌 고유 식별자(guids)입니다.

### <a name="flow-commands"></a>흐름 명령

이러한 명령을 사용하여 Microsoft Flow와 관련된 데이터를 보고 수정할 수 있습니다.

#### <a name="display-all-flows"></a>모든 흐름 표시

```
Get-AdminFlow
```

테넌트의 모든 흐름 목록을 반환합니다.

#### <a name="display-flow-owner-role-details"></a>흐름 소유자 역할 세부 정보 표시

```
Get-AdminFlowOwnerRole –EnvironmentName 'EnvironmentName' –FlowName ‘FlowName’
```

지정된 흐름의 소유자 세부 정보를 반환합니다.

**참고**: *환경* 및 *PowerApps*와 마찬가지로 *FlowName*은 흐름의 표시 이름과 다른 고유 식별자(guid)입니다.

#### <a name="display-flow-user-details"></a>흐름 사용자 세부 정보 표시

```
Get-AdminFlowUserDetails –UserId $Global:currentSession.userId
```

흐름 사용에 관한 사용자 세부 정보를 반환합니다. 이 예제에서는 PowerShell 세션의 현재 로그인한 사용자의 사용자 ID를 입력으로 사용하고 있습니다.

#### <a name="remove-flow-user-details"></a>흐름 사용자 세부 정보 제거

```
Remove-AdminFlowUserDetails –UserId 'UserId'
```

Microsoft 데이터베이스에서 흐름 사용자의 세부 정보를 완전히 삭제합니다. 흐름 사용자 세부 정보를 삭제하기 전에 입력 사용자가 소유한 모든 흐름을 삭제해야 합니다.

**참고**: UserId 필드는 사용자의 Azure Active Directory 레코드의 개체 ID로, **Azure Active Directory** > **사용자** > **프로필** > **개체 ID** 아래의 [Azure Portal](https://portal.azure.com)에 있습니다. 여기에서 이 데이터에 액세스하려면 관리자여야 합니다.

#### <a name="export-all-flows-to-a-csv-file"></a>모든 흐름을 CSV 파일로 내보내기

```
Get-AdminFlow | Export-Csv -Path '.\FlowExport.csv'
```

테넌트의 모든 흐름을 테이블 형식 보기 .csv 파일로 내보냅니다.

### <a name="api-connection-commands"></a>API 연결 명령

테넌트의 API 연결을 보고 관리합니다.

#### <a name="display-all-native-connections-in-your-default-environment"></a>기본 환경의 모든 네이티브 연결 표시

```
Get-AdminPowerAppEnvironment -Default | Get-AdminConnection
```

기본 환경에 있는 모든 API 연결 목록을 표시합니다. 네이티브 연결은 제조업체 포털의 **데이터** > **연결** 탭 아래에 있습니다.

#### <a name="display-all-custom-connectors-in-the-tenant"></a>테넌트의 모든 사용자 지정 커넥터 표시

```
Get-AdminPowerAppConnector
```

테넌트의 모든 사용자 지정 커넥터 세부 정보 목록을 반환합니다.

### <a name="data-loss-prevention-dlp-policy-commands"></a>DLP(데이터 손실 방지) 정책 명령

이러한 cmdlet은 테넌트의 DLP 정책을 제어합니다.

#### <a name="display-all-policies"></a>모든 정책 표시

```
Get-AdminDlpPolicy
```

모든 정책의 목록을 반환합니다.

#### <a name="display-a-filtered-list-of-policies"></a>필터링된 정책 목록 표시

```
Get-AdminDlpPolicy 'DisplayName'
```

표시 이름을 사용하여 정책 필터링

#### <a name="display-all-business-data-only-api-connectors-in-a-policy"></a>정책에 모든 '비즈니스 데이터 전용' API 커넥터 표시

```
Get-AdminDlpPolicy 'PolicyName' | Select –ExpandProperty BusinessDataGroup
```

입력 정책의 *비즈니스 데이터 전용*(또는 *BusinessDataGroup*) 필드에 있는 API 연결을 나열합니다.

#### <a name="add-a-connector-to-the-business-data-only-group"></a>'비즈니스 데이터 전용' 그룹에 커넥터 추가

```
Add-ConnectorToBusinessDataGroup -PolicyName 'PolicyName' –ConnectorName 'ConnectorName'
```

지정된 DLP 정책의 '비즈니스 데이터 전용' 그룹에 커넥터를 추가합니다. 여기서 *DisplayName* 및 *ConnectorName*(입력으로 사용됨)별로 커넥터 목록을 참조하세요.

## <a name="version-history"></a>버전 기록
| 버전 | Date | 업데이트 |
| --- | --- | --- |
| 1.0 | 04/23/2018 | <ol> <li> 환경, 앱, 흐름, 흐름 승인, 연결 및 사용자 지정 커넥터에 대한 관리 cmdlet을 포함하여 앱 작성자를 위한 PowerApps cmdlet의 초기 시작(미리 보기) </li> <li> 환경, 앱 및 흐름에 대한 관리 cmdlet을 포함하여 관리자를 위한 PowerApps cmdlet의 초기 시작(미리 보기) </li></ol>|
| 2.0 | 05/24/2018 | <ol> <li> 앱 작성자 및 관리자용 cmdlet의 사소한 버그 수정 </li> <li> 다음과 같은 새로운 관리 cmdlet을 추가했습니다. <br> Get-AdminConnection <br> Remove-AdminConnection <br> Get-AdminConnectionRoleAssignment <br> Set-AdminConnectionRoleAssignment <br>Remove-AdminConnectionRoleAssignment <br>Get-AdminConnector  <br>Remove-AdminConnector <br>Set-AdminConnectorRoleAssignment  <br>Get-AdminConnectorRoleAssignment  <br>Remove-AdminConnectorRoleAssignment <br>Get-AdminPowerAppsUserDetails <br>Get-AdminFlowUserDetails <br>Remove-AdminFlowUserDetails <br>Get-AdminApiPolicy  <br>Add-AdminApiPolicy <br>Remove-AdminApiPolicy <br>Set-AdminApiPolicy <br>Add-ConnectorToBusinessDataGroup  <br>Remove-ConnectorFromBusinessDataGroup </li> </ol>
| 3.0 | 07/30/2018 | <ol> <li> Add-PowerAppsAccount에 자격 증명을 전달하는 기능 추가(반복 스크립팅을 사용 가능) </li> <li>  앱 작성자 및 관리자용 cmdlet의 사소한 버그 수정 </li> <li> 앱 작성자를 위한 각 cmdlet에 "PowerApp" 또는 "흐름" 접두사 추가 </li> <li>  앱 작성자를 위한 각 cmdlet에 "AdminPowerApp" 또는 "AdminFlow" 접두사 추가 </li> <li> 다음과 같은 새로운 관리 cmdlet을 추가했습니다. <br> New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent <br> Remove-AdminFlowApprovals </li></ol>
| 4.0 | 08/15/2018 | 함수가 동기화되도록 New-AdminPowerAppCdsDatabase에 선택적 매개 변수 추가(예: 데이터베이스가 성공적으로 프로비저닝될 때까지 반환되지 않음)
| 5.0 | 08/24/2018 | 보안 설정에 따라 일부 데이터를 반환하지 않는 흐름 관리자 cdmlet 문제 해결
| 6.0 | 01/09/2019 | <ol><li>이제 PowerShell 갤러리에서 cmdlet을 두 개의 별도 모듈로 제공됩니다. 관리자 및 작성자.</li> <li>관리 cmdlet 추가: Remove-LegacyCDSDatabase</li><li> 작업 예제 추가</li><li>DLP(데이터 손실 방지)에서 HTTP 및 사용자 지정 커넥터를 관리하는 기능 추가</li></ol>|

## <a name="questions"></a>질문

의견, 제안 또는 질문이 있는 경우 [PowerApps 커뮤니티 게시판 관리](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps)에 게시해 주세요.
