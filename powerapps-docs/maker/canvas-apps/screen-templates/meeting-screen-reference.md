---
title: 캔버스 앱의 모임 화면 템플릿 참조 | Microsoft Docs
description: PowerApps의 캔버스 앱의 모임 화면 템플릿 세부 정보 이해
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a7559f84b43d3c0372dea71d49c35461ba9d4e57
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459531"
---
# <a name="reference-information-about-the-meeting-screen-template-for-canvas-apps"></a>캔버스 앱의 모임 화면 템플릿 참조 정보

PowerApps의 캔버스 앱의 모임 화면 템플릿에 중요한 각 컨트롤 화면이 전체 기본 기능에 기여 하는 방법을 이해 합니다. 이 깊이 있는 정보는 컨트롤이 사용자 입력에 응답 하는 방법을 결정 하는 다른 속성의 값 및 동작 수식을 표시 합니다. 이 화면의 기본 기능의 간략한 설명에 대해서는 [모임 화면 개요](meeting-screen-overview.md)를 참조합니다.

이 항목에서는 몇 가지 중요한 컨트롤을 강조 표시 하고 각 컨트롤의 다양한 속성(**Items**와 **OnSelect** 같은)에 설정하는 수식 또는 식을 설명합니다.

* [초대 탭](#invite-tab)
* [일정 탭(LblScheduleTab)](#schedule-tab)
* [텍스트 검색 상자](#text-search-box)
* [추가 아이콘 (AddIcon)](#add-icon)
* [사람 찾아보기 갤러리](#people-browse-gallery) (+ 자식 컨트롤)
* [모임 사용자 갤러리](#meeting-people-gallery) (+ 자식 컨트롤)
* [모임 날짜 선택 (MeetingDateSelect)](#meeting-date-picker)
* [모임 기간 드롭다운 (MeetingDurationSelect)](#meeting-duration-drop-down)
* [모임 시간 찾기 갤러리](#find-meeting-times-gallery) (+ 자식 컨트롤)
* [대화방 갤러리 찾아보기](#room-browse-gallery) (+ 자식 컨트롤)
* [뒤로 펼침 단추 (RoomsBackNav)](#back-chevron) (테넌트에 회의실이 없는 경우 표시 되지 않음)
* [보내기 아이콘](#send-icon)

## <a name="prerequisite"></a>필수 조건

[PowerApps에서 앱을 만들어](../data-platform-create-app-scratch.md) 화면 및 기타 컨트롤을 추가하고 구성하는 방법에 친숙합니다.

## <a name="invite-tab"></a>초대 탭

   ![LblInviteTab 컨트롤](media/meeting-screen/meeting-invite-text.png)

* 속성: **Color**<br>
    값: `If( _showDetails, LblRecipientCount.Color, RectQuickActionBar.Fill )`

    **\_showDetails** 변수는 **LblInviteTab** 컨트롤 또는 **LblScheduleTab** 컨트롤이 선택되었는지 여부를 결정하는데 사용됩니다.  **\_showDetails**의 값이 **true**라면, **LblScheduleTab**이 선택 됩니다. **false** 라면, **LblInviteTab**이 선택 됩니다. **\_showDetails** 의 값이 **true**(초대 탭이 선택되지 않음)이면, 탭의 색은 **LblRecipientCount**의 색과 일치합니다. 그렇지 않으면, **RectQuickActionBar**의 채우기 색과 일치 합니다.

* 속성: **OnSelect**<br> 
    값: `Set( _showDetails, false )`

    **\_showDetails** 변수를 **false**로 설정하여, 초대 탭의 내용이 표시되게 하고 **일정** 탭의 내용을 숨깁니다.

## <a name="schedule-tab"></a>일정 탭

   ![LblInviteTab 컨트롤](media/meeting-screen/meeting-schedule-text.png)

* 속성: **Color**<br>
    값: `If( !_showDetails, LblRecipientCount.Color, RectQuickActionBar.Fill )`

    **\_showDetails** 변수는 **LblInviteTab** 컨트롤 또는 **LblScheduleTab** 컨트롤이 선택되었는지 여부를 결정하는데 사용됩니다.  **\_showDetails**의 값이 **true**라면, **LblScheduleTab**이 선택 됩니다. **false** 라면, **LblInviteTab**이 선택 됩니다. **\_showDetails** 의 값이 **true**(일정 탭이 선택됨)이면, 탭의 색은 **RectQuickActionBar**의 채우기 색과 일치합니다. 그렇지 않으면, **LblRecipientCount**의 색과 일치 합니다.

* 속성: **OnSelect**<br>
    값: `Set( _showDetails, true )`

    **\_showDetails** 변수를 **false**로 설정하여, 일정 탭의 내용이 표시되게 하고 초대 탭의 내용을 숨깁니다.

## <a name="text-search-box"></a>텍스트 검색 상자

   ![TextSearchBox 컨트롤](media/meeting-screen/meeting-search-box.png)

<!--Include description of text search box control?-->

**텍스트 검색 상자** 컨트롤은 화면의 다른 여러 컨트롤에 대해 종속성을 가집니다.:

* 사용자가 텍스트를 입력 하기 시작할 경우 **PeopleBrowseGallery**이 나타납니다.
* 유효한 메일 주소를 입력 하면 **AddIcon**이 표시 됩니다.
* 사용자가 **PeopleBrowseGallery**에서 사용자를 선택 하는 경우, 검색 내용이 다시 설정 됩니다.

## <a name="add-icon"></a>추가 아이콘

   ![AddIcon 컨트롤](media/email-screen/email-add-icon.png)

**추가 아이콘** 컨트롤을 사용하여 앱 사용자는 해당 조직 내에서 존재 하지 않는 사람을 전자 메일 받는사람 목록에 추가할 수 있습니다.

* 속성: **Visible**<br>
    값: 검색 상자에 유효한 전자 메일 주소를 입력 하는 경우에만 컨트롤을 표시합니다:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```

  한 줄씩, 앞에 나오는 코드 블록에 따르면 **추가 아이콘** 컨트롤은 다음 경우에 해당되면 표시 됩니다:

  * **TextSearchBox**가 텍스트를 포함 합니다.
  * **TextSearchBox**의 텍스트가 유효한 전자 메일 주소입니다.
  * **TextSearchBox**의 텍스트가 **MyPeople** 컬렉션에 존재 하지 않습니다.

* 속성: **OnSelect**<br> 
    값: **Collect** 구문은 참석자 목록에 사용자를 추가하고 모임 시간을 새로 고침하고 몇몇 변수를 설정합니다.

    ```powerapps-dot
    Collect( MyPeople,
        { 
            DisplayName: TextSearchBox.Text, 
            UserPrincipalName: TextSearchBox.Text, 
            Mail: TextSearchBox.Text
        }
    );
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    { 
                        RequiredAttendees: Concat(MyPeople, UserPrincipalName & ";")
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ),
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage:1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  이 컨트롤을 선택 하면 **MyPeople** 컬렉션에(참석자 목록) 유효한 전자 메일 주소를(유효한 전자 메일 주소가 텍스트 검색 상자에 입력되면 표시) 추가한 다음 새 사용자 항목으로 가능한 모임 시간을 새로 고칩니다.

  상세한 코드 블록:
  1. **MyPeople** 에 전자 메일 주소를 수집 합니다. 전자 메일 주소를 **DisplayName**, **UserPrincipalName** 및 **Mail** 필드로 수집 합니다.
  1. **TextSearchBox** 컨트롤의 내용을 다시 설정 합니다.
  1. **\_showMeetingTimes** 변수를 **false** 로 설정 합니다. 이 변수는 **FindMeetingTimesGallery**의 표시를 제어하여 선택된 참석자에게 가능한 시간을 표시 합니다.
  1. **\_loadMeetingTimes** 컨텍스트 변수를 **true**로 설정 합니다. 이 변수는 로딩 상태를 설정하여, 사용자에게 해당 데이터가 로드 되는지를 알려주는 **\_LblTimesEmptyState** 와 같은 로딩 상태 컨트롤의 표시를 변경합니다.
  1. **\_selectedMeetingTime**을 **blank()**로 설정 합니다. **\_selectedMeetingTime**은 **FindMeetingTimesGallery** 컨트롤에서 선택된 레코드입니다. 이 숨겨집니다 여기 있기 때문에 다른 참가자를 추가할 수는의 이전 정의가 **_selectedMeetingTime** 는 해당 참석자에 사용할 수 없습니다.
  1. Sets **_selectedRoom** to **Blank()**. **_selectedRoom** 에서 선택한 공간 레코드가 **RoomBrowseGallery**합니다. 공간 가용성의 값에서 결정 됩니다 **_selectedMeetingTime**합니다. 숨겨진, 해당 값을 사용 하 여는 **_selectedRoom** 값 이므로 더 이상 유효 숨겨집니다 수 있어야 합니다.
  1. 집합 **_roomListSelected** 하 **false**합니다. 이 줄의 모든 사용자에 게 적용할 수를 알 수 있습니다. 사무실에서 그룹화 할 수 있습니다 프로그램 방 다른 "회의실 목록." 회의실 목록에 있는 경우에 사용할 수 있도록 첫 번째 select 회의실 목록에서 해당 목록에서 객실을 선택 하기 전에이 화면을 차지 합니다. 변수의 **_roomListSelected** 사용자 (회의실 목록에만 사용 하 여 테 넌 트)에 있는지 여부를 결정은 회의실 목록 또는 회의실 목록 집합 내의 표시 됩니다. 로 설정 되어 **false** 강제로 사용자가 새 대화방 목록을 다시 선택 하도록 합니다.
  1. 사용 하는 [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) 결정 참석자에 대 한 사용 가능한 회의 시간을 수집 하는 작업입니다. 이 작업으로 전달합니다.
      * **UserPrincipalName** 으로 선택한 각 사용자의 합니다 *RequiredAttendees* 매개 변수입니다.
      * **MeetingDurationSelect**합니다. 에 Selected.Minutes 합니다 *MeetingDuration* 매개 변수입니다.
      * MeetingDateSelect.SelectedDate + 8 시간에는 *시작* 매개 변수입니다. 8 시간 이므로, 기본적으로 일정 컨트롤에 대 한 전체 날짜/시간 선택된 된 날짜의 오전 12 시에 추가 됩니다. 아마도 정상 근무 시간 내에서 가용성을 검색 하려고 합니다. 정상적인 작업 시작 시간을 오전 8:00 것입니다.
      * **MeetingDateSelect**합니다. SelectedDate + 17 시간 동안에는 *최종* 매개 변수입니다. 17 시간 때문에 추가 됩니다 오전 12시 + 17 ~ 오후 5:00 =. 정상적인 작업 종료 시간 오후 5:00 것입니다.
      * *15* 에 *MaxCandidates* 매개 변수입니다. 즉, 작업은 선택한 날짜에 대 한 사용 가능한 시간을 15 상위 항목만 반환 합니다. 왜냐하면는 8 시간 근무일에 16 개의 30 분 청크 하 고 30 분 회의 최소가이 화면에서 설정할 수 있습니다 하나 이기 때문입니다.
      * *1* 에 *MinimumAttendeePercentage* 매개 변수입니다. 기본적으로, 참석자를 사용할 수 있는 경우가 아니면 모임에 검색 됩니다.
      * **false** 에 *IsOrganizerOptional* 매개 변수입니다. 앱 사용자가이 회의 대 한 선택적 참석자 아닙니다.
      * "작업"에 *ActivityDomain* 매개 변수입니다. 즉, 검색 시간 정상 작업 시간 필드만 기간.
  1. 합니다 **ClearCollect** 함수 두 열도 추가 합니다. "StartTime" 및 "EndTime"입니다. 이 반환 되는 데이터를 간소화 합니다. 
  사용할 수 있는 시작 시간과 종료 시간을 포함 하는 필드를 **MeetingTimeSlot** 필드입니다. 이 필드는 시작을 포함 하는 레코드 이며는 끝 레코드를 포함 합니다 **날짜/시간** 및 **표준 시간대** 해당 각 제안 값입니다. 이 중첩 레코드를 검색 하기 보다는 "StartTime" 및 "EndTime" 열을 추가 합니다 **MeetingTimes** 컬렉션을 제공 하는 **시작 > 날짜/시간** 고 **최종 > DateTime** 화면 컬렉션의 값입니다.
  1. 완료 되 면 이러한 함수는 모든는 **_loadingMeetingTimes** 변수가로 설정 된 **false**, 로드 상태를 제거 하 고 **_showMeetingTimes** 로설정되어**true**표시 **FindMeetingTimesGallery**합니다.

## <a name="people-browse-gallery"></a>사람 찾아보기 갤러리

   ![PeopleBrowseGallery 컨트롤](media/meeting-screen/meeting-browse-gall.png)

* 속성: **항목**<br>
    값: 
    ```powerapps-dot
    If( !IsBlank( Trim( TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( { searchTerm: Trim(TextSearchBox.Text), top: 15 } )
    )
    ```

이 갤러리의 항목이 검색 결과에서 채워지는 합니다 [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) 작업 합니다. 작업 텍스트를 가져와 `Trim(**TextSearchBox**)` 검색으로 용어 및 상위 15 결과 반환 합니다 기준으로 검색 합니다.
  
**TextSearchBox** 래핑됩니다를 **Trim** 공간에서 사용자 검색을 유효 하지 않기 때문에 작동 합니다. `Office365Users.SearchUser` 작업에 래핑됩니다는 `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` 성능을 낭비는 사용자가 검색 전에 검색 결과 검색 하기 때문에 작동 합니다.

### <a name="people-browse-gallery-title"></a>사람 찾아보기 갤러리 제목

   ![PeopleBrowseGallery 제목 컨트롤](media/meeting-screen/meeting-browse-gall-title.png)

* 속성: **텍스트**<br>
    값: `ThisItem.DisplayName`

    Office 365 프로필에서 사용자의 표시 이름을 표시합니다.

* 속성: **OnSelect**<br>
    값: **Collect** 구문은 참석자 목록에 사용자를 추가하고 모임 시간을 새로 고침하고 몇몇 변수를 설정합니다.

    ```powerapps-dot
    Concurrent(
        Reset( TextSearchBox ),
        Set( _selectedUser, ThisItem ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem ); 
            Concurrent(
                Set( _showMeetingTimes, false ),
                UpdateContext( { _loadMeetingTimes: true } ),
                Set( _selectedMeetingTime, Blank() ),
                Set( _selectedRoom, Blank() ),
                Set( _roomListSelected, false ),
                ClearCollect( MeetingTimes, 
                    AddColumns(
                        'Office365'.FindMeetingTimes(
                            {
                                RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ),
                                MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                                Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ),
                                End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                                MaxCandidates: 15, 
                                MinimumAttendeePercentage: 1, 
                                IsOrganizerOptional: false, 
                                ActivityDomain: "Work"
                            }
                        ).MeetingTimeSuggestions,
                        "StartTime", MeetingTimeSlot.Start.DateTime, 
                        "EndTime", MeetingTimeSlot.End.DateTime
                    )
                )
            );
            UpdateContext( { _loadingMeetingTimes: false } );
            Set( _showMeetingTimes, true )
        )
    )
    ```

    이 컨트롤을 선택 하면 **MyPeople** 컬렉션에(참석자 목록) 유효한 전자 메일 주소를(유효한 전자 메일 주소가 텍스트 검색 상자에 입력되면 표시) 추가한 다음 새 사용자 항목으로 가능한 모임 시간을 새로 고침 합니다.

    이 컨트롤을 선택 하는 점을 선택 하는 **AddIcon** ; 유일한 차이는 `Set(_selectedUser, ThisItem)` 문과 작업의 실행 순서입니다. 따라서이 토론으로 심층 수 없습니다. 자세한 설명은 읽기를 [AddIcon 컨트롤](#add-icon) 섹션입니다.

    이 컨트롤을 선택 하면 다시 설정 **TextSearchBox**합니다. 그런 다음 선택 영역에 없는 경우는 **MyPeople** 컬렉션, 컨트롤:
    1. 집합의 **_loadMeetingTimes** 상태 **true** 및 **_showMeetingTimes** 상태 **false**, 공백을 **_ selectedMeetingTime** 및 **_selectedRoom** 변수 및 새로 고침 합니다 **MeetingTimes** 새로 추가 사용 하 여 컬렉션을 **MyPeople** 컬렉션입니다. 
    1. 설정 합니다 **_loadMeetingTimes** 상태 **false**, 설정 및 **_showMeetingTimes** 에 **true**합니다. 선택 영역에 이미 있으면 합니다 **MyPeople** 컬렉션의 내용만 다시 설정 **TextSearchBox**합니다.

## <a name="meeting-people-gallery"></a>모임 사용자 갤러리

   ![MeetingPeopleGallery 컨트롤](media/meeting-screen/meeting-people-gall.png)

* 속성: **항목**<br>
    값: `MyPeople`

    **MyPeople** 초기화 또는 선택 하 여 추가할 사용자의 컬렉션은 컬렉션의 **PeopleBrowseGallery 제목** 제어 합니다.

* 속성: **Height**<br>
    값: 갤러리 350의 최대 높이 증가 허용 하도록 논리:

    ```powerapps-dot
    Min( 
        76 * RoundUp( CountRows( MeetingPeopleGallery.AllItems ) / 2, 0 ),
        350
    )
    ```

  
   이 갤러리의 높이 350의 최대 높이 갤러리에서 항목의 수를 조정합니다. 수식은 단일 행의 높이 변수로 76 **MeetingPeopleGallery**, 행의 수로 곱합니다. 합니다 **WrapCount** 속성이 2로 true 행 수가 이므로 `RoundUp(CountRows(MeetingPeopleGallery.AllItems) / 2, 0)`합니다.

* 속성: **ShowScrollbar**<br>
    값: `MeetingPeopleGallery.Height >= 350`

    갤러리의 최대 높이 (350)에 도달 하면, 스크롤 막대에 표시 됩니다.

### <a name="meeting-people-gallery-title"></a>모임 사용자 갤러리 제목

   ![MeetingPeopleGallery 제목 컨트롤](media/meeting-screen/meeting-people-gall-title.png)

* 속성: **OnSelect**<br>
    
    값: `Set(_selectedUser, ThisItem)`
    
    설정 된 **_selectedUser** 에서 선택한 항목에 변수 **MeetingPeopleGallery**합니다.

### <a name="meeting-people-gallery-iconremove"></a>모임 사용자 갤러리 iconRemove

   ![MeetingPeopleGallery iconRemove 컨트롤](media/meeting-screen/meeting-people-gall-delete.png)

* 속성: **OnSelect**<br>
    값: A **제거** 참석자 목록에서 사용자를 제거 하는 문에 **수집** 문을 사용할 수 있는 회의 시간 및 몇 가지 변수 설정/해제를 새로 고치려면:

    ```powerapps-dot
    Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) );
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ), 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ), 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage: 1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  높은 수준에서이 컨트롤을 선택 참석자 목록에서 사용자를 제거 및이 사람의 제거 작업에 따라 사용 가능한 회의 시간을 새로 고칩니다.

  앞의 코드의 첫 번째 줄을 다음이 컨트롤을 선택 하는 거의 동일 선택 하 여 **AddIcon** 제어 합니다. 따라서이 토론으로 심층 되지 않습니다. 자세한 설명은 읽기를 [AddIcon 컨트롤 섹션](#add-icon)합니다.

  첫 번째 코드 줄을 선택한 항목을 제거 합니다 **MyPeople** 컬렉션입니다. 다음 코드:
  1. 다시 설정 **TextSearchBox**, 한 다음 선택 항목을 제거 합니다 **MyPeople** 컬렉션입니다. 
  1. 집합의 **_loadMeetingTimes** 상태 **true** 및 **_showMeetingTimes** 상태 **false**, 공백을 **_ selectedMeetingTime** 및 **_selectedRoom** 변수 및 새로 고침 합니다 **MeetingTimes** 새로 추가 사용 하 여 컬렉션을 **MyPeople** 컬렉션입니다. 
  1. 설정 합니다 **_loadMeetingTimes** 상태 **false**, 설정 및 **_showMeetingTimes** 에 **true**합니다.

## <a name="meeting-date-picker"></a>모임 날짜 선택

   ![MeetingDateSelect 컨트롤](media/meeting-screen/meeting-datepicker.png)

* 속성: **DisplayMode**<br>
    값: `If( IsEmpty(MyPeople), DisplayMode.Disabled, DisplayMode.Edit )`

    하나 이상의 참석자에 추가한 될 때까지 회의 대 한 날짜를 선택할 수 없습니다는 **MyPeople** 컬렉션입니다.

* 속성: **OnChange**<br>
    값: `Select( MeetingDateSelect )`

    코드를 트리거 선택한 날짜를 변경 합니다 **OnSelect** 실행 하려면이 컨트롤의 속성입니다.

* 속성: **OnSelect**<br>
    값: A **수집** 문을 사용할 수 있는 회의 시간 및 몇 가지 변수 설정/해제를 새로 고치려면:
  
    ```powerapps-dot
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadingMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ), 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ), 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage: 1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  높은 수준에서이 컨트롤을 선택 하면 새로 사용 가능한 모임 시간을 고칩니다. 날짜를 변경 하는 사용자, 사용 가능한 모임 시간 그 날에 대 한 참석자의 가용성을 반영 하도록 업데이트 해야 할 때문에 유용 합니다.

  초기를 제외 하 고 **수집** 문을 동일 합니다 **OnSelect** 기능의 **AddIcon** 컨트롤입니다. 따라서이 토론으로 심층 되지 않습니다. 자세한 설명은 읽기를 [AddIcon 컨트롤](#add-icon) 섹션입니다.

  이 컨트롤을 선택 하면 다시 설정 **TextSearchBox**합니다. 그런 다음는 다음과 같습니다. 
  1. 집합의 **_loadMeetingTimes** 상태 **true** 및 **_showMeetingTimes** 상태 **false**, 공백을 **_ selectedMeetingTime** 하 고 **_selectedRoom** 변수 및 새로 고침 합니다 **MeetingTimes** 새 날짜 선택 영역을 사용 하 여 컬렉션입니다. 
  1. 설정 합니다 **_loadMeetingTimes** 상태 **false**, 설정 및 **_showMeetingTimes** 에 **true**합니다.

## <a name="meeting-duration-drop-down"></a>모임 기간 드롭다운

   ![MeetingDateSelect 컨트롤](media/meeting-screen/meeting-timepicker.png)

* 속성: **DisplayMode**<br>
    값: `If( IsEmpty(MyPeople), DisplayMode.Disabled, DisplayMode.Edit )`

    하나 이상의 참석자에 추가한 될 때까지 회의 대 한 기간을 선택할 수 없습니다는 **MyPeople** 컬렉션입니다.

* 속성: **OnChange**<br>
    값: `Select(MeetingDateSelect1)`

    코드를 트리거하는 선택한 기간을 변경 합니다 **OnSelect** 의 속성을 **MeetingDateSelect** 컨트롤을 실행할 합니다.

## <a name="find-meeting-times-gallery"></a>모임 시간 찾기 갤러리

   ![FindMeetingTimesGallery 컨트롤](media/meeting-screen/meeting-time-gall.png)

* 속성: **항목**<br>
    값: `MeetingTimes`

    잠재적인 모임 시간의 컬렉션에서 검색 된 [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) 작업 합니다.

* 속성: **Visible**<br>
    값: `_showMeetingTimes && _showDetails && !IsEmpty( MyPeople )`

    갤러리에 표시 되는 경우에만 **_showMeetingTimes** 로 설정 되어 **true**, 사용자가 선택한를 **LblScheduleTab** 컨트롤에 추가 하는 하나 이상의 참석자 이며를 충족 합니다.

### <a name="find-meeting-times-gallery-title"></a>모임 시간 찾기 갤러리 제목

   ![FindMeetingTimesGallery 제목 컨트롤](media/meeting-screen/meeting-time-gall-title.png)

* 속성: **텍스트**<br>
    값: 사용자의 현지 시간으로 표시할 시작 시간을 변환 합니다.

    ```powerapps-dot
    Text(
        DateAdd(
            DateTimeValue( ThisItem.StartTime ),
            - TimeZoneOffset(), 
            Minutes
        ),
        DateTimeFormat.ShortTime
    )
    ```

  검색된 값 **StartTime** UTC 형식으로 되어 있습니다. 하 [UTC에서 현지 시간으로 변환](../functions/function-dateadd-datediff.md#converting-from-utc)의 **DateAdd** 함수를 적용 합니다.
  합니다 [Text 함수](../functions/function-text.md#datetime) 해당 첫 번째 인수와 두 번째 인수에 따라 형식으로 날짜/시간을 사용 합니다. 현지 시간 변환 전달 **ThisItem.StartTime**를 그대로 표시 **DateTimeFormat.ShortTime**합니다.

* 속성: **OnSelect**<br>
    값: 몇 가지 **수집** 회의실 및 해당 제안 된 가용성 뿐만 아니라 여러 변수 설정/해제를 수집 하는 문:

    ```powerapps-dot
    Set( _selectedMeetingTime, ThisItem );
    UpdateContext( { _loadingRooms: true } );
    If( IsEmpty( RoomsLists ),
        ClearCollect( RoomsLists, 'Office365'.GetRoomLists().value) );
    If( CountRows( RoomsLists ) <= 1,
        Set( _noRoomLists, true );
        ClearCollect( AllRooms, 'Office365'.GetRooms().value );
        Set( _allRoomsConcat, Concat( FirstN( AllRooms, 20 ), Address & ";" ) );
        ClearCollect( RoomTimeSuggestions, 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat, 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                    Start: _selectedMeetingTime.StartTime & "Z", 
                    End: _selectedMeetingTime.EndTime & "Z", 
                    MinimumAttendeePercentage: "1",
                    IsOrganizerOptional: "false", 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );
        ClearCollect( AvailableRooms, 
            AddColumns(
                AddColumns(
                    Filter( 
                        First( RoomTimeSuggestions ).AttendeeAvailability,
                        Availability="Free"
                    ), 
                    "Address", Attendee.EmailAddress.Address
                ), 
                "Name", LookUp( AllRooms, Address = Attendee.EmailAddress.Address ).Name 
            )
        );
        ClearCollect( AvailableRoomsOptimal, 
            DropColumns(
                DropColumns( AvailableRooms, "Availability" ), 
                "Attendee" 
            )
        ),
        Set( _roomListSelected, false) 
    );
    UpdateContext( {_loadingRooms: false} )
    ```

  이 코드 블록 높은 수준에서 수집 하지 않은 사용자에 대 한 사용 가능한 객실 대화방 목록, 모임에 대해 선택한 날짜/시간을 기준으로 합니다. 이 고, 그렇지 단순히 방 목록을 검색합니다.

  낮은 수준에서이 코드 블록:
  1. 집합 **_selectedMeetingTime** 선택한 항목에 있습니다. 이 시간 동안 사용할 수 있는 어떤 방 찾으려고 사용 됩니다.
  1. 로드를 설정 하는 상태 변수 **_loadingRooms** 에 **true**, 로드 상태를 설정 합니다.
  1. 경우는 **RoomsLists** 컬렉션이 비어, 사용자의 테 넌 트의 방 목록을 검색 하 고 저장 합니다 합니다 **RoomsLists** 컬렉션입니다.
  1. 사용자가 있는 경우 하나의 회의실 목록 없거나 회의실 목록:
      1. 합니다 **noRoomLists** 변수가로 설정 된 **true**,이 변수는 아래에 표시 된 항목을 확인 하는 데 사용 됩니다는 **RoomBrowseGallery** 컨트롤입니다.
      1. `Office365.GetRooms()` 작업은 테 넌 트의 처음 100 개의 방 검색에 사용 됩니다. 에 저장 됩니다는 **AllRooms** 컬렉션입니다.
      1. 합니다 **_allRoomsConcat** 변수는 회의실의 첫 번째 20 전자 메일 주소의 세미콜론으로 구분 된 문자열로 설정 됩니다는 **AllRooms** 컬렉션입니다. 왜냐하면 합니다 [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) 한 번에 20 person 개체의 사용 가능한 시간에 대 한 검색으로 제한 됩니다.
      1. **RoomTimeSuggestions** 컬렉션 사용 합니다 [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) 에서 처음 20 개 대화방의 가용성을 검색 하는 **AllRooms** 기반 컬렉션 시간 값에는 **_selectedMeetingTime** 변수입니다. 합니다 `& "Z"` 형식을 제대로 지정 하는 데 사용 되는 **DateTime** 값입니다.
      1. 합니다 **AvailableRooms** 컬렉션이 만들어집니다. 이 단순히를 **RoomTimeSuggestions** 컬렉션에 추가 하는 두 개의 추가 열을 사용 하 여 참석자 가용성입니다. "Address" 및 "이름"입니다. "Address"의 대화방에 전자 메일 주소 이며 "Name" 대화방의 이름입니다.
      1. 그런 다음, **AvailableRoomsOptimal** 컬렉션이 만들어집니다. 바로 이것이 합니다 **AvailableRooms** "Availability" 및 "참가자" 열을 사용 하 여 컬렉션에서 제거 합니다. 스키마와 일치 이렇게 **AvailableRoomsOptimal** 하 고 **AllRooms**합니다. 두 컬렉션을 사용할 수 있습니다는 **항목** 의 속성을 **RoomBrowseGallery**합니다.
      1. **_roomListSelected** 로 설정 된 **false**합니다.
  1. 로딩 상태가 **_loadingRooms**로 설정 된 **false** 등등 실행이 완료 되 면 합니다.

## <a name="room-browse-gallery"></a>대화방 갤러리 찾아보기

   ![RoomBrowseGallery 컨트롤](media/meeting-screen/meeting-rooms-gall.png)

* 속성: **항목**<br>
    값: 사용자가 회의실 목록 선택 또는 방 목록 테 넌 트에 있는지 여부에 따라 동일한 스키마의 두 가지 내부 컬렉션을 논리적으로 설정 합니다.

    ```powerapps-dot
    Search(
        If( _roomListSelected || _noRoomLists, AvailableRoomsOptimal, RoomsLists ),
        Trim(TextMeetingLocation1.Text), 
        "Name", 
        "Address"
    )
    ```

  이 갤러리를 표시 합니다 **AvailableRoomsOptimal** 컬렉션 경우 **_roomListSelected** 또는 **_noRoomLists** 됩니다 **true**합니다. 그렇지 않으면 표시 합니다 **RoomsLists** 컬렉션입니다. 이러한 컬렉션의 스키마 동일 하기 때문에 수행할 수 있습니다.

* 속성: **Visible**<br>
    값: ```_showDetails && !IsBlank( _selectedMeetingTime ) && !_loadingRooms```

    갤러리에 세 이전 문이 평가 하는 경우에 표시 됩니다 **true**합니다.

### <a name="roombrowsegallery-title"></a>RoomBrowseGallery 제목

   ![RoomBrowseGallery 제목 컨트롤](media/meeting-screen/meeting-rooms-gall-title.png)

* 속성: **OnSelect**<br>
    값: 논리적으로 바인딩된 집합이 **수집** 하 고 **설정** 수도 없습니다 트리거될 수 있습니다, 회의실 목록 또는 방 사용자가 보고 하는 여부에 따라 구성 하는:

    ```powerapps-dot
    UpdateContext( { _loadingRooms: true } );
    If( !_roomListSelected && !noRoomLists,
        Set( _roomListSelected, true );
        Set( _selectedRoomList, ThisItem.Name );
        ClearCollect( AllRooms, 'Office365'.GetRoomsInRoomList( ThisItem.Address ).value );
        Set( _allRoomsConcat, Concat( FirstN( AllRooms, 20 ), Address & ";" ) );
        ClearCollect( RoomTimeSuggestions, 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat, 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: _selectedMeetingTime.StartTime & "Z", 
                    End: _selectedMeetingTime.EndTime & "Z", 
                    MinimumAttendeePercentage: "1",
                    IsOrganizerOptional: "false", 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );
        ClearCollect( AvailableRooms, 
            AddColumns(
                AddColumns(
                    Filter(
                        First( RoomTimeSuggestions ).AttendeeAvailability, 
                        Availability = "Free"
                    ),
                    "Address", Attendee.EmailAddress.Address 
                ), 
                "Name", LookUp( AllRooms, Address = Attendee.EmailAddress.Address ).Name
            )
        );
        ClearCollect( AvailableRoomsOptimal, 
            DropColumns(
                DropColumns( AvailableRooms, "Availability" )
            ), 
            "Attendee" )
        ),
        Set( _selectedRoom, ThisItem )
    );
    UpdateContext( {_loadingRooms: false} )
    ```

  이 컨트롤을 선택할 때 발생 하는 동작은 여부는 사용자가 현재 보고 있는 회의실 목록 집합 또는 집합 대화방에 따라 달라 집니다. 전자의 경우 다음이 컨트롤을 선택 하는 경우 선택한 회의실 목록에서 선택한 시간에 사용할 수 있는 장소를 검색 합니다. 후자의 경우이 컨트롤을 선택 하면 설정 된 **_selectedRoom** 선택한 항목에 변수입니다. 위의 문에서와 매우 유사 합니다 **선택** 문을 [ **FindMeetingTimesGallery 제목**](#find-meeting-times-gallery)합니다.

  낮은 수준에서 앞에 나오는 코드 블록:
  1. 대화방에 대 한 로드 상태를 설정 하 여 켭니다 **_loadingRooms** 하 **true**합니다.
  1. 회의실 목록에서 선택 된 경우 및 테 넌 트 공간이 있을 경우 참조 목록을 확인 합니다. 이 경우:
      1. 설정 **_roomListSelected** 하 **true** 설정 하 고 **_selectedRoomList** 선택한 항목에 합니다.
      1. 합니다 **_allRoomsConcat** 변수는 회의실의 첫 번째 20 전자 메일 주소의 세미콜론으로 구분 된 문자열로 설정 됩니다는 **AllRooms** 컬렉션입니다. 왜냐하면 합니다 [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) 작업이 한 번에 20 person 개체의 사용 가능한 시간에 대 한 검색을 제한 합니다.
      1. 합니다 **RoomTimeSuggestions** 컬렉션 사용 합니다 [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) 에서 처음 20 개 대화방의 가용성을 검색 하는 작업을 **AllRooms** 컬렉션의 시간 값에 기반 합니다 **_selectedMeetingTime** 변수입니다. 유의 `& "Z"` 형식을 제대로 지정 하는 데 사용 되는 **DateTime** 값입니다.
      1. 합니다 **AvailableRooms** 컬렉션이 만들어집니다. 이 단순히를 **RoomTimeSuggestions** 컬렉션에 추가 하는 두 개의 추가 열을 사용 하 여 참석자 가용성입니다. "Address" 및 "이름"입니다. "Address"의 대화방에 전자 메일 주소 이며 "Name" 대화방의 이름입니다.
      1. 그런 다음, **AvailableRoomsOptimal** 컬렉션이 만들어집니다. 바로 이것이 합니다 **AvailableRooms** "Availability" 및 "참가자" 열을 사용 하 여 컬렉션에서 제거 합니다. 스키마와 일치 이렇게 **AvailableRoomsOptimal** 하 고 **AllRooms**합니다. 두 컬렉션을 사용 하면이 **항목** 속성을 **RoomBrowseGallery**합니다.
      1. **_roomListSelected** 로 설정 된 **false**합니다.
  1. 로딩 상태가 **_loadingRooms**로 설정 된 **false** 등등 실행이 완료 되 면 합니다.

## <a name="back-chevron"></a>펼침 단추를 다시

   ![RoomsBackNav 컨트롤](media/meeting-screen/meeting-back.png)

* 속성: **Visible**<br>
    값: `_roomListSelected && _showDetails`

    이 컨트롤은 모두 회의실 목록 선택 된 경우에 표시 하며 **일정** 탭을 선택 합니다.

* 속성: **OnSelect**<br>
    값: `Set( _roomListSelected, false )`

    때 **_roomListSelected** 로 설정 되어 **false**를 변경 합니다 **RoomBrowseGallery** 컨트롤에서 항목을 표시 하는 **RoomsLists** 컬렉션입니다.

## <a name="send-icon"></a>보내기 아이콘

   ![IconSendItem 컨트롤](media/meeting-screen/meeting-send-icon.png)

* 속성: **DisplayMode**<br>
    값: 아이콘을 편집할 수 있게 되기 전에 특정 모임 세부 정보를 입력 하 여 적용할 논리입니다.
    
    ```powerapps-dot
    If( Len( Trim( TextMeetingSubject1.Text ) ) > 0
        && !IsEmpty( MyPeople ) && !IsBlank( _selectedMeetingTime ),
        DisplayMode.Edit, DisplayMode.Disabled
    )
    ```
  아이콘은 회의 제목을 작성, 회의 대 한 하나 이상의 참가자는 및 모임 시간을 선택한 경우에 선택할 수 있습니다. 그렇지 않은 경우는 비활성화 됩니다.

* 속성: **OnSelect**<br>

    값: 코드를 선택한 참석자에 게 모임 초대를 보내고 모든 입력된 필드의 선택을 취소 합니다.

    ```powerapps-dot
    Set( _myCalendarName, LookUp( 'Office365'.CalendarGetTables().value, DisplayName = "Calendar" ).Name );
    Set( _myScheduledMeeting, 
        'Office365'.V2CalendarPostItem( _myCalendarName,
            TextMeetingSubject1.Text, 
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.StartTime), -TimeZoneOffset(), Minutes) ),
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.EndTime), -TimeZoneOffset(), Minutes) ),
            {
                RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ) & _selectedRoom.Address, 
                Body: TextMeetingMessage1.Text, 
                Location: _selectedRoom.Name, 
                Importance: "Normal", 
                ShowAs: "Busy", 
                ResponseRequested: true
            }
        )
    );
    Concurrent(
        Reset( TextMeetingLocation1 ),
        Reset( TextMeetingSubject1 ),
        Reset( TextMeetingMessage1 ),
        Clear( MyPeople ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoomList, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false )
    )
    ```
  
  낮은 수준에서이 코드 블록:
  1. 집합 **_myCalendarName** 에서 일정 합니다 [Office365.CalendarGetTables()](https://docs.microsoft.com/connectors/office365/#get-calendars) 사용 하 여 작업을 **DisplayName** "일정"의
  1. 일정 회의 입력의 모든 값에서 다양 한 선택 항목을 사용 하 여 화면 전반에서 사용자를 [Office365.V2CalendarPostItem](https://docs.microsoft.com/connectors/office365/#create-event--v2-) 작업 합니다.
  1. 모든 입력된 필드 및 회의 만드는 데 사용 되는 변수를 다시 설정 합니다.

> [!NOTE]
> 해당 지역에 따라 원하는 달력 없을 "일정"의 표시 이름 Outlook 일정의 제목을 무엇 인지 확인 하려면 앱에서 적절 한 변경 내용을 확인 하십시오.

## <a name="next-steps"></a>다음 단계

* [이 화면에 자세히 알아보기](./meeting-screen-overview.md)
* [PowerApps에서 Office 365 Outlook 커넥터에 자세히 알아보기](../connections/connection-office365-outlook.md)
* [PowerApps에서 Office 365 사용자 커넥터에 자세히 알아보기](../connections/connection-office365-users.md)
