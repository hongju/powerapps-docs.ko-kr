---
title: PowerApps에서 모델 기반 앱 보기의 열 선택 및 구성 | MicrosoftDocs
description: 앱에 대한 보기 선택 및 구성 방법 알아보기
keywords: ''
ms.date: 06/11/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 31bfcf18-58c3-491c-91b5-f9b0f5424852
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 25
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-choose-and-configure-columns-in-model-driven-app-views"></a>자습서: 모델 기반 앱 보기의 열 선택 및 구성

<a name="BKMK_ChooseAndConfigureColumns"></a>   

 필터 조건에 따라 PowerApps 보기에 표시되는 열은 보기에 제공되는 값에 매우 중요합니다. 이 자습서에서는 다음 작업을 수행하여 보기를 만들거나 편집합니다.  

-   [보기 편집기 열기](choose-and-configure-columns.md#open-the-view-editor)  
   
-   [열 추가](choose-and-configure-columns.md#BKMK_AddColumns)  
  
-   [열 제거](choose-and-configure-columns.md#BKMK_RemoveColumns)  
  
-   [열 너비 변경](choose-and-configure-columns.md#BKMK_ChangeColumnWidth)  
  
-   [열 이동](choose-and-configure-columns.md#BKMK_MoveAColumns)  
  
-   [열의 상태 표시 활성화 또는 비활성화](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence)  
  
-   [찾기 열 추가](choose-and-configure-columns.md#BKMK_AddFindColumns)  

### <a name="open-the-view-editor"></a>보기 편집기 열기

1.  [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 사이트에서 **모델 기반**(탐색 창의 왼쪽 아래)을 선택합니다.  

    ![모델 기반 디자인 모드](../model-driven-apps/media/model-driven-switch.png)

2.  **데이터**를 확장하고 **엔터티**를 선택하고 원하는 엔터티를 선택한 다음 **보기** 탭을 선택합니다. 

    > [!div class="mx-imgBorder"] 
    > ![ 보기](media/available-views.png)

3. 기존 보기를 선택하여 열거나 도구 모음에서 **보기 추가**를 선택합니다. 

<a name="BKMK_AddColumns"></a>   
### <a name="add-columns"></a>열 추가  
 현재 엔터티 또는 현재 엔터티와 1:N 엔터티 관계를 가진 관련 엔터티에서 열을 포함할 수 있습니다.  
  
 예를 들어 사용자 담당 엔터티의 담당자를 열에 표시할 수 있습니다. 현재 엔터티의 **담당자** 필드를 선택하여 담당자 이름을 표시할 수 있습니다. 그러면 담당자의 **사용자** 레코드를 열 수 있는 링크로 표시됩니다. 이 경우 [열에 대한 현재 상태를 사용하거나 사용하지 않도록 설정](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence)할 수 있는 옵션도 있습니다.  
  
 레코드 담당자의 전화 번호를 표시하려면 **레코드 종류** 드롭다운에서 **담당 사용자(사용자)** 를 선택한 후 **기본 전화** 필드를 선택해야 합니다.  
  
#### <a name="add-columns-to-views"></a>보기에 열 추가  
  
1.  보기를 만들고 편집하는 동안 **열 추가**를 선택합니다. 

    > [!div class="mx-imgBorder"] 
    > ![편집기 보기 열 추가](media/view-editor.png)

    **열 추가** 대화 상자가 나타납니다.

    > [!div class="mx-imgBorder"] 
    > ![열 추가](media/add-columns.png)
  
2.  관련 엔터티에서 필드를 포함하려면 **레코드 종류**를 선택합니다.  
  
3.  관련 엔터티에서 여러 필드를 선택할 수 있습니다.  
  
4.  원하는 필드를 선택한 후 **확인**을 선택하여 **열 추가** 대화 상자를 닫습니다.  
  
 열을 추가하면 보기 너비를 늘입니다. 보기 너비가 페이지에 표시할 수 있는 공간보다 크면 가로 스크롤 막대로 스크롤하고 숨겨진 열을 볼 수 있습니다.  
  
> [!TIP]
>  보기가 특정 필드의 데이터를 필터링하여 특정 값을 가진 레코드만 표시할 경우 보기에 해당 열을 포함하지 마십시오. 예를 들어 활성 레코드만 표시할 경우 보기에 상태 열을 포함하지 마십시오. 대신 보기에 표시된 모든 레코드가 활성 상태임을 나타내도록 보기 이름을 지정합니다.  
  
> [!NOTE]
>  업데이트된 엔터티에 대한 조회 보기에 열을 추가하면 처음 세 열만 표시됩니다.  
  
<a name="BKMK_RemoveColumns"></a>   
### <a name="remove-columns"></a>열 제거  
  
1.  보기를 만들고 편집하는 동안 제거할 열을 선택합니다.  
  
2.  **일반 작업** 영역에서 **제거**를 선택합니다.  
  
3.  확인 메시지에서 **확인**을 선택합니다.  
  
<a name="BKMK_ChangeColumnWidth"></a>   
### <a name="change-column-width"></a>열 너비 변경  
  
1.  보기를 만들고 편집하는 동안 변경할 열을 선택합니다.  
  
2.  **일반 작업** 영역에서 **속성 변경**을 선택합니다.  
  
3.  **열 속성 변경** 대화 상자에서 열 너비를 설정하는 옵션을 선택하고 **확인**을 선택합니다.  
  
<a name="BKMK_MoveAColumns"></a>   
### <a name="move-a-column"></a>열 이동  
  
1.  보기를 만들고 편집하는 동안 이동할 열을 선택합니다.  
  
2.  **일반 작업** 영역에서 화살표를 사용하여 열을 왼쪽 또는 오른쪽으로 이동합니다.  
  
<a name="BKMK_EnableOrDisablePresence"></a>   
### <a name="enable-or-disable-presence-for-a-column"></a>열의 상태 표시 활성화 또는 비활성화  
 다음 조건이 참이면 사용자는 목록에서 사용자가 사용할 수 있는지 여부와 인스턴트 메시징으로 상호 작용할 수 있는지 보여 주는 비즈니스용 Skype 온라인 상태 표시 컨트롤을 볼 수 있습니다.  
  
-   사용자는 Edge 또는 Internet Explorer를 사용합니다.  
  
-   비즈니스용 Skype가 설치되어 있습니다.  
  
-   사용자가 Internet Explorer에서 Microsoft ActiveX를 활성화합니다.  
  
-   사용자의 조직은 시스템 설정에서 시스템의 상태 표시가 활성화되어 있습니다.  
  
 상태 표시 컨트롤 및 활성화하는 설정은 전자 메일 사용 엔터티(사용자, 연락처, 영업 기회, 잠재 고객 또는 사용자 지정 엔터티)의 기본 필드를 표시하는 열에만 사용할 수 있습니다.  
  
#### <a name="enable-or-disable-skype-for-business-presence-for-a-column"></a>열의 비즈니스용 Skype 상태 표시 활성화 또는 비활성화  
  
1.  보기를 만들고 편집하는 동안 변경할 열을 선택합니다.  
  
2.  **일반 작업** 영역에서 **속성 변경**을 선택합니다.  
  
3.  **열 속성 변경** 대화 상자에서 **이 열의 현재 상태 사용**을 선택하거나 선택 취소한 후 **확인**을 선택합니다.  
  
<a name="BKMK_AddFindColumns"></a>   
### <a name="add-find-columns"></a>찾기 열 추가  
 찾기 열은 사용자가 목록에 표시되는 **레코드 검색** 텍스트 상자를 사용하거나 사용자가 조회 필드의 레코드를 검색할 때처럼 응용 프로그램에서 엔터티의 레코드를 검색할 수 있을 때마다 응용 프로그램에서 검색되는 열입니다.  
  
1.  **빠른 찾기** 보기를 엽니다. 빠른 찾기 보기에 대한 자세한 내용은 [보기의 유형](create-edit-views.md#types-of-views)을 참조하십시오.  
  
2.  **찾기 열 추가**를 선택하여 대화 상자를 엽니다.  
  
3.  검색할 열이 포함된 필드를 선택합니다.  
  
4.  **확인**을 선택하여 **찾기 열 추가** 대화 상자를 닫습니다.  

## <a name="community-tools"></a>커뮤니티 도구

**보기 레이아웃 복제기** 및 **보기 디자이너**는 XrmToolBox 커뮤니티가 Dynamics 365 Customer Engagement를 위해 개발하여 제공하는 도구입니다. 커뮤니티 개발 도구에 대해서는 [개발자 도구](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) 항목을 참조하십시오.

> [!NOTE]
> 커뮤니티 도구는 Microsoft Dynamics의 제품이 아니며 커뮤니티 도구에 대해 지원을 확장하지 않습니다. 도구와 관련된 질문이 있으면 게시자에게 문의하십시오. 추가 정보: [XrmToolBox](https://www.xrmtoolbox.com) 

## <a name="next-steps"></a>다음 단계
[보기 만들기 또는 편집](create-edit-views.md)
