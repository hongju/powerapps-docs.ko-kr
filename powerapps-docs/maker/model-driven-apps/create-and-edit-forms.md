---
title: 모델 기반 양식 디자이너를 사용하여 양식 만들기 및 편집 | MicrosoftDocs
ms.custom: ''
ms.date: 12/13/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-forms-using-the-form-designer"></a>양식 디자이너를 사용하여 양식 만들기 및 편집 
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

새 양식 디자이너를 사용하여 모델 기반 앱에 대한 양식을 만들고 디자인합니다.

> [!IMPORTANT]
> 새 모델 기반 양식 디자이너는 현재 기본 양식 만들기 및 편집만 지원합니다. 추가 정보: [양식 유형](types-forms.md)

## <a name="create-a-form"></a>양식 만들기 
1. [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인합니다. 
2. 왼쪽 탐색 창에서 **데이터**를 확장하고 **엔터티**를 선택합니다. 
3. 거래처 엔터티 같은 엔터티를 선택한 다음 **양식** 탭을 선택합니다. 
4. **양식 추가**를 선택한 다음 **기본 양식(미리 보기)** 을 선택합니다.     
    새 양식의 내용은 기존 기본 양식 정의를 사용하여 입력됩니다. 여러 개의 기본 양식이 존재하는 경우 양식 주문의 목록 맨 위에 있는 양식이 새 양식을 채우는 데 사용됩니다. 
5. **저장**을 선택하여 양식을 저장하거나 저장하고 앱 사용자에게 변경 사항을 표시하려는 경우 **게시**를 선택합니다.  

## <a name="edit-a-form"></a>양식 편집 
1. [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인합니다. 
2. 왼쪽 탐색 창에서 확장, **데이터**를 선택하고 **엔터티**를 선택합니다. 
3. 거래처 엔터티 같은 엔터티를 선택한 다음 **양식** 탭을 선택합니다.
4. 편집하려는 양식을 선택한 다음 **양식 편집(미리보기)** 을 선택합니다.  
   또는 원하는 양식 옆의 **...** 을 선택한 다음 **양식 편집(미리보기)** 을 선택합니다. 
5. **저장**을 선택하여 양식을 저장하거나 저장하고 앱 사용자에게 변경 사항을 표시하려는 경우 **게시**를 선택합니다. 

## <a name="add-and-remove-fields"></a>필드 추가 및 제거 
양식에서 필드를 추가하거나 제거하려면 필드 창을 사용합니다. 필드 창을 사용하면 검색 및 필터를 통해 필드를 빠르게 찾을 수 있습니다. 또한 사용되지 않는 필드만 표시하는 옵션도 포함되어 있습니다. 

### <a name="add-a-field"></a>필드 추가
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form)
2. 양식 미리보기에서 다른 기존 필드나 섹션을 선택합니다. 
    - 기존 필드를 선택하면 새 필드가 기존 필드 아래에 추가됩니다. 
    - 섹션을 선택하면 열 전체에 필드를 균등하게 배분하기 위해 사용 가능한 공간에 새 필드가 추가됩니다. 
3. **필드 추가**를 선택하거나 왼쪽 창에서 **필드**를 선택합니다.  
   양식 디자이너가 시작될 때 필드 창은 기본적으로 열립니다. 
4. **필드** 창에서 추가하려는 필드를 검색, 필터링 또는 스크롤합니다. 
   필드를 찾을 수 없는 경우 양식에 이미 있을 수 있습니다. 양식에 이미 추가된 필드를 포함하여 모든 필드를 보려면 **사용되지 않은 필드만 표시**를 지웁니다. 
5. **필드** 창에서 필드를 선택하여 양식에 추가합니다. <br />
   또는 원하는 필드 옆의 **...** 을 선택한 다음 **선택한 섹션에 추가**를 선택합니다. 
6. **저장**을 선택하여 양식을 저장하거나 저장하고 최종 사용자에게 변경 사항을 표시려는 경우 **게시**를 선택합니다. 

### <a name="remove-a-field"></a>필드 제거
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form)
2. 양식 미리보기에서 양식에서 제거하려는 필드를 선택합니다. 
3. **삭제**를 선택합니다. <br />
4. **저장**을 선택합니다. 

    > [!NOTE]
    >   -  실수로 필드를 제거한 경우에는 **실행 취소**를 선택하여 작업을 되돌립니다. 
    >   -  필수 또는 잠긴 필드는 제거할 수 없습니다. 

## <a name="add-and-remove-tabs-and-sections"></a>탭 및 섹션 추가 및 제거 
양식에 탭 또는 섹션을 추가 또는 제거하려면 레이아웃 창을 사용합니다. 

### <a name="add-a-tab"></a>탭 추가
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form) 
2. 양식 미리보기에서 다른 기존 탭이나 양식을 선택합니다. 
    - 기존 탭을 선택하면 기존 탭의 오른쪽에 새 탭이 추가됩니다. 
    - 양식을 선택하면 새 탭이 양식의 맨 오른쪽 탭으로 추가됩니다. 
3. **컨트롤 추가**를 선택하거나 왼쪽 창에서 **레이아웃**을 선택합니다.  
4. **레이아웃** 창에서 **2열 탭**과 같은 탭 컨트롤을 선택하여 양식에 추가합니다. <br />
   또는 원하는 탭 컨트롤 옆의 **...** 을 선택한 다음 **양식에 추가**를 선택합니다.  
5. **저장**을 선택합니다. 


### <a name="remove-a-tab"></a>탭 제거
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form)
2. 양식 미리보기에서 삭제할 탭을 선택한 후 **삭제**를 선택합니다. 
3. **저장**을 선택합니다. 
    > [!NOTE]
    >    - 실수로 탭을 삭제한 경우에는 **실행 취소**를 선택하여 삭제 작업을 되돌립니다. 
    >     - 양식에는 하나 이상의 탭이 있어야 합니다. 양식에서 유일한 탭인 탭은 삭제할 수 없습니다. 
    >    - 잠긴 섹션이 있는 탭은 삭제할 수 없습니다. 
    >    - 필수 섹션 또는 잠긴 필드가 있는 탭은 삭제할 수 없습니다. 

### <a name="add-a-section"></a>섹션 추가 
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form)
2. 양식 미리보기에서 다른 기존 섹셕이나 탭을 선택합니다. 
    - 기존 섹션을 선택하는 경우 새 섹션이 기존 섹션 아래에 추가됩니다. 
    - 탭을 선택하면 탭의 첫 번째 열 맨 아래에 새 섹션이 추가됩니다. 
3. **컨트롤 추가**를 선택하거나 왼쪽 창에서 **레이아웃**을 선택합니다.
4. **레이아웃** 창에서 섹션 컨트롤을 선택하여 양식에 추가합니다. <br />
   또는 원하는 섹션 컨트롤 옆의 **...** 을 선택한 다음 **선택한 탭에 추가**를 선택합니다.      
5. **저장**을 선택합니다. 
 

### <a name="delete-a-section"></a>섹션을 삭제합니다. 
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form) 
2. 양식 미리보기에서 삭제할 섹션을 선택한 후 **삭제**를 선택합니다.  
3. **저장**을 선택합니다. 
    > [!NOTE]
    >    - 실수로 섹션을 삭제한 경우에는 **실행 취소**를 선택하여 삭제 작업을 되돌립니다. 
    >    - 탭에는 각 열에 하나 이상의 섹션이 있어야 합니다.  
    >    - 섹션이 탭 열에 하나만 있는 경우에는 섹션을 삭제할 수 없습니다. 
    >    - 잠긴 섹션은 삭제할 수 없습니다. 
    >    - 필수 또는 잠긴 필드가 있는 섹션은 삭제할 수 없습니다. 
 
## <a name="use-the-tree-view"></a>트리 보기 사용 
트리 보기 창에는 양식에 있는 컨트롤 및 필드의 시각적 계층 구조가 표시됩니다. 트리 보기의 아이콘을 통해 필드 또는 컨트롤의 유형을 빠르게 식별할 수 있습니다. 

트리 보기를 사용하여 양식에 있는 필드 및 컨트롤을 선택할 수도 있습니다. 트리 보기는 양식 미리보기에 표시되지 않는 숨겨진 요소를 선택하려는 경우에 유용합니다. 

트리 보기에서 노드를 확장하거나 축소하여 노드 내의 요소를 보거나 숨길 수 있습니다. 트리 보기에서 요소를 선택하면 해당 요소가 양식 미리보기에서 강조 표시되고 속성 창에 요소의 속성이 표시됩니다. 

   ![트리 보기](media/tree-view.png)

### <a name="open-the-tree-view"></a>트리 보기 열기 
1. 양식 디자이너를 열어 양식을 만들거나 편집합니다. 추가 정보: [양식 만들기](#create-a-form) 및 [양식 편집](#edit-a-form)  
2. 왼쪽 창에서 **트리 보기**를 선택합니다.

## <a name="see-also"></a>참조
[모델 기반 양식 디자이너 개요](form-designer-overview.md) <br />
[필드 만들기 및 편집](../common-data-service/create-edit-field-portal.md)
