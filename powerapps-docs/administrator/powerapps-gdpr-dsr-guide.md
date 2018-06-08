---
title: PowerApps 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답 | Microsoft Docs
description: PowerApps 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답하는 방법 연습
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 14fe0c749a17a1a28ebc7c8680ff55df2392999e
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552947"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>PowerApps 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답

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

## <a name="discover"></a>검색
DSR 요청에 응답하는 첫 번째 단계는 요청의 대상인 개인 데이터를 찾는 것입니다. 해당하는 개인 데이터를 찾고 검토하는 이 첫 번째 단계에서는 DSR 요청이 DSR 요청을 수락 또는 거부하기 위한 조직의 요구 사항을 충족하는지 확인할 수 있습니다. 예를 들어 해당하는 개인 데이터를 찾고 검토한 후 요청을 수락할 경우 다른 사용자의 권한과 자유에 부정적인 영향을 미칠 수 있으므로 해당 요청이 조직의 요구 사항을 충족하지 않는다고 결정할 수 있습니다.

### <a name="step-1-find-personal-data-for-the-user-in-powerapps"></a>1단계: PowerApps에서 사용자에 대한 개인 데이터 찾기
다음은 특정 사용자에 대한 개인 데이터를 포함하는 PowerApps 리소스의 유형에 대한 요약입니다.

개인 데이터를 포함하는 리소스 |    용도
--- | ---
환경 |   환경은 조직의 비즈니스 데이터, 앱 및 흐름을 저장, 관리 및 공유하는 공간입니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872239)
환경 사용 권한 | 사용자에게는 작성자에게 부여되는 환경 역할 및 환경 내의 관리 권한이 할당됩니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872240)
캔버스 앱  | 빈 캔버스를 기반으로 빌드되고 200개 이상의 데이터 원본에 연결될 수 있는 플랫폼 간 비즈니스 앱입니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872241)
캔버스 앱 권한  | 캔버스 앱은 조직 내의 사용자와 공유할 수 있습니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872242)
연결  | 커넥터가 사용하고 API, 시스템, 데이터베이스 등에 대한 연결을 허용합니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872243)
연결 권한  | 특정 유형의 연결은 조직 내의 사용자와 공유할 수 있습니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872244)
사용자 지정 커넥터    | PowerApps 표준 커넥터 중 하나를 통해 제공되지 않는 데이터 원본에 대한 액세스 권한을 제공하기 위해 사용자가 만든 사용자 지정 커넥터입니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872245)
사용자 지정 커넥터 권한    | 사용자 지정 커넥터는 조직 내의 사용자와 공유할 수 있습니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872246)
PowerApps 사용자 및 사용자 앱 설정    | PowerApps는 PowerApps 런타임 및 포털 환경을 전달하는 데 사용되는 다양한 사용자 기본 설정 및 설정을 저장합니다.
PowerApps 알림 | PowerApps는 앱이 사용자와 공유될 경우 및 앱용 CDS 내보내기 작업이 완료될 경우를 포함하여 사용자에게 다양한 유형의 알림을 보냅니다.
게이트웨이 | 게이트웨이는 PowerApps와 클라우드에 없는 데이터 원본 간에 빠르고 안전하게 데이터를 전송하기 위해 사용자가 설치할 수 있는 온-프레미스 데이터 게이트웨이입니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872247)
게이트웨이 권한 | 게이트웨이는 조직 내의 사용자와 공유할 수 있습니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872249)
모델 기반 앱 및 모델 기반 앱 권한  | 모델 기반 앱 디자인은 앱 개발에 대해 구성 요소에 중점을 두는 방법입니다. 모델 기반 앱 및 해당 사용자 액세스 권한은 앱용 CDS 데이터베이스 내에 데이터로 저장됩니다.  [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872248)

PowerApps는 특정 사용자에 대한 개인 데이터를 찾기 위한 다음과 같은 환경을 제공합니다.

- **웹 사이트 액세스**: [PowerApps 사이트](https://web.powerapps.com), [PowerApps 관리 센터](https://admin.powerapps.com/) 및 [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)
- **PowerShell 액세스**: PowerApps cmdlet([앱 작성자](https://go.microsoft.com/fwlink/?linkid=871448) 및 [관리자](https://go.microsoft.com/fwlink/?linkid=871804)용) 및 [온-프레미스 게이트웨이 cmdlet](https://go.microsoft.com/fwlink/?linkid=872238)

이러한 리소스 유형별로 이러한 환경을 사용하여 특정 사용자에 대한 개인 데이터를 찾는 방법에 대한 자세한 단계는 [PowerApps 고객 데이터를 내보내기 위한 DSR(Data Subject Rights) 요청에 응답](powerapps-gdpr-export-dsr.md)을 참조하세요.

데이터를 찾은 후에는 특정 작업을 수행하여 데이터 주체에 의한 요청을 충족할 수 있습니다.

### <a name="step-2-find-personal-data-for-the-user-in-microsoft-flow"></a>2단계: Microsoft Flow에서 사용자에 대한 개인 데이터 찾기
PowerApps 라이선스에는 항상 Microsoft Flow 기능이 포함되어 있습니다. Microsoft Flow는 PowerApps 라이선스에 포함될 뿐만 아니라 독립 실행형 서비스로도 제공됩니다.

Microsoft Flow 서비스를 통해 저장된 개인 데이터를 검색하는 방법에 대한 자세한 내용은 [Microsoft Flow에 대한 GDPR 데이터 주체 요청에 응답](https://go.microsoft.com/fwlink/?linkid=872250)을 참조하세요.

> [!IMPORTANT]
> 관리자는 PowerApps 사용자에 대해 이 단계를 완료하는 것이 좋습니다.

### <a name="step-3-find-personal-data-for-the-user-in-instances-of-cds-for-apps"></a>3단계: 앱용 CDS 인스턴스에서 사용자에 대한 개인 데이터 찾기
PowerApps 커뮤니티 요금제를 포함한 특정 PowerApps 라이선스는 조직 내 사용자가 앱용 CDS 인스턴스를 만들고 앱용 CDS에서 앱을 만들고 빌드하는 기능을 제공합니다. PowerApps 커뮤니티 요금제는 사용자가 개별 환경에서 앱용 CDS를 사용해 볼 수 있는 무료 라이선스입니다. 각 PowerApps 라이선스에 포함된 기능에 대해서는 [PowerApps 가격](https://powerapps.microsoft.com/pricing/) 페이지를 참조하세요.

앱용 CDS를 통해 저장된 개인 데이터를 검색하는 방법에 대한 자세한 내용은 [앱용 Common Data Service의 고객 데이터에 대한 DSR(Data Subject Rights) 요청에 응답](common-data-service-gdpr-dsr-guide.md)을 참조하세요.

> [!IMPORTANT]
> 관리자는 PowerApps 사용자에 대해 이 단계를 완료하는 것이 좋습니다.

## <a name="rectify"></a>수정
데이터 주체가 조직 데이터에 있는 개인 데이터를 수정하도록 요청하는 경우 본인과 조직은 요청을 수용하는 것이 적절한지 여부를 결정해야 합니다. 데이터 수정에는 문서 또는 다른 유형이나 항목에서 개인 데이터를 편집, 수정 또는 제거하는 작업이 포함될 수 있습니다.

Azure Active Directory를 사용하여 PowerApps 내에서 사용자의 ID(개인 데이터)를 관리할 수 있습니다. 엔터프라이즈 고객은 지정된 Microsoft 서비스 내에서 제한된 편집 기능을 사용하여 DSR 수정 요청을 관리할 수 있습니다. Microsoft는 데이터 프로세서로서 시스템에서 생성된 로그가 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트 기록 레코드를 구성하기 때문에 이 로그를 수정하는 기능을 제공하지 않습니다. 자세한 내용은 [GDPR: DSR(데이터 주체 요청)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)을 참조하세요.

## <a name="restrict"></a>제한
데이터 주체는 개인 데이터 처리를 제한하도록 요청할 수 있습니다.  기존 API(응용 프로그래밍 인터페이스)와 UI(사용자 인터페이스)를 모두 제공합니다.  이러한 환경은 엔터프라이즈 고객의 테넌트 관리자에게 데이터 내보내기 및 데이터 삭제의 조합을 통해 DSR을 관리하는 기능을 제공합니다. 고객은 다음을 요청할 수 있습니다.

* 다음을 포함하여 사용자 개인 데이터의 전자 복사본 내보내기:

    - 계정
    - 시스템 생성 로그
    - 연결된 로그

* Microsoft 시스템 내에 있는 계정 및 관련 데이터 삭제.

## <a name="export"></a>내보내기
“데이터 이식성 권한”을 사용하면 데이터 주체가 다른 데이터 컨트롤러에게 전송될 수 있는 자신의 개인 데이터 복사본을 전자 형식(“구조화되고, 일반적으로 사용되고, 컴퓨터에서 읽을 수 있고, 상호 운용 가능한 형식”)으로 요청할 수 있습니다.

자세한 내용은 [PowerApps 고객 데이터를 내보내기 위한 DSR(Data Subject Rights) 요청에 응답](powerapps-gdpr-export-dsr.md)을 참조하세요.

## <a name="delete"></a>삭제
조직의 고객 데이터에서 개인 데이터 제거를 통한 “삭제 권한”은 GDPR의 주요 보호 방법입니다. 개인 데이터 제거에는 시스템 생성 로그가 포함되지만 감사 로그 정보는 포함되지 않습니다.

PowerApps를 통해 사용자는 조직의 일상 업무에 중요한 부분인 기간 업무 응용 프로그램을 빌드할 수 있습니다. 사용자가 조직을 떠나면 사용자가 만든 특정 데이터 및 리소스를 삭제할지 여부를 수동으로 검토하고 결정해야 합니다. 다른 고객 데이터는 사용자 계정이 Azure Active Directory에서 삭제될 때마다 자동으로 삭제됩니다.

자세한 내용은 [PowerApps 고객 데이터를 삭제하기 위한 DSR(Data Subject Rights) 요청에 응답](powerapps-gdpr-delete-dsr.md)을 참조하세요.
