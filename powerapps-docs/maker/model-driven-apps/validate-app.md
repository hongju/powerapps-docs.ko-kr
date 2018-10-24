---
title: 앱 디자이너를 사용하여 모델 기반 앱의 유효성 검사 및 게시 | MicrosoftDocs
description: 모델 기반 앱의 유효성을 검사하고 게시하는 방법 알아보기
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 10
topic-status: Drafting
ms.openlocfilehash: e3802ef423e7012974c24311c36b78cd56f8ed06
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693727"
---
# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>앱 디자이너를 사용하여 모델 기반 앱의 유효성 검사 및 게시

앱을 작동하는 데 필요하지만 앱에 추가되지 않은 자산 종속성을 확인하도록 앱의 유효성을 검사합니다. 유효성 검사를 성공한 후 앱을 게시합니다. 
  
예를 들어 추가하지 않은 사례 혼합(우선 순위별) 또는 사례 확인 추세(일별)와 같은 차트를 사용하는 앱에 고객 서비스 성능 대시보드를 추가했습니다. 이 앱의 유효성을 검사할 때 모든 누락, 필요한 자산 목록을 얻게 됩니다.  
  
앱의 유효성을 검사할 때 앱 디자이너 캔버스는 누락된 자산에 대한 세부 정보를 표시합니다.  
  
1.  앱 디자이너에서 **유효성 검사**를 선택합니다.  
  
     알림 표시줄이 나타나고 앱에 오류 또는 경고가 있는지 여부를 표시합니다. 알림 표시줄은 예를 들어 엔터티에 양식 또는 보기가 없거나 앱이 구성 요소를 포함하지 않는 경우에 경고를 표시합니다. 사이트 맵이 앱에 대해 구성되지 않은 경우 오류가 나타날 수 있습니다. 주소 지정 경고 없이 앱을 게시할 수 있지만 게시하려면 먼저 오류를 수정해야 합니다.  
  
     ![앱에 경고를 표시하는 알림 표시줄](media/app-designer-warning-notification.png "앱에 경고를 표시하는 알림 표시줄")  
  
     앱 디자이너는 또한 필요한 자산을 누락한 각 아티팩트 또는 자산 타일에 종속성의 수와 함께 경고 기호를 표시합니다.  
  
     ![앱 디자이너 타일의 누락된 구성 요소 경고](media/warning--button-on-app-designer-tile.png "앱 디자이너 타일의 누락된 구성 요소 경고")  
  
2.  필요한 자산을 추가하려면 캔버스의 오른쪽에서 **필수** 탭을 선택합니다. 앱에서 하나 이상의 필수 자산이 누락된 경우 **필수** 탭이 표시됩니다.  
  
     탭은 필수 구성 요소 목록을 보여줍니다.  
  
     ![앱에서 누락된 구성 요소 목록을 보여주는 필수 탭](media/app-designer-required-components-tab.png "앱에서 누락된 구성 요소 목록을 보여주는 필수 탭")  
  
3.  추가하려는 자산을 선택한 다음, **종속성 추가**를 선택합니다. 필수 자산을 추가하는 경우 자산을 추가한 타일의 수가 감소합니다.  
  
    > [!NOTE]
    >  예를 들어 다양한 앱 구성 요소에서 일반 자산이 필요한 경우 대시보드 및 엔터티에서 양식이 필요하며 해당 자산을 대시보드 종속성 트리에서 한 번만 추가합니다. 종속성 개수는 엔터티 타일이 아닌 대시보드 타일에서만 감소합니다. 그러나 종속성은 둘 모두에 대해 확인됩니다.  
    >   
    >  **최신 종속성 가져오기** ![앱 디자이너에서 최신 종속성 가져오기 단추](media/app-designer-get-latest-dependencies.png "앱 디자이너에서 최신 종속성 가져오기 단추")를 선택하거나 **유효성 검사**를 다시 선택하여 종속성의 최신 집합을 가져옵니다. 앱을 저장한 후에만 이러한 단추가 표시됩니다.  
  
     제안된 필수 구성 요소를 추가하지 않으려는 경우 **종속성 숨기기**를 선택합니다. 앱 디자이너에서 앱을 열 때 확인되지 않은 경고가 나타나며 **유효성 검사** 또는 **최신 종속성 가져오기** ![앱 디자이너에서 최신 종속성 가져오기 단추](media/app-designer-get-latest-dependencies.png "앱 디자이너에서 최신 종속성 가져오기 단추")를 선택합니다.  
  
    > [!NOTE]
    >  지금 종속성을 숨기고 이 앱을 나중에 내보내려는 경우 이러한 모든 종속성이 다시 표시됩니다.  
  
## <a name="publish-an-app-using-the-app-designer"></a>앱 디자이너를 사용하여 앱 게시

사용자가 사용할 수 있도록 앱을 게시합니다.  
  
 구성 요소를 추가하고, 유효성을 검사하고, 앱을 저장한 후 명령 모음에서 **게시**를 선택합니다. [내 앱](advanced-navigation.md#my-apps) 페이지의 앱 타일에서 앱을 게시할 수도 있습니다. **편집 중인 앱** 보기의 게시하려는 앱 타일의 오른쪽 아래 모서리에서 **더 많은 옵션** 단추(**...**)를 선택한 다음, **게시**를 선택합니다.  
  
 앱 상태가 게시됨으로 변경됩니다. 앱 디자이너의 오른쪽 위 모서리에서 확인할 수 있습니다. 앱이 **편집 중인 앱** 보기에서 **게시된 앱** 보기로 이동하고, 게시된 날짜가 앱 타일에 표시됩니다.  
  
> [!NOTE]
> - 앱에 유효성 검사 오류가 있으면 알림 표시줄에 오류가 표시됩니다. 오류를 해결할 때까지 앱을 게시할 수 없습니다.  
> - 저장할 때까지 앱을 게시할 수 없습니다.  

## <a name="next-steps"></a>다음 단계  
[PowerApps와 모델 기반 앱 공유](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [모바일 장치에서 모델 기반 앱 실행](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
