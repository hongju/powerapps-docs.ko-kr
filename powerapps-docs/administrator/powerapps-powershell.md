---
title: PowerShell 지원(미리 보기) | Microsoft Docs
description: 다양한 PowerShell cmdlet에 대한 설명 및 cmdlet을 설치 및 실행하는 방법에 대한 연습
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: 953efbabcdce55ac58376f927d5e399e69a40974
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerApps에 대한 PowerShell 지원(미리 보기)
최근에 앱 작성자 및 관리자용 PowerShell cmdlet 미리 보기가 제공되면서 [PowerApps](https://web.powerapps.com) 또는 [PowerApps 관리 센터](https://admin.powerapps.com)에서 현재는 수동으로만 가능한 다양한 모니터링 및 관리 작업을 자동화할 수 있습니다.

## <a name="installation"></a>설치
앱 작성자용 PowerShell cmdlet을 실행하려면 다음을 수행합니다.

1. [PowerShell 스크립트 파일](https://go.microsoft.com/fwlink/?linkid=872358)을 다운로드합니다.

2. 폴더에 파일의 압축을 풉니다.

3. 같은 폴더에서 관리자 권한으로 PowerShell 명령 창을 엽니다.

4. 다음 일회성 PowerShell 명령을 실행합니다(이는 현재 컴퓨터에서 PowerShell 명령을 실행한 적이 없다고 가정함).

    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Force
    ```

5. 다음 명령을 사용하여 필요한 모듈을 가져옵니다.

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6. 명령에 액세스하기 전에 다음 명령을 사용하여 자격 증명을 제공합니다. cmdlet을 계속 사용하기 위해 다시 로그인하기 전에 이러한 자격 증명을 새로 고치는 데는 최대 8시간이 걸립니다.

    ```
    Add-PowerAppsAccount
    ```

7.  현재 다음 명령을 사용하여 PowerShell 파일을 수동으로 차단 해제해야 할 수 있는 [알려진 문제](https://powerusers.microsoft.com/t5/Administering-PowerApps/Getting-errors-when-I-try-to-import-the-preview-powerapps/td-p/109036)가 있습니다.

    ```
    dir . | Unblock-File
    ```

## <a name="powerapps-cmdlets-for-app-makers-preview"></a>앱 작성자용 PowerApps cmdlet(미리 보기)

### <a name="prerequisite"></a>필수 조건
유효한 PowerApps 라이선스를 보유한 사용자는 이러한 cmdlet으로 작업을 수행할 수 있지만, 이러한 사용자는 함께 만들거나 자신과 공유된 리소스(예: 앱, 흐름 등)에만 액세스할 수 있습니다.

### <a name="cmdlet-list"></a>Cmdlet 목록
| 용도 | Cmdlet |
| --- | --- |
| 환경 읽기 | Get-PowerAppsEnvironment <br> Get-FlowEnvironment
| 캔버스 앱 읽기, 업데이트 및 삭제 | Get-App <br> Remove-App <br> Publish-App <br> Set-AppDisplayName <br> Get-AppVersion <br> Restore-AppVersion
| 캔버스 앱 권한 읽기, 업데이트 및 삭제 | Get-AppRoleAssignment <br> Set-AppRoleAssignment <br> Remove-AppRoleAssignment
| 흐름 읽기, 업데이트 및 삭제 | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| 흐름 권한 읽기, 업데이트 및 삭제 | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| 흐름 승인 읽기 및 응답 | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| 연결 읽기 및 삭제 | Get-Connection <br> Remove-Connection
| 연결 권한 읽기, 업데이트 및 삭제 | Get-ConnectionRoleAssignment <br> Set-ConnectionRoleAssignment <br> Remove-ConnectionRoleAssignment
| 커넥터 읽기 및 삭제 | Get-Connector <br> Remove-Connector
| 사용자 지정 커넥터 권한 읽기, 업데이트 및 삭제 | Get-ConnectorRoleAssignment <br> Set-ConnectorRoleAssignment <br> Remove-ConnectorRoleAssignment

> [!NOTE]
> 다음 명령을 사용하여 각 cmdlet에 대한 구문을 이해하고 샘플을 봅니다.
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>관리자용 PowerApps cmdlet(미리 보기)

### <a name="prerequisite"></a>필수 조건
관리자 cmdlet에서 관리 작업을 수행하려면 다음이 필요합니다.

* 유료 PowerApps 요금제 2 라이선스 또는 PowerApps 요금제 2 평가판 라이선스. [http://web.powerapps.com/trial](http://web.powerapps.com/trial)에서 30일 평가판 라이선스를 등록할 수 있습니다. 평가판 라이선스가 만료된 경우 갱신할 수 있습니다.

* 다른 사용자의 리소스를 검색해야 하는 경우 [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) 권한. (환경 관리자는 권한이 있는 환경 및 환경 리소스에만 액세스할 수 있습니다.)

### <a name="cmdlet-list"></a>Cmdlet 목록
| 용도 | Cmdlet
| --- | ---
| 환경 읽기 및 삭제 | Get-AdminEnvironment <br> Remove-AdminEnvironment
| 환경 읽기, 업데이트 및 삭제 권한 <br><br> 이러한 cmdlet은 앱용 CDS(Common Data Service) 데이터베이스가 없는 환경에서만 작동합니다. | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| 캔버스 앱 읽기 및 제거 | Get-AdminApp <br> Remove-AdminApp
| 캔버스 앱 권한 읽기, 업데이트 및 삭제 | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| 흐름 읽기, 업데이트 및 삭제 | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole

> [!NOTE]
> 다음 명령을 사용하여 각 cmdlet에 대한 구문을 이해하고 샘플을 봅니다.
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>질문

의견, 제안 또는 질문이 있는 경우 [PowerApps 커뮤니티 게시판 관리](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps)에 게시해 주세요.
