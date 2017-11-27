---
title: "앱에서 데이터 연결 추가 | Microsoft Docs"
description: "기존 앱 또는 새 앱에서 데이터 연결 추가"
services: 
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/02/2017
ms.author: archanan
ms.openlocfilehash: 3fe41ceddcce1ee8d1daa9b3532b4c92a94d8eee
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="add-a-data-connection-in-powerapps"></a>PowerApps에서 데이터 연결 추가
PowerApps에서 처음부터 앱을 빌드할 때 또는 기존 앱에서 데이터 연결을 추가합니다. 이 토픽에서는 PowerApps Studio를 사용하지만 [연결 관리](add-manage-connections.md) 토픽에서 설명된 대로 [powerapps.com](https://web.powerapps.com)을 사용할 수도 있습니다.

앱의 데이터 연결은 SharePoint, Salesforce, OneDrive 또는 [다른 많은 데이터 소스 중 하나](connections-list.md)에 연결할 수 있습니다.

이 문서 이후 [다음 단계](#next-steps)는 다음 예와 같이 앱에서 데이터 원본의 데이터를 표시하고 관리하기 위한 것입니다.

* OneDrive에 연결하고 사용자 앱에서 Excel 통합 문서의 데이터를 관리합니다.
* Twilio에 연결하고 사용자 앱에서 SMS 메시지를 보냅니다.
* SQL Server에 연결하고 사용자 앱에서 테이블을 업데이트합니다.

## <a name="prerequisites"></a>필수 조건
PowerApps에 [등록](signup-for-powerapps.md)하여 [설치](http://aka.ms/powerappsinstall)하고 연 다음 등록 시 사용했던 동일한 자격 증명으로 로그인합니다.

## <a name="background-on-data-connections"></a>데이터 연결에 대한 배경
대부분의 PowerApps 앱은 클라우드 서비스에 저장된 **데이터 원본**이라는 외부 정보를 사용합니다. 비즈니스용 OneDrive에 저장된 Excel 파일의 테이블이 일반적인 예입니다. 앱에서 **커넥터**를 사용하여 이러한 데이터 원본에 액세스할 수 있습니다.

가장 일반적인 데이터 원본은 정보를 검색하고 저장하는 데 사용할 수 있는 테이블입니다. 데이터 원본에 대한 커넥터를 사용하여 데이터를 비즈니스용 OneDrive, DropBox, SQL Server 등과 같은 클라우드 서비스에 저장할 수 있는 Microsoft Excel 통합 문서, SharePoint 목록, SQL 테이블 및 다른 많은 형식으로 읽고 쓸 수 있습니다.

테이블 이외의 데이터 원본에는 전자 메일, 일정, Twitter 및 알림이 포함됩니다.

**[갤러리](controls/control-gallery.md)**, **[폼 표시](controls/control-form-detail.md)** 및 **[폼 편집](controls/control-form-detail.md)** 컨트롤을 사용하면 데이터 원본의 데이터를 읽고 쓸 수 있는 앱을 손쉽게 만들 수 있습니다. 시작하려면 [데이터 폼 이해](working-with-forms.md)를 읽어 보세요.

## <a name="add-a-connection"></a>연결 추가
1. (화면의 왼쪽 가장자리에 있는) **파일** 메뉴에서 **새로 만들기**를 클릭하거나 탭합니다.
   
    ![파일 메뉴의 새 옵션](./media/add-data-connection/file-new.png)
2. **비어 있는 앱** 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.
   
    ![앱을 처음부터 만들기](./media/add-data-connection/blank-app.png)
3. 가운데 창에서 **데이터에 연결**을 클릭하거나 탭합니다.
4. **데이터** 창의 연결 목록에 원하는 항목이 포함되어 있는 경우 해당 항목을 클릭하거나 탭하여 앱에 추가합니다. 그렇지 않은 경우 다음 단계를 건너뜁니다.
   
    ![데이터 원본 추가](./media/add-data-connection/choose-existing-connections.png)
5. **새 연결**을 클릭하거나 탭하여 커넥터의 목록을 표시합니다.
   
    ![연결 추가](./media/add-data-connection/new-connection.png)
6. 만들려는 연결의 유형이 표시될 때까지 커넥터 목록을 스크롤한 다음(예: **Office 365 Outlook**) 해당 항목을 클릭하거나 탭합니다.
   
    ![연결 선택](./media/add-data-connection/choose-connection.png)
7. **만들기**를 클릭하거나 탭하여 연결을 만들고 앱에 추가합니다.
   
    **Microsoft Translator**와 같은 일부 커넥터는 추가 단계가 필요하지 않으며 즉시 데이터를 표시할 수 있습니다. 다른 커넥터의 경우 자격 증명을 제공하고, 데이터의 특정 집합을 지정하거나 다른 단계를 수행하라는 메시지가 표시됩니다. 예를 들어 [SharePoint](connections/connection-sharepoint-online.md) 및 [SQL Server](connections/connection-azure-sqldatabase.md)는 사용하기 전에 추가 정보가 필요합니다.

## <a name="view-or-change-a-data-source"></a>데이터 원본 보기 또는 변경
앱을 업데이트하는 경우 갤러리, 폼 또는 **Item** 속성이 있는 다른 컨트롤에 표시되는 데이터의 원본을 식별하거나 변경해야 할 수 있습니다. 예를 들어 다른 사람이 만든 앱에서 작업하거나 이전에 구성한 데이터 원본을 상기시키고자 할 수 있습니다.

1. 데이터 원본을 식별하려는 컨트롤을 선택합니다.
   
    예를 들어 왼쪽 가장자리 근처에 있는 화면 및 컨트롤의 계층적 목록에 있는 항목을 클릭하거나 탭하여 갤러리(갤러리 내 컨트롤이 아님)를 선택합니다.
   
    데이터 원본의 이름이 오른쪽 창의 **속성** 탭에 나타납니다.
   
    ![속성 탭에서 데이터 원본](./media/add-data-connection/properties-tab.png)
2. 데이터 원본에 대한 자세한 정보를 보거나 이를 변경하려면 오른쪽 창에서 **데이터**를 클릭하거나 탭합니다.
   
    ![데이터 창](./media/add-data-connection/data-pane.png)
3. 데이터 원본을 변경하려면 데이터 원본 옆의 아래쪽 화살표를 클릭하거나 탭한 다음 다른 원본을 선택하거나 만듭니다.

## <a name="next-steps"></a>다음 단계
* Excel, SharePoint 또는 SQL Server와 같은 원본에서 데이터를 표시하고 업데이트하려면 [갤러리를 추가](add-gallery.md)하고 [폼을 추가](add-form.md)합니다.
* 다른 원본에 있는 데이터의 경우, [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) 및 [Microsoft Translator](connections/connection-microsoft-translator.md)에 대한 데이터와 같이 커넥터 특정 기능을 사용합니다.

