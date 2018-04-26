---
title: 파워 쿼리 문제 해결 | Microsoft Docs
description: 앱용 Common Data Service에서 사용자 지정 엔터티를 만들기 위해 파워 쿼리 사용과 관련된 문제 해결
documentationcenter: na
author: mllopis
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: aa6e54c635db195a254e0f406205d53775f59cd5
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-power-query"></a>파워 쿼리 문제 해결
파워 쿼리를 사용하여 외부 소스의 데이터를 포함하는 사용자 지정 엔터티를 만들 때 이 오류는 다음과 같은 경우에 나타날 수 있습니다.

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

파워 쿼리가 PowerApps 또는 Common Data Service에서 조직의 데이터에 액세스할 수 없는 경우 오류가 나타납니다. 이 상황은 다음 두 가지 경우에 발생합니다.

* 앱이 사용자 대신 회사 데이터에 액세스하는 것에 사용자가 동의하는 것을 AAD(Azure Active Directory) 테넌트 관리자가 허용하지 않았습니다.
* 관리되지 않는 Active Directory 테넌트 사용. 관리되지 않는 테넌트는 셀프 서비스 등록 제안을 완료하기 위해 만든 전역 관리자가 없는 디렉터리입니다. 이 시나리오를 해결하려면 사용자는 먼저 관리되는 테넌트로 전환한 후, 다음 섹션에 설명되어 있는 이 문제에 대한 두 가지 해결책 중 하나를 수행합니다.

이 문제를 해결하려면 AAD 관리자는 이 항목의 뒷부분에 나오는 절차의 단계를 따라야 합니다.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>사용자가 앱이 회사 데이터에 액세스하는 것에 동의하도록 허용
이는 아마도 다음 방법보다 쉽기는 하지만, 더 광범위한 사용 권한을 허용합니다.

1. [https://portal.azure.com](https://portal.azure.com)에서 **Azure Active Directory** 블레이드를 열고 **사용자 설정**을 선택합니다.
1. **앱이 사용자 대신 회사 데이터에 액세스하는 것에 사용자가 동의할 수 있음** 옆에 있는 **예**를 선택한 다음, **저장**을 선택합니다.

## <a name="allow-power-query-to-access-company-data"></a>파워 쿼리에서 회사 데이터에 액세스하도록 허용
다른 해결 방법으로 테넌트 관리자는 테넌트 전체 사용 권한을 수정하지 않고 파워 쿼리에 액세스 권한을 부여할 수 있습니다.

1. [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps)을 설치합니다.
2. 다음 PowerShell 명령을 실행합니다.
   * Login-AzureRmAccount(및 테넌트 관리자로 로그인)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

이 방식의 장점은(테넌트 차원의 솔루션 대비) 이 솔루션이 매우 대상 지정적이란 점입니다. **파워 쿼리** 서비스 주체만 프로비전하므로 테넌트의 다른 사용 권한은 전혀 변경되지 않습니다.

