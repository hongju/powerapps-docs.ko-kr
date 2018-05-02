---
title: 고객 작성 데이터에 대한 DSR 가이드 | Microsoft Docs
description: 고객 작성 데이터에 대한 PowerApps DSR 가이드
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: paulliew
ms.openlocfilehash: cff822e24f1384833caa0baa945a7d3d07a8ee9b
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-customer-data-in-common-data-service-for-apps"></a>앱용 Common Data Service의 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답

## <a name="introduction-to-dsr-requests"></a>DSR 요청 소개
EU GDPR(일반 데이터 보호 규정) 준수 과정을 지원하기 위한 노력의 일환으로 Microsoft는 준비를 돕기 위해 이 설명서를 개발했습니다. 이 설명서에서는 GDPR에 대비하기 위해 수행할 작업을 설명하고, PowerApps, Microsoft Flow 및 앱용 CDS(Common Data Service)를 사용할 때 GDPR 준수를 지원하기 위해 지금 Microsoft와 함께 수행할 수 있는 단계의 예제를 공유합니다.

GDPR은 사람들(규정에서 데이터 주체)에게 고용주 또는 다른 유형의 기관이나 조직(데이터 컨트롤러 또는 간단하게 컨트롤러)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다. GDPR에서 개인 데이터는 식별되거나 식별 가능한 자연인에 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 제공합니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 개인 데이터에 대한 수정을 요청하거나, 개인 데이터의 처리를 제한하거나, 개인 데이터를 삭제하거나, 다른 관리자에게 이동할 수 있도록 전자 형식으로 개인 데이터를 수신할 권한이 포함됩니다. 데이터 주체가 개인 데이터에 대한 작업을 수행하도록 관리자에게 공식적으로 요청하는 것을 DSR(Data Subject Rights) 요청이라고 합니다.

이 가이드에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 관리자 고객이 개인 데이터를 찾고 이에 대한 조치를 취하여 DSR 요청에 응답하는 방법을 설명합니다. 특히 여기에는 Microsoft 클라우드에 있는 개인 데이터를 찾고, 액세스하고, 조치를 위하는 방법이 포함됩니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.

1. **검색** - 검색 및 검색 도구를 사용하여 DSR 요청의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다. 잠재적으로 반응형 문서가 수집되면 다음 단계에 설명된 하나 이상의 DSR 작업을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR 요청에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다.

2. **액세스** - Microsoft 클라우드에 있는 개인 데이터를 검색하고 요청된 경우 데이터 주체에게 제공할 수 있는 복사본을 만듭니다.

3. **수정** - 개인 데이터를 변경하고 개인 데이터에 대한 다른 요청된 작업을 구현합니다(해당하는 경우).

4. **제한** - 다양한 온라인 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.

5. **삭제** - Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.

6. **내보내기** - 개인 데이터의 전자 복사본(컴퓨터에서 읽을 수 있는 형식으로)을 데이터 주체에게 제공합니다.

이 가이드의 각 섹션에서는 데이터 컨트롤러 조직이 Microsoft 클라우드의 개인 데이터에 대한 DSR 요청에 응답하기 위해 수행할 수 있는 기술적인 절차를 설명합니다.

## <a name="common-data-service-customer-data"></a>Common Data Service 고객 데이터

> [!IMPORTANT]
> 앱용 Common Data Service 및 Common Data Service(이전 버전)에 모두 적용됨

앱용 CDS(Common Data Service) 및 CDS 이전 버전이라는 두 가지 CDS가 있으며 각 CDS의 개인 데이터 프로세스는 서로 다릅니다.

[PowerApps 사이트](https://web.powerapps.com)에서 다음 단계에 따라 CDS 환경 유형을 확인할 수 있습니다.

1.  [환경] 드롭다운 목록에서 **환경**을 선택합니다.
2.  **데이터** > **엔터티**로 이동합니다.

    다음 엔터티가 표시되는 경우 환경은 앱용 CDS입니다.

    ![PowerApps 엔터티 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    다음 엔터티가 표시되는 경우 환경은 CDS 이전 버전입니다.

    ![PowerApps 레거시 엔터티 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

사용 중인 CDS 환경 유형을 확인한 후 이 문서의 해당 섹션에 따라 개인 데이터를 식별할 수 있습니다.

> [!NOTE]
> 일부 환경은 앱용 CDS에 있고 다른 환경은 CDS(이전 버전)에 있을 수 있으므로 조직의 각 환경에 대해 아래 설명된 프로세스를 반복해야 합니다.

## <a name="user-personal-data-in-common-data-service-for-apps"></a>앱용 Common Data Service의 사용자 개인 데이터

### <a name="prerequisites"></a>필수 조건
사용자는 Office 365 관리 센터에서 만들어지고 CDS에 액세스하기 위해 해당하는 Common Data Service 사용자 라이선스가 할당되어 있어야 합니다.  사용자가 Common Data Service를 사용하여 시작하려면 먼저 보안 역할도 필요합니다.

사용자 개인 데이터는 Office 365 관리 센터 및 CDS 시스템 사용자 엔터티에 보관됩니다.  Office 365 관리 센터에서 보관 및 유지 관리되는 특정 표준 사용자 개인 데이터 집합이 있습니다(예: 사용자 이름, 사용자 ID, 전화, 메일 및 주소). 이 사용자 개인 데이터 집합은 모든 환경에서 CDS 시스템 사용자 엔터티와 동기화됩니다.  시스템 관리자는 Office 365 관리 센터에서 이 개인 데이터 집합만 업데이트할 수 있고 이러한 특성은 자동으로 앱용 CDS에 동기화됩니다. 시스템 관리자는 사용자 지정 특성을 만들어 CDS 시스템 사용자 엔터티 내에서 추가적인 사용자 개인 데이터를 캡처할 수도 있습니다.  이러한 사용자 지정 특성은 시스템 관리자가 CDS 내에서 수동으로 유지 관리 및 관리합니다.

Office 365 관리 센터에서 사용자가 삭제될 경우 사용자 레코드는 조직 운영에 중요할 수 있는 비즈니스 응용 프로그램의 중단을 방지하기 위해 CDS 시스템 사용자 엔터티에서 자동으로 제거되지 않습니다.  CDS 시스템 관리자가 응용 프로그램을 사용하여 CDS에서 사용자 개인 데이터를 찾아 제거해야 합니다.

Office 365 전역 관리자 역할 및 CDS 시스템 관리자 보안 역할이 있는 사용자만 아래에 나열된 검색, 수정, 내보내기 및 삭제 작업을 수행할 수 있습니다.

### <a name="discover"></a>검색

시스템 관리자는 여러 CDS 인스턴스를 만들 수 있습니다.  이러한 인스턴스는 평가판, 개발 또는 프로덕션용으로 사용할 수 있습니다.   이러한 각 인스턴스에는 시스템 관리자가 추가했을 수 있는 사용자 지정 특성이 포함된 시스템 사용자 엔터티의 복사본과 Office 365 관리 센터에서 동기화된 사용자 개인 데이터가 있습니다.

시스템 관리자는 PowerApps 관리 센터에서 Dynamics 365 관리 센터로 이동하여 모든 CDS 인스턴스의 목록을 찾을 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서:

1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.

    ![PowerApps 환경 세부 정보](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    모든 인스턴스의 목록이 표시됩니다.

    ![PowerApps 인스턴스 선택기](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

CDS 사용자의 개인 데이터를 다음에서 찾을 수 있습니다.

|개인 데이터를 포함하는 리소스 | 용도 | 웹 사이트 액세스 | 프로그래밍 방식 액세스
| --- | --- | --- | ---
| 엔터티 레코드 | 시스템 사용자 엔터티 | [PowerApps 관리 센터](https://admin.powerapps.com) | [Web API를 통해](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)
| 감사 기록 | 사용자가 엔터티 수준에서 만들거나, 액세스하거나, 변경하거나, 삭제한 리소스를 고객이 식별하도록 허용합니다. | [PowerApps 관리 센터](https://admin.powerapps.com) | [Web API를 통해](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)

#### <a name="user"></a>User
Office 365 관리 센터에서 유지 관리 및 관리되는 사용자 개인 데이터는 Azure Active Directory에 저장됩니다.  이 개인 데이터는 Office 365 관리 센터에서 관리되고 모든 CDS 환경에 자동으로 동기화됩니다.  사용자가 활성 상태인 동안 시스템 관리자는 CDS에서 직접 이 개인 데이터를 업데이트할 수 없습니다. 이 개인 데이터는 Office 365 관리 센터 내에서 직접 업데이트해야 합니다.  추가 개인 데이터(예: 사용자 지정 특성)는 CDS에 직접 추가할 수 있고 시스템 관리자가 수동으로 유지 관리 및 관리해야 합니다.

CDS 시스템 관리자는 다음 단계를 수행하여 사용자를 찾고 특정 사용자와 연결된 개인 데이터를 찾을 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서:

1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.
4.  환경 이름을 클릭합니다.
5.  **열기** 단추를 클릭합니다.
6.  **설정** > **보안**으로 이동합니다.
7.  **사용자**를 클릭합니다.
8.  **검색** 입력 상자에 사용자를 입력합니다.
9.  **검색** 단추를 클릭합니다.
10. 사용자를 두 번 클릭합니다.

    ![PowerApps 사용자 양식](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>감사 기록
Common Data Service의 엔터티에 대한 [감사 추적이 사용하도록 설정](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity)된 경우 사용자 개인 데이터는 사용자가 수행 중인 이벤트와 함께 감사 기록에 기록됩니다.

### <a name="rectify"></a>수정

데이터 주체가 조직 데이터에 있는 개인 데이터를 수정하도록 요청한 경우 본인과 조직은 요청을 수용하는 것이 적절한지 여부를 결정해야 합니다.  데이터 수정에는 문서 또는 다른 유형이나 항목에서 개인 데이터를 편집, 수정 또는 제거하는 등의 작업 수행이 포함될 수 있습니다.

Azure Active Directory를 사용하여 앱용 Common Data Service에서 최종 사용자의 ID(개인 데이터)를 관리할 수 있습니다. 엔터프라이즈 고객은 제공된 Microsoft 서비스의 특성에 따른 제한된 편집 기능을 포함하여 DSR 수정 요청을 관리하는 기능을 사용할 수 있습니다.  Microsoft는 데이터 프로세서로서 시스템에서 생성된 로그가 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트 기록 레코드를 구성하기 때문에 이 로그를 수정하는 기능을 제공하지 않습니다. 자세한 내용은 [GDPR: Data Subject Requests (DSRs)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)(GDPR: DSR(Data Subject Requests))를 참조하세요.

사용자 레코드가 Azure Active Directory에서 삭제되면 시스템 관리자는 모든 인스턴스에서 나머지 사용자 개인 데이터(예: 추가했을 수 있는 사용자 지정 특성)를 제거할 수 있습니다.  

### <a name="export"></a>내보내기

#### <a name="system-user"></a>시스템 사용자
시스템 사용자 엔터티에 저장된 사용자 개인 데이터를 포털의 사용자 목록에서 Excel로 내보낼 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서:

1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.
4.  환경 이름을 클릭합니다.
5.  [열기] 단추를 클릭합니다. [설정] > [보안]으로 이동합니다.
6.  [사용할 수 있는 사용자] 보기를 선택합니다.
7.  [Excel로 내보내기] 단추를 클릭합니다.

#### <a name="audit-history"></a>감사 기록
아래에 설명된 단계를 수행하여 응용 프로그램에서 감사 기록의 스크린샷을 캡처 및 복사할 수 있습니다.
[PowerApps 관리 센터](https://admin.powerapps.com/)에서,
1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.
4.  환경 이름을 클릭합니다.
5.  [열기] 단추를 클릭합니다.
6.  [설정] > [감사]로 이동합니다.

    ![PowerApps 감사 기록 메뉴](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

7.  [감사 요약] 보기를 클릭합니다.
8.  사용자 감사 레코드를 찾습니다.

    ![PowerApps 감사 기록 세부 정보](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

9.  Alt+PrtScn을 눌러 스크린샷을 캡처합니다.
10. 스크린샷을 파일로 저장합니다.
11. 그런 다음, 파일을 DSR 요청자에게 보낼 수 있습니다.

### <a name="delete"></a>삭제

#### <a name="user"></a>User
사용자가 Office 365 관리 센터에서 삭제되면 사용자의 상태는 CDS에서 사용 안 함으로 설정되지만, 사용자 개인 데이터는 조직 운영에 중요할 수 있는 응용 프로그램의 중단을 방지하기 위해 자동으로 삭제되지 않습니다.
CDS에서 사용자 개인 데이터를 삭제하려면 시스템 관리자가 사용할 수 없는 사용자의 개인 데이터를 수동으로 제거해야 합니다.

#### <a name="remove-user-personal-data-via-user-form"></a>사용자 양식을 통해 사용자 개인 데이터 제거
Azure Active Directory에서 사용자 레코드를 삭제하면 사용자 양식에 다음 메시지가 표시됩니다.
이 사용자의 정보는 더 이상 Office 365에서 관리되지 않습니다. 이 사용자와 연결된 모든 개인 데이터를 제거하거나 바꿔서 DSR 요청에 응답하도록 이 레코드를 업데이트할 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서,
1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.
4.  환경 이름을 클릭합니다.
5.  **열기** 단추를 클릭합니다.
6.  **설정** > **보안** > **사용자**를 클릭합니다.
7.  **사용할 수 없는 사용자** 보기를 선택합니다.
8.  **레코드 검색**에 사용자 이름을 입력하고 **검색** 단추를 클릭합니다.
9.  검색 결과에서 사용자 이름을 두 번 클릭합니다.
10. 모든 개인 데이터를 제거하고 **저장**을 클릭합니다.

#### <a name="remove-user-personal-data-via-excel-importexport"></a>Excel 가져오기/내보내기를 통해 사용자 개인 데이터 제거
1.  **설정** > **보안** > **사용자**를 클릭합니다.
2.  **사용할 수 없는 사용자** 보기를 선택합니다.
3.  업데이트할 모든 사용자 개인 데이터 열이 포함된 Excel 서식 파일을 만듭니다.
4.  **파일 다운로드**를 클릭합니다.
5.  다운로드한 Excel 파일을 열고 업데이트한 다음 파일을 저장합니다.
6.  [사용할 수 없는 사용자] 보기 창으로 돌아가서 [데이터 가져오기]를 클릭합니다.
7.  [데이터 파일 업로드] 대화 상자에서 업데이트된 Excel을 선택합니다.
8.  [필드 매핑] 창에서 필요한 내용을 모두 변경합니다.
9.  [다음] 및 [제출]을 클릭합니다.

Excel 서식 파일 사용에 대한 자세한 내용은 [추가 Excel 정보](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates)를 참조하세요.


#### <a name="remove-audit-history-via-the-audit-summary-view-form"></a>감사 요약 보기 양식을 통해 감사 기록 제거

[PowerApps 관리 센터](https://admin.powerapps.com/)에서,
1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.
4.  환경 이름을 클릭합니다.
5.  [열기] 단추를 클릭합니다.
6.  [설정] > [감사]를 클릭합니다.
7.  [감사 요약] 보기를 선택합니다.
8.  사용자가 수행한 변경 내용 찾기
9.  행에서 확인란을 클릭합니다.
10. [변경 내용 삭제] 아이콘을 클릭합니다.

## <a name="personal-data-stored-in-common-data-service-for-apps-databases"></a>앱용 Common Data Service 데이터베이스에 저장된 개인 데이터

### <a name="prerequisites"></a>필수 조건
개인(예: 관리 중인 고객)의 개인 데이터를 CDS 엔터티의 콘텐츠에 저장하고 있을 수 있습니다.  

개인이 조직에 DSR 요청을 제출하면 CDS 시스템 관리자는 응용 프로그램 내에서 해당 개인이 참조될 수 있는 모든 엔터티를 찾아야 합니다.  CDS 관리자는 개인의 DSR 요청에 응답할 수 있도록 사용 중인 다양한 엔터티 내에 개인 데이터가 저장된 위치의 인벤토리를 유지 관리해야 합니다.

콘텐츠 내의 개인 데이터는 제품 내 기능을 사용하여 엔터티에서 내보내거나, 수정하거나, 삭제할 수 있습니다.  

### <a name="discover"></a>검색
CDS 관리자가 개인으로부터 DSR 요청을 받으면 해당 관리자는 이 개인의 개인 데이터가 포함된 환경/CDS 인스턴스를 식별해야 합니다.  콘텐츠 내에 저장한 개인 데이터를 식별하는 데 도움이 되도록 개인의 개인 데이터를 저장하도록 결정한 환경, 인스턴스 및 엔터티의 인벤토리를 유지 관리하기 위한 정책과 절차를 개발해야 합니다.

개인 데이터가 저장되는 환경, 인스턴스, 엔터티 및 필드의 인벤토리를 사용하여 개인 데이터를 검색하도록 CDS 검색 엔진을 구성할 수 있습니다.  CDS 관리자는 검색 엔터티 및 필드를 구성할 수 있습니다. 자세한 내용은 [관련성 검색 구성](https://go.microsoft.com/fwlink/?linkid=872506)을 참조하세요.
그러면 CDS 관리자가 CDS 환경에 액세스하여 검색을 수행할 수 있습니다.

1.  **검색** 아이콘을 클릭합니다.
2.  **관련성 검색**을 선택합니다.

    ![PowerApps 관련성 검색 메뉴](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3.  [검색] 상자에 개인의 개인 데이터를 입력합니다.
4.  [검색] 단추를 클릭합니다.

    ![PowerApps 관련성 검색 결과](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

콘텐츠의 개인 데이터는 일반적으로 주요 엔터티(예: 계정, 연락처, 잠재 고객, 기회 등)에 저장되지만 개인의 개인 데이터를 저장하는 위치의 인벤토리를 유지 관리하는 것은 본인의 책임입니다.

### <a name="rectify"></a>수정
CDS 시스템 관리자는 관련성 검색의 결과 목록을 사용하여 개인의 개인 데이터를 업데이트할 수 있습니다.  그러나 이 개인의 개인 데이터를 다른 사용자 지정 엔터티에도 저장했을 수 있습니다.  CDS 시스템 관리자는 이러한 다른 사용자 지정 엔터티의 인벤토리를 유지 관리하고 개인의 개인 데이터를 적절하게 업데이트해야 합니다.

관련성 검색 결과에서:

1.  개별 개인 데이터가 발견된 항목을 클릭합니다.
2.  해당하는 경우 개별 개인 데이터를 업데이트합니다.
3.  [저장]을 클릭합니다.

    ![PowerApps 계정 세부 정보](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>내보내기
아래에 설명된 단계를 수행하여 데이터의 스크린샷을 캡처하고 DSR 요청자와 공유할 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서,
1.  [환경] 탭으로 이동합니다.
2.  환경 목록에서 환경을 선택합니다.
3.  Dynamics 365 관리 센터 링크를 클릭합니다.
4.  환경 이름을 클릭합니다.
5.  **검색** 아이콘을 클릭합니다.
6.  [관련성 검색]을 선택합니다.
7.  [검색] 상자에 개인의 개인 데이터를 입력합니다.
8.  [검색] 단추를 클릭합니다.
9.  항목을 찾아 두 번 클릭합니다.
10. <alt>+<PrtScn>을 눌러 스크린샷을 캡처합니다.
11. 스크린샷을 파일로 저장합니다.
12. 그런 다음, 파일을 DSR 요청자에게 보낼 수 있습니다.

### <a name="delete"></a>삭제

CDS 관리자는 해당 데이터가 저장된 레코드에서 개인의 개인 데이터를 삭제할 수 있습니다.  CDS 관리자는 (1) 개인 데이터가 저장된 레코드를 삭제하거나 (2) 레코드에서 개인 데이터의 콘텐츠를 제거하도록 선택할 수 있습니다.  

> [!NOTE]
> CDS 관리자는 환경을 사용자 지정하여 레코드가 엔터티에서 삭제되지 않도록 할 수 있습니다. 이 방법으로 구성된 경우에는 레코드 자체를 삭제하지 않고 레코드에서 개인 데이터의 콘텐츠를 제거해야 합니다.

관련성 검색 결과에서,
1.  개별 개인 데이터가 발견된 항목을 클릭합니다.
2.  리본에서 [삭제] 아이콘을 클릭합니다(참고: 레코드를 삭제할 수 없는 경우 이 아이콘을 사용할 수 없음).

    ![PowerApps 계정 삭제](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-common-data-service-previous-version-databases"></a>Common Data Service(이전 버전) 데이터베이스에 저장된 개인 데이터

### <a name="prerequisites"></a>필수 조건

개인(예: 관리 중인 고객 또는 사용자)의 개인 데이터를 CDS 엔터티의 콘텐츠에 저장하고 있을 수 있습니다.  

개인이 조직에 DSR 요청을 제출하면 CDS 시스템 관리자는 응용 프로그램 내에서 해당 개인이 참조될 수 있는 모든 엔터티를 찾아야 합니다.  CDS 관리자는 개인의 DSR 요청에 응답할 수 있도록 사용 중인 다양한 엔터티 내에 개인 데이터가 저장된 위치의 인벤토리를 유지 관리해야 합니다.

콘텐츠 내의 개인 데이터는 제품 내 기능을 사용하여 엔터티에서 내보내거나, 수정하거나, 삭제할 수 있습니다.  

### <a name="discover"></a>검색
CDS 관리자가 개인으로부터 DSR 요청을 받으면 해당 관리자는 이 개인의 개인 데이터가 포함된 환경/CDS 인스턴스를 식별해야 합니다.  콘텐츠 내에 저장한 개인 데이터를 식별하는 데 도움이 되도록 개인의 개인 데이터를 저장하도록 결정한 환경, 인스턴스 및 엔터티의 인벤토리를 유지 관리하기 위한 정책과 절차를 개발해야 합니다.

개인의 개인 데이터는 다음에서 찾을 수 있습니다.

|개인 데이터를 포함하는 리소스 | 용도 | 웹 사이트 액세스 |    프로그래밍 방식 액세스
| --- | --- | --- | ---
|엔터티 레코드 | 각 비즈니스 엔터티에서 비즈니스 트랜잭션을 캡처합니다. | PowerApps 작성자 포털 |    아니요

#### <a name="entity-records"></a>엔터티 레코드
개별 개인 데이터는 비즈니스 엔터티에 저장할 수 있습니다.
이 버전의 Common Data Service에는 고유한 데이터베이스 스키마 및 인프라가 포함됩니다.  여기에는 고유한 엔터티가 있고 이러한 엔터티의 관리는 [PowerApps 사이트](http://web.powerapps.com/)를 사용하여 관리됩니다.

엔터티 목록을 보려면:

1.  환경을 선택합니다.

    ![PowerApps 레거시 엔터티](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2.  **데이터** > **엔터티** 탭으로 이동합니다.
3.  엔터티(예: 계정 엔터티)를 선택합니다.

    ![PowerApps 레거시 엔터티 세부 정보 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4.  엔터티를 클릭합니다.
5.  **데이터** 탭을 클릭합니다. 엔터티의 레코드 목록이 표시됩니다.

    ![PowerApps 레거시 계정 데이터](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

6.  **데이터 내보내기** 아이콘을 클릭합니다.
7.  내보내기가 완료되면 Excel 워크시트를 엽니다.
8.  [편집 사용] 상자를 클릭합니다.
9.  [찾기 및 검색] 아이콘을 클릭합니다.
10. 검색할 개인 정보를 입력합니다.
콘텐츠의 개인 데이터는 일반적으로 주요 엔터티(예: 계정, 연락처, 잠재 고객, 기회, 작업자 등)에 저장되지만 개인의 개인 데이터를 저장하는 위치의 인벤토리를 유지 관리하는 것은 본인의 책임입니다.
11. 개인 데이터가 저장된 엔터티의 인벤토리 목록을 사용하여 **각 비즈니스 엔터티에 대해 위 단계를 반복하여 개별 개인 데이터를 검색**합니다.

### <a name="rectify"></a>수정
데이터 주체가 조직 데이터에 있는 개인 데이터를 수정하도록 요청한 경우 본인과 조직은 요청을 수용하는 것이 적절한지 여부를 결정해야 합니다.  데이터 수정에는 문서 또는 다른 유형이나 항목에서 개인 데이터를 편집, 수정 또는 제거하는 등의 작업 수행이 포함될 수 있습니다.

Azure Active Directory를 사용하여 앱용 Common Data Service에서 최종 사용자의 ID(개인 데이터)를 관리할 수 있습니다. 엔터프라이즈 고객은 제공된 Microsoft 서비스의 특성에 따른 제한된 편집 기능을 포함하여 DSR 수정 요청을 관리하는 기능을 사용할 수 있습니다.  Microsoft는 데이터 프로세서로서 시스템에서 생성된 로그가 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트 기록 레코드를 구성하기 때문에 이 로그를 수정하는 기능을 제공하지 않습니다.  

자세한 내용은 [GDPR: Data Subject Requests (DSRs)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)(GDPR: DSR(Data Subject Requests))를 참조하세요.

CDS 환경에 있는 개인 데이터를 수정하려면 엔터티 데이터를 Excel 워크시트로 내보내고, 업데이트한 다음, 업데이트를 다시 데이터베이스로 가져오면 됩니다.
CDS 관리자는 개별 개인 데이터가 저장된 모든 엔터티를 식별하고 이러한 각 엔터티에 대해 아래 단계를 반복해야 합니다.

[PowerApps 사이트에서](http://web.powerapps.com/):

1.  **데이터** > **엔터티**를 클릭합니다.
2.  엔터티를 클릭합니다(예: 계정).
3.  **데이터** 옵션을 클릭합니다.
4.  **데이터 내보내기** 아이콘을 클릭합니다.
5.  **Excel에서 열기** 아이콘을 클릭합니다(내보내기가 완료된 경우).
6.  Excel 워크시트에서 **편집을 사용하도록 설정**하고 개인 데이터를 업데이트합니다.
7.  업데이트된 워크시트를 **저장**합니다(파일의 위치를 알 수 있도록 **다른 이름으로 저장** 수행).

    ![PowerApps 레거시 계정 데이터](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

8.  필요한 개인 데이터 업데이트
9.  업데이트 저장
10. [데이터] > [엔터티] > [계정] 양식에서 [데이터 가져오기] 아이콘을 클릭합니다.
11. [검색] 상자를 클릭합니다.
12. 업데이트가 포함된 파일을 선택합니다.
13. [열기] 상자를 클릭합니다.
14. [가져오기] 단추를 클릭합니다.

### <a name="export"></a>내보내기

각 엔터티의 개인 데이터를 보고 Excel 워크시트로 내보낼 수 있습니다.

[PowerApps 사이트에서](http://web.powerapps.com/):

1.  **데이터** > **엔터티**로 이동합니다.
2.  원하는 **엔터티**를 선택하여 데이터를 보고 내보냅니다.
3.  **데이터** 옵션을 클릭합니다.
4.  **데이터 내보내기** 아이콘을 클릭합니다. 이 내보내기 작업은 백그라운드에서 실행되고 완료되면 알림이 표시됩니다.
5. 내보낸 데이터를 보려면 [Excel에서 열기] 아이콘을 클릭합니다.

### <a name="delete"></a>삭제
데이터 내보내기/가져오기 기능을 사용하여 엔터티에 저장된 개인 데이터를 삭제할 수 있습니다.

CDS 관리자는 개별 개인 데이터가 포함된 모든 엔터티를 식별하고 각 엔터티에 대해 다음 단계를 반복해야 합니다.

[PowerApps 사이트에서](http://web.powerapps.com/):

1.  **데이터** > **엔터티**를 클릭합니다.
2.  **엔터티** 목록을 아래로 스크롤하여 원하는 엔터티를 찾아서 개인 데이터를 제거합니다.
3.  엔터티를 클릭합니다.
4.  **데이터** 옵션을 클릭합니다.
5.  **데이터 내보내기** 아이콘을 클릭합니다.
6.  **Excel에서 열기** 아이콘을 클릭합니다(내보내기가 완료된 경우).
7.  Excel 워크시트에서 **편집을 사용하도록 설정**합니다.
8.  업데이트된 워크시트를 **저장**합니다(파일의 위치를 알 수 있도록 [다른 이름으로 저장] 수행).
9.  제거할 개인 데이터 레코드의 행을 삭제합니다.
10. 업데이트 저장
11. **엔터티** 양식에서 **데이터 가져오기** 아이콘을 클릭합니다.
12. **검색** 상자를 클릭합니다.
13. 업데이트가 포함된 파일을 선택합니다.
14. **열기** 상자를 클릭합니다.
15. [가져오기] 단추를 클릭합니다.
