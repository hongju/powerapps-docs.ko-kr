---
title: 커넥터 개요 | Microsoft Docs
description: 앱 빌드에 사용 가능한 모든 연결 개요
documentationcenter: ''
author: lancedMicrosoft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 08/28/2017
ms.author: lanced
ms.openlocfilehash: dc68b0f404c2a8d636deb4e77c2ada4582ed3a37
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="overview-of-connectors-for-powerapps"></a>PowerApps용 커넥터의 개요
데이터는 PowerApps에서 빌드하는 앱을 포함해 대부분 앱의 핵심입니다. 데이터는 *데이터 원본*에 저장되며 *연결*을 만들어 해당 데이터를 앱으로 구현합니다. 이 연결은 특정 *커넥터*를 사용하여 데이터 원본과 데이터를 교환합니다. PowerApps에는 SharePoint, SQL Server, Office 365, Salesforce, Twitter 등을 포함한 많은 인기 서비스 및 온-프레미스 데이터 원본용 커넥터가 있습니다. 앱에 데이터 추가를 시작하려면 [PowerApps에서 데이터 연결 추가](add-data-connection.md)를 참조하세요.

다음 표에는 가장 인기 있는 커넥터에 대한 자세한 정보의 링크가 있습니다. 커넥터의 전체 목록은 [모든 커넥터](#all-connectors)를 참조하세요.

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![일반 데이터 서비스](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![비즈니스용 OneDrive](./media/connections-list/onedrive.png) |[**비즈니스용 OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365 사용자](./media/connections-list/office365.png) |[**Office 365 사용자**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="types-of-connectors"></a>커넥터 유형
PowerApps에 두 가지 유형의 커넥터, 즉 위에 나와 있는 것과 같은 *표준 커넥터*와 *사용자 지정 커넥터*가 있습니다. PowerApps에서 표준 커넥터로 지원하는 데이터 원본에 연결할 경우 해당 커넥터를 사용합니다. 사용자가 빌드한 서비스와 같이 다른 소스에 연결해야 할 경우 [사용자 지정 커넥터 등록 및 사용](../canvas-apps/register-custom-api.md)을 참조합니다.

표준 커넥터는 연결하는 데이터 소스의 유형과 해당 데이터 원본에서 데이터를 반환하는 방식에 따라 다르게 동작합니다.

* 일부 커넥터 SharePoint, SQL Server, Excel 등의 테이블 형식 데이터 원본과 작동합니다. 이러한 데이터 원본 작업 시 데이터가 PowerApps에 표로 반환됩니다. PowerApps는 이러한 자체 함수(예: [Patch()](functions/function-patch.md), [Collect()](functions/function-clear-collect-clearcollect.md), [Update()](functions/function-update-updateif.md))를 사용하고 이 데이터와 상호 작용합니다. 또한 테이블 형식 데이터가 양식 및 갤러리에서 사용하기 쉽고, 테이블의 필드가 갤러리 또는 양식의 필드로 표시됩니다. 자세한 내용은 다음 문서를 참조하세요.

    [PowerApps 데이터 원본에 대한 이해](working-with-data-sources.md)

    [Excel 데이터에서 앱 생성](get-started-create-from-data.md)

    [앱을 처음부터 만들기](get-started-create-from-blank.md)

    > [!NOTE]
> Excel에서 데이터에 연결하려면 통합 문서는 OneDrive와 같은 클라우드 저장소 서비스에서 호스팅해야 합니다. 자세한 내용은 [PowerApps에서 클라우드 저장소에 연결](connections/cloud-storage-blob-connections.md)을 참조하세요.

* 다른 커넥터는 Twitter, Facebook 및 Office 365 Outlook 등의 함수 기반 데이터 원본과 작용합니다. 이러한 데이터 원본 작업 시 데이터는 기본 서비스의 특정 함수 호출에 기반하여 PowerApps로 반환됩니다. 예를 들어 Twitter 커넥터를 통해 `Twitter.MyFollowers()`를 호출하여 팔로워 목록을 반환합니다. 이 데이터를 양식 또는 갤러리에서 사용할 수 있지만, 테이블 형식 데이터보다 약간 더 많은 작업이 필요합니다. 자세한 내용은 [PowerApps에서 Twitter에 연결](connections/connection-twitter.md)을 참조하세요.

## <a name="all-connectors"></a>모든 커넥터
다음 표에 모든 커넥터가 나열됩니다. 각 커넥터에 대한 자세한 내용은 [Microsoft Connector Reference](https://docs.microsoft.com/connectors/)를 참조하세요. 프리미엄 커넥터는 PowerApps 요금제 1 또는 요금제 2가 필요합니다. 자세한 내용은 [PowerApps 가요금제](https://powerapps.microsoft.com/pricing/)를 참조하세요.

| &nbsp; | &nbsp; |
| --- | --- |
| 10to8 Appointment Scheduling<br>Act!<br>Adobe Creative Cloud ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Adobe Sign<br>Amazon Redshift ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Apache Impala ![프리미엄 커넥터](./media/connections-list/premium.png)<br>AppFigures<br>Approvals<br>Asana<br>AWeber ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Azure AD<br>Azure Application Insights<br>Azure Automation<br>Azure Blob Storage<br>Azure Cosmos DB<br>Azure Data Lake<br>Azure Event Grid<br>Azure Event Grid Publish<br>Azure File Storage<br>Azure Log Analytics<br>Azure Log Analytics Data Collector<br>Azure Queues<br>Azure Resource Manager<br>Azure Table Storage<br>Basecamp 2<br>Basecamp 3<br>Benchmark Email ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Bing Maps<br>Bing Search<br>Bitbucket ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Bitly<br>Bizzy (H3 Solutions, Inc.)<br>Blogger<br>Box<br>bttn<br>Buffer<br>Calendly ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Campfire<br>Capsule CRM ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Chatter ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Cognito Forms<br>일반 데이터 서비스 ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Computer Vision API<br>Content Conversion<br>Content Moderator<br>DB2 ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Disqus<br>DocFusion365 – SP ![프리미엄 커넥터](./media/connections-list/premium.png)<br>DocuSign ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Dropbox<br>Dynamics 365<br>Dynamics 365 for Financials<br>Dynamics for Operations<br>Dynamics NAV<br>Easy Redmine ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Elastic Forms<br>Event Hubs<br>Eventbrite ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Excel<br>Face API<br>Facebook<br>File System<br>Flic<br>FlowForma ![프리미엄 커넥터](./media/connections-list/premium.png)<br>FreshBooks ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Freshdesk<br>Freshservice ![프리미엄 커넥터](./media/connections-list/premium.png)<br>FTP<br>GitHub<br>Gmail<br>Google 캘린더<br>Google 연락처<br>Google 드라이브<br>Google Sheets<br>Google Tasks<br>GoToMeeting ![프리미엄 커넥터](./media/connections-list/premium.png)<br>GoToTraining ![프리미엄 커넥터](./media/connections-list/premium.png)<br>GoToWebinar ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Harvest ![프리미엄 커넥터](./media/connections-list/premium.png)<br>HelloSign ![프리미엄 커넥터](./media/connections-list/premium.png)<br>HipChat<br>HTTP with Azure AD ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Informix ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Infusionsoft ![프리미엄 커넥터](./media/connections-list/premium.png) |Inoreader<br>Insightly<br>Instagram<br>Instapaper<br>Intercom<br>JIRA ![프리미엄 커넥터](./media/connections-list/premium.png)<br>JotForm ![프리미엄 커넥터](./media/connections-list/premium.png)<br>LeanKit ![프리미엄 커넥터](./media/connections-list/premium.png)<br>LinkedIn<br>LiveChat ![프리미엄 커넥터](./media/connections-list/premium.png)<br>LUIS<br>메일<br>MailChimp ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Mandrill ![프리미엄 커넥터](./media/connections-list/premium.png)<br>중간<br>Microsoft Forms<br>Microsoft StaffHub<br>Microsoft Teams<br>Microsoft Translator<br>MSN 날씨<br>Muhimbi PDF<br>MySQL ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Nexmo ![프리미엄 커넥터](./media/connections-list/premium.png)<br>알림<br>Office 365 예약<br>Office 365 그룹<br>Office 365 Outlook<br>Office 365 사용자<br>Office 365 비디오<br>OneDrive<br>비즈니스용 OneDrive<br>OneNote(비즈니스)<br>Oracle Database ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Outlook Customer Manager<br>Outlook 작업<br>Outlook.com<br>PagerDuty<br>Parserr<br>Paylocity ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Pinterest<br>Pipedrive ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Pitney Bowes Data Validation ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Pivotal Tracker<br>Planner<br>Plivo ![프리미엄 커넥터](./media/connections-list/premium.png)<br>PostgreSQL ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Power BI<br>PowerApps 알림 ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Project Online<br>Redmine<br>RSS<br>Salesforce ![프리미엄 커넥터](./media/connections-list/premium.png)<br>SendGrid<br>Service Bus<br>SFTP<br>SharePoint<br>비즈니스용 Skype<br>Slack<br>SmartSheet<br>SMTP<br>SparkPost<br>SQL Server<br>Stripe ![프리미엄 커넥터](./media/connections-list/premium.png)<br>SurveyMonkey ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Teamwork Projects ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Teradata ![프리미엄 커넥터](./media/connections-list/premium.png)<br>텍스트 분석<br>Todoist<br>Toodledo<br>Trello<br>Twilio<br>Twitter<br>TypeForm<br>UserVoice ![프리미엄 커넥터](./media/connections-list/premium.png)<br>Video Indexer<br>Vimeo<br>Visual Studio Team Services<br>WebMerge<br>WordPress<br>Wunderlist<br>Yammer<br>YouTube<br>Zendesk ![프리미엄 커넥터](./media/connections-list/premium.png) |

특정 커넥터에 관해 질문이 있는 경우 [PowerApps 포럼](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1)을 사용해 주세요. 새 커넥터에 대한 아이디어나 개선을 위한 제한 사항이 있다면 [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas)를 사용하세요.
