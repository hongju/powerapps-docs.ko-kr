---
title: SharePoint 목록 양식 사용자 지정 | Microsoft Docs
description: PowerApps를 사용하여 사용자가 SharePoint 목록에서 항목을 만들고 업데이트하는 양식을 사용자 지정합니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/04/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d33f541ea698b02a662edb652f809095f47acc6e
ms.sourcegitcommit: f84095d964fe1fe5cc5290e5edbee284bd768e1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59042735"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>PowerApps를 사용하여 SharePoint 목록 양식 사용자 지정

브라우저에서 PowerApps를 열어서 SharePoint 목록의 양식을 쉽게 사용자 지정할 수 있습니다. C#과 같은 기존 코드를 작성하거나 InfoPath와 같은 다른 앱을 다운로드할 필요가 없습니다. 변경 내용을 게시하는 경우 해당 사용자가 모두 사용하기 위해 SharePoint 목록 내에 양식이 포함됩니다. PowerApps에서 분석 보고서를 검토하고, 조건부 서식 지정을 쉽게 만들고, 다른 데이터 원본에 연결할 수도 있습니다.

이 항목의 단계를 수행하기 위해 사용자 지정 작동 방식을 볼 수 있도록 간단한 목록을 만든 다음, 고유한 목록에 동일한 개념을 적용할 수 있습니다.

> [!NOTE]
> **양식 사용자 지정** 옵션을 사용할 수 없거나 목록에서 제대로 작동하지 않는 경우 [PowerApps에서 지원하지 않는](connections/connection-sharepoint-online.md#known-issues) 데이터 형식이 포함될 수 있습니다. 다른 목록 또는 [환경](working-with-environments.md)으로 양식을 전환할 수도 없습니다.

## <a name="create-a-list"></a>목록 만들기

SharePoint 사이트에서 목록을 만듭니다 하와 해당 목록에 이러한 열을 추가 합니다.

- **세부 정보**(예/아니요)
- **가격**(통화)
- **가용성**(시간 없는 날짜)
- **색**(선택)

> [!div class="mx-imgBorder"]
> ![사이트 콘텐츠 선택 > 새로 만들기 > 목록에서 목록 이름 입력 하 고 만들기를 선택 합니다. 각 열에 대 한 추가 열을 선택, 목록 유형 지정 (예/아니요, 통화, 날짜, 선택 항목) 목록 이름 (세부 정보, 가격, 가용성, 색)을 지정 하 고 저장을 선택 합니다.](./media/customize-list-form/create-list.gif)

## <a name="open-the-form"></a>폼 열기

1. 명령 모음에서 선택 **PowerApps**를 선택한 후 **양식을 사용자 지정**합니다.

    PowerApps Studio는 동일한 브라우저 탭에서 열립니다.

1. **PowerApps Studio 시작** 대화 상자가 열리면 **건너뛰기**를 선택합니다.

> [!div class="mx-imgBorder"]
> ![명령 모음에서 PowerApps를 선택 하 고 사용자 지정 폼을 선택 합니다. PowerApps Studio는 동일한 브라우저 탭에서 열립니다. PowerApps Studio 대화 상자 시작 열리면 Skip을 선택 합니다.](./media/customize-list-form/create-form.gif)

## <a name="move-and-remove-a-field"></a>이동 하 고 필드를 제거 합니다.

1. 끌기 합니다 **가용성** 필드 목록의 맨 아래에 필드입니다.

    지정 된 순서로 필드가 나타납니다.

1. 마우스로 합니다 **첨부 파일** 필드에서 나타나고 다음을 선택 하는 줄임표 (...)를 선택 **제거**합니다.

    지정 된 필드가 폼에서 사라집니다.

> [!div class="mx-imgBorder"]
> ![필드 목록의 맨 아래에 사용 가능한 필드를 끕니다. 첨부 파일 필드 위로 마우스를 가져갑니다, 그리고 표시 되는 줄임표 (...)를 선택 하 고 제거를 선택 합니다.](./media/customize-list-form/move-remove-fields.gif)

## <a name="set-conditional-formatting"></a>조건부 서식 지정 설정

**세부 정보**가 예로 설정되는 경우에만 **가격**, **가용성** 및 **색** 필드가 사라지도록 구성할 수 있습니다.

1. 왼쪽된 탐색 모음에서 **Details_DataCard1**, 끝에 표시 되는 숫자를 기록해 둡니다 **DataCardValue**합니다.

1. 설정를 **표시 유형** 의 속성을 **색**, **가용성**, 및 **가격** 을 다음이 수식으로 카드 (대체, 필요한 경우를 숫자를 이전 단계에서 적어둔):

    **If(DataCardValue2.Value = true, true)**

1. Alt 키를 누른 채 **세부 정보** 설정/해제를 여러 번 클릭하거나 눌러서 선택합니다.

    구성한 세 개의 필드가 표시되고 양식에서 사라집니다.

> [!div class="mx-imgBorder"]
> ![왼쪽된 탐색 모음에서 DataCardValue 끝에 표시 되는 숫자를 note 합니다. 이 수식으로 색, 가용성 및 가격의 표시 여부 속성 카드를 설정 합니다. Alt 키를 누른 채 여러 번 정보 컨트롤을 선택 합니다.](./media/customize-list-form/conditional-format.gif)

## <a name="save-and-publish-the-form"></a>저장 하 고 양식을 게시합니다

1. **파일** 메뉴를 열고 **저장**을 선택한 다음, **SharePoint에 게시**를 두 번 선택합니다.

1. 왼쪽 위 모퉁이에서 뒤로 화살표를 선택한 다음, **SharePoint로 돌아가기**를 선택합니다.

> [!div class="mx-imgBorder"]
> ![파일 메뉴를 열고, 저장, 선택한 다음 SharePoint에 게시를 두 번 선택 합니다. 왼쪽 위 모퉁이의 뒤로 화살표를 선택 하 고 SharePoint에 다시 선택 합니다.](./media/customize-list-form/save-form.gif)

## <a name="further-customize-your-form"></a>양식을 사용자 지정 추가

1. 열 목록, 선택 **새로 만들기** 명령 모음에서 선택한 후에 **사용자 지정** 폼의 맨 위 근처 합니다.

1. 다양 한 방법으로 이러한 항목을 설명 하는 것과 같은에서 양식을 사용자 지정 합니다.

    - 크기, 방향 또는 둘 다를 변경합니다(예: [양식 넓히기](set-aspect-ratio-portrait-landscape.md)).
    - [하나 이상의 카드 사용자 지정](working-with-cards.md) (예를 들어, 카드의 표시 텍스트 또는 입력 컨트롤 변경).
    - [조회 필드](sharepoint-lookup-fields.md)를 만듭니다.

    자세한 정보: [SharePoint 양식 통합 이해](sharepoint-form-integration.md)합니다.

## <a name="use-the-default-form"></a>기본 양식 사용

1. SharePoint 목록에서 오른쪽 위 모서리 근처의 기어 아이콘을 선택하여 설정 페이지를 연 다음, **설정 나열**을 선택합니다.

2. **일반 설정** 아래에서 **양식 설정**을 선택합니다.

3. **양식 설정** 페이지에서 이 옵션 중 하나를 선택한 다음, **확인**을 선택합니다.

    - **기본 SharePoint 양식 사용** - 사용자가 목록을 열고 명령 모음에서 **새로 만들기**를 선택할 때 목록에 대한 기본 양식이 표시됩니다.

    - **PowerApps에서 만든 사용자 지정 양식 사용** - 사용자가 목록을 열고 명령 모음에서 **새로 만들기**를 선택할 때 사용자 지정 양식이 표시됩니다. (대안으로 PowerApps에서 양식을 다시 게시할 수 있습니다.)

    필요에 따라 옵션을 앞뒤로 전환할 수 있습니다.

    ![양식 설정 옵션](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-form"></a>사용자 지정 양식 삭제

1. SharePoint 목록에서 오른쪽 위 모서리 근처의 기어 아이콘을 선택하여 설정 페이지를 연 다음, **설정 나열**을 선택합니다.

1. **일반 설정** 아래에서 **양식 설정**을 선택합니다.

1. **양식 설정** 페이지에서 **기본 SharePoint 양식 사용**을 선택한 다음, **사용자 지정 양식 삭제**를 선택합니다.

    ![사용자 지정 양식 삭제](./media/customize-list-form/use-default-sharepoint.png)

## <a name="q--a"></a>Q & A

### <a name="forms-vs-apps"></a>양식 및 앱

**Q:** SharePoint 또는 PowerApps에서 만드는 독립 실행형 앱에서 사용자 지정된 양식을 다 하는 방법

**A:** SharePoint 목록 폼을 사용자 지정 하면 폼이 PowerApps Studio 또는 PowerApps Mobile에서 앱으로 표시 되지 않습니다. 양식을 만든 목록에서만 해당 양식을 열 수 있습니다.

**Q:** 경우는 양식을 사용자 지정 하는 SharePoint 목록에서 데이터를 관리 하 고 독립 실행형 앱을 만들어야 하면?

**A:** 사용자가 (예: 데스크톱 브라우저)에서 SharePoint를 종료 하지 않고 데이터를 관리 하려는 경우 양식을 사용자 지정 합니다. 예를 들어 사용자가 모바일 디바이스에서 SharePoint 외부의 데이터를 관리하려는 경우 앱을 만듭니다.

**Q:** 양식 사용자 지정 및 동일한 목록에 대 한 앱을 만들 수 있나요?

**A:** 예입니다.

**Q:** 목록 사용자 지정 및 동일한 기능을 사용 하 여 앱을 만들 수 있나요?

**A:** 예입니다.

**Q:** 수 양식을 사용자 지정 하는 기본 환경 이외의 환경에서 내 조직의?

**A:** 아니요.

### <a name="manage-your-custom-form"></a>사용자 지정 양식 관리

**Q:** 공유 하는 방법 쉽게 양식 내 다른 사용자와?

**A:** 폼을 열고 **링크 복사**, 다음 형식을 사용 하려는 모든 사용자에 게 링크를 보냅니다.

**Q:** 변경 내 다른 사용자에 게 표시 하지 않고 폼을 업데이트할 수 있습니까?

**A:** 예입니다. 원하는 만큼 양식을 변경하고 저장할 수 있지만 **SharePoint에 게시**를 두 번 선택하지 않으면 변경 내용이 다른 사용자에게 보이지 않습니다.

**Q:** 이전 버전으로 목록 양식을 사용자 지정 하 고, 실수 되돌릴 수 있나요?

**A:** 예입니다.

1. 목록을 열고, 명령 모음에서 **PowerApps**를 선택한 다음, **양식 사용자 지정**을 선택합니다.

1. PowerApps Studio에서 **파일**을 선택한 다음, **모든 버전 보기**를 선택합니다. **버전** 페이지가 새 브라우저 탭에 열립니다.

    > [!NOTE]
    > **모든 버전 보기** 단추가 표시되지 않으면 **저장**을 선택합니다. 그러면 단추가 표시됩니다.

1. **버전** 페이지나 브라우저 탭을 닫지 않고 다른 브라우저 탭의 **저장** 페이지로 돌아가서 왼쪽 탐색 창의 맨 위에 있는 화살표를 클릭하거나 탭한 다음, **SharePoint로 돌아가기**를 클릭하거나 탭하여 양식의 잠금을 해제하고 PowerApps Studio를 닫습니다.

1. 다른 브라우저 탭의 **버전** 페이지로 돌아가서 복원할 버전을 찾은 다음, **복원**을 선택합니다.

    > [!NOTE]
    > 폼을 다른 사용자에 의해 잠겨 있기 때문에 복원에 실패 한다는 오류 메시지를 받게 되 면 폼을 잠금 해제할 때까지 기다린 후 다시 시도 하십시오.

**Q:** 이동할 수 있습니까 내 양식을 한 목록에서 다른?

**A:** 아니요.

### <a name="administer-your-custom-form"></a>사용자 지정 양식 관리

**Q:** 폼을 공유 하려면 어떻게 해야 하나요?

**A:** 형식을 공유할 필요가 없습니다-폼 SharePoint 목록에서 사용 권한을 상속 받습니다. 사용자 지정을 완료한 후 [SharePoint에 다시 게시](customize-list-form.md#save-and-publish-the-form)만 하면 다른 사람이 사용할 수 있습니다.

**Q:** 폼을 사용자 지정할 수는?

**A:** 를 관리 하려면 SharePoint 권한을 가진 모든 사용자가 디자인, 또는 연결 된 목록을 편집 합니다.

**Q:** 만들기 또는 사용자 지정 목록 양식을 사용 하는 데 PowerApps 라이선스가 필요 합니까?

**A:** 필요는 [PowerApps가 포함 된 Office 365 계획](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus.md#licenses)합니다.

**Q:** 게스트 사용자에 게 사용자 지정 양식이 있는 목록에 액세스 하는 경우 어떻게 되나요?

**A:** 게스트 사용자는 PowerApps를 사용 하 여 사용자 지정 된 된 목록 양식에 액세스 하려고 하면 오류 메시지를 가져옵니다.

**Q:** 관리자로 서 어떻게 가져오나 요 모든 사용자 지정된 양식 목록을 조직에서?

**A:** PowerApps에 대 한 테 넌 트 관리자 인 경우 조직의 기본 PowerApps 환경에 대 한 환경 관리자 권한이 다음을 수행 합니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com)의 환경 목록에서 조직의 기본 환경을 선택합니다.

1. 기본 환경 페이지의 맨 위에서 **리소스**를 선택합니다.

1. 앱 목록에서 사용 하 여 앱에 대 한 확인을 **SharePoint 양식** 앱 유형-이 사용자 지정된 양식입니다.

    ![사용자 지정된 양식 목록](./media/customize-list-form/all-customized-forms.png)
