---
title: 앱에서 흐름 시작 | Microsoft Docs
description: 앱에서 사용자의 단추 선택과 같은 이벤트가 발생한 후 하나 이상의 작업을 수행하는 흐름을 만듭니다.
services: ''
suite: powerapps
documentationcenter: ''
author: stepsic-microsoft-com
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/05/2017
ms.author: sharik
ms.openlocfilehash: 378394fe0c42d0418a62974c26b217ab473d40ed
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="start-a-flow-in-an-app"></a>앱에서 흐름 시작
Microsoft Flow를 사용하여 앱에서 이벤트가 발생할 때 하나 이상의 작업을 수행하는 논리를 만들 수 있습니다. 예를 들어 사용자가 단추를 선택하면 SharePoint 목록에 항목을 만들거나, 전자 메일 또는 모임 요청을 보내거나, 클라우드에 파일을 추가하거나, 이러한 모든 작업을 추가하도록 해당 단추를 구성합니다. 흐름을 시작하도록 앱에서 모든 컨트롤을 구성하여 PowerApps를 닫은 경우에도 계속 실행되도록 할 수 있습니다.

## <a name="prerequisites"></a>필수 조건

* PowerApps에 [등록](../signup-for-powerapps.md)하고 다음 단계 중 하나를 수행합니다.

  * [Windows Store](http://aka.ms/powerappsinstall)에서 Windows용 PowerApps Studio를 설치하고 연 다음 등록 시에 사용한 것과 동일한 자격 증명으로 로그인합니다.
  * [powerapps.com](http://web.powerapps.com)에서 왼쪽 아래에 있는 **새 앱**을 클릭하거나 탭하여 웹용 PowerApps Studio를 엽니다.
* [컨트롤을 구성](add-configure-controls.md)하는 방법을 알아봅니다.

## <a name="create-a-flow"></a>흐름 만들기
1. [powerapps.com](http://web.powerapps.com)에 로그인한 다음 왼쪽 탐색 모음에서 **흐름**을 선택합니다.

2. **내 흐름** 페이지에서 **빈 페이지에서 만들기**를 선택합니다.

    ![템플릿을 사용하지 않고 흐름을 만드는 옵션](./media/using-logic-flows/create-from-blank.png)

    **PowerApps**가 기본 트리거로 추가됩니다.

    ![흐름을 시작하는 트리거로 추가된 PowerApps](./media/using-logic-flows/set-trigger.png)

3. **새 단계**를 선택한 다음 **작업 추가**을 선택합니다.

    ![작업을 추가하는 옵션](./media/using-logic-flows/add-action.png)

4. **모든 서비스 및 작업 검색** 상자에서 다음 예와 같이 흐름에 대한 작업을 지정합니다.

   1. 상자에서 **SharePoint**를 입력한 다음 **작업** 아래의 목록에서 **SharePoint - 항목 만들기**를 선택합니다.

       ![SharePoint 항목을 만드는 옵션](./media/using-logic-flows/create-sharepoint-item.png)

   2. 메시지가 표시되면 SharePoint에 연결하기 위한 자격 증명을 제공합니다.

   3. **사이트 주소** 상자에서 목록이 포함된 SharePoint Online 사이트의 URL을 입력하거나 붙여넣습니다.

       > [!NOTE]
> 목록이 포함되지 않은 사이트의 URL을 지정합니다.

   4. **목록 이름** 상자에서 사용하려는 목록을 선택합니다.

   5. **제목** 상자를 클릭하거나 탭한 다음 **동적 콘텐츠 추가**를 선택합니다.

       ![[제목] 필드에서 [PowerApps에서 질문] 매개 변수 추가](./media/using-logic-flows/ask-in-powerapps.png)

   6. 매개 변수 목록에서 **PowerApps에서 질문**을 선택합니다.

       ![매개 변수 추가](./media/using-logic-flows/add-parameter.png)

5. (선택 사항) 지정한 주소로 승인 메일을 보내거나 다른 데이터 원본에서 관련 항목을 만드는 것과 같은 추가 작업을 하나 이상 지정합니다.

6. 화면 위쪽에서 흐름 이름을 입력하거나 붙여넣은 다음 **흐름 만들기**를 선택합니다.

    ![흐름 이름 지정 및 저장](./media/using-logic-flows/name-flow.png)

## <a name="add-a-flow-to-an-app"></a>앱에 흐름 추가
1. PowerApps의 **파일** 메뉴에서 **새로 만들기**를 선택합니다.

2. **빈 앱** 타일에서 **전화 레이아웃**을 선택합니다.

3. **[텍스트 입력](controls/control-text-input.md)** 컨트롤을 추가하고, **RecordTitle**이라는 이름을 지정합니다.

4. **[단추](controls/control-button.md)** 컨트롤을 추가하고 **RecordTitle** 아래로 이동합니다.

5. **[단추](controls/control-button.md)** 컨트롤을 선택하고 **작업** 탭에서 **흐름**을 선택합니다.

    ![[작업] 탭의 [흐름] 옵션](./media/using-logic-flows/action-tab.png)

6. 표시되는 창에서 이전 절차에서 만든 흐름을 선택합니다.

    > [!NOTE]
> 만든 흐름을 사용할 수 없는 경우 PowerApps가 흐름을 만든 환경으로 설정되어 있는지 확인합니다.

    ![사용자 지정 창에서 흐름 추가](./media/using-logic-flows/add-flow-from-pane.png)

7. 수식 입력줄에서 자동으로 추가된 수식 끝에 **(RecordTitle.Text)**를 입력하거나 붙여넣습니다.

    ![흐름이 포함된 OnSelect 속성](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>흐름 테스트
1. F5 키를 누르거나 오른쪽 위 모서리의 화살표를 선택하여 [미리 보기]를 엽니다.

    ![흐름이 포함된 OnSelect 속성](./media/using-logic-flows/open-preview.png)

2. **RecordTitle**에 텍스트를 입력하거나 붙여넣은 다음 **[단추](controls/control-button.md)** 컨트롤을 클릭하거나 탭합니다.

    제목으로 지정한 텍스트를 사용하여 지정한 목록에 SharePoint 항목이 만들어집니다. 흐름이 실행될 때 목록이 열려 있었으면 브라우저 창을 새로 고쳐 변경 내용을 표시합니다.
