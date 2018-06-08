---
title: 앱용 CDS(Common Data Service) 고객 데이터에 대한 DSR 요청에 응답 | Microsoft Docs
description: 앱용 CDS(Common Data Service) 고객 데이터에 대한 DSR 요청에 응답하는 방법 연습
author: jamesol-msft
ms.reviewer: paulliew
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: ef5d646e30f5d09dbfe5f111a3ad018b030f79d9
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168231"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-common-data-service-for-apps-customer-data"></a>앱용 Common Data Service 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답

## <a name="introduction-to-dsr-requests"></a>DSR 요청 소개
EU(유럽 연합) GDPR(일반 데이터 보호 규정)은 사람들(규정에서 ‘데이터 주체’)에게 고용주 또는 다른 유형의 기관이나 조직(‘데이터 컨트롤러’ 또는 간단하게 ‘컨트롤러’)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다. GDPR에서 개인 데이터는 식별되거나 식별 가능한 자연인에 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 개인 데이터와 관련된 다음 작업을 수행할 권한을 데이터 주체에게 제공합니다.

* 복사본 얻기
* 수정 요청
* 처리 제한
* 삭제
* 다른 컨트롤러에게 이동할 수 있도록 전자 형식으로 수신

데이터 주체가 개인 데이터에 대한 작업을 수행하도록 컨트롤러에게 공식적으로 요청하는 것을 DSR(Data Subject Rights) 요청이라고 합니다.

이 문서에서는 Microsoft에서 GDPR에 대비하는 방법을 설명하고, PowerApps, Microsoft Flow 및 앱용 CDS(Common Data Service)를 사용할 때 GDPR 준수를 지원하기 위해 수행할 수 있는 단계의 예제를 공유합니다. Microsoft 제품, 서비스 및 관리 도구를 사용하여 컨트롤러 고객이 DSR 요청에 대한 응답으로 Microsoft 클라우드에서 개인 데이터를 찾고 액세스하여 이에 대한 조치를 취하는 방법을 알아봅니다.

이 문서에서는 다음 작업을 설명합니다.

* **검색** - 검색 및 검색 도구를 사용하여 DSR 요청의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다. 잠재적으로 반응형 문서가 수집되면 다음 DSR 작업을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR 요청에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다.

* **액세스** - Microsoft 클라우드에 있는 개인 데이터를 검색하고 요청된 경우 데이터 주체에게 제공할 수 있는 데이터 복사본을 만듭니다.

* **수정** - 개인 데이터를 변경하고 개인 데이터에 대한 다른 요청된 작업을 구현합니다(해당하는 경우).

* **제한** - 다양한 온라인 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.

* **삭제** - Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.

* **내보내기** - 개인 데이터의 전자 복사본(컴퓨터에서 읽을 수 있는 형식으로)을 데이터 주체에게 제공합니다.

## <a name="cds-for-apps-customer-data"></a>앱용 CDS 고객 데이터

> [!IMPORTANT]
> 앱용 CDS 및 이전 버전의 Common Data Service에 모두 적용됨

앱용 CDS 및 이전 버전의 CDS(Common Data Service)에는 개인 데이터를 조작하기 위한 개별 프로세스가 포함됩니다.

[PowerApps](https://web.powerapps.com)에 로그인하고 다음 단계에 따라 CDS 환경 유형을 확인할 수 있습니다.

1. **환경** 드롭다운 목록에서 환경을 선택합니다.
2. 탐색 창에서 **데이터**를 클릭하거나 탭한 다음, **엔터티**를 클릭하거나 탭합니다.

    다음 엔터티가 나열되는 경우 사용 중인 환경은 앱용 CDS입니다.

    ![PowerApps 엔터티 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    다음 엔터티가 나열되는 경우 사용 중인 환경은 이전 버전의 CDS입니다.

    ![PowerApps 레거시 엔터티 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

사용 중인 CDS 환경 유형을 확인한 후 다음 섹션의 단계에 따라 개인 데이터를 식별합니다.

> [!NOTE]
> 일부 환경은 앱용 CDS에 있고 다른 환경은 이전 버전의 CDS에 있을 수 있으므로 조직의 각 환경에 대해 아래 설명된 프로세스를 반복해야 합니다.

## <a name="user-personal-data-in-cds-for-apps"></a>앱용 CDS의 사용자 개인 데이터

### <a name="prerequisites"></a>필수 조건
Office 365 관리 센터에서 사용자를 만들고 사용자에게 적절한 사용자 라이선스 및 보안 역할을 할당한 후 사용자가 앱용 CDS에 액세스하고 이를 사용해야 합니다.

표준 사용자 개인 데이터(예: 사용자 이름, 사용자 ID, 전화, 메일 및 주소)는 Office 365 관리 센터에서 보관 및 유지 관리됩니다. 시스템 관리자는 Office 365 관리 센터에서 이 개인 데이터만 업데이트할 수 있고 데이터는 자동으로 앱용 CDS 시스템 사용자 엔터티에 동기화됩니다. 시스템 관리자는 사용자 지정 특성을 만들어 앱용 CDS 시스템 사용자 엔터티 내에서 추가적인 사용자 개인 데이터를 캡처한 다음, 이러한 특성을 수동으로 유지 관리 및 관리할 수도 있습니다.

조직 운영에 중요할 수 있는 비즈니스 응용 프로그램의 중단을 방지하기 위해, Office 365 관리 센터 내에서 사용자가 삭제될 경우 해당 사용자의 레코드는 앱용 CDS 시스템 사용자 엔터티에서 자동으로 제거되지 않습니다. 사용자의 상태는 앱용 CDS에서 사용 안 함으로 설정되지만, 앱용 CDS 시스템 관리자는 응용 프로그램 내의 앱용 CDS에서 사용자의 개인 데이터를 찾아서 제거해야 합니다.

Office 365 전역 관리자 및 CDS 시스템 관리자만 아래에 나열된 검색, 수정, 내보내기 및 삭제 작업을 수행할 수 있습니다.

### <a name="discover"></a>검색
시스템 관리자는 여러 앱용 CDS 인스턴스를 만들 수 있습니다. 이러한 인스턴스는 평가판, 개발 또는 프로덕션용으로 사용할 수 있습니다. 이러한 각 인스턴스에는 시스템 관리자가 추가했을 수 있는 사용자 지정 특성이 포함된 시스템 사용자 엔터티의 복사본과 Office 365 관리 센터에서 동기화된 사용자 개인 데이터가 있습니다.

시스템 관리자는 PowerApps 관리 센터에서 Dynamics 365 관리 센터로 이동하여 모든 앱용 CDS 인스턴스의 목록을 찾을 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

3.  **Dynamics 365 관리 센터**를 클릭하거나 탭합니다.

    ![PowerApps 환경 세부 정보](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    모든 인스턴스 목록이 표시됩니다.

    ![PowerApps 인스턴스 선택기](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

다음 리소스 내에서 앱용 CDS 사용자의 개인 데이터를 찾을 수 있습니다.

|리소스 | 용도 | 웹 사이트 액세스 | 프로그래밍 방식 액세스
| --- | --- | --- | ---
| 엔터티 레코드 | 시스템 사용자 엔터티로 알려져 있으며, 사용자의 개인 데이터를 저장합니다. | [PowerApps 관리 센터](https://admin.powerapps.com) | [Web API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update) 사용
| 감사 기록 | 사용자가 엔터티 수준에서 만들거나, 액세스하거나, 변경하거나, 삭제한 리소스를 고객이 식별하도록 허용합니다. | [PowerApps 관리 센터](https://admin.powerapps.com) | [Web API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update) 사용

#### <a name="user"></a>User
사용자 개인 데이터는 Azure Active Directory에 저장되고 자동으로 모든 앱용 CDS 환경에 동기화됩니다. 사용자가 활성 상태인 동안 시스템 관리자는 앱용 CDS에서 직접 이 개인 데이터를 업데이트할 수 없습니다. Office 365 관리 센터 내에서 이 데이터를 업데이트해야 합니다. 시스템 관리자는 개인 데이터(예: 사용자 지정 특성)를 앱용 CDS에 직접 추가할 수 있지만 이 데이터를 수동으로 관리해야 합니다.

사용자 및 해당 개인 데이터를 찾으려면 [PowerApps 관리 센터](https://admin.powerapps.com/)로 이동하여 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택한 다음, **열기**를 클릭하거나 탭합니다.

3. **설정** > **보안** > **사용자**로 이동합니다.

4. **검색** 상자에 사용자 이름을 입력한 다음, **검색**을 클릭하거나 탭합니다.

5. 사용자의 개인 데이터를 보려면 사용자 이름을 두 번 클릭하거나 두 번 탭합니다.

    ![PowerApps 사용자 양식](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>감사 기록
앱용 CDS의 엔터티에 대한 [감사 추적](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity)이 사용하도록 설정된 경우 사용자 개인 데이터는 사용자가 수행하는 작업과 함께 감사 기록에 기록됩니다.

### <a name="rectify"></a>수정
데이터 주체가 조직 데이터에 있는 개인 데이터를 수정하도록 요청하는 경우 본인과 조직은 요청을 수용하는 것이 적절한지 여부를 결정해야 합니다. 데이터 수정에는 문서 또는 다른 유형이나 항목에서 개인 데이터를 편집, 수정 또는 제거하는 작업이 포함될 수 있습니다.

Azure Active Directory를 사용하여 앱용 CDS 내에서 사용자의 ID(개인 데이터)를 관리할 수 있습니다. 엔터프라이즈 고객은 지정된 Microsoft 서비스 내에서 제한된 편집 기능을 사용하여 DSR 수정 요청을 관리할 수 있습니다. Microsoft는 데이터 프로세서로서 시스템에서 생성된 로그가 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트 기록 레코드를 구성하기 때문에 이 로그를 수정하는 기능을 제공하지 않습니다. 자세한 내용은 [GDPR: DSR(데이터 주체 요청)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)을 참조하세요.

사용자 레코드가 Azure Active Directory에서 삭제되면 시스템 관리자는 모든 인스턴스에서 해당 사용자에 관련된 모든 나머지 개인 데이터(예: 사용자 지정 특성)를 제거할 수 있습니다.  

### <a name="export"></a>내보내기

#### <a name="system-user"></a>시스템 사용자
시스템 사용자 엔터티에 저장된 사용자 개인 데이터를 관리 센터 내의 사용자 목록에서 Excel로 내보낼 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택한 다음, **열기**를 클릭하거나 탭합니다.

3. **설정** > **보안**으로 이동한 다음, **사용할 수 있는 사용자 보기**를 선택합니다.

4. **Excel로 내보내기**를 클릭합니다.

#### <a name="audit-history"></a>감사 기록
관리 센터 내에서 감사 기록의 스크린샷을 만들 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택한 다음, **열기**를 클릭하거나 탭합니다.

3. **설정** > **감사**로 이동한 다음, **감사 요약 보기**를 선택합니다.

    ![PowerApps 감사 기록 메뉴](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

4. 사용자 감사 레코드를 찾은 다음, Alt+PrtScn을 눌러 스크린샷을 만듭니다.

    ![PowerApps 감사 기록 세부 정보](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

5. 스크린샷을 파일에 저장하면 DSR 요청자에게 보낼 수 있습니다.

### <a name="delete"></a>삭제

#### <a name="user"></a>User
조직 운영에 중요할 수 있는 비즈니스 응용 프로그램의 중단을 방지하기 위해, Office 365 관리 센터 내에서 사용자가 삭제될 경우 해당 사용자의 레코드는 앱용 CDS 시스템 사용자 엔터티에서 자동으로 제거되지 않습니다. 사용자의 상태는 앱용 CDS에서 사용 안 함으로 설정되지만, 앱용 CDS 시스템 관리자는 응용 프로그램 내의 앱용 CDS에서 사용자의 개인 데이터를 찾아서 제거해야 합니다.

#### <a name="remove-a-users-personal-data-from-the-users-summary-page"></a>사용자의 요약 페이지에서 사용자 개인 데이터 제거
Azure Active Directory에서 사용자 레코드를 삭제하면 사용자의 요약 페이지에 다음 메시지가 표시됩니다.

이 사용자의 정보는 더 이상 Office 365에서 관리되지 않습니다. 이 사용자와 연결된 모든 개인 데이터를 제거하거나 바꿔서 DSR 요청에 응답하도록 이 레코드를 업데이트할 수 있습니다.*

[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택한 다음, **열기**를 클릭하거나 탭합니다.

3. **설정** > **보안** > **사용자**로 이동한 다음, **사용할 수 없는 사용자 보기**를 선택합니다.

4. **검색** 상자에 사용자 이름을 입력한 다음, **검색**을 클릭하거나 탭합니다.

9. 검색 결과 목록에서 사용자 이름을 두 번 클릭합니다.

10. 사용자의 요약 페이지에서 모든 개인 데이터를 제거한 다음, **저장**을 클릭하거나 탭합니다.

#### <a name="remove-a-users-personal-data-by-using-excel"></a>Excel을 사용하여 사용자의 개인 데이터 제거
[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택한 다음, **열기**를 클릭하거나 탭합니다.

3. **설정** > **보안** > **사용자**로 이동한 다음, **사용할 수 없는 사용자 보기**를 선택합니다.

4. 사용자 개인 데이터에서 Excel 서식 파일을 만들고 다운로드합니다. 단계별 지침은 [새 Excel 서식 파일 만들기](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates#create-a-new-excel-template)를 참조하세요.

8. 다운로드한 Excel 서식 파일을 열고, 사용자 개인 데이터를 제거한 다음, 파일을 저장합니다.

9. **사용할 수 없는 사용자 보기** 페이지로 돌아가서 **데이터 가져오기**를 클릭하거나 탭합니다.

10. **데이터 파일 업로드** 대화 상자에서 Excel 서식 파일을 선택하고 **필드 매핑** 창에서 필요한 내용을 모두 변경합니다.

12. **다음**을 클릭하거나 탭한 후, **제출**을 클릭하거나 탭합니다.

#### <a name="remove-audit-history-from-the-audit-summary-view-page"></a>감사 요약 보기 페이지에서 감사 기록 제거
[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택한 다음, **열기**를 클릭하거나 탭합니다.

3. **설정** > **감사**로 이동한 다음, **감사 요약 보기**를 선택합니다.

4. 사용자의 변경 기록을 찾고, 행 옆의 확인란을 클릭하거나 탭한 다음, **변경 기록 삭제**를 클릭하거나 탭합니다.

## <a name="personal-data-stored-in-databases-of-cds-for-apps"></a>앱용 CDS 데이터베이스에 저장된 개인 데이터

### <a name="prerequisites"></a>필수 조건
개인(예: 관리 중인 고객)의 개인 데이터를 앱용 CDS 엔터티 내에 저장하고 있을 수 있습니다.  

CDS 시스템 관리자는 DSR 요청에 응답하여 해당 데이터를 찾을 수 있도록 사용 중인 각 개인의 다양한 엔터티 내에 개인 데이터가 저장된 위치의 인벤토리를 유지 관리해야 합니다.  

개인 데이터는 제품 내 기능을 사용하여 엔터티에서 내보내거나, 수정하거나, 삭제할 수 있습니다.  

### <a name="discover"></a>검색
CDS 시스템 관리자가 개인으로부터 DSR 요청을 받으면 해당 관리자는 이 개인의 개인 데이터가 포함된 환경/CDS 인스턴스를 식별해야 합니다. 개인 데이터는 일반적으로 주요 엔터티(예: 계정, 연락처, 잠재 고객, 기회 등)에 저장되지만, DSR 요청에 응답할 수 있도록 각 개인의 개인 데이터를 저장하는 위치의 인벤토리를 유지 관리하기 위한 정책과 절차를 개발하는 것은 본인의 책임입니다.

인벤토리를 사용하면 CDS 시스템 관리자는 검색 엔터티 및 필드를 구성한 다음, 앱용 CDS 환경에 액세스하여 개인 데이터를 검색할 수 있습니다. 자세한 내용은 [관련성 검색 구성](https://go.microsoft.com/fwlink/?linkid=872506)을 참조하세요.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택하고, [검색] 단추를 클릭하거나 탭한 다음, **관련성 검색**을 클릭하거나 탭합니다.

    ![PowerApps 관련성 검색 메뉴](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. 검색 상자에 해당 개인의 개인 데이터를 입력한 다음, **검색**을 클릭하거나 탭합니다.

    ![PowerApps 관련성 검색 결과](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

### <a name="rectify"></a>수정
CDS 시스템 관리자는 관련성 검색의 결과 목록을 사용하여 개인의 개인 데이터를 업데이트할 수 있습니다. 그러나 개인의 개인 데이터를 다른 사용자 지정 엔터티에 저장할 수도 있습니다. CDS 시스템 관리자는 이러한 다른 사용자 지정 엔터티의 인벤토리를 유지 관리하고 개인의 개인 데이터를 적절하게 업데이트해야 합니다.

관련성 검색 결과에서 다음을 수행합니다.

1. 개인의 개인 데이터를 포함하는 항목을 클릭하거나 탭합니다.

2. 해당하는 경우 개인의 개인 데이터를 업데이트한 다음, **저장**을 클릭하거나 탭합니다.

    ![PowerApps 계정 세부 정보](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>내보내기
데이터의 스크린샷을 만들고 DSR 요청자와 공유할 수 있습니다.

[PowerApps 관리 센터](https://admin.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **환경**을 클릭하거나 탭한 다음, 목록에서 환경을 선택합니다.

2. **Dynamics 365 관리 센터**를 클릭하거나 탭하고, 목록에서 환경을 선택하고, [검색] 단추를 클릭하거나 탭한 다음, **관련성 검색**을 클릭하거나 탭합니다.

    ![PowerApps 관련성 검색 메뉴](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. 검색 상자에 해당 개인의 개인 데이터를 입력한 다음, **검색**을 클릭하거나 탭합니다.

    ![PowerApps 관련성 검색 결과](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

4. 검색 결과 목록에서 항목을 두 번 클릭합니다.

5. Alt+PrtScn을 눌러 스크린샷을 만듭니다.

6. 스크린샷을 파일에 저장하면 DSR 요청자에게 보낼 수 있습니다.

### <a name="delete"></a>삭제
CDS 시스템 관리자는 해당 데이터가 저장된 레코드에서 개인의 개인 데이터를 삭제할 수 있습니다.  CDS 시스템 관리자는 개인 데이터가 저장된 레코드를 삭제하거나 레코드에서 개인 데이터의 콘텐츠를 제거하도록 선택할 수 있습니다.  

> [!NOTE]
> CDS 관리자는 환경을 사용자 지정하여 레코드가 엔터티에서 삭제되지 않도록 할 수 있습니다. 이 방법으로 구성된 경우에는 레코드 자체를 삭제하지 않고 레코드에서 개인 데이터의 콘텐츠를 제거해야 합니다.

관련성 검색 결과에서 다음을 수행합니다.

1. 개인의 개인 데이터를 포함하는 항목을 클릭하거나 탭합니다.

2. 리본에서 **삭제**를 클릭하거나 탭합니다. (레코드를 삭제할 수 없는 경우에는 **삭제**를 사용할 수 없습니다.)

    ![PowerApps 계정 삭제](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-databases-of-the-previous-version-of-cds"></a>이전 버전의 CDS 데이터베이스에 저장된 개인 데이터

### <a name="prerequisites"></a>필수 조건
개인(예: 관리 중인 고객)의 개인 데이터를 CDS 엔터티 내에 저장하고 있을 수 있습니다.  

CDS 시스템 관리자는 DSR 요청에 응답하여 해당 데이터를 찾을 수 있도록 사용 중인 각 개인의 다양한 엔터티 내에 개인 데이터가 저장된 위치의 인벤토리를 유지 관리해야 합니다.  

개인 데이터는 제품 내 기능을 사용하여 엔터티에서 내보내거나, 수정하거나, 삭제할 수 있습니다.  

### <a name="discover"></a>검색
CDS 시스템 관리자가 개인으로부터 DSR 요청을 받으면 해당 관리자는 이 개인의 개인 데이터가 포함된 환경/CDS 인스턴스를 식별해야 합니다. 개인 데이터는 일반적으로 주요 엔터티(예: 계정, 연락처, 잠재 고객, 기회 등)에 저장되지만, DSR 요청에 응답할 수 있도록 각 개인의 개인 데이터를 저장하는 위치의 인벤토리를 유지 관리하기 위한 정책과 절차를 개발하는 것은 본인의 책임입니다.

다음 리소스 내에서 이전 버전의 CDS 사용자의 개인 데이터를 찾을 수 있습니다.

|리소스 | 용도 | 웹 사이트 액세스 |  프로그래밍 방식 액세스
| --- | --- | --- | ---
|엔터티 레코드 | 각 비즈니스 엔터티에서 비즈니스 트랜잭션을 캡처합니다. | [PowerApps](https://web.powerapps.com) |      아니요

#### <a name="entity-records"></a>엔터티 레코드
개인의 개인 데이터는 비즈니스 엔터티에 저장할 수 있습니다.

이 버전의 CDS에는 고유한 데이터베이스 스키마 및 인프라가 포함됩니다. 여기에는 고유한 엔터티가 포함되고 [PowerApps](http://web.powerapps.com/)에서 이러한 엔터티를 관리합니다.

엔터티 목록을 보려면 다음을 수행합니다.

1. **환경** 드롭다운 목록에서 환경을 선택합니다.

2. 탐색 창에서 **데이터**를 클릭하거나 탭한 다음, **엔터티**를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

3. 엔터티 목록에서 아래와 같이 엔터티(예: 계정 엔터티)를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티 세부 정보 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4. **데이터** 탭을 클릭하거나 탭합니다. 엔터티의 레코드 목록이 표시됩니다.

    ![PowerApps 레거시 계정 데이터](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

5. **데이터 내보내기**를 클릭하거나 탭합니다.

6. 내보내기가 완료되면 **Excel에서 열기**를 클릭하거나 탭한 다음, **편집 사용**을 클릭하거나 탭합니다.

7. [검색] 단추를 클릭하거나 탭하고, 검색 상자에 해당 개인의 개인 데이터를 입력한 다음, **검색**을 클릭하거나 탭합니다.

8. 인벤토리 목록을 사용하여 각 비즈니스 엔터티에 대해 위 단계를 반복하여 개인의 개인 데이터를 모두 검색합니다.

### <a name="rectify"></a>수정
데이터 주체가 조직 데이터에 있는 개인 데이터를 수정하도록 요청하는 경우 본인과 조직은 요청을 수용하는 것이 적절한지 여부를 결정해야 합니다. 데이터 수정에는 문서 또는 다른 유형이나 항목에서 개인 데이터를 편집, 수정 또는 제거하는 작업이 포함될 수 있습니다.

Azure Active Directory를 사용하여 이전 버전의 CDS 내에서 사용자의 ID(개인 데이터)를 관리할 수 있습니다. 엔터프라이즈 고객은 지정된 Microsoft 서비스 내에서 제한된 편집 기능을 사용하여 DSR 수정 요청을 관리할 수 있습니다. Microsoft는 데이터 프로세서로서 시스템에서 생성된 로그가 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트 기록 레코드를 구성하기 때문에 이 로그를 수정하는 기능을 제공하지 않습니다. 자세한 내용은 [GDPR: DSR(데이터 주체 요청)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)을 참조하세요.

CDS 환경에 있는 개인 데이터를 수정하려면 엔터티 데이터를 Excel 스프레드시트로 내보내고, 업데이트한 다음, 업데이트를 다시 데이터베이스로 가져오면 됩니다.

CDS 시스템 관리자는 개인의 개인 데이터가 포함된 모든 엔터티를 식별하고 각 엔터티에 대해 다음 단계를 반복해야 합니다.

[PowerApps](http://web.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **데이터**를 클릭하거나 탭한 다음, **엔터티**를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. 엔터티 목록에서 아래와 같이 엔터티(예: 계정 엔터티)를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티 세부 정보 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. **데이터** 탭을 클릭하거나 탭합니다. 엔터티의 레코드 목록이 표시됩니다.

    ![PowerApps 레거시 계정 데이터](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. **데이터 내보내기**를 클릭하거나 탭합니다.

5. 내보내기가 완료되면 **Excel에서 열기**를 클릭하거나 탭한 다음, **편집 사용**을 클릭하거나 탭합니다.

6. 메뉴 모음에서 **파일**을 클릭하거나 탭하고, **다른 이름으로 저장**을 클릭하거나 탭한 다음, 파일을 저장할 위치를 선택합니다.

7. 필요한 개인 데이터를 업데이트하고 스프레드시트를 저장합니다.

10. PowerApps에서 엔터티의 **데이터** 탭으로 돌아가서 **데이터 가져오기**를 클릭하거나 탭합니다.

11. **검색**을 클릭한 다음, 방금 업데이트한 Excel 스프레드시트를 선택하여 엽니다.

12. **가져오기**를 클릭합니다.

### <a name="export"></a>내보내기
각 엔터티에서 Excel 스프레드시트로 개인 데이터를 내보내고 이를 볼 수 있습니다.

[PowerApps](http://web.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **데이터**를 클릭하거나 탭한 다음, **엔터티**를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. 엔터티 목록에서 아래와 같이 내보내고 보려는 엔터티(예: 계정 엔터티)를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티 세부 정보 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. **데이터** 탭을 클릭하거나 탭합니다. 엔터티의 레코드 목록이 표시됩니다.

    ![PowerApps 레거시 계정 데이터](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. **데이터 내보내기**를 클릭하거나 탭합니다.

    이 내보내기 작업은 백그라운드에서 실행되고 완료되면 알림이 표시됩니다.

5. 내보낸 데이터를 보려면 **Excel에서 열기**를 클릭하거나 탭합니다.

### <a name="delete"></a>삭제
데이터 내보내기/가져오기 기능을 사용하여 엔터티에 저장된 개인 데이터를 삭제할 수 있습니다.

CDS 시스템 관리자는 개인의 개인 데이터가 포함된 모든 엔터티를 식별하고 각 엔터티에 대해 다음 단계를 반복해야 합니다.

[PowerApps](http://web.powerapps.com/)에서 다음을 수행합니다.

1. 탐색 창에서 **데이터**를 클릭하거나 탭한 다음, **엔터티**를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. 엔터티 목록에서 아래와 같이 개인 데이터를 제거할 엔터티(예: 계정 엔터티)를 클릭하거나 탭합니다.

    ![PowerApps 레거시 엔터티 세부 정보 목록](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. **데이터** 탭을 클릭하거나 탭합니다. 엔터티의 레코드 목록이 표시됩니다.

    ![PowerApps 레거시 계정 데이터](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. **데이터 내보내기**를 클릭하거나 탭합니다.

5. 내보내기가 완료되면 **Excel에서 열기**를 클릭하거나 탭한 다음, **편집 사용**을 클릭하거나 탭합니다.

6. 메뉴 모음에서 **파일**을 클릭하거나 탭하고, **다른 이름으로 저장**을 클릭하거나 탭한 다음, 파일을 저장할 위치를 선택합니다.

7. 엔터티에서 제거하려는 개인 데이터가 포함된 행을 삭제하고 스프레드시트를 저장합니다.

10. PowerApps에서 엔터티의 **데이터** 탭으로 돌아가서 **데이터 가져오기**를 클릭하거나 탭합니다.

11. **검색**을 클릭한 다음, 방금 업데이트한 Excel 스프레드시트를 선택하여 엽니다.

12. **가져오기**를 클릭합니다.