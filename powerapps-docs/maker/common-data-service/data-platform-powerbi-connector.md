---
title: PowerBI 보고서 만들기 | Microsoft Docs
description: PowerBI Desktop에서 앱 커넥터용 Common Data Service를 사용하여 사용자 데이터에 연결합니다.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: 5fffcbcd8f58ae05f3fe5b3b4f871cf39d003321
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218191"
---
# <a name="create-a-power-bi-report"></a>Power BI 보고서 만들기
앱용 Common Data Service를 사용하면 Power BI Desktop을 사용하여 사용자 데이터에 바로 연결하여 보고서를 만들고 Power BI에 게시할 수 있습니다. Power BI에서 보고서는 대시보드에서 사용하고, 다른 사용자와 공유하며, Power BI 모바일 앱의 플랫폼 간 액세스할 수 있습니다.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>필수 조건

앱용 Common Data Service와 함께 Power BI를 사용하려면 다음이 필요합니다.

* 사용자의 로컬 컴퓨터에서 실행되는 무료 응용 프로그램인 Power BI Desktop을 다운로드 및 설치합니다. [여기에서](https://powerbi.microsoft.com/desktop/) Power BI Desktop을 다운로드할 수 있습니다.
* 포털에 액세스할 수 있는 작성자 권한 및 엔터티 내 데이터에 액세스할 수 있는 읽기 권한이 있는 앱용 Common Data Service.

## <a name="finding-your-common-data-service-for-apps-environment-url"></a>앱용 Common Data Service 환경 URL 찾기

1. [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)를 열고 연결하려는 환경을 선택한 다음, 오른쪽 위 모서리에서 **설정 기어**를 클릭하고 **고급 사용자 지정**을 클릭합니다.

    ![앱용 CDS 환경](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "앱용 CDS 환경")

2. 개발자 리소스 섹션에서 **리소스**를 클릭하면 새 탭이 열립니다.

    ![앱용 CDS 환경](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "앱용 CDS 환경")

3. 새 탭에서 URL의 루트를 복사합니다. 이는 사용자 환경에 대해 고유한 URL입니다. URL은 **https://yourenvironmentid.crm.dynamics.com/** 형식이 됩니다. URL의 나머지 부분은 복사하지 마십시오. PowerBI 보고서를 만들 때 사용할 수 있도록 편리한 위치에 적어둡니다.

    ![앱용 CDS 환경](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "앱용 CDS 환경")

## <a name="connecting-to-common-data-service-for-apps-from-power-bi-desktop"></a>Power BI Desktop에서 앱용 Common Data Service에 연결

1. **Power BI Desktop**을 시작합니다. 처음인 경우 시작 화면이 표시되거나 바로 빈 캔버스가 표시될 수 있습니다. 어떤 방법이든 **데이터 가져오기**를 클릭하고 **자세히**를 선택하여 Power BI Desktop에 사용할 수 있는 데이터 소스의 전체 목록을 엽니다.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. 커넥터의 목록에서 **온라인 서비스** 및 **앱용 Common Data Service(베타)** 를 클릭합니다. **연결**을 클릭합니다.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. **앱용 Common Data Service 환경 URL**을 **서버 URL** 필드에 붙여넣고 **확인**을 클릭합니다. 처음인 경우 PowerApps와 앱용 Common Data Service에 연결하는 데 사용하는 것과 동일한 자격 증명으로 로그인하라는 메시지가 표시됩니다.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. 3개의 폴더로 그룹화된 사용자 환경에 사용할 수 있는 모든 엔터티가 탐색기에 표시됩니다. **공통 데이터 모델** 폴더를 확장합니다.

   * 공통 데이터 모델 - 이는 일반적으로 사용되는 표준 엔터티이며 모든 환경에서 공통 데이터 모델의 일부로 사용할 수 있습니다.
   * 사용자 지정 엔터티 - 환경에서 생성하거나 가져온 엔터티입니다.
   * 시스템 - 공통 데이터 모델 및 사용자 정의 엔터티를 비롯한 사용자 환경의 모든 엔터티를 포함합니다.

     ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. 오른쪽 창에서 데이터의 미리 보기를 확인하려면 **계정** 엔터티를 선택하고 **로드**를 클릭합니다.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. 이제 엔터티가 보고서에 로드되었습니다. 보고서 빌드를 시작하거나 이 프로세스를 반복하여 추가 엔터티를 추가할 수 있습니다.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. 보고서 캔버스에 새로운 시각화를 추가하려면 필드 패널에서 **이름** 필드를 클릭합니다. 이제 이 프로세스를 반복하고 시각화를 변경하여 보고서를 빌드할 수 있습니다.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>옵션 집합 사용

옵션 집합은 앱 및 흐름에서 사용자에게 값에 대한 드롭다운 목록을 제공하기 위해 엔터티에서 사용됩니다. Power BI 커넥터 옵션 집합을 사용하면 고유한 값과 표시 값을 모두 표시하는 두 개의 열로 필드가 표시됩니다.

예를 들어, ApprovalStatus라는 엔터티에 옵션 집합이 있는 경우 Power BI에서 다음과 같은 두 필드를 확인할 수 있습니다.

* ApprovalStatus - 이는 사용자 옵션 집합의 각 항목에 대한 고유한 정수 값을 표시하며, 필터를 적용할 때 유용합니다. 따라서 나중에 표시 이름을 변경하는 경우 영향을 받지 않습니다.
* ApprovalStatus_display - 항목의 친숙한 표시 이름을 표시하며, 테이블 또는 차트에서 옵션을 표시할 때 주로 사용됩니다.

    |ApproalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|제출됨
    2|검토 중
    3|Approved
    4|거부됨

## <a name="navigating-relationships"></a>관계 탐색

앱용 Common Data Service의 관계에서는 사용자가 PowerBI Desktop 내에서 GUID 필드를 사용하여 두 엔터티 간 관계를 만들어야 합니다. 이는 시스템 생성 고유 식별자로, 다른 필드에 모호성 또는 중복이 존재하는 레코드 만들기에서 관계가 생성되었음을 보장합니다. Power BI Desktop에서의 관계 관리에 관한 자세한 내용은 [여기에서](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships) 확인할 수 있습니다.

일부 관계는 자동으로 생성될 수 있지만, 보고서를 만들 때 사용자는 여전히 올바른 관계가 설정되었는지 검토 및 확인할 수 있습니다.

* 엔터티의 조회 필드는 관련된 엔터티의 레코드 GUID를 포함합니다.
* 관련된 엔터티는 Accountid 또는 MyCustomEntityid와 같은 GUID를 포함하는 “[EntityName]id” 형식의 필드를 가집니다.
* PowerBI Desktop 관계 관리 기능을 사용하면 관련된 엔터티에서 조회 필드 및 ID 필드 간의 새 관계를 만들 수 있습니다.


## <a name="next-steps"></a>다음 단계
* [엔터티에서 필드 관리](data-platform-manage-fields.md)
* [엔터티 간의 관계 정의](data-platform-entity-lookup.md)


