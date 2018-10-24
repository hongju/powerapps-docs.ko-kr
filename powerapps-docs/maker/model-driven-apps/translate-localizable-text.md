---
title: 모델 기반 앱의 지역화할 수 있는 텍스트 번역 | Microsoft Docs
description: 다국어를 지원하도록 번역된 지역화할 수 있는 텍스트를 가져오는 방법 알아보기
ms.custom: ''
ms.date: 06/03/2018
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2e305313f3b86be2ea410f6668676b56aa79d95
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690799"
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>모델 기반 앱의 지역화할 수 있는 텍스트 번역

필드 레이블 또는 드롭다운 목록 값과 같은 엔터티 또는 필드 텍스트를 사용자 지정한 경우, 조직의 기본 언어 버전으로 작업하지 않는 조직의 사용자에게 원하는 언어로 지정된 텍스트를 제공할 수 있습니다. 

이 프로세스의 단계는 다음과 같습니다.
1. 사용자 환경에 다른 언어를 사용하도록 설정
2. 지역화할 수 있는 텍스트 내보내기
3. 지역화할 수 있는 텍스트 번역하기
4. 지역화된 텍스트 가져오기

## <a name="enable-other-languages-for-your-environment"></a>사용자 환경에 다른 언어를 사용하도록 설정

아직 사용자 환경에 언어를 사용하도록 설정하지 않은 경우 [언어 사용](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)에 설명된 단계를 따라 언어를 사용하도록 설정하세요.

> [!IMPORTANT]
> 각 언어를 사용하도록 설정하는 데 몇 분 정도 걸릴 수 있습니다. 이때 사용자 환경의 다른 사용자는 앱을 사용하지 못할 수 있습니다. 사용자에게 가장 방해가 적은 시간에 언어를 사용하도록 설정해야 합니다.

> [!TIP]
> 어를 사용하도록 설정할 때 각 언어에 사용되는 LCID 값을 메모하세요. 이 값은 지역화할 수 있는 텍스트에 대한 내보낸 데이터의 언어를 나타냅니다. 언어 코드는 4자리 또는 5자리 로캘 ID입니다. 유효한 로캘 ID 값은 [LCID(로캘 ID) 차트](http://go.microsoft.com/fwlink/?LinkId=122128)에서 찾을 수 있습니다.

## <a name="export-the-localizable-text"></a>지역화할 수 있는 텍스트 내보내기

내보낼 지역화할 수 있는 텍스트의 범위는 지역화할 수 있는 텍스트가 포함된 비관리 솔루션입니다. 이 작업은 솔루션 탐색기를 통해서만 수행할 수 있습니다.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

메뉴 표시줄에서 지역화할 수 있는 텍스트가 포함된 비관리 솔루션을 열고 **번역** > **번역 내보내기**를 선택합니다. 

![번역 내보내기](media/export-localizable-text.png)

다음과 같은 경고가 표시됩니다.
> 번역의 사용자 지정된 레이블을 내보내는 데 몇 분 정도 걸릴 수 있습니다. 첫 번째 내보내기가 완료될 때까지 내보내기 링크를 다시 클릭하지 마세요. 지금 내보내시겠습니까? 

계속하려면 **확인**을 클릭하세요.

내보내기가 완료되면 다운로드 폴더에서 `CrmTranslations_{0}_{1}.zip`이라는 파일을 찾을 수 있습니다. 여기서 `{0}`은 솔루션의 고유한 이름이며, `{1}`은 솔루션의 버전 번호입니다.

## <a name="get-the-localizable-text-translated"></a>지역화할 수 있는 텍스트 번역하기

언어 전문가, 번역 에이전시 또는 지역화 회사에 이 파일을 보낼 수 있습니다.

텍스트 번역에 대한 지식이 있거나 서식만 보려면 내보낸 zip 파일의 압축을 풀어서 XML 파일이 두 개 있는지 볼 수 있습니다. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

Microsoft Office Excel로 CrmTranslations.xml 파일을 열 수 있습니다.

> [!TIP]
> 일반적으로 XML 파일을 Excel로 열지 않는 경우 Excel을 연 다음, 압축을 푼 CrmTranslations.xml 파일의 경로를 붙여넣어 파일을 열도록 선택할 수 있습니다.

> [!IMPORTANT]
> 파일 형식을 변경하지 않도록 하세요. 다른 형식으로 파일을 저장하는 경우 파일을 다시 가져올 수 없습니다.

Excel에서 데이터를 볼 때는 **지역화된 레이블** 탭을 확인하세요.

![지역화를 위해 내보낸 텍스트](media/localized-labels-tab-exported-languages.png)

사용자 지정 엔터티 또는 필드에는 지역화할 수 있는 텍스트를 위한 빈 셀이 있습니다. 이러한 항목에 지역화된 값을 추가하세요.

> [!NOTE]
> 표시 이름이나 임의의 표준 엔터티 또는 엔터티 필드에 대한 설명을 변경한 경우에도 지역화된 문자열에는 원래 값에 대한 번역이 계속 반영됩니다. 이러한 새 값을 반영하도록 지역화해야 합니다.

**표시 문자열** 탭에는 리본 명령, 오류 메시지 및 양식 레이블과 같은 기타 UI 요소에 표시되는 텍스트가 포함되어 있습니다.

### <a name="updating-localizable-text-in-the-base-language"></a>기본 언어로 지역화할 수 있는 텍스트 업데이트

특수한 메시지에 포함된 표준 엔터티 또는 엔터티 필드의 표시 이름을 변경하는 경우 **표시 문자열** 탭의 정보를 업데이트하여 사용자 지정된 이름을 사용할 수 있습니다.

> [!TIP]
> 시스템 엔터티 메시지를 편집하기 위해 노출된 UI에는 엔터티 이름에 대한 여러 참조가 포함되어 있지만 모두 포함된 것은 아닙니다. 이 기술을 사용하면 더 많은 것을 확인할 수 있습니다. 자세한 정보: [시스템 엔터티 메시지 편집](../common-data-service/edit-system-entity-messages.md)

예를 들어 계정 엔터티의 표시 이름을 *Company*로 변경하는 경우 **표시 문자열**의 기본 언어 열을 검색하여 `account`, `accounts`, `Account`, and `Accounts`와 같은 일치 항목을 찾은 다음, 각각 `company`, `companies`, `Company` 및 `Companies`로 적절히 바꿀 수 있습니다.

> [!IMPORTANT]
> 이를 위해 파일에서 일반적인 찾기/바꾸기를 수행하지는 마세요. 일치하는 텍스트가 실제로 자신이 변경한 이름을 나타내는지 주의해야 합니다.


## <a name="import-the-localized-text"></a>지역화된 텍스트 가져오기
텍스트를 가져오려면 파일을 압축하고 시스템으로 가져와야 합니다.

### <a name="compress-the-files"></a>파일 압축

`CrmTranslations.xml` 파일이 변경된 후에는 `[Content_Types].xml` 파일과 함께 zip 형식으로 압축해야 합니다. *두 파일*을 선택한 다음, 마우스 오른쪽 단추로 클릭하여 상황에 맞는 메뉴를 엽니다. 상황에 맞는 메뉴에서 **보낼 대상** > **압축 폴더**를 선택합니다.

### <a name="import-the-files"></a>파일 가져오기

번역을 내보낸 비관리 솔루션의 메뉴에서 **번역** > **번역 가져오기**를 선택합니다. 

![번역 가져오기](media/import-translations.png)

압축된 번역 텍스트가 포함된 파일을 선택하고 **가져오기**를 선택합니다.

![선택한 파일 가져오기](media/import-translated-text-dialog.png)

번역된 텍스트를 가져온 후에는 모든 사용자 지정 항목을 게시하여 앱의 변경 사항을 확인해야 합니다.

## <a name="community-tools"></a>커뮤니티 도구

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/)는 XrmToolBox 커뮤니티가 개발한 도구입니다. Easy Translator를 사용하여 컨텍스트 정보가 포함된 번역을 내보내고 가져올 수 있습니다. 

> [!NOTE]
> 커뮤니티 도구는 Microsoft에서 지원하지 않습니다.
> 도구에 대한 질문이 있으면 게시자에게 문의하세요. 자세한 정보: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>다음 단계
[조직의 지역 및 언어 옵션](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[시스템 엔터티 메시지 편집](../common-data-service/edit-system-entity-messages.md)

