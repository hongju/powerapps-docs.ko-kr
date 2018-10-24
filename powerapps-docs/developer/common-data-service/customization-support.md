---
title: 앱용 Common Data Service 앱 빌드 사례 | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e9810433-224b-4bde-851a-e581cf5fb8a4
caps.latest.revision: 21
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1eda4b591a3296001ffa62b16e185b421a197e75
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865044"
---
# <a name="common-data-service-for-apps-supported-and-unsupported-app-building-practices"></a>앱용 Common Data Service 지원 및 지원되지 않는 앱 빌드 사례

<!--
The way your organization works is unique. Some organizations have well-defined business processes that they apply using PowerApps apps. Others aren’t happy with their current business processes and use PowerApps to apply new data and processes to their business. Whatever situation you find yourself in, you’ll find a lot of customization capabilities in PowerApps so that it can work for your organization.  
  
 Of course you’re eager to get started, but please take a few minutes to read the content in this section. This will introduce you to important terms, give you some background about why things are done a certain way, and help you avoid potential problems in the future.  

## What is metadata and why should you care?  
 In the past, you may have customized business applications by editing the source code. This created complications because each organization had unique changes and it was very difficult, or extremely expensive, to upgrade. Then application developers started exposing application programming interfaces (APIs) so that other developers could interact with the application and add their own logic without touching the source code. This was moderately better because it means developers can extend the application without changing it. But it still requires a developer to write code.  -->
  
 최신 비즈니스 응용 프로그램은 사용자가 코드를 작성하지 않고도 앱을 만들 수 있도록 메타데이터 기반 아키텍처를 사용합니다. 메타데이터란 “데이터에 대한 데이터”를 의미하며 앱용 Common Data Service에 저장된 데이터의 구조를 정의합니다. 이 메타데이터를 사용하여 응용 프로그램은 데이터 구조에 대한 변경 내용을 인식하고 이를 통해 응용 프로그램은 데이터 구조 변경 내용에 따라 조정할 수 있습니다. 메타데이터를 알고 있으므로 메타데이터에 연결된 추가 기능을 포함할 수 있습니다.  

원하는 방법으로 작업하는 앱을 빌드하는 엔터티, 보기, 필드, 차트 및 대시보드와 같은 앱용 Common Data Service를 변경하는 것을 *사용자 지정*이라고 합니다.  
 
PowerApps에서 도구를 사용하여 앱을 빌드 및 사용자 지정할 때 메타데이터 또는 메타데이터에 의존하는 기능에서 사용되는 데이터를 추가 또는 업데이트합니다. 앱을 만드는 데 사용되는 데이터의 종류를 알고 있으므로 이 데이터를 고려하여 앱을 중단하지 않으면서 앱용 Common Data Service 환경에 새 기능을 추가할 수 있습니다. <!-- This way you should always be able to apply an update rollup or upgrade to the latest version and enjoy the best new features.  -->

<!--  
> **Customize or Configure?**   
> Most people say they want to customize the application, so we use the word “customize” to describe changing the system to make it work the way you want. Some people prefer to use the word “configure” because it suggests that no code was required to make changes. Call it whatever you like, we just want to make it clear that you don’t need to be a developer to customize or create PowerApps apps.  -->
  
PowerApps 앱을 빌드하고 사용자 지정하는 데 개발자일 필요가 없습니다. 그러나 PowerApps는 개발자가 코드를 작성할 수 있도록 하는 웹 서비스 집합 및 API를 제공합니다. 지원되는 메서드를 사용하여 코드를 작성하는 경우 앱용 Common Data Service 환경이 업데이트될 때 작업을 계속할 수 있습니다.  
  
<a name="BKMK_SupportedCust"></a>   
## <a name="what-kinds-of-customizations-are-supported"></a>지원되는 사용자 지정의 종류는 무엇인가요?  
 사용 가능한 PowerApps 도구를 사용하여 대부분의 앱 빌드 및 사용자 지정을 수행할 수 있기를 기대합니다. 사용자 지정 도구가 요구 사항에 맞지 않는 경우 타사에서 제공하는 솔루션을 설치하거나 앱을 코딩하는 개발자를 채용할 수 있습니다. 코드가 필요한 솔루션에 투자해야 하는 경우 지원되는 API만을 사용하여 코드가 작성되는지 확인해야 합니다. 그러면 가져오는 앱 및 모든 솔루션에 대한 투자를 보호할 수 있습니다.  
  
 PowerApps 앱을 확장하는 개발자는 SDK([Dynamics 365 Customer Engagement를 사용하여 개발을 위한 모범 사례](https://docs.microsoft.com/dynamics365/customer-engagement/developer/best-practices-sdk))에 설명된 규칙 및 모범 사례를 따를 책임이 있습니다. SDK는 개발자에게 사용 가능한 API를 설명하고 가장 잘 사용하는 방법에 대한 지침을 제공합니다. Microsoft는 SDK에 나와 있는 API 및 사례만을 지원합니다. 문제를 해결할 수 있는 방법은 인터넷에서 찾을 수 있지만 SDK에서 나와 있는 API를 활용하지 않으면 Microsoft에서 지원되지 않습니다. 개발자가 변경 내용을 적용하기 전에 지원되는 메서드를 사용하는지 여부를 확인해야 합니다.  
  
 개발자가 SDK에 설명된 API 및 모범 사례를 사용하는 경우 앱용 Common Data Service에 만드는 변경 내용에 기존 사용자 지정을 중단할 수 있는 잠재성이 있는지 테스트할 수 있습니다. 우리의 목표는 지원되는 메서드를 사용하여 작성된 코드 사용자 지정이 앱용 Common Data Service에 대한 새 버전 또는 업데이트가 릴리스될 때 계속해서 작동하는 것입니다. 개발자가 매번 해당 코드를 변경하지 않고도 향상된 기능을 사용하여 새 버전으로 업그레이드할 수 있으므로 유용합니다.  
  
 앱용 Common Data Service의 새 버전의 변경 내용이 지원되는 사용자 지정을 중단한다는 것을 감지하는 경우 영향을 받는 항목 및 사용자가 이를 수정하도록 해당 코드를 변경할 수 있는 방법을 설명합니다.  
  
<a name="BKMK_Unsupported"></a>   
## <a name="what-kinds-of-customizations-arent-supported"></a>지원되지 않는 사용자 지정의 종류는 무엇인가요?  
 특정 API 및 프로그래밍 사례가 Microsoft에서 지원되지 않는다고 해서 작동하지 않는다는 것은 아닙니다. <!--  “Unsupported by Microsoft” means exactly what it says: you can’t get support about these APIs or programming practices from Microsoft. We don’t test them and we don’t know if something we change will break them. We can’t predict what will happen if someone changes code in our application.  --> 지원되지 않는 API 및 프로그래밍 사례를 사용하는 개발자는 해당 코드를 지원해야 할 책임이 있습니다. 해당 코드가 작동하는지 확인하기 위해 테스트해야 합니다.  
  
 앱용 Common Data Service 환경에서 지원되지 않는 사용자 지정을 사용하도록 선택한 경우 수행된 작업을 문서화하고 Microsoft 기술 지원에 문의하기 전에 해당 사용자 지정 항목을 제거하는 전략을 수립해야 합니다. 지원되지 않는 사용자 지정에 도움이 필요한 경우 사용자 지정을 준비한 개발자 또는 조직에 문의합니다.  
  
<a name="BKMK_CommonUnsupportedCustomizations"></a>   
### <a name="common-unsupported-customization-practices"></a>일반적인 지원되지 않는 사용자 지정 사례  
 다음은 지원되지 않는 일반적인 사용자 지정 사례의 목록입니다. 전체 목록은 아닙니다. 자세한 정보: [Dynamics 365에 지원되는 확장: 지원되지 않는 사용자 지정](https://docs.microsoft.com/dynamics365/customer-engagement/developer/supported-extensions#Unsupported). 
 
**JavaScript를 사용하여 웹 응용 프로그램 DOM(문서 개체 모델) 요소와 상호 작용**  
 응용 프로그램 어디서나 사용되는 모든 JavaScript 라이브러리는 문서화된 API와만 상호 작용해야 합니다. JavaScript 개발자가 응용 프로그램을 사용하여 작업하는 경우 특정 이름을 사용하여 DOM 요소에 자주 액세스합니다. PowerApps 앱은 웹 응용 프로그램이므로 이러한 기술은 작동하지만 참조하는 요소의 이름은 언제든지 변경될 수 있기 때문에 업데이트 중 중단될 가능성이 높습니다. 응용 프로그램에 필요한 변경 내용을 만들 권한이 있으며 이 빈도는 페이지가 생성되는 방법의 변경을 의미합니다. 페이지의 현재 구조에 종속된 모든 변경 내용을 추가하는 것은 테스트에 투자해야 하며 아마도 응용 프로그램에 업데이트를 적용할 때마다 이러한 스크립트의 사용자 지정 코드를 변경해야 할 필요가 있음을 의미합니다.  
  
 jQuery는 JavaScript 개발자가 사용하는 매우 일반적인 라이브러리입니다. jQuery를 사용하는 대부분의 이점은 정확하게 앱용 Common Data Service 응용 프로그램 페이지에서 지원하지 않는 DOM 요소에 액세스하고 이를 만들 수 있는 개발자의 기능을 단순화하는 것입니다. jQuery는 개발자가 HTML 웹 리소스를 사용하여 사용자 지정 사용자 인터페이스를 만들 때 권장되지만, PowerApps 응용 프로그램 페이지 내에서 지원되는 API가 jQuery를 사용할 필요는 없습니다.  
  
 **JavaScript를 사용하여 문서화되지 않은 내부 개체 또는 메서드 사용**  
앱용 Common Data Service는 페이지 내에서 많은 JavaScript 개체를 사용합니다. JavaScript 개발자는 페이지를 디버깅한 다음, 이러한 개체에 액세스하고 다시 사용하여 이러한 개체를 검색할 수 있습니다. 이러한 개체 제거 또는 메서드의 이름 변경을 포함하여 이러한 개체에 필요한 변경 내용을 만드는 권한을 보유합니다. 스크립트에서 이러한 개체를 참조하는 경우 찾을 수 없으면 스크립트가 중단됩니다.  <a name="BKMK_Metadata"></a>   
 
<a name="BKMK_CombineCustomizations"></a>   
## <a name="combine-customization-capabilities"></a>사용자 지정 기능 결합  
 이러한 섹션의 항목은 개별 사용자 지정 기능을 자세히 설명합니다. 그러나 비즈니스 요구 사항을 충족하는 솔루션은 하나 이상의 다른 기능과 함께 기능 중 하나를 자주 사용한다는 점을 염두에 두어야 합니다.  
  
<a name="BKMK_ChooseTheRightCustomization"></a>   
### <a name="choose-the-right-customization-capability-for-the-job"></a>작업에 대한 올바른 사용자 지정 기능 선택  
 PowerApps에서 사용할 수 있는 다양한 모든 사용자 지정 기능을 사용하면 그 중 하나에 익숙해지고 모든 문제를 해결하는 데 사용할 수 있습니다. 해결하려는 비즈니스 문제를 평가할 때 달성하려는 최종 결과에 대해 생각한 다음, 그 결과를 얻을 수 있는 방법에 대해 되돌아봅니다.  
 
<a name="BKMK_changesinperformance"></a>   
## <a name="changes-that-affect-common-data-service-for-apps-environment-performance"></a>앱용 Common Data Service 환경 성능에 영향을 주는 변경 내용  
 메타데이터를 변경하는 솔루션 가져오기 및 사용자 지정 적용은 앱용 Common Data Service 환경 성능에 영향을 줄 수 있습니다. 정상적인 시스템 작동을 방해할 수 있는 작업은 다음과 같습니다.  
  
-   엔터티, 대체 키, 특성 또는 관계를 추가, 제거 또는 변경합니다.   
-   솔루션 가져오기
  
-   사용자 지정 게시 
  
이러한 변경 내용을 프로덕션 시스템에 적용하는 경우 사용자에게 가장 방해가 적을 때 이러한 작업을 예약하는 것이 좋습니다.   
  
  
## <a name="next-steps"></a>다음 단계  
[PowerApps의 모델 기반 앱이란?](../../maker/model-driven-apps/model-driven-app-overview.md)

