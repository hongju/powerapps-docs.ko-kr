---
title: 조직의 라이선스 관리 | Microsoft Docs
description: Office 365 테넌트에서 PowerApps에 등록하는 라이선스, 관리 및 사용자에 대한 일반적인 질문 및 답변
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: jamesol
ms.openlocfilehash: 8a734ef57a3820e38d52ad2bd87a2ab8979c0348
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168047"
---
# <a name="manage-powerapps-licenses-in-your-organization"></a>조직의 PowerApps 라이선스 관리
이 문서에서는 조직의 사용자가 PowerApps에 액세스하여 사용하는 방법 및 PowerApps 서비스에 대한 액세스를 제어하는 방법을 설명합니다.

## <a name="sign-up-for-powerapps"></a>PowerApps에 등록
### <a name="what-is-powerapps"></a>PowerApps란?
Microsoft PowerApps를 사용하면 Windows, iOS 및 Android 모바일 장치용 응용 프로그램을 만들 수 있습니다. 이러한 앱을 사용하여 Twitter, Office 365, Dropbox, Excel을 비롯한 일반적인 SaaS 서비스에 연결을 만들 수 있습니다.

### <a name="how-do-users-sign-up-for-powerapps"></a>사용자가 PowerApps에 등록하려면 어떻게 할까요?
조직의 개별 사용자용 유일한 등록 옵션은 PowerApps 계획 2 평가판입니다. 여기서 PowerApps 웹 사이트를 통해 등록할 수 있습니다.

##### <a name="option-1"></a>옵션 1
사용자는 [powerapps.microsoft.com](https://powerapps.microsoft.com)으로 이동하고, **무료로 등록**을 선택하고, [portal.office.com](https://portal.office.com/Start?sku=powerapps)을 통해 PowerApps에 대한 등록 프로세스를 완료하여 등록할 수 있습니다.

##### <a name="option-2"></a>옵션 2
사용자는 [powerapps.microsoft.com](https://powerapps.microsoft.com)으로 이동하고, **로그인**을 선택하고, 해당 작업 또는 학교 계정을 사용하여 로그인하여 등록하거나 PowerApps 사용 약관을 수락함으로써 PowerApps 계획 2 평가판에 등록할 수 있습니다.    

조직의 사용자가 PowerApps에 등록할 경우 해당 사용자에게는 PowerApps 라이선스가 자동으로 할당됩니다.

> [!NOTE]
> PowerApps 내에서 평가판 라이선스에 등록하는 사용자는 Office 365, Dynamics 365 또는 PowerApps에 대한 다른 라이선스를 갖고 있지 않는 한 Office 365 관리자 포털에 PowerApps 계획 2 평가판 사용자로 표시되지 않습니다.

자세한 내용은 [PowerApps 셀프 서비스 등록](../maker/signup-for-powerapps.md)을 참조하세요.

### <a name="how-can-users-in-my-organization-gain-access-to-powerapps"></a>조직의 사용자가 PowerApps에 대한 액세스 권한을 얻으려면 어떻게 하나요?
조직 내의 사용자는 다음과 같은 세 가지 방법으로 PowerApps에 액세스할 수 있습니다.

* [사용자가 PowerApps에 등록하려면 어떻게 하나요?](#how-do-users-sign-up-for-powerapps) 섹션에 설명된 대로 PowerApps 계획 2 평가판에 개별적으로 등록할 수 있습니다.
* Office 365 관리 포털 내에서 PowerApps 라이선스를 할당할 수 있습니다.
* 사용자에게는 PowerApps 서비스에 대한 액세스 권한을 포함하는 Office 365 및 Dynamics 365 요금제가 할당되었습니다. PowerApps 기능을 포함하는Office 365 및 Dynamics 365 요금제에 대한 목록은 [PowerApps 가격 책정 페이지](https://powerapps.microsoft.com/pricing)를 참조하세요.

### <a name="can-i-block-users-in-my-organization-from-signing-up-for-powerapps"></a>조직의 사용자가 PowerApps에 등록하지 못하도록 차단할 수 있나요?
개별 사용자는 30일 동안 Microsoft PowerApps 계획 2의 기능을 사용해 볼 수 있습니다. 이 경우에 [사용자가 PowerApps에 등록하려면 어떻게 하나요?](#how-do-users-sign-up-for-powerapps) 섹션에 설명된 대로 비용이 발생하지 않습니다.  이 옵션은 테넌트의 모든 사용자에게 제공되고 관리자에 의해 해제될 수 없습니다.  사용자의 평가판이 만료된 후에 사용자는 PowerApps 계획 2 기능에 액세스할 수 없게 됩니다.  

사용자가 Microsoft PowerApps 계획 2의 30일 평가판에 등록하고 조직 내에서 지원하지 않도록 선택한 경우 회사에 비용을 부과할 수 없습니다. 개별 사용자가 Microsoft PowerApps에 등록할 때 Bing, Wunderlist, OneDrive 또는 Outlook.com과 같은 Microsoft의 많은 공용 클라우드 서비스와 마찬가지로 개별 사용자와 Microsoft 간의 관계는 어떠한 방식으로든 사용자 조직에서 제공되는 서비스를 의미하지 않습니다.

마지막으로 회사에서 Microsoft PowerApps의 내부에서 조직 전용 데이터 사용을 제한하려고 하는 경우 DLP(데이터 손실 방지) 정책을 통해 가능합니다. 자세한 내용은 [DLP(데이터 손실 방지) 정책](prevent-data-loss.md)을 참조하세요.

## <a name="administration-of-powerapps"></a>PowerApps의 관리
### <a name="why-has-the-powerapps-icon-appeared-in-the-office-365-app-launcher"></a>Office 365 앱 시작 관리자에서 PowerApps 아이콘을 표시하는 이유
Microsoft PowerApps는 Office 365 Suite의 핵심 부분이며 기존 Office 365 SKU의 일부인 서비스로 사용되도록 설정합니다. 전 세계에 있는 사용자는 이제 Microsoft PowerApps를 사용할 수 있습니다. 해당 기능은 앱 시작 관리자 화면의 ‘모든 앱’에 표시됩니다. [라이선스 개요](pricing-billing-skus.md)를 참조하면 Office 365 SKU에 이제 PowerApps가 포함됩니다.

기본적으로 ‘모든 앱’에서 PowerApps 타일을 제거하려는 경우 다음 섹션을 참조하세요.

### <a name="how-do-i-remove-powerapps-from-existing-users"></a>기존 사용자에게서 PowerApps를 제거하려면 어떻게 할까요?
사용자에게 PowerApps 계획 1 또는 PowerApps 계획 2 라이선스가 할당된 경우 다음 단계를 수행하여 해당 사용자에게서 PowerApps 라이선스를 제거할 수 있습니다.

1. [Office 365 관리 포털](https://portal.microsoftonline.com/)로 이동합니다.

2. 왼쪽 탐색 모음에서 **사용자**를 선택한 다음 **활성 사용자**를 선택합니다.

3. 라이선스를 제거하려는 사용자를 찾은 다음 해당 이름을 선택합니다.

4. 사용자 세부 정보 창의 **제품 라이선스** 섹션에서 **편집**을 선택합니다.

5. **Microsoft PowerApps 계획 1** 또는 **Microsoft PowerApps 계획 2**라는 라이선스를 찾고 토글을 **끄기**로 설정한 다음 **저장**을 선택합니다.

    ![](./media/signup-question-and-answer/remove-license.png)

사용자가 Office 365 및 Dynamics 365 계획 라이선스를 통해 PowerApps에 액세스할 수 있으면 다음 단계를 수행하여 PowerApps 서비스에 대한 액세스를 비활성화할 수 있습니다.

1. [Office 365 관리 포털](https://portal.microsoftonline.com/)로 이동합니다.

2. 왼쪽 탐색 모음에서 **사용자**를 선택한 다음 **활성 사용자**를 선택합니다.

3. 액세스를 제거하려는 사용자를 찾은 다음 해당 이름을 선택합니다.

4. 사용자 세부 정보 창의 **제품 라이선스** 섹션에서 **편집**을 선택합니다.

5. 사용자의 Office 365 또는 Dynamics 365 라이선스를 확장하고, **Office 365용 PowerApps** 또는 **Dynamics 365용 PowerApps**라는 서비스에 대한 액세스를 비활성화한 다음, **저장**을 선택합니다.

    ![](./media/signup-question-and-answer/remove-service-plan.png)

라이선스의 대량 제거 작업을 PowerShell을 통해서도 가능합니다. 자세한 예제는 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](https://technet.microsoft.com/library/dn771774.aspx)를 참조하세요.   마지막으로 라이선스 내에서 서비스의 대량 제거에 대한 추가 지침은 [Office 365 PowerShell을 사용하여 서비스에 대한 액세스 비활성화](https://technet.microsoft.com/library/dn771769.aspx)에서 찾을 수 있습니다.

조직 내의 사용자에게서 PowerApps 라이선스 또는 서비스를 제거하면 해당 사용자의 다음 위치에서 PowerApps 및 Dynamics 365 아이콘을 제거하게 됩니다.

* [Office.com](https://office.com)

    ![](./media/signup-question-and-answer/office-home.png)
* Office 365 AppLauncher "waffle"

    ![](./media/signup-question-and-answer/office-waffle.png)

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data-using-powerapps"></a>PowerApps를 사용하여 조직의 비즈니스 데이터에 액세스하는 사용자의 기능을 제한하려면 어떻게 하나요?
아래와 같이 PowerApps를 사용하면 비즈니스 및 비즈니스 이외의 데이터에 데이터 영역을 만들 수 있습니다.  이러한 데이터 손실 방지 정책이 구현되면 사용자는 비즈니스 및 비즈니스 이외의 데이터를 결합하는 PowerApps를 실행하거나 디자인하지 않도록 방지됩니다. 자세한 내용은 [DLP(데이터 손실 방지) 정책](prevent-data-loss.md)을 참조하세요.

![](./media/signup-question-and-answer/data-loss-prevention-policy.png)

### <a name="why-did-10000-licenses-for-microsoft-powerapps-show-up-in-my-office-365-tenant"></a>Microsoft PowerApps의 10,000개 라이선스가 Office 365 테넌트에서 나타나는 이유
조건에 맞는 조직인 경우 조직의 사용자는 30일 동안 Microsoft PowerApps 계획 2를 사용해 볼 수 있으며, 이러한 평가판 라이선스는 테넌트에서 새 PowerApps 사용자에 대해 사용 가능한 용량을 나타냅니다. 이러한 라이선스에 대한 요금이 청구되지 않습니다. 특히, 다음과 같은 두 가지 이유로 PowerApps에서 10,000개(평가판)의 라이선스가 Office 365 관리 포털에 표시되는 것을 확인할 수 있습니다.

* 테넌트에서 하나 이상의 사용자가 2016년 4월부터 2016년 10월에 걸친 PowerApps 공용 미리 보기에 참여한 경우 "Microsoft PowerApps 및 논리 흐름"이라고 레이블이 지정된 10,000개의 라이선스가 표시됩니다.

    ![](./media/signup-question-and-answer/licenses_2.png)
* 테넌트에서 하나 이상의 사용자가 [사용자가 PowerApps에 등록하려면 어떻게 하나요?](#how-do-users-sign-up-for-powerapps) 섹션에서 설명된 평가판 등록 **옵션 1**을 수행하여 PowerApps 계획 2 평가판에 등록한 경우 "Microsoft PowerApps 및 Flow"라는 레이블이 지정된 10,000개의 라이선스가 표시됩니다.

    ![](./media/signup-question-and-answer/licenses_1.png)

Office 365 관리 포털을 통해 사용자에게 직접 추가 사용자 라이선스를 할당하도록 선택할 수 있지만 이러한 방법은 Microsoft PowerApps 계획 2에 대한 평가판 라이선스이며 사용자에게 할당되고 30일 후에 만료됩니다.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>무료인가요? 이러한 라이선스에 대한 수수료를 지불하나요?
이러한 라이선스는 30일 동안 사용자가 Microsoft PowerApps 계획 2를 사용하기 위한 평가판 라이선스입니다.

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>현재 조직에서 사용자의 ID를 관리하는 방법을 어떻게 변경할 수 있나요?
조직에 기존 Office 365 환경이 있고 조직의 모든 사용자에게 Office 365 계정이 있는 경우 ID 관리는 변경되지 않습니다.

이미 조직에 기존 Office 365 환경이 있지만 조직의 일부 사용자에게 Office 365 계정이 없는 경우 테넌트에서 사용자를 만들고 사용자의 회사 또는 학교 전자 메일 주소에 따라 라이선스를 할당합니다. 즉, 조직의 사용자가 서비스에 등록하는 만큼 특정 시점에 관리하는 사용자 수가 증가하게 됩니다.

조직의 Office 365 환경이 전자 메일 도메인에 연결되지 않은 경우 ID를 관리하는 방법에 변화가 없습니다. 사용자가 새 클라우드 전용 사용자 디렉터리에 추가되면 테넌트 관리자 자격으로 인수하고 관리하는 옵션이 있습니다.

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>사용자를 위해 Microsoft에서 만든 테넌트를 관리하는 프로세스는 무엇인가요?
Microsoft에서 테넌트를 만든 경우 다음 단계를 사용하여 해당 테넌트를 클레임하고 관리할 수 있습니다.

1. 관리하려는 테넌트 도메인과 일치하는 전자 메일 주소 도메인을 사용하는 PowerApps에 등록하여 테넌트를 조인합니다. 예를 들어 Microsoft가 contoso.com 테넌트를 만든 경우 @contoso.com으로 끝나는 메일 주소와 테넌트를 조인합니다.
2. 도메인 소유권을 확인하여 관리자 컨트롤을 클레임합니다. 사용자가 테넌트에 있는 경우 도메인 소유권을 확인하여 관리자 역할로 승격할 수 있습니다. 이렇게 하려면 다음 단계를 수행하세요.
3. [https://portal.office.com](https://portal.office.com/Start?sku=powerapps)으로 이동합니다.
4. 왼쪽 위 모서리에서 앱 시작 관리자 아이콘을 선택하고 관리자를 선택합니다
5. **관리자 되기** 페이지의 지침을 읽고 **예, 관리자가 되겠습니다.** 를 선택합니다.  

> [!NOTE]
> 이 옵션이 표시되지 않으면 Office 365 관리자가 이미 설정되어 있습니다.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>여러 도메인이 있는 경우 사용자를 추가할 Office 365 테넌트를 제어할 수 있나요?
아무 작업을 수행하지 않은 경우 각 사용자 전자 메일 도메인 및 하위 도메인에 테넌트가 만들어집니다.

모든 사용자가 해당 전자 메일 주소 확장명에 관계 없이 동일한 테넌트에 포함되도록 하려면 다음을 수행하세요.  

* 미리 대상 테넌트를 만들거나 기존 테넌트를 사용합니다. 해당 테넌트 내에 통합하려는 모든 기존 도메인 및 하위 도메인을 추가합니다. 그런 다음 해당 도메인 및 하위 도메인에서 끝나는 전자 메일 주소를 가진 모든 사용자는 등록할 때 자동으로 대상 테넌트에 조인합니다.

> [!IMPORTANT]
> 테넌트가 생성되면 해당 테넌트에서 사용자를 이동하도록 지원되는 자동화된 메커니즘이 없습니다. 단일 Office 365 테넌트에 도메인을 추가하는 방법에 대한 자세한 내용은 [Office 365에 사용자 및 도메인 추가](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7)를 참조하세요.
