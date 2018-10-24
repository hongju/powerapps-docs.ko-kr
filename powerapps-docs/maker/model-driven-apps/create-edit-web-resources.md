---
title: PowerApps에서 모델 기반 앱 웹 리소스 만들기 또는 편집 | MicrosoftDocs
description: 웹 리소스를 만들거나 편집하는 방법 알아보기
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: ef4ba8df-9ba9-4066-b40d-def9761c7de2
caps.latest.revision: 21
ms.author: matp
manager: kvivek
ms.openlocfilehash: 8d9414ba4c900f98ac26010e4e6d7240b336e2d7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696063"
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>모델 기반 앱 웹 리소스를 만들거나 편집하여 앱 확장

웹 리소스는 일반적으로 개발자가 웹 개발에 사용되는 파일을 통해 앱을 확장하는 데 사용됩니다. 앱 사용자는 개발자 또는 디자이너가 제공하는 웹 리소스를 관리해야 할 수 있습니다.  

> [!TIP]
> 웹 리소스에 대한 자세한 내용은 [개발자 설명서: 고객 참여를 위한 웹 리소스](/dynamics365/customer-engagement/developer/web-resources)를 참조하세요.<br /> PowerApps에 추가하는 웹 리소스 종속성에 대한 자세한 내용은 [개발자 설명서: 웹 리소스 종속성](/dynamics365/customer-engagement/developer/web-resources)을 참조하세요.
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>웹 리소스란?  

웹 리소스는 시스템에 저장된 가상 파일입니다. 각 웹 리소스에는 URL에서 파일을 검색하는 데 사용할 수 있는 고유한 이름이 있습니다. 이러한 방식으로 생각해 보세요: 웹앱을 실행하는 실제 웹 서버에 액세스할 수 있는 경우 해당 웹 사이트에 파일을 복사할 수 있습니다. 하지만 대부분의 온라인 서비스에서는 이를 수행할 수 없습니다.  대신 웹 리소스를 사용하여 파일을 시스템에 업로드한 다음, 웹 서버에 파일로 복사한 것처럼 파일 이름을 참조할 수 있습니다.  
  
예를 들어, HTML 페이지를 "new_myWebResource.htm" 이라는 웹 리소스로 만든 경우 다음과 같은 URL을 사용하여 브라우저에서 해당 페이지를 열 수 있습니다.  
 
`<base URL>/WebResources/new_myWebResource.htm   `
  
여기서 *\<기준 URL>* 은 `dynamics.com`에서 끝나는 앱을 보는 데 사용하는 URL의 일부입니다. 웹 리소스는 시스템의 데이터이므로 조직에 대해 라이센스가 부여된 사용자만 이러한 방식으로 액세스할 수 있습니다. 일반적으로 웹 리소스는 직접 참조되기 보다는 양식에 포함됩니다. 가장 일반적인 사용법은 양식 스크립트에 대한 JavaScript 라이브러리를 제공하는 것입니다.  
    
웹 리소스는 시스템에 있는 데이터이며 솔루션을 인식하므로 이를 솔루션의 일부로 내보내고 다른 조직으로 해당 솔루션을 가져와 다른 조직으로 이동시킬 수 있습니다. 솔루션 탐색기를 사용하여 웹 리소스를 작동해야 합니다.
  
## <a name="open-solution-explorer"></a>솔루션 탐색기 열기

생성한 모든 웹 리소스의 이름 부분은 사용자 지정 접두사입니다. 이는 작업 중인 솔루션의 솔루션 게시자를 기반으로 설정됩니다. 사용자 지정 접두사에 관심이 있는 경우에는 이 웹 리소스에 대해 원하는 사용자 지정 접두사가 있는 관리되지 않는 솔루션에서 작업하는지 확인해야 합니다. 자세한 내용: [솔루션 게시자 접두사 변경](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>웹 리소스 보기

솔루션 탐색기를 연 상태에서 **구성 요소** 아래의 **웹 리소스**를 선택합니다.

![웹 리소스 보기](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>웹 리소스 만들기 및 편집  

[웹 리소스 보기](#view-web-resources)에서 **새로 만들기**를 선택하여 새 웹 리소스를 만들거나 기존 웹 리소스를 두 번 클릭하여 편집합니다.

![새 웹 리소스 양식](media/new-web-resource-form.png)

양식을 작성하여 웹 리소스를 만들거나 편집합니다.
  
|필드|설명|  
|-----------|-----------------|  
|**Name**|*필수*. 이 웹 리소스의 고유한 이름입니다. 웹 리소스를 저장한 후에는 변경할 수 없습니다.<br />&bull; 이 이름에는 문자, 숫자, 마침표 및 비연속적인 앞으로 기울어진 슬래시("/") 문자만 포함할 수 있습니다.<br /> &bull; 솔루션 게시자 사용자 지정 접두사가 웹 리소스의 이름 앞에 추가됩니다.|  
|**표시 이름**|웹 리소스 목록을 볼 때 표시되는 이름입니다.|  
|**설명**|웹 리소스에 대한 설명입니다.|  
|**형식**|*필수*. 이는 웹 리소스의 형식입니다. 웹 리소스를 저장한 후에는 변경할 수 없습니다.|  
|**텍스트 편집기**|웹 리소스 형식이 텍스트 파일의 종류를 나타내는 경우, 텍스트 편집기를 사용하여 콘텐츠를 편집할 페이지를 열려면 이 단추를 선택합니다.<br />자세한 내용: [텍스트 편집기를 적절하게 사용](#use-the-text-editor-appropriately)| 
|**언어**|언어를 선택할 수 있습니다. 이 옵션은 웹 리소스 데이터를 저장하는 레코드에만 태그를 지정합니다. 웹 리소스의 동작은 변경되지 않습니다.|  
|**파일 업로드**|**찾아보기...** 선택 단추를 클릭하여 웹 리소스로 업로드할 파일을 선택합니다.<br />&bull; 새 웹 리소스를 만들거나 기존 웹 리소스를 덮어쓸 때 파일을 업로드할 수 있습니다.<br />&bull; 파일의 파일 이름 확장명은 허용된 확장명과 일치해야 합니다.<br />&bull; 기본적으로 웹 리소스로 업로드할 수 있는 최대 크기 파일은 5MB입니다. 이 값은 **시스템 설정** > **이메일** 탭 > **첨부 파일에 대한 파일 크기 제한 설정** 설정을 사용하여 Dynamics 365 고객 참여에서 수정할 수 있습니다. 자세한 내용: [시스템 설정 대화 상자 - 이메일 탭](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**URL**|웹 리소스를 저장하면 웹 리소스에 대한 URL이 여기에 표시됩니다. 브라우저에서 웹 리소스를 보려면 이 링크를 선택합니다.|  
  
변경 내용을 추가한 후 **저장**을 선택한 다음, **게시**를 선택합니다.  

> [!NOTE]
> 웹 리소스에 대한 변경 내용은 게시할 때까지 응용 프로그램에 표시되지 않습니다.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>텍스트 편집기를 적절하게 사용

웹 리소스의 응용 프로그램에서 제공하는 텍스트 편집기는 텍스트 파일의 간단한 편집에만 사용해야 합니다. 이를 사용하여 HTML 웹 리소스를 만들고 편집할 수 있지만 텍스트 편집기를 사용하여 만든 HTML 웹 리소스만 편집해야 합니다. 텍스트 편집기는 매우 간단한 HTML 콘텐츠를 위해 설계되었습니다. 

> [!IMPORTANT]
> 텍스트 편집기를 사용하여 HTML 웹 리소스의 콘텐츠를 만들지 않은 경우에는 텍스트 편집기를 사용하여 편집하지 마세요.  
> 텍스트 편집기는 편집을 허용하는 방식으로 HTML 소스를 수정하는 컨트롤을 사용합니다. 이러한 변경으로 인해 브라우저의 페이지가 다르게 동작하고 더 정교한 코드가 작동을 중지할 수 있습니다. 텍스트 편집기로 HTML 웹 리소스를 열어서 변경하지 않고 저장하면 일부 HTML 웹 리소스가 중단될 수 있습니다.  자세한 내용: [개발자 설명서: HTML 웹 리소스에 대한 텍스트 편집기 사용](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
외부 편집기를 사용하여 텍스트 파일을 편집한 다음, **파일 업로드** 단추로 업로드하기 전에 로컬로 저장하는 것이 좋습니다. 이렇게 하면 이전 버전으로 돌아가야 하는 경우 웹 리소스의 복사본을 유지할 수 있습니다. 메모장과 같은 간단한 편집기를 사용할 수 있지만 더 많은 고급 기능이 있는 텍스트 편집기를 사용하는 것이 좋습니다. [Visual Studio Community](https://www.visualstudio.com/vs/community/) 및 [Visual Studio Code](https://code.visualstudio.com/)는 무료이며 웹 리소스에서 사용하는 텍스트 기반 파일을 편집할 수 있는 강력한 기능을 제공합니다.  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>양식에 웹 리소스 만들기 및 편집

양식에 웹 리소스를 추가하거나 편집하여 사용자에게 더 매력적이고 유용한 정보를 제공할 수 있습니다. 

> [!NOTE]
> 양식 머리글이나 바닥글에는 웹 리소스를 포함할 수 없습니다.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>양식으로 이동
솔루션 탐색기를 연 상태에서 **구성 요소** 아래의 **엔터티**를 확장한 다음, 작업할 엔터티를 확장합니다.

**양식**을 선택하고 목록에서 기본 형식의 양식을 찾은 다음, 항목을 두 번 클릭하거나 탭하여 양식을 열고 편집합니다.

### <a name="add-or-edit-web-resource-in-a-form"></a>양식에 웹 리소스 추가 또는 편집

양식의 웹 리소스에 대해 설정할 수 있는 속성에 대한 자세한 내용은 [웹 리소스 속성](web-resource-properties-legacy.md)을 참조하세요.

### <a name="preview"></a>미리 보기

기본 양식이 표시되는 방식 및 이벤트가 작동하는 방법을 미리 보려면:
- **홈** 탭에서 **미리 보기**를 선택한 다음, **양식 만들기**, **업데이트 양식** 또는 **읽기 전용 양식**을 선택합니다.
- 미리 보기 양식을 닫으려면 **파일** 메뉴에서 **닫기**를 선택합니다.

### <a name="save"></a>저장

양식 편집을 완료하면 **홈** 탭에서 **저장 및 닫기**를 선택하여 양식을 닫습니다. 

### <a name="publish"></a>게시

사용자 지정이 완료되면 다음을 게시합니다.
- 현재 편집 중인 구성 요소에 대해서만 사용자 지정을 게시하려면 탐색 창에서 작업 중인 엔터티를 선택한 다음, **게시**를 선택합니다.
- 게시되지 않은 모든 구성 요소에 대한 사용자 지정을 한 번에 게시하려면 탐색 창에서 **엔터티**를 선택한 다음, **작업** 도구 모음에서 **모든 사용자 지정 게시**를 선택합니다.
   
  
### <a name="see-also"></a>참고 항목  

[웹 리소스 속성](web-resource-properties-legacy.md) <br /> 
[양식 만들기 및 설계](create-design-forms.md) <br />
[사용자 지정 시작](getting-started-customization.md) <br /> 
[개발자 디벨로퍼: 고객 참여를 위한 웹 리소스](/dynamics365/customer-engagement/developer/web-resources)
