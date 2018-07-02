---
title: Common Data Service for Apps 개발자 개요 | Microsoft Docs
description: 개발자가 Common Data Service for Apps를 사용하여 값을 추가하는 방법에 대해 알아봅니다.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
ms.openlocfilehash: c07a6505c0a08eca706c08cc2e4d607cd5322dfe
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36949256"
---
# <a name="common-data-service-for-apps-developer-overview"></a>Common Data Service for Apps 개발자 개요
PowerApps는 사용자, 비즈니스, ISV(독립 소프트웨어 공급업체) 및 SI(시스템 통합자)에게 기간 업무 앱을 빌드할 수 있는 강력한 플랫폼을 제공합니다. 이번 릴리스에서 PowerApps에 새로 추가된 것은 Common Data Service의 확장입니다. 이는 현재 Common Data Service for Apps라고 하며 Dynamics 365 for Sales, Marketing, Customer Service를 지원하는 Dynamics 365 플랫폼의 핵심 기능을 포함하고 있습니다.


## <a name="get-started"></a>시작하기
Dynamics 365 for Sales, Marketing 또는 Customer Service 앱을 이미 경험하신 분들은 그 경험을 적용하여 Common Data Service for Apps를 사용자 지정하고 확장할 수 있습니다.

Dynamics 365 for Sales, Marketing 또는 Customer Service 앱을 처음 접하는 분들은 다음 항목을 통해 Common Data Service for Apps를 시작하는 데 도움이 되는 중요한 개념의 개요를 알아볼 수 있습니다.

> [!NOTE]
> - 모델 기반 앱은 Common Data Service for Apps에 연결됩니다. 개발자가 응용 프로그램 수준에서 값을 추가하는 방법은 [모델 기반 앱 개발자 개요](../model-driven-apps/overview.md)를 참조하세요. 이 섹션의 콘텐츠는 개발자가 서비스 수준에서 수행할 수 있는 확장만 참조합니다. 
> - Common Data Service for Apps는 Dynamics 365 for Sales, Marketing 또는 Customer Service 앱에 의해 사용되는 플랫폼과 동일하므로 [Dynamics 365 Customer Engagement 개발자 가이드](/dynamics365/customer-engagement/developer/developer-guide)에서 개발자를 위한 더 완벽한 정보를 찾을 수 있습니다. 이러한 항목에서는 개발자 가이드 및 기타 가이드에 대한 링크가 포함된 개요를 제공하여 자세한 내용을 확인할 수 있도록 합니다.


## <a name="tools-and-resources-for-developers"></a>개발자를 위한 도구 및 리소스

개발자는 Common Data Service for Apps를 사용하여 솔루션을 작업할 때 다음 도구와 리소스를 사용하게 됩니다.

### <a name="tools-available-for-download-from-nuget"></a>NuGet에서 다운로드할 수 있는 도구

다음 도구는 NuGet 패키지로 배포됩니다. [개발자 가이드: NuGet에서 도구 다운로드](/dynamics365/customer-engagement/developer/download-tools-nuget) 항목에는 이러한 최신 버전의 도구를 다운로드하여 추출할 수 있는 PowerShell 스크립트가 포함되어 있습니다.

|도구  |설명  |
|---------|---------|
|코드 생성 도구 `CrmSvcUtil.exe`|조직 서비스에서 사용하는 엔터티 데이터 모델을 나타내는 초기 바인딩 .NET Framework 클래스를 생성하는 명령줄 코드 생성 도구입니다. <br />자세한 정보: <br />[조직 서비스](use-web-services.md#organization-service)<br />[Dynamics 365 Customer Engagement 개발자 가이드: 코드 생성 도구를 사용하여 초기 바인딩 엔터티 클래스 만들기 ](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)|
|구성 마이그레이션 도구 `DataMigrationUtility.exe`|환경에서 구성 데이터를 이동하는 데 사용됩니다. 구성 데이터는 사용자 지정 기능을 정의하는 데 사용되며 일반적으로 사용자 지정 엔터티에 저장됩니다. 이 도구는 비즈니스 데이터를 이동하도록 설계되지 않았습니다. <br /> 자세한 정보: [Dynamics 365 Customer Engagement 관리자 가이드: 구성 마이그레이션 도구를 사용하여 인스턴스 및 조직에서 구성 데이터 이동](/dynamics365/customer-engagement/admin/manage-configuration-data)|
|패키지 배포자 `PackageDeployer.exe`|Common Data Service for Apps 인스턴스에 패키지를 배포하는 데 사용됩니다. 패키지는 솔루션을 포함하고 있는 설치 가능한 단위입니다. <br /> 자세한 정보: <br />[솔루션 패키지 배포](introduction-solutions.md#deploy-solution-packages)<br />[Dynamics 365 Customer Engagement 개발자 가이드: Dynamics 365 패키지 배포자용 패키지 만들기](/dynamics365/customer-engagement/developer/create-packages-package-deployer)|
|플러그 인 등록 도구 `PluginRegistration.exe`|.NET 어셈블리 플러그 인 클래스를 서버 이벤트에 가입하는 데 사용되는 도구입니다. <br />자세한 정보: <br />[플러그 인 만들기](apply-business-logic-with-code.md#create-a-plug-in)<br />[Dynamics 365 Customer Engagement 개발자 가이드: 연습: 플러그 인 도구를 사용하여 플러그 인 등록](/dynamics365/customer-engagement/developer/walkthrough-register-plugin-using-plugin-registration-tool)|
|SolutionPackager 도구 `SolutionPackager.exe`|소스 제어 시스템에서 파일을 간편하게 관리할 수 있도록 Common Data Service for Apps 압축 솔루션 파일을 역방향으로 여러 개의 XML 파일 및 기타 파일로 분해할 수 있는 도구입니다.<br /> 자세한 정보: <br />[솔루션 팀 개발](introduction-solutions.md#team-development-of-solutions)<br />[Dynamics 365 Customer Engagement 개발자 가이드: SolutionPackager 도구를 사용하여 솔루션 파일 압축 및 추출](/dynamics365/customer-engagement/developer/compress-extract-solution-file-solutionpackager)|

### <a name="net-sdk-assemblies"></a>.NET SDK 어셈블리 

다음은 개발자가 사용할 수 있는 어셈블리 .NET입니다. 최신 버전은 해당 NuGet 패키지에서 다운로드할 수 있습니다.

#### <a name="work-with-data"></a>데이터 작업

이러한 어셈블리를 사용하여 조직 서비스 및 검색 서비스와 상호 작용할 수 있습니다.

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: Dynamics 365 조직 서비스 사용](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service)

**NuGet 패키지**: [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.CoreAssemblies/)

|어셈블리  |네임스페이스  |
|---------|---------|
|Microsoft.Crm.Sdk.Proxy.dll|[Microsoft.Crm.Sdk](/dotnet/api/microsoft.crm.sdk)<br />[Microsoft.Crm.Sdk.Messages](/dotnet/api/microsoft.crm.sdk.messages)|
|Microsoft.Xrm.Sdk.dll|[Microsoft.Xrm.Sdk](/dotnet/api/microsoft.xrm.sdk)<br />[Microsoft.Xrm.Sdk.Client](/dotnet/api/microsoft.xrm.sdk.client)<br />[Microsoft.Xrm.Sdk.Discovery](/dotnet/api/microsoft.xrm.sdk.discovery)<br />[Microsoft.Xrm.Sdk.Messages](/dotnet/api/microsoft.xrm.sdk.messages)<br />[Microsoft.Xrm.Sdk.Metadata](/dotnet/api/microsoft.xrm.sdk.metadata)<br />[Microsoft.Xrm.Sdk.Metadata.Query](/dotnet/api/microsoft.xrm.sdk.metadata.query)<br />[Microsoft.Xrm.Sdk.Organization](/dotnet/api/microsoft.xrm.sdk.organization)<br />[Microsoft.Xrm.Sdk.Query](/dotnet/api/microsoft.xrm.sdk.query)<br />[Microsoft.Xrm.Sdk.WebServiceClient](/dotnet/api/microsoft.xrm.sdk.webserviceclient)|

#### <a name="create-process-designer-workflow-extensions"></a>프로세스 디자이너(워크플로) 확장

이 어셈블리를 사용하여 프로세스 디자이너에 사용자 지정 작업을 추가할 수 있습니다. 

자세한 정보 [Dynamics 365 Customer Engagement 개발자 가이드: 사용자 지정 워크플로 작업(워크플로 어셈블리)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies)

**NuGet 패키지**: [Microsoft.CrmSdk.Workflow](https://www.nuget.org/packages/Microsoft.CrmSdk.Workflow/) 

|어셈블리|네임스페이스|
|---------|---------|
|Microsoft.Xrm.Sdk.Workflow.dll|[Microsoft.Xrm.Sdk.Workflow](/dotnet/api/microsoft.xrm.sdk.workflow)<br />[Microsoft.Xrm.Sdk.Workflow.Activities](/dotnet/api/microsoft.xrm.sdk.workflow.activities)<br />[Microsoft.Xrm.Sdk.Workflow.Designers](/dotnet/api/microsoft.xrm.sdk.workflow.designers)|

#### <a name="build-windows-client-applications"></a>windows 클라이언트 응용 프로그램 빌드

이러한 어셈블리를 사용하면 용이하게 조직 서비스에 연결하고 windows 클라이언트 응용 프로그램을 빌드할 수 있습니다. 

자세한 정보 [Dynamics 365 Customer Engagement 개발자 가이드: XRM 도구를 사용하여 Windows 클라이언트 응용 프로그램 빌드](/dynamics365/customer-engagement/developer/build-windows-client-applications-xrm-tools)

**NuGet 패키지**:
- [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/)(Microsoft.Xrm.Tooling.Connector.dll)
- [Microsoft.CrmSdk.XrmTooling.WpfControls](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/) 

|어셈블리|네임스페이스  |
|---------|---------|
|Microsoft.Xrm.Tooling.Connector.dll|[Microsoft.Xrm.Tooling.Connector](/dotnet/api/microsoft.xrm.tooling.connector)<br />[Microsoft.Xrm.Tooling.Connector.Model](/dotnet/api/microsoft.xrm.tooling.connector.model)|
|Microsoft.Xrm.Tooling.CrmConnectControl.dll|[Microsoft.Xrm.Tooling.CrmConnectControl](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Model](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.model)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Properties](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.properties)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Utility](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.utility)|
|Microsoft.Xrm.Tooling.WebResourceUtility.dll|[Microsoft.Xrm.Tooling.WebResourceUtility](/dotnet/api/microsoft.xrm.tooling.webresourceutility)|

#### <a name="create-packages"></a>패키지 만들기

이러한 어셈블리를 사용하여 패키지 배포자용 패키지를 만들 수 있습니다.

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: Dynamics 365 패키지 배포자용 패키지 만들기](/dynamics365/customer-engagement/developer/create-packages-package-deployer)

**NuGet 패키지**: [Microsoft.CrmSdk.XrmTooling.PackageDeployment](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment/)

|어셈블리|네임스페이스  |
|---------|---------|
|Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.dll|[Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase](/dotnet/api/microsoft.xrm.tooling.packagedeployment.crmpackageextentionbase)|

#### <a name="create-custom-virtual-entity-data-providers"></a>사용자 지정 가상 엔터티 데이터 공급자 만들기

이 어셈블리를 사용하여 사용자 지정 가상 엔터티 데이터 공급자를 만들 수 있습니다. 

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: 가상 엔터티 시작](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)

**NuGet 패키지**: [Microsoft.CrmSdk.Data](https://www.nuget.org/packages/Microsoft.CrmSdk.Data/)

|어셈블리  |네임스페이스  |
|---------|---------|
|Microsoft.Xrm.Sdk.Data.dll|[Microsoft.Xrm.Sdk.Data](/dotnet/api/microsoft.xrm.sdk.data)<br />[Microsoft.Xrm.Sdk.Data.CodeGen](/api/microsoft.xrm.sdk.data.codegen)<br />[Microsoft.Xrm.Sdk.Data.Converters](/dotnet/api/microsoft.xrm.sdk.data.converters)<br />[Microsoft.Xrm.Sdk.Data.Exceptions](/dotnet/api/microsoft.xrm.sdk.data.exceptions)<br />[Microsoft.Xrm.Sdk.Data.Expressions](/dotnet/api/microsoft.xrm.sdk.data.expressions)<br />[Microsoft.Xrm.Sdk.Data.Infra](/dotnet/api/microsoft.xrm.sdk.data.infra)<br />[Microsoft.Xrm.Sdk.Data.Mappings](/dotnet/api/microsoft.xrm.sdk.data.mappings)|

#### <a name="extend-outlook-client"></a>Outlook 클라이언트 확장

이 어셈블리를 사용하여 Microsoft Dynamics 365 for Outlook 및 Microsoft Dynamics 365 for Microsoft Office Outlook with Offline Access와 상호 작용할 수 있습니다. 

자세한 정보: [Dynamics 365 Customer Engagement 개발자 가이드: Dynamics 365 Customer Engagement for Outlook 확장](/dynamics365/customer-engagement/developer/extend-customer-engagement-outlook)

**NuGet 패키지**: [Microsoft.CrmSdk.Outlook](https://www.nuget.org/packages/Microsoft.CrmSdk.Outlook/)

|어셈블리|네임스페이스|
|---------|---------|
|Microsoft.Crm.Outlook.Sdk.dll|[Microsoft.Crm.Outlook.Sdk](/dotnet/api/microsoft.crm.outlook.sdk)|



## <a name="community-tools-for-common-data-service-for-apps"></a>Common Data Service for Apps 커뮤니티 도구

Dynamics 365 커뮤니티에서 도구를 만듭니다! 가장 인기가 많은 도구는 [XrmToolBox](https://www.xrmtoolbox.com/)에 배포됩니다. XrmToolBox는 Common Data Service for Apps에 연결되는 Windows 응용 프로그램으로 사용자 지정, 구성 및 운영 작업을 쉽게 할 수 있는 도구를 제공합니다. 관리, 사용자 지정 또는 구성 작업을 더 적은 시간으로 더 쉽게 수행할 수 있도록 30개 이상의 플러그 인이 제공됩니다.

다음은 XrmToolBox를 통해 배포되는 엄선된 커뮤니티 도구 목록으로, Common Data Service for Apps와 함께 사용할 수 있습니다.

|도구  |설명  |
|---------|---------|
|[특성 관리자](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)|특성의 형식을 삭제/변경 또는 이름을 바꾸는 데 사용됩니다.|
|[초기 바인딩 생성기](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.EarlyBoundGenerator/)|초기 바인딩 엔터티/옵션 설정/작업을 생성합니다. SDK의 CrmSvcUtil을 사용하고, 클래스를 만드는 데 사용되는 명령줄을 보여줍니다.|
|[Excel로 내보내기](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|선택한 보기/fetchxml에서 Excel로 손쉽게 레코드를 내보냅니다.|
|[FetchXML 작성기](https://www.xrmtoolbox.com/plugins/Cinteros.Xrm.FetchXmlBuilder/)|FetchXml 쿼리 만들기 및 테스트|
|[메타데이터 브라우저](https://www.xrmtoolbox.com/plugins/MsCrmTools.MetadataBrowser/)|Dynamics CRM 조직에서 메타데이터 찾아보기|
|[플러그 인 추적 뷰어](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.PluginTraceViewer/)|간편한 필터링을 사용하여 플러그 인 추적 로그를 조사하고 가능성 표시|
|[사용자 설정 유틸리티](https://www.xrmtoolbox.com/plugins/MsCrmTools.UserSettingsUtility/)|사용자 개인 설정을 대량으로 관리|

> [!NOTE]
> 커뮤니티에서 만든 도구는 Microsoft에서 지원하지 않습니다. 커뮤니티 도구와 관련하여 질문 또는 문제가 있으면 해당 도구의 게시자에게 문의하세요.
