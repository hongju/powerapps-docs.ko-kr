---
title: 앱에서 데이터 연결 추가 | Microsoft Docs
description: 기존 앱 또는 새 앱에서 데이터 연결 추가
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/06/2018
ms.author: lanced
ms.openlocfilehash: 734e36b00658455198b64317b6f068c0018755a4
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39018494"
---
# <a name="add-a-data-connection-in-powerapps"></a>PowerApps에서 데이터 연결 추가
PowerApps에서 처음부터 앱을 빌드할 때 또는 기존 앱에서 데이터 연결을 추가합니다. 앱은 SharePoint, Salesforce, OneDrive 또는 [다른 많은 데이터 원본](connections-list.md)에 연결할 수 있습니다.

이 문서 이후 [다음 단계](#next-steps)는 다음 예와 같이 앱에서 데이터 원본의 데이터를 표시하고 관리하기 위한 것입니다.

* OneDrive에 연결하고 사용자 앱에서 Excel 통합 문서의 데이터를 관리합니다.
* Twilio에 연결하고 사용자 앱에서 SMS 메시지를 보냅니다.
* SQL Server에 연결하고 사용자 앱에서 테이블을 업데이트합니다.

## <a name="prerequisites"></a>필수 조건
PowerApps에 [등록](../signup-for-powerapps.md)한 다음, 등록에 사용한 동일한 자격 증명을 입력하여 [로그인](http://web.powerapps.com)합니다.

## <a name="add-a-data-source"></a>데이터 원본 추가
1. **홈** 탭에서 **비어 있는 상태에서 시작** 타일을 마우스로 가리킨 다음, **이 앱 만들기**를 선택합니다.

    ![앱을 처음부터 만들기](./media/add-data-connection/blank-app-tile.png)

1. **PowerApps Studio 시작** 대화 상자에서 **건너뛰기**를 선택합니다.

3. 가운데 창에서 **데이터에 연결**을 클릭하거나 탭합니다.

4. **데이터** 창의 연결 목록에 원하는 항목이 포함되어 있는 경우 해당 항목을 선택하여 앱에 추가합니다. 그렇지 않은 경우 다음 단계를 건너뜁니다.

    ![데이터 원본 추가](./media/add-data-connection/choose-existing-connections.png)

5. **새 연결**을 선택하여 커넥터의 목록을 표시합니다.

    ![연결 추가](./media/add-data-connection/new-connection.png)

6. 만들려는 연결의 유형이 표시될 때까지 커넥터 목록을 스크롤한 다음(예: **Office 365 Outlook**), 해당 항목을 선택합니다.

    ![연결 선택](./media/add-data-connection/choose-connection.png)

7. **만들기**를 선택하여 연결을 만들고 앱에 추가합니다.

    **Office 365 Outlook**과 같은 일부 커넥터는 추가 단계가 필요하지 않으며 즉시 데이터를 표시할 수 있습니다. 다른 커넥터의 경우 자격 증명을 제공하고, 데이터의 특정 집합을 지정하거나 다른 단계를 수행하라는 메시지가 표시됩니다. 예를 들어 [SharePoint](connections/connection-sharepoint-online.md) 및 [SQL Server](connections/connection-azure-sqldatabase.md)는 사용하기 전에 추가 정보가 필요합니다.

## <a name="add-another-data-source"></a>다른 데이터 원본 추가
1. 데이터 원본을 추가할 컨트롤을 추가합니다.

    컨트롤에는 갤러리 및 목록 상자에 포함된 것 같은 **Items** 속성이나 양식에 포함된 것 같은 **Item** 속성이 있어야 합니다.

1. **데이터** 창(자동으로 열림)에서 **데이터 원본** 아래에 있는 목록을 열고 **데이터 원본 추가**를 선택합니다.

1. 4단계부터 시작하여 이전 절차를 수행합니다.

## <a name="identify-or-change-a-data-source"></a>데이터 원본 식별 또는 변경
앱을 업데이트하는 경우 갤러리, 양식 또는 다른 컨트롤에 표시되는 데이터의 원본을 식별하거나 변경해야 할 수 있습니다. 예를 들어 다른 사용자가 만들거나 자신이 오래전에 만든 앱을 업데이트할 때 데이터 원본을 식별해야 할 수 있습니다.

1. 데이터 원본을 식별 또는 변경하려는 컨트롤을 선택합니다.

    예를 들어 왼쪽 가장자리 근처에 있는 화면 및 컨트롤의 계층적 목록에 있는 항목을 클릭하거나 탭하여 갤러리(갤러리 내 컨트롤이 아님)를 선택합니다.

    데이터 원본의 이름이 오른쪽 창의 **속성** 탭에 나타납니다.

2. 데이터 원본을 선택하여 변경하거나 이에 대한 추가 정보를 표시합니다.

    ![데이터 창](./media/add-data-connection/data-pane.png)

3. 데이터 원본을 변경하려면 데이터 원본 목록을 열고 다른 원본을 선택하거나 만듭니다.

     ![데이터 창](./media/add-data-connection/datasource-list.png)

## <a name="next-steps"></a>다음 단계
* Excel, SharePoint 또는 SQL Server와 같은 원본에서 데이터를 표시하고 업데이트하려면 [갤러리를 추가](add-gallery.md)하고 [폼을 추가](add-form.md)합니다.
* 다른 원본에 있는 데이터의 경우, [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) 및 [Microsoft Translator](connections/connection-microsoft-translator.md)에 대한 데이터와 같이 커넥터 특정 기능을 사용합니다.
