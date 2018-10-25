---
title: SharePoint 목록 양식 사용자 지정 | Microsoft Docs
description: PowerApps를 사용하여 사용자가 SharePoint 목록에서 항목을 만들고 업데이트하는 양식을 사용자 지정합니다.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/11/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 218fb97f6cd523275c0ba296ea120d487cf67e4c
ms.sourcegitcommit: c26976af24a3e510e4eced78cf5c48cc2f71cae2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48025674"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>PowerApps를 사용하여 SharePoint 목록 양식 사용자 지정

브라우저에서 PowerApps를 열어서 SharePoint 목록의 양식을 쉽게 사용자 지정할 수 있습니다. C#과 같은 기존 코드를 작성하거나 InfoPath와 같은 다른 앱을 다운로드할 필요가 없습니다. 변경 내용을 게시하는 경우 해당 사용자가 모두 사용하기 위해 SharePoint 목록 내에 양식이 포함됩니다. PowerApps에서 분석 보고서를 검토하고, 조건부 서식 지정을 쉽게 만들고, 다른 데이터 원본에 연결할 수도 있습니다.

이 항목의 단계를 수행하기 위해 사용자 지정 작동 방식을 볼 수 있도록 간단한 목록을 만든 다음, 고유한 목록에 동일한 개념을 적용할 수 있습니다.

> [!NOTE]
> **양식 사용자 지정** 옵션을 사용할 수 없거나 목록에서 제대로 작동하지 않는 경우 [PowerApps에서 지원하지 않는](connections/connection-sharepoint-online.md#known-issues) 데이터 형식이 포함될 수 있습니다. 다른 목록 또는 [환경](working-with-environments.md)으로 양식을 전환할 수도 없습니다.

## <a name="prerequisites"></a>필수 조건

SharePoint 사이트에서 목록을 만들고 다음 열을 추가합니다.

- **ProductName**(한 줄 텍스트)
- **세부 정보**(예/아니요)
- **가격**(통화)
- **가용성**(시간 없는 날짜)
- **색**(선택)

## <a name="open-the-form-in-powerapps"></a>PowerApps에서 양식 열기

1. 생성한 목록을 연 다음, 명령 모음에서 **새로 만들기**를 선택합니다.

    양식이 열리고 추가된 필드와 함께 **제목** 및 **첨부 파일**을 보여줍니다.

1. 양식의 위쪽 가까이에서 **사용자 지정**을 선택합니다.

    PowerApps Studio는 동일한 브라우저 탭에서 열립니다.

1. **PowerApps Studio 시작** 대화 상자가 열리면 **건너뛰기**를 선택합니다.

## <a name="hide-extra-fields"></a>추가 필드 숨기기

PowerApps는 화면 가운데에 양식을 표시하지만 이 양식에는 필요하지 않은 필드가 있습니다.

- **데이터** 창에서 **제목** 및 **첨부 파일** 필드에 대한 확인란의 선택을 취소합니다.

    해당 필드가 양식에서 사라지고 사용자가 추가한 필드만 남습니다.

    ![필드 목록](./media/customize-list-form/field-list.png)

## <a name="set-conditional-formatting"></a>조건부 서식 지정 설정

**세부 정보**가 예로 설정되는 경우에만 **가격**, **가용성** 및 **색** 필드가 사라지도록 구성할 수 있습니다.

1. **가격** 카드를 클릭하거나 눌러서 선택합니다.

    ![가용성 카드 선택](./media/customize-list-form/select-card.png)

1. 속성 목록에서 **Visible**을 선택합니다.

    ![visible 속성 선택](./media/customize-list-form/select-property.png)

1. 수식 입력줄에서 이 수식을 입력하거나 붙여넣습니다.

    **If(DataCardValue3.Value = true, true)**

    ![Visible 속성의 값 설정](./media/customize-list-form/build-formula.png)

1. **가용성** 및 **색** 카드에서 마지막 세 단계를 반복합니다.

1. Alt 키를 누른 채 **세부 정보** 설정/해제를 여러 번 클릭하거나 눌러서 선택합니다.

    구성한 세 개의 필드가 표시되고 양식에서 사라집니다.

1. (선택 사항) 다음을 비롯한 다양한 방법으로 양식을 사용자 지정합니다.

    - 크기, 방향 또는 둘 다를 변경합니다(예: [양식 넓히기](set-aspect-ratio-portrait-landscape.md)).
    - 사용자가 [첨부 파일을 업로드](controls/properties-text.md)수 있도록 컨트롤을 추가합니다.
    - [조회 필드](sharepoint-lookup-fields.md)를 만듭니다.

## <a name="save-publish-and-show-the-form"></a>양식 저장, 게시 및 표시

1. **파일** 메뉴를 열고 **저장**을 선택한 다음, **SharePoint에 게시**를 두 번 선택합니다.

1. 왼쪽 위 모퉁이에서 뒤로 화살표를 선택한 다음, **SharePoint로 돌아가기**를 선택합니다.

1. 명령 모음에서 **새로 만들기**를 선택하여 사용자 지정된 양식을 엽니다.

1. **세부 정보** 설정/해제를 여러 번 선택하여 마지막 세 개의 필드를 숨기고 표시합니다.

[양식을 추가로 사용자 지정](sharepoint-form-integration.md)하려면 해당 양식을 열고 양식의 맨 위 가까이에서 **사용자 지정**을 선택한 다음, 변경 내용을 만들고 저장하고 게시합니다.

이 양식에서 하나 이상의 항목을 만들면 **제목** 필드는 비어 있습니다. 이 필드는 기본 보기를 수정해 숨길 수 있습니다.

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

## <a name="q--a"></a>질문과 답변

### <a name="forms-vs-apps"></a>양식 및 앱

**Q:** 사용자 지정 양식이 SharePoint나 PowerApps에서 만드는 독립 실행형 앱과 다른 점은 무엇인가요?

**A:** SharePoint 목록에 대한 양식을 사용자 지정하는 경우 양식은 PowerApps Studio 또는 PowerApps Mobile에서 앱으로 표시되지 않습니다. 양식을 만든 목록에서만 해당 양식을 열 수 있습니다.

**Q:** 언제 양식을 사용자 지정하여 SharePoint 목록에서 데이터를 관리하고 독립 실행형 앱을 만들어야 하나요?

**A:** 예를 들어 사용자가 데스크톱 브라우저에서 SharePoint를 종료하지 않고 데이터를 관리하는 경우 양식을 사용자 지정합니다. 예를 들어 사용자가 모바일 장치에서 SharePoint 외부의 데이터를 관리하려는 경우 앱을 만듭니다.

**Q:** 동일한 목록에 대해 양식을 사용자 지정하고 앱을 만들 수 있나요?

**A:** 예.

**Q:** 동일한 기능을 사용하여 목록을 사용자 지정하고 앱을 만들 수 있나요?

**A:** 예.

**Q:** 내 조직의 기본 환경 이외의 환경에서 양식을 사용자 지정할 수 있나요?

**A:** 아니요.

### <a name="manage-your-custom-form"></a>사용자 지정 양식 관리

**Q:** 다른 사용자와 내 양식을 쉽게 공유하려면 어떻게 할까요?

**A:** 양식을 열고 **링크 복사**를 선택한 다음, 양식을 사용하려는 사용자에게 링크를 보냅니다.

**Q:** 내 변경 사항을 다른 사용자에게 보여주지 않고 내 양식을 업데이트할 수 있나요?

**A:** 예. 원하는 만큼 양식을 변경하고 저장할 수 있지만 **SharePoint에 게시**를 두 번 선택하지 않으면 변경 내용이 다른 사용자에게 보이지 않습니다.

**Q:** 목록 양식을 사용자 지정하다가 실수를 하면 이전 버전으로 되돌릴 수 있나요?

**A:** 예.

1. 목록을 열고, 명령 모음에서 **PowerApps**를 선택한 다음, **양식 사용자 지정**을 선택합니다.

1. PowerApps Studio에서 **파일**을 선택한 다음, **모든 버전 보기**를 선택합니다. **버전** 페이지가 새 브라우저 탭에 열립니다.

    > [!NOTE]
    > **모든 버전 보기** 단추가 표시되지 않으면 **저장**을 선택합니다. 그러면 단추가 표시됩니다.

1. **버전** 페이지나 브라우저 탭을 닫지 않고 다른 브라우저 탭의 **저장** 페이지로 돌아가서 왼쪽 탐색 창의 맨 위에 있는 화살표를 클릭하거나 탭한 다음, **SharePoint로 돌아가기**를 클릭하거나 탭하여 양식의 잠금을 해제하고 PowerApps Studio를 닫습니다.

1. 다른 브라우저 탭의 **버전** 페이지로 돌아가서 복원할 버전을 찾은 다음, **복원**을 선택합니다.

    > [!NOTE]
    > 양식이 다른 사용자에 의해 잠겨 있어서 복원에 실패했다는 오류 메시지가 표시되면 해당 사용자가 양식의 잠금을 해제할 때까지 기다린 다음 다시 시도합니다.

**Q:** 내 양식을 한 목록에서 다른 목록으로 이동할 수 있나요?

**A:** 아니요.

### <a name="administer-your-custom-form"></a>사용자 지정 양식 관리

**Q:** 내 양식을 공유하려면 어떻게 할까요?

**A:** 양식을 공유할 필요가 없습니다. 양식은 SharePoint 목록에서 사용 권한을 상속받습니다. 사용자 지정을 완료한 후 [SharePoint에 다시 게시](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint)만 하면 다른 사람이 사용할 수 있습니다.

**Q:** 누가 양식을 사용자 지정할 수 있나요?

**A:** 연결된 목록을 관리, 디자인 또는 편집할 수 있는 SharePoint 권한을 가진 사람이면 가능합니다.

**Q:** 사용자 지정 목록 양식을 만들거나 사용하는 데 PowerApps 라이선스가 필요한가요?

**A:** [PowerApps가 포함된 Office 365 계획](../../administrator/pricing-billing-skus.md#licenses)이 필요합니다.

**Q:** 게스트 사용자가 사용자 지정 양식이 있는 목록에 액세스하면 어떻게 되나요?

**A:** PowerApps를 사용하여 사용자 지정된 목록 양식에 게스트 사용자가 액세스하려고 하면 오류 메시지가 표시됩니다.

**Q:** 관리자가 조직의 모든 사용자 지정 양식 목록을 얻으려면 어떻게 해야 하나요?

**A:** PowerApps의 테넌트 관리자이거나 조직의 기본 PowerApps 환경에 대해 환경 관리자 권한이 있는 경우 다음을 수행합니다.

1. [PowerApps 관리 센터](https://admin.powerapps.com)의 환경 목록에서 조직의 기본 환경을 선택합니다.

1. 기본 환경 페이지의 맨 위에서 **리소스**를 선택합니다.

1. 앱 목록에서 **SharePoint 양식** 앱 유형이 있는 앱을 찾습니다. 이러한 항목이 사용자 지정 양식입니다.

    ![사용자 지정된 양식 목록](./media/customize-list-form/all-customized-forms.png)
