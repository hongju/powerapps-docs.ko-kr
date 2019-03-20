---
title: 사용자 화면 템플릿 참조 | Microsoft Docs
description: PowerApps의 캔버스 앱에 대 한 사용자 화면 템플릿을 작동 하는 방법의 세부 정보 이해
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 1/2/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 09b92a1e2bc87ac6f4e2ec651aa67a845e0f07b1
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459462"
---
# <a name="reference-information-about-the-people-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 사용자 화면 템플릿에 대 한 참조 정보

PowerApps의 캔버스 앱에 대 한 중요 한 각 사용자 화면 템플릿의 컨트롤 화면의 전체 기본 기능에 기여 하는 방법을 이해 합니다. 이 심층 동작 수식 및 컨트롤 사용자 입력에 응답 하는 방법을 결정 하는 다른 속성의 값을 표시 합니다. 이 화면의 기본 기능의 간략 한 설명을에 대 한 참조를 [사용자 화면 개요](people-screen-overview.md)합니다.

이 항목에서는 몇 가지 중요 한 컨트롤을 강조 표시 하 고 다양 한 속성을 수식 또는 식에 설명 (같은 **항목** 하 고 **OnSelect**) 이러한 컨트롤은 설정 됩니다.

* [검색 입력란](#text-search-box)
* [사용자 찾아보기 갤러리](#user-browse-gallery) (+ 자식 컨트롤)
* [사용자 추가 갤러리](#people-added-gallery) (+ 자식 컨트롤)

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="text-search-box"></a>텍스트 검색 상자

![TextSearchBox 컨트롤](media/people-screen/people-search-box.png)

몇 가지 다른 컨트롤과 상호 작용 하거나 텍스트 검색 상자에 대 한 종속성:

* 모든 텍스트를 입력 하기 시작할 경우 **UserBrowseGallery** 표시 됩니다.
* 사용자가 내에서 사용자를 선택 하는 경우 **UserBrowseGallery**, 검색 내용을 다시 설정 됩니다.

## <a name="user-browse-gallery"></a>사용자 찾아보기 갤러리

![UserBrowseGallery 컨트롤](media/people-screen/people-browse-gall.png)

* 속성: **항목**<br>
    값: 사용자가 입력을 시작 하는 경우에 사용자를 조회 하는 논리:
    
    ```powerapps-dot
    If( !IsBlank( Trim( TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser(
            {
                searchTerm: Trim( TextSearchBox.Text ), 
                top: 15
            }
        )
    )
    ```
    
이 갤러리의 항목이 검색 결과에서 채워지는 합니다 [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) 작업 합니다. 작업 텍스트를 가져와 `Trim(TextSearchBox)` 검색으로 용어 및 상위 15 결과 반환 합니다 기준으로 검색 합니다. **TextSearchBox** 래핑됩니다는 `Trim()` 공간에서 사용자 검색을 유효 하지 않으므로 작동 합니다.

합니다 `Office365Users.SearchUser` 작업에 래핑됩니다는 `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` 만 검색 상자는 사용자가 입력 한 텍스트를 포함 하는 경우 작업을 호출 해야 하기 때문에 작동 합니다. 이 성능을 향상 시킵니다.

### <a name="userbrowsegallery-title-control"></a>UserBrowseGallery 제목 컨트롤

![UserBrowseGallery 제목 컨트롤](media/people-screen/people-browse-gall-title.png)

* 속성: **텍스트**<br>값: `ThisItem.DisplayName`

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

   * 설정 된  **\_selectedUser** 선택한 항목에 변수입니다.
   * 재설정에 검색 용어가 **TextSearchBox**합니다.
   * 선택한 항목을 추가 합니다 **MyPeople** 앱 사용자가 선택한 모든 사용자 컬렉션, 컬렉션입니다.

### <a name="userbrowsegallery-profileimage-control"></a>UserBrowseGallery ProfileImage 컨트롤

![UserBrowseGallery ProfileImage 컨트롤](media/people-screen/people-browse-gall-image.png)

* 속성: **이미지**<br>
    값: 사용자의 프로필 사진을 검색할 논리입니다.

    ```powerapps-dot
    If( !IsBlank( ThisItem.Id ) && 
            'Office365Users'.UserPhotoMetadata( ThisItem.Id ).HasPhoto,
        'Office365Users'.UserPhoto( ThisItem.Id )
    )
    ```

**이미지** 사용 하 여 사용자의 이미지를 검색 하는 컨트롤을 [Office365Users.UserPhoto](https://docs.microsoft.com/connectors/office365users/#get-user-photo--v1-) 작업 합니다. 그러나 그렇게 하기 전에 확인할 두 가지:
  
   * 인지는 ID 필드가 비어 있거나 비어 있지 않습니다. 그래야 합니다 **이미지** 전에 검색 결과 사용 하 여 채워진 갤러리 사용자 사진을 검색 하는 동안 컨트롤입니다.
   * 사용자의 사진에 있는지 여부 (사용 하 여 합니다 [Office365Users.UserPhotoMetadata](https://docs.microsoft.com/connectors/office365users/#get-user-photo-metadata) 작업). 그래야 합니다 `Office365Users.UserPhoto` 조회 사용자 프로필 사진이 없는 경우 예외를 반환 합니다.

이미지 검색 되지 않습니다 하는 경우, **이미지** 컨트롤은 빈 하며 **iconUser** 컨트롤 대신 표시 됩니다.

## <a name="people-added-gallery"></a>갤러리 사용자 추가

![PeopleAddedGallery 컨트롤](media/people-screen/people-people-gall.png)

* 속성: **항목**<br>
    값: `MyPeople`

초기화 또는 선택 하 여 추가할 사용자는 컬렉션을 **UserBrowseGallery 제목** 컨트롤입니다.

### <a name="peopleaddedgallery-title-control"></a>PeopleAddedGallery 제목 컨트롤

![PeopleAddedGallery 제목 컨트롤](media/people-screen/people-people-gall-title.png)

* 속성: **OnSelect**<br>
    값: `Set( _selectedUser, ThisItem )`

설정 된 **_selectedUser** 에서 선택한 항목에 변수 **EmailPeopleGallery**합니다.

### <a name="peopleaddedgallery-iconremove-control"></a>PeopleAddedGallery iconRemove 컨트롤

![PeopleAddedGallery iconRemove 컨트롤](media/people-screen/people-people-gall-delete.png)

* 속성: **OnSelect**<br>
    값: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

레코드를 조회 합니다 **MyPeople** 컬렉션 위치 **UserPrincipalName** 일치 하는 **UserPrincipalName** 선택한 항목 및 다음 제거를 기록 하는 컬렉션입니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 자세히 알아보려면](./people-screen-overview.md)합니다.
* [Office 365 Outlook 커넥터에 자세히 알아보려면](../connections/connection-office365-outlook.md)합니다.
* [Office 365 사용자 커넥터에 자세히 알아보려면](../connections/connection-office365-users.md)합니다.
