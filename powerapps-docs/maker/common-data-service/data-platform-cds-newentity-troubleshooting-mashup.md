---
title: 파워 쿼리 문제 해결 | Microsoft Docs
description: 앱용 CDS(Common Data Service)에서 사용자 지정 엔터티를 만들기 위해 파워 쿼리 사용과 관련된 문제를 해결합니다.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
ms.openlocfilehash: b89d7a59406d19759b84c34dbda84b98b10d5e58
ms.sourcegitcommit: f236364ecb06dd86244cd9a607c31e0d716912e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="troubleshooting-power-query"></a>파워 쿼리 문제 해결
파워 쿼리를 사용하여 외부 소스의 데이터를 포함하는 사용자 지정 엔터티를 만들 때 이 오류는 다음과 같은 경우에 나타날 수 있습니다.

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

파워 쿼리가 PowerApps 또는 앱용 CDS(Common Data Service)에서 조직의 데이터에 액세스할 수 없는 경우 오류가 나타납니다. 이 상황은 다음 두 가지 경우에 발생합니다.

* 앱이 사용자 대신 회사 데이터에 액세스하는 것에 사용자가 동의하는 것을 AAD(Azure Active Directory) 테넌트 관리자가 허용하지 않았습니다.
* 관리되지 않는 Active Directory 테넌트 사용. 관리되지 않는 테넌트는 셀프 서비스 등록 제안을 완료하기 위해 만든 전역 관리자가 없는 디렉터리입니다. 이 시나리오를 해결하려면 사용자는 먼저 관리되는 테넌트로 전환한 후, 다음 섹션에 설명되어 있는 이 문제에 대한 두 가지 해결책 중 하나를 수행합니다.

이 문제를 해결하려면 Azure Active Directory 관리자는 이 항목의 뒷부분에 나오는 절차의 단계를 따라야 합니다.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>사용자가 앱이 회사 데이터에 액세스하는 것에 동의하도록 허용
이는 아마도 다음 방법보다 쉽기는 하지만, 더 광범위한 사용 권한을 허용합니다.

1. [https://portal.azure.com](https://portal.azure.com)에서 **Azure Active Directory** 블레이드를 열고 **사용자 설정**을 선택합니다.
2. **앱이 사용자 대신 회사 데이터에 액세스하는 것에 사용자가 동의할 수 있음** 옆에 있는 **예**를 선택한 다음, **저장**을 선택합니다.

## <a name="allow-power-query-to-access-company-data"></a>파워 쿼리에서 회사 데이터에 액세스하도록 허용
다른 해결 방법으로 테넌트 관리자는 테넌트 전체 사용 권한을 수정하지 않고 파워 쿼리에 액세스 권한을 부여할 수 있습니다.

1. [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps)을 설치합니다.
2. 다음 PowerShell 명령을 실행합니다.
   * Login-AzureRmAccount(및 테넌트 관리자로 로그인)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

이 방식의 장점은(테넌트 차원의 솔루션 대비) 이 솔루션이 매우 대상 지정적이란 점입니다. **파워 쿼리** 서비스 주체만 프로비전하므로 테넌트의 다른 사용 권한은 전혀 변경되지 않습니다.

## <a name="updating-personal-data"></a>개인 데이터 업데이트

사용자는 쿼리 편집기 및에서 액세스 가능한 `Options` 대화 상타를 통해 매시업 및 기타 정보(예: 쿼리 이름 및 매시업 메타데이터)를 업데이트할 수 있습니다.

PowerApps에서는 데이터 창으로 이동하고, 확장하고, 엔터티 창 메뉴 항목을 클릭하여 쿼리 편집기에 액세스할 수 있습니다. 거기에서 "..." 메뉴를 클릭하고 쿼리 편집을 선택합니다. 그런 다음, 리본 메뉴에서 `Options` 단추를 클릭하고 `Export Diagnostics` 단추를 클릭합니다.


## <a name="deleting-personal-data"></a>개인 데이터 삭제

대부분의 데이터는 30일 이내에 자동으로 삭제됩니다. 매시업 관련 데이터 및 메타데이터의 경우 사용자가 PowerApps를 통해 해당 매시업을 모두 제거해야 합니다. 관련된 데이터 및 메타데이터는 모두 30일 이내에 삭제됩니다.

매시업은 데이터 통합자 프로젝트를 제거하여 Power Apps에서 제거할 수 있습니다. 해당 프로젝트는 "..." 단추를 클릭하고 `Delete` 옵션을 선택하여 이름 탭에서 제거할 수 있습니다.

"데이터의 새 엔터티(기술 미리 보기)" 기능을 통해 매시업을 만든 경우 "..." 단추를 클릭하고, 쿼리 편집을 선택하고, 리본 메뉴에서 옵션을 선택하고, 마지막으로 "모든 쿼리 제거" 단추를 클릭하여 제거할 수 있습니다. 쿼리를 삭제하려고 한다고 확인하면 삭제됩니다.


## <a name="exporting-personal-data"></a>개인 데이터 내보내기

사용자가 쿼리 편집기를 열고, 리본 메뉴에서 `Options` 단추를 클릭하고, `Export Diagnostics` 단추를 클릭할 수 있습니다.

PowerApps에서는 데이터 창으로 이동하고, 확장하고, 엔터티 창 메뉴 항목을 클릭하여 쿼리 편집기에 액세스할 수 있습니다. 거기에서 "..." 메뉴를 클릭하고 쿼리 편집을 선택합니다. 그런 다음, 리본 메뉴에서 `Options` 단추를 클릭하고 `Export Diagnostics` 단추를 클릭합니다.

Azure Portal에서 UI(사용자 인터페이스)의 사용자 작업에 관련된 시스템 생성 로그에 액세스할 수 있습니다.


