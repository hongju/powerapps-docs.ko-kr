---
title: "PowerApps를 사용하여 SharePoint 목록 양식을 사용자 지정 | Microsoft Docs"
description: "PowerApps를 사용하여 SharePoint의 목록 양식을 사용자 지정합니다."
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/13/2017
ms.author: sharik
ms.openlocfilehash: 162314b1bb94e8358e5ddb290adf9db9f43950a0
ms.sourcegitcommit: ce66ba8eadc41d5f260217d164f8317b90ae1504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2017
---
# <a name="customize-a-sharepoint-list-form-using-powerapps"></a>PowerApps를 사용하여 SharePoint 목록 양식을 사용자 지정

PowerApps에서 SharePoint 목록 양식을 쉽게 사용자 지정할 수 있습니다. SharePoint 목록 양식을 사용자 지정하기 위해 InfoPath를 사용하여 수행하던 많은 작업을 이제 PowerApps를 사용하여 브라우저에서 인라인으로 작업할 수 있습니다. 이에 더해 PowerApps에는 훨씬 더 많은 기능이 제공됩니다!

PowerApps는 SharePoint와 직접 통합되어 있기 때문에 컴퓨터에 다른 앱을 다운로드할 필요가 없습니다. PowerApps를 사용하면 코드를 작성하지 않고도 풍부한 사용자 지정 양식을 만들 수 있습니다. 게시되고 나면 양식은 SharePoint 목록에 포함되며 목록의 모든 사용자가 사용할 수 있습니다.

또한 PowerApps는 SharePoint에 완벽하게 통합되기 때문에 양식을 두 곳에서 관리할 필요가 없습니다. 사용 권한은 SharePoint를 통해 상속되고 관리됩니다. 무엇보다, PowerApps를 SharePoint와 통합하면 분석 보고서, 조건부 서식 지정을 위한 간편한 가리킨 다음 클릭(point-and-click) 규칙 및 다른 데이터 소스에 연결과 같은 여러 가지 강력한 기능에 액세스할 수 있습니다.

사용자 지정을 시작할 준비가 되셨나요? 이제 시작하겠습니다.

> [!NOTE]
> 이 기능은 SharePoint 고객에게 단계적으로 제공됩니다. 현재 SharePoint 목록에 **양식 사용자 지정** 옵션이 표시되지 않더라도 곧 표시될 예정입니다.

## <a name="create-a-custom-list-form-app-in-powerapps"></a>PowerApps에서 사용자 지정 목록 양식 앱 만들기

> [!NOTE]
> PowerApps에서 지원하지 않는 데이터 형식이 SharePoint 목록에 포함되어 있으면 **양식 사용자 지정** 옵션을 사용할 수 없거나 제대로 작동하지 않을 수 있습니다.

SharePoint 목록의 명령 모음에서 **PowerApps**를 클릭하거나 탭한 다음 **양식 사용자 지정**을 클릭하거나 탭합니다. 이렇게 하면 브라우저에 웹용 PowerApps Studio가 열리고 다음 예제와 같이 PowerApps에서 단일 화면 양식 앱이 생성됩니다.

![단일 화면 양식 앱](./media/customize-list-form/list-form-app.png)

언제든지 SharePoint 목록으로 돌아가려면 웹용 PowerApps Studio의 왼쪽 위 모서리에서 **SharePoint로 돌아가기**를 클릭하거나 탭합니다.

## <a name="customize-the-list-form"></a>목록 양식 사용자 지정

PowerApps는 양식을 사용자 지정하는 다양한 방법을 제공합니다. 예를 들어 레이아웃을 변경하고, 텍스트에 서식을 지정하고, 이미지나 차트를 추가하고, 사용자 지정 데이터 유효성 검사를 추가하고, 규칙을 추가하거나, 추가 보기를 만들 수 있습니다.

양식에 보이지 않아야 하는 **AccountID** 필드가 있다고 가정하겠습니다.

![AccountID 필드 선택](./media/customize-list-form/select-card.png)

PowerApps에서는 필드 숨기기가 쉽습니다. 양식 사용자 지정 옵션에서 **AccountID** 확인란의 선택을 취소하기만 하면 됩니다.

![AccountID 확인란 선택 취소](./media/customize-list-form/checkbox.png)

필드를 숨기고 다른 양식을 변경하는 방법에 대한 단계별 지침은 [PowerApps에서 양식 사용자 지정](customize-forms-sharepoint.md)을 참조하세요.

## <a name="save-and-publish-the-list-form-back-to-sharepoint"></a>목록 양식을 저장하고 SharePoint에 다시 게시

1. 완료되면 **파일**을 클릭하거나 탭한 다음 **저장**을 클릭하거나 탭합니다. 이렇게 하면 PowerApps 양식 앱에 변경 내용이 저장됩니다.

1. 다른 사람이 사용할 수 있도록 SharePoint에 양식을 다시 게시하려면 **SharePoint에 게시**를 클릭하거나 탭합니다. 양식 공유에 대해 걱정하지 않아도 됩니다. 양식은 SharePoint 목록에서 사용 권한을 상속받습니다.

    ![SharePoint에 게시](./media/customize-list-form/publish-to-sharepoint.png)  

## <a name="view-your-list-form-in-sharepoint"></a>SharePoint에서 목록 양식 보기

1. 사용자 지정 양식을 보려면 **SharePoint로 돌아가기**를 클릭하거나 탭한 다음 SharePoint 목록에서 원하는 항목을 클릭하거나 탭합니다. 양식이 브라우저 창의 오른쪽에 인라인으로 열립니다.

    ![SharePoint에서 양식 인라인으로 열기](./media/customize-list-form/list-form-open.png)

1. [양식을 추가로 사용자 지정](sharepoint-form-integration.md)하려면 **사용자 지정**을 클릭하거나 탭한 다음 변경을 수행합니다. 완료되면 변경 사항을 저장해야 합니다.

    ![단추 사용자 지정](./media/customize-list-form/customize-button.png)

    사용자 지정 및 저장은 원하는 만큼 많이 수행할 수 있지만 변경 내용은 **SharePoint에 게시**를 클릭하거나 탭해야 SharePoint에 표시됩니다.

## <a name="toggle-between-using-the-default-sharepoint-form-and-the-custom-form"></a>기본 SharePoint 양식 사용과 사용자 지정 양식 사용 전환

1. SharePoint 목록에서 **설정**을 클릭하거나 탭하고 **목록 설정**을 클릭하거나 탭한 다음 **양식 설정**을 클릭하거나 탭합니다.

1. **양식 설정** 페이지에서 다음 중 하나를 클릭하거나 탭한 다음 **확인**을 클릭하거나 탭합니다.

    * **기본 SharePoint 양식 사용** - SharePoint는 목록에 기본 SharePoint 양식을 사용합니다.

    * **Use a custom form created in PowerApps**(PowerApps에서 만든 사용자 지정 양식 사용) - SharePoint는 PowerApps에서 사용자 지정한 양식을 사용합니다. (또는 웹용 PowerApps Studio의 **저장** 페이지에서 양식을 다시 게시할 수 있습니다.)

    필요에 따라 옵션을 앞뒤로 전환할 수 있습니다.

    ![양식 설정 옵션](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-list-form"></a>사용자 지정 목록 양식 삭제

1. SharePoint 목록에서 **설정**을 클릭하거나 탭하고 **목록 설정**을 클릭하거나 탭한 다음 **양식 설정**을 클릭하거나 탭합니다.

1. **양식 설정** 페이지에서 **기본 SharePoint 양식 사용**을 클릭하거나 탭한 다음 **Use a custom form created in PowerApps**(PowerApps에서 만든 사용자 지정 양식 사용) 옵션에서 **Delete custom form**(사용자 지정 양식 삭제)을 클릭하거나 탭합니다. 이렇게 하면 PowerApps에서 만든 사용자 지정 양식이 삭제되고 양식이 기본 SharePoint 양식으로 돌아갑니다.

    ![사용자 지정 양식 삭제](./media/customize-list-form/use-default-sharepoint.png)

## <a name="top-questions-about-list-form-customization"></a>목록 양식 사용자 지정에 대한 주요 질문

### <a name="customizing-forms-versus-creating-apps"></a>양식 사용자 지정 및 앱 생성

**Q:** 사용자 지정 목록 양식이 SharePoint나 PowerApps에서 만드는 독립 실행형 앱과 다른 점은 무엇인가요?

**A:** SharePoint에서 만드는 목록 양식 앱은 SharePoint 목록에서만 사용할 수 있는 특별한 유형의 PowerApps 앱입니다. 이러한 목록 양식 앱은 웹용 PowerApps Studio나 PowerApps Mobile의 앱 목록에 표시되지 않으며 SharePoint 목록 외부에서는 실행할 수 없습니다.

**Q:** 사용자 지정 목록 양식은 언제 만들고 독립 실행형 앱은 언제 만들어야 하나요?

**A:** 사용자가 SharePoint를 사용하여 양식에 액세스하도록 하고, 사용자가 목록 항목을 만들거나 보거나 편집하는 방식을 사용자 지정하려면, SharePoint 내에서 사용자 지정 목록 양식을 만드는 것이 좋습니다. 사용자를 위해 SharePoint 사이트와 독립적으로 사용할 수 있는 완전히 사용자 지정된 환경을 만들려면, 독립 실행형 응용 프로그램을 만드는 것이 좋습니다.

**Q:** 같은 목록에 대해 목록 양식을 사용자 지정하고 독립 실행형 응용 프로그램을 만들 수 있나요?

**A:** 예. 독립 실행형 앱과 사용자 지정 목록 양식은 서로 독립적이므로 개별적으로 사용자 지정하고 관리할 수 있습니다.

**Q:** 양식 목록을 사용자 지정하는 기능과 독립 실행형 앱을 사용자 지정하는 기능이 동일한가요?

**A:** 예. 독립 실행형 앱에서 하듯이 [컨트롤을 추가 및 구성](add-configure-controls.md)하거나, [사용 가능한 데이터 원본에 연결](add-data-connection.md)하거나, [자체 데이터 원본을 추가](register-custom-api.md)할 수 있습니다.

**Q:** 조직의 기본 환경 이외의 환경에서 사용자 지정 목록 양식을 만들 수 있나요?

**A:** 아니요. 현재 사용자 지정 목록 양식은 조직의 기본 PowerApps 환경에서만 만들 수 있습니다. 사용자 지정 목록 양식을 다른 환경에서 만들거나 다른 환경으로 마이그레이션할 수 없습니다.

### <a name="managing-your-custom-list-form"></a>사용자 지정 목록 양식 관리

**Q:** 다른 사람과 공유할 수 있는 내 목록 양식에 대한 직접 링크는 어떻게 얻을 수 있나요?

**A:** SharePoint 목록에서 양식을 연 다음 **링크 복사**를 클릭하거나 탭합니다.

**Q:** 내 변경 사항을 다른 사람에게 보이지 않으면서 내 목록 양식을 업데이트할 수 있나요?

**A:** 예. 양식을 원하는 만큼 변경하고 저장할 수 있지만 그 내용은 **[SharePoint에 게시](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint)**를 클릭하거나 탭할 때까지 다른 사람에게 보이지 않습니다.

**Q:** 목록 양식을 사용자 지정하다가 실수를 하면 이전 버전으로 되돌릴 수 있나요?

**A:** 예. 양식을 변경하고 변경 내용을 저장한 다음에 실수한 걸 깨닫게 되면, PowerApps를 사용하여 이전 버전의 양식으로 되돌릴 수 있습니다.

1. SharePoint 목록의 명령 모음에서 **PowerApps**를 클릭하거나 탭한 다음 **양식 사용자 지정**을 클릭하거나 탭합니다.

1. 웹용 PowerApps Studio에서 **파일**을 클릭하거나 탭한 다음 **저장** 페이지에서 **모든 버전 보기**를 클릭하거나 탭합니다. **버전** 페이지가 새 브라우저 탭에 열립니다.

    > [!NOTE]
    > **모든 버전 보기** 단추가 표시되지 않으면 **저장**을 클릭하거나 탭합니다. 그러면 단추가 표시됩니다.

1. **버전** 페이지나 브라우저 탭을 닫지 않고 다른 브라우저 탭의 **저장** 페이지로 돌아가서 왼쪽 탐색 창의 맨 위에 있는 화살표를 클릭하거나 탭한 다음 **SharePoint로 돌아가기**를 클릭하거나 탭하여 양식의 잠금을 해제하고 웹용 PowerApps Studio을 종료합니다.

1. 다른 브라우저 탭의 **버전** 페이지로 돌아가서 복원할 버전을 찾은 다음 **복원**을 클릭합니다.

    > [!NOTE]
    > 양식이 다른 사용자에 의해 잠겨 있어서 복원에 실패했다는 오류 메시지가 표시되면 해당 사용자가 양식의 잠금을 해제할 때까지 기다린 다음 다시 시도합니다.

**Q:** 사용자 지정 목록 양식을 한 목록에서 다른 목록으로 이동할 수 있나요?

**A:** 아니요. 이 기능은 현재 지원되지 않습니다.

### <a name="administering-your-custom-list-form"></a>사용자 지정 목록 양식 관리

**Q:** 사용자 지정 목록 양식을 다른 사람과 어떻게 공유하나요?

**A:** 양식을 공유할 필요가 없습니다. 양식은 SharePoint 목록에서 사용 권한을 상속받습니다. 사용자 지정을 완료한 후 [SharePoint에 다시 게시](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint)만 하면 다른 사람이 사용할 수 있습니다.

**Q:** 어떤 사람이 목록 양식을 사용자 지정할 수 있나요?

**A:** 연결된 목록을 관리, 디자인 또는 편집할 수 있는 SharePoint 권한을 가진 사람이면 가능합니다.

**Q:** 게스트 사용자가 사용자 지정 양식이 있는 목록에 액세스하면 어떻게 되나요?

**A:** PowerApps를 사용하여 사용자 지정된 목록 양식에 게스트 사용자가 액세스하려고 하면 오류 메시지가 표시됩니다.

**Q:** 관리자가 조직의 모든 사용자 지정 양식 목록을 얻으려면 어떻게 해야 하나요?

**A:** PowerApps의 테넌트 관리자이거나 조직의 기본 PowerApps 환경에 대해 환경 관리자 권한이 있는 경우 다음을 수행하십시오.

1. [PowerApps 관리 센터](https://admin.powerapps.com)로 이동하여 환경 목록에서 조직의 기본 환경을 선택합니다.

1. 기본 환경 페이지의 맨 위에서 **리소스**를 클릭하거나 탭합니다.

1. 앱 목록에서 **SharePoint 양식** 앱 유형이 있는 앱을 찾습니다. 이러한 항목이 사용자 지정 양식입니다.

    ![사용자 지정된 양식 목록](./media/customize-list-form/all-customized-forms.png)
