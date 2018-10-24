---
title: 솔루션 게시자 접두사 변경 | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 5881dd6742dd441d135768d3a96fd36dbef9e700
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693839"
---
# <a name="change-the-solution-publisher-prefix"></a>솔루션 게시자 접두사 변경

수행한 모든 사용자 지정은 솔루션의 일부입니다. 모든 솔루션에는 게시자가 있습니다. 기본적으로 PowerApps를 사용하여 작업하는 솔루션은 **CDS 기본 게시자**와 연결된 **Common Data Services 기본 솔루션**이 됩니다.

기본 사용자 지정 접두사는 이 게시자에 임의로 할당됩니다. 예를 들어 `cr8a3`이 될 수 있습니다. 즉, 조직에 대해 만들어진 메타데이터의 모든 새 항목의 이름은 해당 항목을 고유하게 식별하는 데 사용되는 이름 앞에 추가되는 이것을 갖습니다. **Animal**이라는 새 항목을 만드는 경우 앱에 대한 CDS에서 사용되는 고유한 이름은 `cr8a3_animal`입니다. 모든 새 필드(특성), 관계 또는 옵션 집합 옵션에 대해서도 마찬가지입니다.

다른 솔루션 게시자에 대해 생성된 메타데이터 항목과 함께 설치되도록 솔루션을 배포하는 경우가 아니면 사용자 지정 접두사는 실제로 중요하지 않습니다. 사용자의 앱을 사용하는 대부분의 사람들에게 표시되지 않습니다. 하지만 보고서 작성과 같은 작업을 수행하는 개발자 및 다른 기술 사용자에게 노출됩니다. 항목을 추가한 솔루션을 이해하는 빠른 방법을 제공합니다.

이러한 이유로 많은 사람들은 특히 다른 솔루션에서 가져온 항목을 포함하는 메타데이터 항목을 보는 경우에 더욱 의미 있을 수 있도록 솔루션 게시자 접두사를 변경하려고 합니다. 

> [!NOTE]
> 솔루션 게시자 접두사를 변경하는 경우 새 메타데이터 항목을 만들기 전에 수행해야 합니다. 메타데이터 항목의 이름을 변경할 수 없습니다.
> 사용자 지정 접두사 값을 변경하는 경우 다음 필드를 탭해야 합니다. **옵션 값 접두사**는 사용자 지정 접두사에 따라 숫자를 자동으로 생성합니다. 이 숫자는 옵션 집합에 옵션을 추가할 때 사용되며 옵션을 추가하는 데 사용되었던 솔루션의 표시기를 제공합니다. 

## <a name="change-the-solution-publisher-prefix-for-the-cds-default-publisher"></a>CDS 기본 게시자에 대한 솔루션 게시자 접두사 변경  

 1. PowerApps 포털의 왼쪽 아래 모서리에서 **모델 기반**을 선택합니다.
 2. 왼쪽 탐색 창에서 **고급**을 클릭하여 **Common Data Services 기본 솔루션**을 엽니다.
 3. 솔루션 탐색기의 왼쪽 탐색 창에서 **정보** 영역을 선택합니다.
 4. **게시자** 링크를 클릭하여 **CDS 기본 게시자** 양식을 엽니다.
 5. **접두사** 필드 값을 원하는 사용자 지정 접두사로 편집합니다.
 6. **저장 후 닫기**를 클릭합니다.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>모든 게시자에 대한 솔루션 게시자 접두사 변경

해당 솔루션을 배포하는 사용자는 일반적으로 **Common Data Services 기본 솔루션**이 아닌 사용자가 만드는 솔루션 내에서 작업합니다. 사용자 지정 접두사는 일반적으로 솔루션을 만들 때 설정됩니다. 다음 단계를 수행하여 사용 중인 다른 관리되지 않는 솔루션에 대한 사용자 지정 접두사를 변경할 수 있습니다. 

 1. PowerApps 포털의 왼쪽 아래 모서리에서 **모델 기반**을 선택합니다.
 2. 왼쪽 탐색 창에서 **고급**을 클릭하여 **Common Data Services 기본 솔루션**을 엽니다.
 3. 페이지의 URL을 편집하여 `dynamics.com` 후의 모든 항목을 제거하고 페이지를 다시 로드합니다.
 4. **설정** > **사용자 지정** > **사용자 지정**으로 이동합니다. 
 5. **게시자**를 클릭합니다. 이제 사용 가능한 게시자 목록을 볼 수 있습니다.
 6. 편집하려는 게시자를 클릭하여 게시자 양식을 엽니다.
 7. **접두사** 필드 값을 원하는 사용자 지정 접두사로 편집합니다.
 6. **저장 후 닫기**를 클릭합니다.
  