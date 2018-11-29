---
title: 모델 기반 앱 보기 정의 액세스 | MicrosoftDocs
description: 이 항목에서는 엔터티 보기에 액세스하는 방법에 대해 설명합니다.
ms.custom: ''
ms.date: 06/12/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: 034c8bef-0d1c-4ef9-8da7-f81343c4553a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="access-a-model-driven-app-view-definition-in-powerapps"></a>PowerApps의 모델 기반 앱 보기 정의 액세스

 이 항목에서는 보기 정의를 열어 보기를 구성하기 위한 속성 및 옵션을 표시합니다. 다음과 같은 몇 가지 방법으로 PowerApps에서 보기 정의에 액세스할 수 있습니다. 
  
  
## <a name="open-a-view-in-powerapps"></a>PowerApps에서 보기 열기

1.  [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인합니다.  


    > [!IMPORTANT]
    > "**모델 기반** 디자인 모드를 사용할 수 없는 경우 [환경 만들기](https://docs.microsoft.com/powerapps/administrator/create-environment)를 해야 할 수 있습니다. 

2.  **데이터**를 확장하고 **엔터티**를 선택한 다음 **거래처** 엔터티를 선택합니다.   
3. **보기** 탭을 선택한 다음 **필터 제거**를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![거래처 보기 정의](media/account-view-definitions.png)

4. 거래처 엔터티 **모든 거래처** 보기와 같이 열려는 보기를 선택합니다.

    > [!div class="mx-imgBorder"] 
    > ![모든 거래처 보기](media/all-accounts-view.png)

5. 보기 편집기에서 다음과 같은 여러 작업을 수행할 수 있습니다. 
 
- [보기의 레코드 정렬](configure-sorting.md)
- [보기에서 열 선택 및 구성](choose-and-configure-columns.md)
- [사용자 지정 컨트롤을 사용하여 데이터 시각화](use-custom-controls-data-visualizations.md) 

## <a name="open-a-view-from-an-app"></a>앱에서 보기 열기

엔터티에 대한 목록 보기의 명령 모음에서 줄임표(...) 단추를 선택하면 다음 명령이 표시됩니다.  
- **보기**: 기본 솔루션에서 현재 보기의 정의를 엽니다.  
  
- **새 시스템 보기**: 새 창을 열어 기본 솔루션에서 현재 엔터티에 대한 새 보기를 만듭니다.  
  
- **엔터티 사용자 지정**: 그런 다음 **보기**를 선택할 수 있는 기본 솔루션의 현재 엔터티의 정의로 이동합니다.  
  
- **시스템 보기**: **보기**를 선택한 경우를 제외하고 동일한 창을 **엔터티 사용자 지정**으로 엽니다.  

## <a name="open-a-view-in-solution-explorer"></a>솔루션 탐색기에서 보기를 엽니다. 
  
1.  [솔루션 탐색기](advanced-navigation.md#solution-explorer)를 엽니다.  
  
2.  **구성 요소**에서 **엔터티**를 확장한 다음 원하는 엔터티를 확장합니다.  
  
3.  **보기**를 선택합니다.  
  
4.  열려는 보기를 두 번 클릭합니다.  
  
 이 보기 목록에는 사용자가 더 쉽게 보기를 찾는 데 사용할 수 있는 필터가 4개 있습니다.  
  
    - **모든 활성 보기**  
  
    - **활성 공용 보기**  
  
    - **비활성 공용 보기**  
  
    - **활성 시스템 정의 보기**  
  
 보기가 연결된 엔터티가 관리형 솔루션의 일부인 경우 기본 솔루션에서 해당 엔터티의 보기를 계속 만들거나 편집할 수 있습니다. 시스템 보기가 엔터티에 연결되어 있으면 별도의 솔루션 구성 요소로 사용할 수 없습니다. 필드와 달리 보기는 솔루션에서 일관되는 고유 이름에 사용자 지정 접두사를 사용하지 않으므로 솔루션 컨텍스트에서 보기를 만들지 않아도 됩니다. 
 
## <a name="next-steps"></a>다음 단계
[보기 이해 ](create-edit-views.md)


