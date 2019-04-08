---
title: 캔버스 앱에서 데이터 연결 추가 | Microsoft Docs
description: 기존 캔버스 앱 또는 빈 앱에 데이터 연결 추가
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/06/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 28357a6187831e05fe27075b8b22514950215ab4
ms.sourcegitcommit: fc604f3e7f0399bdabee86ce94f67de49531a444
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545064"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>PowerApps의 캔버스 앱에 데이터 연결 추가

PowerApps에서 처음부터 앱을 빌드할 때 또는 기존 캔버스 앱에서 데이터 연결을 추가합니다. 앱은 SharePoint, Salesforce, OneDrive 또는 [다른 많은 데이터 원본](connections-list.md)에 연결할 수 있습니다.

이 문서 이후 [다음 단계](#next-steps)는 다음 예와 같이 앱에서 데이터 원본의 데이터를 표시하고 관리하기 위한 것입니다.

* OneDrive에 연결하고 사용자 앱에서 Excel 통합 문서의 데이터를 관리합니다.
* Twilio에 연결하고 사용자 앱에서 SMS 메시지를 보냅니다.
* SQL Server에 연결하고 사용자 앱에서 테이블을 업데이트합니다.

## <a name="prerequisites"></a>필수 조건

PowerApps에 [등록](../signup-for-powerapps.md)한 다음, 등록에 사용한 동일한 자격 증명을 입력하여 [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)합니다.

## <a name="open-a-blank-app"></a>비어 있는 앱 열기

1. **홈** 탭에서 **빈 페이지의 캔버스 앱**을 선택합니다.

1. 앱에 대한 이름을 지정하고 **만들기**를 선택합니다.

1. **PowerApps Studio 시작** 대화 상자에서 **건너뛰기**를 선택합니다.

## <a name="add-data-source"></a>데이터 원본 추가

1. 가운데 창에서 **데이터** 창을 열기 위해 **데이터에 연결**을 선택합니다.

    컨트롤이 화면에 이미 포함된 기존 앱에서는 동일한 창을 열기 위해 **보기** > **데이터 원본**을 선택합니다.

1. **데이터 원본 추가**를 선택합니다.

1. 원하는 연결이 연결 목록에 포함되어 있으면, 앱에 추가하기 위해 선택합니다. 그렇지 않은 경우 다음 단계로 건너뜁니다.

    ![기존 연결 선택](./media/add-data-connection/choose-existing-connection.png)

1. 연결의 목록을 표시하기 위해 **새 연결**을 선택합니다.

    ![연결 추가](./media/add-data-connection/add-connection.png)

1. 검색 창에서 원하는 연결의 처음 몇 문자를 입력 또는 붙여넣은 후, 연결이 표시되면 선택합니다.

    ![연결 검색](./media/add-data-connection/search-connections.png)

1. **만들기**를 선택하여 연결을 만들고 앱에 추가합니다.

    **Office 365 Outlook**과 같은 일부 커넥터는 추가 단계가 필요하지 않으며 즉시 데이터를 표시할 수 있습니다. 다른 커넥터의 경우 자격 증명을 제공하고, 데이터의 특정 집합을 지정하거나 다른 단계를 수행하라는 메시지가 표시됩니다. 예를 들어 [SharePoint](connections/connection-sharepoint-online.md) 및 [SQL Server](connections/connection-azure-sqldatabase.md)는 사용하기 전에 추가 정보가 필요합니다.

## <a name="identify-or-change-a-data-source"></a>데이터 원본 식별 또는 변경
앱을 업데이트하는 경우 갤러리, 양식 또는 다른 컨트롤에 표시되는 데이터의 원본을 식별하거나 변경해야 할 수 있습니다. 예를 들어 다른 사용자가 만들거나 자신이 오래전에 만든 앱을 업데이트할 때 데이터 원본을 식별해야 할 수 있습니다.

1. 데이터 원본을 식별하거나 변경하려는 갤러리와 같은 컨트롤을 선택합니다.

    데이터 원본의 이름이 오른쪽 창의 **속성** 탭에 나타납니다.

    ![연결 확인](./media/add-data-connection/identify-connection.png)

1. 데이터 원본에 대한 자세한 정보를 표시하거나 변경하려면 해당 이름 옆에 있는 아래쪽 화살표를 선택합니다.

    현재 데이터 원본에 대한 자세한 정보가 표시되고, 다른 데이터 원본을 선택하거나 만들 수 있습니다.

    ![연결 변경](./media/add-data-connection/change-connection.png)

## <a name="next-steps"></a>다음 단계

* Excel, SharePoint 또는 SQL Server와 같은 원본에서 데이터를 표시하고 업데이트하려면 [갤러리를 추가](add-gallery.md)하고 [폼을 추가](add-form.md)합니다.
* 다른 원본에 있는 데이터의 경우, [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) 및 [Microsoft Translator](connections/connection-microsoft-translator.md)에 대한 데이터와 같이 커넥터 특정 기능을 사용합니다.
