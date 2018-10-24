---
title: PowerApps에서 모델 기반 앱 주요 양식에 대한 웹 리소스 속성 | Microsoft Docs
description: 기본 양식에 대한 웹 리소스 속성 이해
Keywords: Main form; Web resource properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 82cd41ea-95b0-4606-9e7d-43eb5ce9ecd6
ms.openlocfilehash: a08ca32b1d300d4302064940e65fd1d067c3ade6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39695575"
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>모델 기반 앱 양식에 대한 웹 리소스 속성

양식에 웹 리소스를 추가하거나 편집하여 앱 사용자에게 더 매력적이고 유용한 정보를 제공할 수 있습니다. 양식 설정 웹 리소스는 이미지 또는 HTML 파일 컨트롤입니다.

> [!NOTE]
> Silverlight 웹 리소스는 사용되지 않으며 통합 인터페이스 클라이언트에서 작동하지 않습니다.

## <a name="access-web-resource-properties"></a>웹 리소스 속성에 액세스

양식을 보면서 다음을 수행할 수 있습니다.
- **웹 리소스를 추가하는 경우:**: 삽입하려는 탭(예: **일반** 또는 **노트**)을 선택한 다음, **삽입** 탭에서 **웹 리소스**를 선택합니다.<br />![웹 리소스 삽입](media/insert-web-resource.png)
- **웹 리소스를 편집하는 경우**: 편집하려는 양식 탭 및 웹 리소스를 선택한 다음, **홈** 탭에서 **속성 변경**을 선택합니다. <br />![웹 리소스 속성 변경](media/web-resource-change-properties.png)

그러면 **웹 리소스 추가** 또는 **웹 리소스 속성** 대화 상자가 열립니다.

![웹 리소스 추가 대화 상자](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>웹 리소스 속성

 **웹 리소스 추가** 또는 **웹 리소스 속성** 대화 상자에는 웹 리소스의 형식에 따라 두세 개의 탭이 있습니다.

### <a name="general-tab"></a>일반 탭

이러한 속성은 사용할 웹 리소스 및 동작 방식을 정의합니다.

|필드|설명|
|--|--|
|**웹 리소스**|*필수* 기존 웹 리소스를 조회하거나 새로 만듭니다. **양식 설정 웹 리소스** 보기를 사용하여 양식에서 시각적 요소로 추가될 수 있는 HTML 및 이미지 웹 리소스만 포함합니다.|
|**Name**|*필수* 양식에 추가될 웹 리소스 제어에 대한 이름을 지정합니다. 이 값은 양식에서 제어를 고유하게 식별합니다.|
|**레이블**|*필수* **이름** 필드 값에 따라 자동으로 생성됩니다. 양식에 추가될 웹 리소스 제어에 대한 지역화할 수 있는 텍스트를 지정합니다. 표시하려면 **양식에 레이블 표시**를 선택합니다.|
|**기본적으로 표시**|이 기능을 사용하면 양식이 로드되는 경우 웹 리소스를 볼 수 있습니다. 비즈니스 규칙 또는 양식 스크립트가 필요에 따라 웹 리소스를 표시하는 경우 이 필드의 선택을 취소합니다. 추가 정보: [양식 요소 표시 또는 숨기기](visibility-options-legacy.md)|
|**모바일에 사용**|이 웹 리소스를 모바일 앱에서 표시하려면 이 옵션을 선택합니다.|

선택한 웹 리소스의 형식에 따라 추가 속성을 설정합니다.

HTML 웹 리소스의 경우 다음이 표시됩니다.

![HTML 웹 리소스 속성](media/web-resource-general-html-properties.png)

|필드|설명|
|--|--|
|**사용자 지정 매개 변수(데이터)**|일반적으로 `data` 쿼리 문자열 매개 변수로 HTML 웹 리소스에 전달될 구성 데이터입니다. HTML 페이지와 관련된 스크립트는 이 데이터에 액세스하고 페이지의 동작을 변경하는 데 사용할 수 있습니다.|
|**지원되는 경우 프레임 간 스크립팅 제한**|HTML 웹 리소스의 콘텐츠를 완전히 신뢰할 수 없는 경우 이 옵션을 사용합니다. 추가 정보: [개발자 설명서: 프레임 간 스크립팅을 제한할지 선택](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**레코드 개체 형식 코드 및 고유 식별자를 매개 변수로 전달**|페이지에서 실행되는 스크립트가 레코드에 대한 데이터에 액세스할 수 있도록 이 양식으로 표시되는 현재 레코드에 대한 데이터는 HTML 웹 리소스 페이지에 전달될 수 있습니다. 자세한 정보: <br />[웹 리소스에 매개 변수 전달](#pass-parameters-to-web-resources)<br />[개발자 설명서: 레코드에 대한 컨텍스트 정보 전달](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

이미지 웹 리소스의 경우 모든 사용자가 페이지에 액세스할 수 있도록 하는 보조 기술에 대해 중요한 **대체 텍스트**를 지정하는 옵션이 있습니다.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>서식 지정 탭

**서식 지정** 탭에서 표시되는 옵션은 삽입되는 웹 리소스의 형식 및 삽입되는 컨텍스트에 따라 다릅니다. 이러한 옵션에는 열과 행 표시 수, 테두리 표시 여부 및 스크롤 동작을 지정하는 방법이 포함됩니다.

![웹 리소스 서식 지정 속성](media/web-resource-formatting-properties.png)

|속성|설명|  
|--------------|-----------------|
|**제어가 차지하는 열 수 선택**|웹 리소스를 포함하는 섹션에 둘 이상의 열이 있다면 섹션에 있는 최대 열 수를 차지하도록 필드를 설정할 수 있습니다.|  
|**제어가 차지하는 행 수 선택**|행 수를 지정하여 웹 리소스의 높이를 제어하거나 **사용 가능한 공간을 사용하도록 자동으로 확장**을 선택하여 웹 리소스 높이를 사용 가능한 공간으로 확장할 수 있습니다.|  
|**IFRAME의 스크롤 형식 선택**|IFRAME을 사용하여 HTML 웹 리소스를 양식에 추가합니다.<br /><br /> - **필요에 따라**: 웹 리소스가 사용할 수 있는 크기보다 큰 경우 스크롤 막대를 표시합니다.<br />- **항상**: 항상 스크롤 막대를 표시합니다.<br />- **사용 안 함**: 스크롤 막대를 표시하지 않습니다.|  
|**테두리 표시**|웹 리소스 주위에 테두리를 표시합니다.|  


### <a name="dependencies-tab"></a>종속성 탭

웹 리소스는 스크립트를 사용하여 양식의 필드와 상호 작용할 수 있습니다. 필드가 양식에서 제거되면 웹 리소스의 스크립트도 중단될 수 있습니다. 웹 리소스의 스크립트에서 참조된 필드를 실수로 제거할 수 없도록 **종속 필드**에 추가합니다.

![웹 리소스 종속성 속성](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>웹 리소스에 매개 변수 전달 

HTML 웹 리소스는 매개 변수가 쿼리 문자열 매개 변수로 전달되도록 허용할 수 있습니다.  
  
레코드에 대한 정보는 **레코드 개체 형식 코드 및 고유 식별자를 매개 변수로 전달** 옵션을 사용하여 전달될 수 있습니다. 정보가 **사용자 지정 매개 변수(데이터)** 필드에 입력된 경우 데이터 매개 변수를 사용하여 전달됩니다. 전달된 값은 다음과 같습니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`data`|**사용자 지정 매개 변수(데이터)** 에 대한 텍스트를 입력한 경우에만 이 매개 변수가 전달됩니다.|  
|`orglcid`|조직의 기본 언어 LCID|  
|`orgname`|조직의 이름|  
|`userlcid`|사용자의 기본 언어 LCID|  
|`type`|**이 항목을 사용하지 마세요.** 엔터티 형식 코드 이 숫자 값은 다른 조직에서 사용자 지정 엔터티에 대해 다를 수 있습니다. 대신 엔터티 형식 이름을 사용합니다.|  
|`typename`|엔터티 형식 이름|  
|`id`|레코드의 ID 값 엔터티 레코드가 저장될 때까지 이 매개 변수에는 값이 없습니다.|  
  
다른 매개 변수는 허용되지 않습니다. 다른 매개 변수를 사용하는 경우 웹 리소스가 열리지 않습니다. 여러 값을 전달해야 하는 경우 데이터 매개 변수가 오버로드되어 더 많은 매개 변수를 포함할 수 있습니다.

추가 정보: [개발자 설명서: 레코드에 대한 컨텍스트 정보 전달](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>참고 항목

[웹 리소스를 만들거나 편집하여 앱 확장](create-edit-web-resources.md)<br />
[기본 양식 및 해당 구성 요소 사용](use-main-form-and-components.md)
