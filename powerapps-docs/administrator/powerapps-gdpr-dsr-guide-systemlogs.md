---
title: PowerApps, Microsoft Flow 및 앱용 CDS(Common Data Service)에서 시스템 생성 로그에 대한 DSR 요청에 응답 | Microsoft Docs
description: PowerApps, Microsoft Flow 및 앱용 CDS(Common Data Service)에서 시스템 생성 로그에 대한 DSR 요청에 응답하는 방법 연습
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: 970cf64f9312e1d9f820671d313ee497f3e27b61
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="responding-to-dsr-requests-for-system-generated-logs-in-powerapps-microsoft-flow-and-common-data-service-for-apps"></a>PowerApps, Microsoft Flow 및 앱용 Common Data Service에서 시스템 생성 로그에 대한 DSR 요청에 응답
Microsoft에서는 EU(유럽 연합) GDPR(일반 데이터 보호 규정)의 광범위한 ‘개인 데이터’ 정의에 따라 사적인 것으로 간주할 수 있는 시스템 생성 로그에 액세스하고 이를 내보내고 삭제하는 기능을 제공합니다. GDPR에 따라 사적인 것으로 간주할 수 있는 시스템 생성 로그의 예는 다음과 같습니다.
* 사용자 활동 로그와 같은 제품 및 서비스 사용 데이터
* 사용자 검색 요청 및 쿼리 데이터
* 사용자 또는 다른 시스템의 시스템 기능 및 상호 작용의 산물로 제품 및 서비스에서 생성되는 데이터

시스템 생성 로그의 데이터를 제한하거나 수정하는 기능은 지원되지 않습니다. 시스템 생성 로그의 데이터는 Microsoft 클라우드 내에서 수행된 실제 작업을 구성하고 &mdash;해당 데이터의 수정 사항이 포함&mdash;된 진단 데이터는 작업의 기록 레코드를 손상하고 사기 및 보안 위험을 증가시킵니다.

## <a name="accessing-and-exporting-system-generated-logs"></a>시스템 생성 로그 액세스 및 내보내기
관리자는 사용자의 PowerApps, Microsoft Flow 및 앱용 CDS(Common Data Service) 서비스/응용 프로그램 사용에 관련된 시스템 생성 로그에 액세스할 수 있습니다.

시스템 생성 로그에 액세스하고 이를 내보내려면 다음을 수행합니다.

1. [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/)로 이동하고 Office 365 전역 관리자의 자격 증명을 사용하여 로그인합니다.

2. 페이지 위쪽의 **개인 정보** 드롭다운 목록에서 **Data Subject Request**를 선택합니다.

3. **Data Subject Request** 페이지의 **시스템 생성 로그** 아래에서 **데이터 로그 내보내기**를 선택합니다. 데이터 로그 내보내기에 조직에서 제출한 데이터 내보내기 요청 목록이 표시됩니다.

4. 사용자에 대한 새 요청을 만들려면 **데이터 내보내기 요청 만들기**를 클릭합니다.

    새 요청을 만든 후에는 상태를 추적할 수 있는 **데이터 로그 내보내기** 페이지에 해당 요청이 나열됩니다. 요청이 완료된 후에는 링크를 클릭하여 시스템 생성 로그에 액세스할 수 있고, 이 로그는 요청을 만든 후 30일 이내에 조직의 Azure Storage 위치로 내보냅니다. 데이터는 일반적이고 컴퓨터에서 읽을 수 있는 파일 형식(예: XML, CSV 또는 JSON)으로 저장됩니다. Azure 계정 및 Azure Storage 위치가 없는 경우 데이터 로그 내보내기 도구가 시스템 생성 로그를 내보낼 수 있도록 조직에 대한 Azure 계정 및/또는 Azure Storage 위치를 만들어야 합니다. 자세한 내용은 [Azure Storage 소개](https://docs.microsoft.com/azure/storage/common/storage-introduction)를 참조하세요.

다음 표에서는 시스템 생성 로그에 액세스하고 이를 내보내는 방법을 요약합니다.

| 질문 | 답변 |
| --- | --- |
| Microsoft 데이터 로그 내보내기 도구가 요청을 완료하는 데 걸리는 시간은 얼마나 되나요? |    이는 여러 요인에 따라 결정됩니다. 대부분의 경우 1~2일 이내에 완료되어야 하지만 최대 30일이 소요될 수 있습니다.
| 어떤 형식으로 출력되나요? | 출력은 구조화된 컴퓨터에서 읽을 수 있는 파일 형식(예: XML, CSV 또는 JSON)입니다.
| 시스템 생성 로그에 대한 액세스 요청을 제출할 수 있는 데이터 로그 내보내기 도구에 대한 액세스 권한은 누구에게 있나요? | Office 365 전역 관리자는 GDPR 로그 관리자 도구에 액세스할 수 있습니다.
| 데이터 로그 내보내기 도구가 반환하는 데이터는 무엇인가요? | 데이터 로그 내보내기 도구는 Microsoft에서 저장하는 시스템 생성 로그를 반환합니다. 내보낸 데이터는 Office 365, Azure, Dynamics, PowerApps, Microsoft Flow 및 앱용 CDS를 포함한 다양한 Microsoft 서비스에 걸쳐 있습니다.
| 사용자에게 데이터가 어떻게 반환되나요? |   데이터는 조직의 Azure Storage 위치로 내보내지며, 조직 내의 관리자가 이 데이터를 사용자에게 표시/반환하는 방법을 결정해야 합니다.
| 시스템 생성 로그의 데이터는 어떻게 표시되나요? |  JSON 형식 시스템 생성 로그 레코드의 예: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  보안 및 감사 목적으로 일부 기능에서는 개인 정보의 무결성을 유지 관리하기 위해 시스템 생성 로그를 내보내거나 삭제할 수 없습니다.
>
>

## <a name="deleting-system-generated-logs"></a>시스템 생성 로그 삭제
액세스 요청을 통해 검색된 시스템 생성 로그를 삭제하려면 서비스에서 사용자를 제거하고 해당 Azure Active Directory 계정을 영구적으로 삭제해야 합니다. 사용자를 영구적으로 삭제하는 방법에 대한 자세한 내용은 [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)에서 찾을 수 있는 ‘Azure Data Subject Request GDPR 문서’의 **사용자 삭제** 섹션을 참조하세요. 사용자 계정을 영구적으로 삭제하는 작업은 일단 시작하면 되돌릴 수 없다는 점에 유의해야 합니다.

사용자 계정을 영구적으로 삭제하면 30일 이내에 PowerApps, Microsoft Flow 및 앱용 CDS에 대한 시스템 생성 로그에서 사용자 데이터가 제거됩니다.