---
title: 모델 기반 앱 개발자 개요 | Microsoft Docs
description: 개발자가 모델 기반 앱에 값을 추가하는 방법을 알아봅니다.
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
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 39fe83cdb059e0f1df634b9933f4a2f4251bca7b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42852417"
---
# <a name="model-driven-apps-developer-overview"></a>모델 기반 앱 개발자 개요

PowerApps는 사용자, 비즈니스, 파트너, ISV(독립 소프트웨어 공급업체) 및 SI(시스템 통합자)에게 기간 업무 앱을 빌드할 수 있는 강력한 플랫폼을 제공합니다. 이번 릴리스의 PowerApps에는 새로운 Common Data Service for Apps를 사용하여 빌드된 모델 기반 앱이 새로 추가되었습니다. Common Data Service for Apps에는 이제 Dynamics 365 고객 관계 응용 프로그램의 핵심 기능이 포함되어 있습니다. 모델 기반 앱을 사용하면 이러한 응용 프로그램과 동일한 확장성 기능을 사용하는 앱을 빌드할 수 있습니다.

모델 기반 앱은 코드가 없거나 짧은 코드로 만든 구성 요소로서 주로 앱 개발 방법에 집중하고 있습니다. 개발자가 제공할 수 있는 값은 응용 프로그램을 확장하는 것입니다. 코드 작성을 시작하기 전에 먼저 모델 기반 앱을 빌드하는 방법과 코드 없이 적용할 수 있는 옵션을 알아보는 것으로 시작하겠습니다. 

## <a name="get-started"></a>시작하기
Dynamics 365 고객 관계 앱을 이미 경험한 경우 모델 기반 앱을 빌드한 환경을 적용할 수 있습니다. 몇 가지 새 디자이너를 사용할 수 있지만 일반적으로 개념은 동일 합니다.

> [!NOTE]
> 모델 기반 앱은 Common Data Service for Apps에 연결됩니다. 개발자가 서비스 수준에서 값을 추가하는 방법에 대한 자세한 내용은 [Common Data Service for Apps 개발자 개요](../common-data-service/overview.md)를 참조하세요.
> 이 섹션의 내용은 모델 기반 앱 사용자를 위한 환경에 적용되는 확장 개발자에게만 적용됩니다. 

Dynamics 365 고객 관계 응용 프로그램을 처음 사용하는 경우 이 섹션의 주제는 개발자가 모델 기반 앱 작업을 시작하는 데 도움이 되는 주요 개념에 대해 개략적으로 설명합니다. 

> [!NOTE]
> Common Data Service for Apps 및 Dynamics 365 Customer Engagement는 동일한 플랫폼을 활용하므로 [Dynamics 365 Customer Engagement 개발자 가이드](/dynamics365/customer-engagement/developer/developer-guide)에서 개발자를 위한 더 완벽한 정보를 찾을 수 있습니다. 이러한 항목에서는 개발자 가이드 및 기타 가이드에 대한 링크가 포함된 개요를 제공하여 자세한 내용을 확인할 수 있도록 합니다.


## <a name="community-tools-for-model-driven-apps"></a>모델 기반 앱에 대한 커뮤니티 도구

Dynamics 365 커뮤니티에서 도구를 만듭니다! 가장 인기 있는 대부분의 도구가 [XrmToolBox](https://www.xrmtoolbox.com/)를 통해 배포됩니다. XrmToolBox는 Common Data Service for Apps에 연결하여 사용자 지정, 구성 및 운영 작업을 쉽게 수행할 수 있는 도구를 제공하는 Windows 응용 프로그램입니다. 관리, 사용자 지정 또는 구성 작업을 더 적은 시간으로 더 쉽게 수행할 수 있도록 30개 이상의 플러그 인이 제공됩니다.

다음은 모델 기반 앱으로 작업할 때 사용할 수 있는 XrmToolBox를 통해 배포되는 커뮤니티 도구에 대해 선택된 목록입니다.

|도구  |설명  |
|---------|---------|
|[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/)(쉬운 번역기)|컨텍스트 정보가 포함된 번역을 내보내고 가져옵니다.|
|[Export to Excel](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)(Excel로 내보내기)|선택한 보기/fetchxml에서 Excel로 레코드를 쉽게 내보냅니다.|
|[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)|단일 화면에서 사용자 지정 엔터티 아이콘을 관리합니다.|
|[Ribbon Workbench 2016](https://www.xrmtoolbox.com/plugins/RibbonWorkbench2016/)|XrmToolbox 내에서 Dynamics CRM 리본 또는 명령 모음을 편집합니다.|
|[View Designer](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.ViewDesigner/)(뷰 디자이너)|FetchXML 작성기를 사용하여 뷰 레이아웃을 디자인하고 쿼리를 변경할 수 있는 간편한 UI입니다.|
|[View Layout Replicator](https://www.xrmtoolbox.com/plugins/MsCrmTools.ViewLayoutReplicator/)(뷰 레이아웃 복제기)|한 번의 작업에서 동일한 엔터티의 여러 뷰에 동일한 레이아웃을 적용합니다.|
|[WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/)(WebResources 관리자)|웹 리소스를 쉽게 관리합니다.|

XrmToolBox를 통해 배포되지 않는 또 다른 도구는 Jason Lattimer의 [CRM REST 작성기](https://github.com/jlattimer/CRMRESTBuilder)입니다. 이 도구는 Web API와 함께 사용할 JavaScript 코드를 생성합니다.

> [!NOTE]
> 커뮤니티에서 만든 도구는 Microsoft에서 지원하지 않습니다. 커뮤니티 도구와 관련하여 질문 또는 문제가 있으면 해당 도구의 게시자에게 문의하세요.




