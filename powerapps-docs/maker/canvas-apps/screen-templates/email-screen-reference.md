---
title: 캔버스 앱에 대 한 전자 메일 화면 템플릿에 대 한 참조 | Microsoft Docs
description: PowerApps의 캔버스 앱에 대 한 전자 메일 화면 템플릿을 작동 하는 방법의 세부 정보 이해
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8f77fe1194ace2f8cb5abeb3f9657cc76aab263a
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459485"
---
# <a name="reference-information-about-the-email-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 전자 메일 화면 템플릿에 대 한 참조 정보

PowerApps의 캔버스 앱에 대 한 전자 메일 화면 템플릿에 중요 한 각 컨트롤 화면의 전체 기본 기능에 기여 하는 방법을 이해 합니다. 이 심층 동작 수식 및 컨트롤 사용자 입력에 응답 하는 방법을 결정 하는 다른 속성의 값을 표시 합니다. 이 화면의 기본 기능의 간략 한 설명을에 대 한 참조를 [전자 메일 화면 개요](email-screen-overview.md).

이 항목에서는 몇 가지 중요 한 컨트롤을 강조 표시 하 고 다양 한 속성을 수식 또는 식에 설명 (같은 **항목** 하 고 **OnSelect**) 이러한 컨트롤은 설정 됩니다.

* [검색 입력란](#text-search-box)
* [추가 아이콘](#add-icon)
* [사람 찾아보기 갤러리](#people-browse-gallery)
* [전자 메일 사용자 갤러리](#email-people-gallery) (+ 자식 컨트롤)
* [메일 아이콘](#mail-icon)

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="text-search-box"></a>텍스트 검색 상자

   ![TextSearchBox 컨트롤](media/email-screen/email-search-box.png)

화면에서 다른 여러 컨트롤에 대 한 종속성을 **검색 입력란** 제어 합니다.

* 모든 텍스트를 입력 하기 시작할 경우 **PeopleBrowseGallery** 나타납니다.
* 유효한 전자 메일 주소를 입력 하면 **AddIcon** 나타납니다.
* 사용자가 내에서 사용자를 선택 하는 경우 **PeopleBrowseGallery**, 검색 내용을 다시 설정 됩니다.

## <a name="add-icon"></a>추가 아이콘

   ![AddIcon 컨트롤](media/email-screen/email-add-icon.png)

합니다 **추가 아이콘** 컨트롤을 사용 하면 앱 사용자가 구성 되는 전자 메일 받는 사람 목록에 해당 조직 내에서 존재 하지 않습니다 하는 사람을 추가할 수 있습니다.

* 속성: **Visible**<br>
    값: 검색 상자에 유효한 전자 메일 주소를 입력 하는 경우에 컨트롤을 표시 하는 논리:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```
  한 줄씩, 앞에 나오는 코드 블록에 따르면 합니다 **추가 아이콘** 컨트롤 표시 됩니다. 경우에만:

    * **TextSearchBox** 텍스트를 포함 합니다.
    * 텍스트가 **TextSearchBox** 유효한 전자 메일 주소입니다.
    * 텍스트가 **TextSearchBox** 에 존재 하지 않는 합니다 **MyPeople** 컬렉션입니다.

* 속성: **OnSelect**<br>
    값: 이 선택 하면 올바른 전자 메일 주소를 추가 합니다 **MyPeople** 컬렉션입니다. 이 컬렉션은 받는 사람 목록으로 화면에서 사용 됩니다.

    ```powerapps-dot
    Collect( MyPeople,
        { 
            DisplayName: TextSearchBox.Text, 
            UserPrincipalName: TextSearchBox.Text, 
            Mail: TextSearchBox.Text
        }
    );
    Reset( TextSearchBox )
    ```
  
  이 코드 블록에 행을 추가 합니다 **MyPeople** 컬렉션에 있는 텍스트를 사용 하 여 세 개의 필드를 채우려고 **TextSearchBox**합니다. 이러한 세 가지 필드는 **DisplayName**하십시오 **UserPrincipalName**, 및 **메일**합니다. 내용을 다시 **TextSearchBox**합니다.

## <a name="people-browse-gallery"></a>사람 찾아보기 갤러리

   ![PeopleBrowseGallery 컨트롤](media/email-screen/email-browse-gall.png)

* 속성: **항목**<br>
    값: 에 입력 된 검색 텍스트가 상위 15 검색 결과 **TextSearchBox** 제어 합니다.
    
    ```powerapps-dot
    If( !IsBlank( Trim(TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( {searchTerm: Trim( TextSearchBox.Text ), top: 15} )
    )
    ```

  이 갤러리의 항목이 검색 결과에서 채워지는 합니다 [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) 작업 합니다. 작업 텍스트를 가져와 `Trim(TextSearchBox)` 검색으로 용어 및 상위 15 결과 반환 합니다 기준으로 검색 합니다.
  
  **TextSearchBox** 래핑됩니다는 `Trim()` 공간에서 사용자 검색을 유효 하지 않으므로 작동 합니다. 합니다 `Office365Users.SearchUser` 작업에 래핑됩니다는 `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` 검색 상자는 사용자가 입력 한 텍스트를 포함 하는 경우에 작업이 수행 되는 함수입니다. 이 성능을 향상 시킵니다. 

### <a name="people-browse-gallery-title-control"></a>사람 찾아보기 갤러리 제목 컨트롤

   ![PeopleBrowseGallery 제목 컨트롤](media/email-screen/email-browse-gall-title.png)

* 속성: **텍스트**<br>
    값: `ThisItem.DisplayName`

  Office 365 프로필에서 사용자의 표시 이름을 표시합니다.

* 속성: **OnSelect**<br>
    값: 사용자는 응용 프로그램 수준 컬렉션에 추가할 코드 및 사용자를 선택 합니다.

    ```powerapps-dot
    Concurrent(
        Set( _selectedUser, ThisItem ),
        Reset( TextSearchBox ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem )
        )
    )
    ```
다음 세 가지를 동시에 수행이 컨트롤을 선택 합니다.

   * 설정 된 **_selectedUser** 선택한 항목에 변수입니다.
   * 재설정에 검색 용어가 **TextSearchBox**합니다.
   * 선택한 항목을 추가 합니다 **MyPeople** 컬렉션, 받는 사람 집합으로 전자 메일 화면에는 선택한 모든 사용자의 컬렉션입니다.

## <a name="email-people-gallery"></a>전자 메일 사용자 갤러리

   ![EmailPeopleGallery 컨트롤](media/email-screen/email-people-gall.png)

* 속성: **항목**<br>
    값: `MyPeople`

  초기화 또는 선택 하 여 추가할 사용자는 컬렉션을 **PeopleBrowseGallery 제목** 컨트롤입니다.

* 속성: **Height**<br>
    값: 갤러리에서 현재 항목의 수에 따라, 높이 설정 하려면 논리:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery.TemplateHeight + EmailPeopleGallery.TemplatePadding * 2) *
            RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0 ),
        304
    )
    ```

  이 갤러리의 높이 304의 최대 높이 사용 하 여 갤러리에서 항목의 수를 조정합니다.
  
  걸리는 `TemplateHeight + TemplatePadding * 2` 단일 행의 총 높이 **EmailPeopleGallery**, 행의 수로 곱합니다. 이후 `WrapCount = 2`, true 행 수가 `RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0)`합니다.

* 속성: **ShowScrollbar**<br>
    값: `EmailPeopleGallery.Height >= 304`
  
  갤러리의 높이 304에 도달 하면 스크롤 막대가 표시 됩니다.

### <a name="email-people-gallery-title-control"></a>전자 메일 사용자 갤러리 제목 컨트롤

   ![EmailPeopleGallery 제목 컨트롤](media/email-screen/email-people-gall-text.png)

* 속성: **OnSelect**<br>
    값: `Set(_selectedUser, ThisItem)`

  설정 된 **_selectedUser** 에서 선택한 항목에 변수 **EmailPeopleGallery**합니다.

### <a name="email-people-gallery-iconremove-control"></a>전자 메일 사용자 갤러리 iconRemove 컨트롤

   ![MonthDayGallery 제목 컨트롤](media/email-screen/email-people-gall-delete.png)

* 속성: **OnSelect**<br>
    값: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

  레코드를 조회 합니다 **MyPeople** 컬렉션 위치 **UserPrincipalName** 일치 하는 **UserPrincipalName** 제거에서 기록 하 고 선택한 항목의는 컬렉션입니다.

## <a name="mail-icon"></a>메일 아이콘

* 속성: **OnSelect**<br>
    값: 사용자의 전자 메일 메시지를 보내도록 논리:

    ```powerapps-dot
    Set( _emailRecipientString, Concat( MyPeople, Mail & ";" ) );
    'Office365'.SendEmail( _emailRecipientString, 
        TextEmailSubject.Text,  
        TextEmailMessage.Text, 
        { Importance:"Normal" }
    );
    Reset( TextEmailSubject );
    Reset( TextEmailMessage );
    Clear( MyPeople )
    ```

  전자 메일 메시지를 보내는 전자 메일 주소의 세미콜론으로 구분 된 문자열로 필요 합니다. 위의 코드:
  1. 코드의 첫 번째 줄은는 **메일** 의 모든 행에서 필드를 **MyPeople** 컬렉션을 세미콜론으로 구분 된 전자 메일 주소의 단일 문자열로 연결 및 설정의 **_ emailRecipientString** 변수를 문자열 값입니다.

  1. 사용 하 여는 [Office365.SendEmail](https://docs.microsoft.com/connectors/office365/#sendemail) 받는 사람에 게 전자 메일을 보내는 작업을 합니다.
    작업에 세 개의 필수 매개 변수를 **하**, **주체**, 및 **본문**, 및 하나의 선택적 매개 변수-**중요도**합니다. 이들은 위의 코드에서 **_emailRecipientString**하십시오 **TextEmailSubject**합니다. 텍스트 **TextEmailMessage**합니다. 텍스트 및 **Normal**, 각각.
  1. 마지막으로 다시 설정 합니다 **TextEmailSubject** 및 **TextEmailMessage** 컨트롤과 지웁니다 합니다 **MyPeople** 컬렉션입니다.

* 속성: **DisplayMode**<br>
    값: `If( Len( Trim( TextEmailSubject.Text ) ) > 0 && !IsEmpty( MyPeople ), DisplayMode.Edit, DisplayMode.Disabled )` 보낼 전자 메일에 대 한 텍스트 및 받는 사람 전자 메일 제목 줄 있어야 합니다 (**MyPeople**) 컬렉션은 비워둘 수 없습니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 자세히 알아보기](./email-screen-overview.md)
* [PowerApps에서 Office 365 Outlook 커넥터에 자세히 알아보기](../connections/connection-office365-outlook.md)
* [PowerApps에서 Office 365 사용자 커넥터에 자세히 알아보기](../connections/connection-office365-users.md)
