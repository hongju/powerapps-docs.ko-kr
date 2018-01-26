---
title: "문제 해결 - 이 데이터베이스에 대한 매시업을 만들거나 검색할 수 없습니다. | Microsoft Docs"
description: "AAD 제한 사항에 대한 관리자 변경에 의해 CDS 및 파워 쿼리를 사용하여 사용자 정의 엔터티를 만드는 문제를 해결합니다."
services: 
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: b534400317e39dffec30f185c180de34098a378f
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="troubleshooting---unable-to-create-or-retrieve-a-mashup-for-this-database"></a>문제 해결 - 이 데이터베이스에 대한 매시업을 만들거나 검색할 수 없습니다.
**데이터에서 새 엔터티(기술 미리 보기)** 기능을 사용하는 경우 다음과 같이 오류가 발생할 수 있습니다.

    *Unable to create or retrieve a mashup for the current database*

**파워 쿼리**를 사용하여 외부 데이터 원본의 데이터를 기반으로 하는 **CDS(Common Data Service)**에서 *사용자 지정 엔터티*를 만드는 기능을 사용 중인 경우 발생할 수 있습니다. 오류는 **파워 쿼리**가 **PowerApps 또는 CDS**에 있는 조직의 데이터에 액세스할 수 없을 때 트리거됩니다. 이 상황이 발생할 수 있는 경우 두 가지 시나리오가 있습니다.

* 앱이 사용자 대신 회사 데이터에 액세스하는 것에 사용자가 동의하는 것을 **AAD(Azure Active Directory)** 테넌트 관리자가 허용하지 않았습니다.
* 관리되지 않는 Active Directory 테넌트 사용. 관리되지 않는 테넌트는 셀프 서비스 등록 제안을 완료하기 위해 만든 전역 관리자가 없는 디렉터리입니다. 이 시나리오를 해결하려면 사용자는 *먼저* 관리되는 테넌트로 전환한 다음, 다음 섹션에 설명되어 있는 이 문제에 대한 두 가지 솔루션 중 하나를 수행합니다.

위에서 설명한 문제를 해결할 수 있는 두 가지 방법이 있습니다.

* 사용자가 앱이 회사 데이터에 액세스하는 것에 동의하는 데 필요한 단계를 AAD 관리자가 따르도록 합니다.
* AAD 관리자가 **파워 쿼리**를 허용하여 데이터에 액세스할 수 있도록 합니다.

이러한 솔루션에 필요한 각 단계는 다음에 설명되어 있습니다.

## <a name="allowing-users-to-give-apps-consent-to-access-company-data"></a>사용자가 앱이 회사 데이터에 액세스하는 것에 동의하도록 허용

AAD 테넌트 관리자에게 문의하여, 사용자가 앱이 회사 데이터에 액세스하는 것에 동의할 수 있도록 다음 단계를 수행하도록 합니다.

1. [https://portal.azure.com](https://portal.azure.com)을 방문합니다.
2. **Azure Active Directory** 블레이드를 엽니다.
3. **사용자 설정**을 선택합니다.
4. **앱이 사용자 대신 회사 데이터에 액세스하는 것에 사용자가 동의할 수 있음** 옆에 있는 **예**를 선택한 다음, **저장**을 선택합니다.
5. 해당 프로세스가 완료되면 문제가 해결됩니다.

이는 아마도 가장 쉬운 방법이긴 하지만, 다음 옵션보다 광범위한 사용 권한을 허용합니다.

## <a name="allowing-power-query-to-access-company-data"></a>파워 쿼리에서 회사 데이터에 액세스하도록 허용
다른 해결책은 테넌트 차원의 사용 권한을 수정하지 않고 테넌트 관리자가 **파워 쿼리**를 허용하도록 하는 것입니다. 테넌트 관리자가 이를 위해 다음 단계를 수행하도록 합니다.

1. [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps)을 설치합니다.
2. 다음 PowerShell 명령을 실행합니다.
   * Login-AzureRmAccount(및 테넌트 관리자로 로그인)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

이 방식의 장점은(테넌트 차원의 솔루션 대비) 이 솔루션이 매우 대상 지정적이란 점입니다. **파워 쿼리** 서비스 주체만 프로비전하므로 테넌트의 다른 사용 권한은 전혀 변경되지 않습니다.

