---
title: 일정 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대 한 달력 화면 템플릿의 작동 방식을 이해 하 고, 화면을 수정 하 고, 앱의 일부로 확장
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/28/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 745b4232a43a06c46866e83ca2452f8a55afeddf
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459508"
---
# <a name="overview-of-the-calendar-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 달력 화면 템플릿의 개요

캔버스 앱에서 사용자에 게 해당 Office 365 Outlook 계정에서 예정 된 이벤트를 표시 하는 일정 화면을 추가 합니다. 해당 일의 이벤트의 목록을 통해 스크롤하여 달력에서 날짜를 선택할 수 있습니다. 정보 목록에 표시, 각 이벤트에 대 한 자세한 세부 정보를 표시 하는 두 번째 화면을 추가, 각 이벤트에 대 한 참가자의 목록을 표시 및 기타 사용자 지정 확인을 변경할 수 있습니다.

와 같은 Office 365에서 다양 한 데이터를 표시 하는 다른 템플릿 기반 화면을 추가할 수도 있습니다 [전자 메일](email-screen-overview.md)를 [사람들이](people-screen-overview.md) 조직에서와 [가용성](meeting-screen-overview.md) 사람들이 사용자의 모임에 초대 하려고 수 있습니다.

이 개요에 설명 합니다.
> [!div class="checklist"]
> * 기본 일정 화면을 사용 하는 방법입니다.
> * 수정 하는 방법.
> * 앱에 통합 하는 방법.

이 화면의 기본 기능을 심층 분석에 대해서는 [달력 화면 참조](calendar-screen-reference.md)합니다.

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 일정 화면을 추가:

1. [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps를 다음 앱을 만들거나 기존 앱을 PowerApps Studio 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 에 **홈** 선택 리본의 탭 **새 화면** > **달력**합니다.

    기본적으로 화면 다음과 비슷합니다.

    ![일정 화면](media/calendar-screen/calendar-initial.png)

1. 데이터를 표시 하려면 화면 위쪽 드롭다운 목록에서 옵션을 선택 합니다.

    ![로드가 완료 되 면 일정 화면](./media/calendar-screen/calendar-screen.png)

몇 가지 유용한 참고 사항:

* 오늘 날짜는 기본적으로 선택한 오른쪽 위 모서리에서 달력 아이콘을 선택 하 여를 쉽게 반환할 수 있습니다.
* 다른 날짜를 선택 하면 원을 둘러싼 하 고 밝은 색 사각형 (기본 테마에 적용 된 경우에 파란색) 오늘 날짜를 묶습니다.
* 특정 날짜에 대 한 하나 이상의 이벤트를 예약 하면 작은 컬러 원을 달력에서 날짜는 아래에 나타납니다.
* 하나 이상의 이벤트를 예약 된 날짜를 선택 하면 이벤트 달력에서 목록에 나타납니다.

## <a name="modify-the-screen"></a>화면을 수정

몇 가지 일반적인 방법으로이 화면의 기본 기능을 수정할 수 있습니다.

* [달력 지정](calendar-screen-overview.md#specify-the-calendar)합니다.
* [이벤트에 대 한 다양 한 세부 정보 표시](calendar-screen-overview.md#show-different-details-about-an-event)합니다.
* [비차단 이벤트 숨기기](calendar-screen-overview.md#hide-nonblocking-events)합니다.

추가 화면을 수정 하려는 경우 사용 합니다 [달력 화면 참조](./calendar-screen-reference.md) 가이드로 합니다.

### <a name="specify-the-calendar"></a>달력 지정

사용자에 게 표시 되어야 하는 일정을 이미 알고 있는 경우에 앱을 게시 하기 전에 해당 일정을 지정 하 여 화면을 간소화할 수 있습니다. 이 변경,이 제거할 수 있습니다 일정의 드롭다운 목록에 대 한 필요성을 제거 합니다.

1. 설정 된 **[OnStart](../controls/control-screen.md)** 속성을 다음이 수식으로 앱의 기본 화면:

    ```powerapps-dot
    Set( _userDomain, Right( User().Email, Len( User().Email ) - Find( "@", User().Email ) ) );
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -( Weekday( _firstDayOfMonth) - 2 + 1 ), Days )
    );
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    Set( _calendarVisible, false );
    Set( _myCalendar, 
        LookUp( Office365.CalendarGetTables().value, DisplayName = "{YourCalendarNameHere}" )
    );
    Set( _minDate, 
        DateAdd( _firstDayOfMonth, -( Weekday(_firstDayOfMonth) - 2 + 1 ), Days )
    );
    Set( _maxDate, 
        DateAdd(
            DateAdd( _firstDayOfMonth, -( Weekday(_firstDayOfMonth) - 2 + 1 ), Days ),
            40, 
            Days 
        )
    );
    ClearCollect( MyCalendarEvents, 
        Office365.GetEventsCalendarViewV2( _myCalendar.Name, 
            Text( _minDate, UTC ), 
            Text( _maxDate, UTC ) 
        ).value
    );
    Set( _calendarVisible, true )
    ```

    > [!NOTE]
    > 이 수식은 약간의 기본값에서 편집 합니다 **OnSelect** 일정을 선택 하기 위한 드롭다운 목록의 속성. 해당 컨트롤에 대 한 자세한 내용은 해당 섹션을 참조 합니다 [달력 화면 참조](./calendar-screen-reference.md#calendar-drop-down)합니다.

1. 바꿉니다 `{YourCalendarNameHere}`를 표시 하려는 달력의 이름 사용 하 여 중괄호를 포함 하 여 (예를 들어 **달력**).

    > [!IMPORTANT]
    > 다음 단계를 앱에 하나의 일정 화면을 추가한를 가정 합니다. 둘 이상 컨트롤 이름을 추가한 경우 (같은 **iconCalendar1**) 다른 숫자를 사용 하 여 종료 되 고 수식을 적절 하 게 조정 해야 합니다.

1. 설정 합니다 **Y** 의 속성을 **iconCalendar1** 컨트롤을이 식:

    `RectQuickActionBar1.Height + 20`

1. 설정 합니다 **Y** 의 속성을 **LblMonthSelected1** 컨트롤을이 식:

    `iconCalendar1.Y + iconCalendar1.Height + 20`

1. 설정 합니다 **텍스트** 의 속성을 **LblNoEvents1** 이 값으로 제어:

    `"No events scheduled"`

1. 설정 된 **Visible** 속성을 **LblNoEvents1** 을 다음이 수식으로:

    `CountRows(CalendarEventsGallery1.AllItems) = 0 && _calendarVisible`

1. 이러한 컨트롤을 삭제 합니다.

    - **dropdownCalendarSelection1**
    - **LblEmptyState1**
    - **iconEmptyState1**

1. 일정 화면 기본 화면을 하지 않으면 앱을 테스트할 수 있도록 기본 화면에서 달력 화면으로 이동 하는 단추를 추가 합니다.

    예를 들어 단추에 추가 **Screen1** 를 탐색 하는 **Screen2** 비어 있는 상태에서 만든 앱에 일정 화면을 추가한 경우.

1. 앱을 저장 한 다음 브라우저 또는 모바일 장치에서 테스트 합니다.

### <a name="show-different-details-about-an-event"></a>이벤트에 대 한 다른 정보를 표시 합니다.

기본적으로 달력에서 갤러리의 이름은 **CalendarEventsGallery**, 시작 시간, 기간, 제목 및 각 이벤트의 위치를 보여 줍니다. 모든 필드 (예: 구성)를 표시 하도록 갤러리를 구성할 수 있습니다 하는 [Office 365 커넥터](https://docs.microsoft.com/connectors/office365/#calendareventclientreceive) 지원 합니다.

1. **CalendarEventsGallery**로 설정 합니다 **텍스트** 새 또는 기존 레이블을에 속성 `ThisItem` 마침표 뒤에.

    IntelliSense는 선택할 수 있는 필드를 나열 합니다.

1. 원하는 필드를 선택 합니다.

    레이블이 지정 된 정보를 보여 줍니다.

### <a name="hide-nonblocking-events"></a>비차단 이벤트 숨기기

여러 사무실, 팀 멤버는 사무실 수 하는 경우에 서로 알리기 위해 모임 요청을 보냅니다. 모든 사용자의 일정을 차단를 방지 하려면 요청을 보내는 사람 설정 가용성 **무료**합니다. 몇 가지 속성을 업데이트 하 여 달력 및 갤러리에서 이러한 이벤트를 숨길 수 있습니다.

1. 설정 된 **항목** 속성을 **CalendarEventsGallery** 을 다음이 수식으로:

    ```powerapps-dot
    SortByColumns(
        Filter(
            MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = 
                Text( _dateSelected, DateTimeFormat.ShortDate ),
            ShowAs <> "Free"
        ),
        "Start"
    )
    ```

    이 수식에는 **필터** 해당 선택한 것과 다른 날짜에 대 한 예약 된 이벤트 뿐만 아니라 이벤트의 가용성에 설정 된 함수를 숨깁니다 **무료**합니다.

1. 일정을 설정 합니다 **Visible** 의 속성을 **원** 컨트롤을 다음이 수식으로:

    ```powerapps-dot
    CountRows(
        Filter(
            MyCalendarEvents,
            DateValue( Text(Start) ) = DateAdd( _firstDayInView, ThisItem.Value, Days ),
            ShowAs <> "Free"
        )
    ) > 0 && !Subcircle1.Visible && Title2.Visible
    ```
    이 수식은 앞의 수식은으로 동일한 필터가 포함 되어 있습니다. 따라서 이벤트 표시기 원이 나타납니다. 날짜에서 두 개 이상 있어 가용성 되지 않는 한 선택한 날짜에는 더 많은 이벤트 설정 하는 경우에 **무료**합니다.

## <a name="integrate-the-screen-into-an-app"></a>화면을 앱에 통합

일정 화면 자체 오른쪽에 있는 컨트롤의 강력한 번들 이지만 일반적으로 가장 큰, 더 다양 한 응용 프로그램의 일부로 수행 합니다. 다양 한 방법으로, 이러한 옵션을 추가 하는 등의 더 큰 앱에이 화면을 통합할 수 있습니다.

* [이벤트 세부 정보를 보려면](calendar-screen-overview.md#view-event-details)합니다.
* [이벤트 참석자 표시](calendar-screen-overview.md#show-event-attendees)합니다.

### <a name="view-event-details"></a>이벤트 세부 정보 보기

사용자의 이벤트를 선택 하는 경우 **CalendarEventsGallery**, 해당 이벤트에 대 한 자세한 정보를 보여 주는 다른 화면을 열 수 있습니다.

> [!NOTE]
> 이 절차에서는 동적 콘텐츠를 사용 하 여 갤러리에서 이벤트 세부 정보를 보여 줍니다. 하지만 다른 접근 방식을 수행 하 여 비슷한 결과 얻을 수 있습니다. 예를 들어, 자세한 디자인 컨트롤 대신는 일련의 레이블로 사용 하 여 가져올 수 있습니다.

1. 명명 된 빈 화면을 추가 **EventDetailsScreen**, 빈 유연한 높이 갤러리 및 일정 화면으로 이동 하는 단추를 포함 하는 합니다.

1. 유연한 높이 갤러리에서 추가 **레이블을** 컨트롤 및 **HTML 텍스트** 설정 됩니다는 **AutoHeight** 모두의 속성 **true** .

    > [!NOTE]
    > PowerApps에서 해당 콘텐츠를 표시 해야 하므로 HTML 텍스트로 각 이벤트의 메시지 본문을 검색 한 **HTML 텍스트** 제어 합니다.

1. 설정 합니다 **Y** 의 속성을 **HTML 텍스트** 컨트롤을이 식:

    `Label1.Y + Label1.Height + 20`

1. 스타일 요구에 맞게 필요에 따라 추가 속성을 조정 합니다.

    예를 들어, 아래 구분선을 추가 하려면 수는 **HTML 텍스트** 컨트롤입니다.

1. 설정 된 **항목** 을 다음이 수식으로 유연한 높이 갤러리의 속성:

    ```powerapps-dot
    Table(
        { Title: "Subject", Value: _selectedCalendarEvent.Subject },
        { 
            Title: "Time", 
            Value: _selectedCalendarEvent.Start & " - " & _selectedCalendarEvent.End 
        },
        { Title: "Body", Value: _selectedCalendarEvent.Body }
    )
    ```

    이 수식은 갤러리의 필드 값으로 설정 된 동적 데이터를 만듭니다 **_selectedCalendarEvent**에서 이벤트를 선택할 때마다 설정 됩니다는 **CalendarEventsGallery** 제어 합니다. 이 갤러리를 더 레이블을 추가 하 여 더 많은 필드를 포함 하도록 확장할 수 있지만이 집합은 좋은 출발점을 제공 합니다.

1. 곳에서 갤러리 항목을 사용 하 여 설정 합니다 **텍스트** 의 속성을 **레이블** 컨트롤을 `ThisItem.Title`, 및 **HtmlText** 속성은 **HTML 텍스트**  컨트롤을 `ThisItem.Value`입니다.

1. **CalendarEventsGallery**설정 합니다 **OnSelect** 의 속성을 **제목** 컨트롤을 다음이 수식으로:

    ```powerapps-dot
    Set( _selectedCalendarEvent, ThisItem );
    Navigate( EventDetailsScreen, None )
    ```

    > [!Note]
    > 사용 하는 대신 합니다 **_selectedCalendarEvent** 변수를 사용할 수 있습니다 대신 **CalendarEventsGallery**합니다. 선택 합니다.

### <a name="show-event-attendees"></a>이벤트 참가자를 보여 줍니다.

`Office365.GetEventsCalendarViewV2` 여러 필수 및 선택적 참석자의 세미콜론으로 구분 된 집합을 포함 하는 각 이벤트에 대 한 필드를 검색 하는 작업입니다. 이 절차에서는에서는 참가자의 각 집합을 구문 분석, 참석자는 조직에 있는 확인 및 모든 사용자의 Office 365 프로필을 검색 합니다.

1. 앱에 Office 365 사용자 커넥터에 포함 되지 않은 경우 [추가](../add-data-connection.md)합니다.

1. 모임 참가자의 Office 365 프로필을 검색 하려면 설정 합니다 **OnSelect** 의 속성을 **제목** 에서 제어할를 **CalendarEventsGallery** 을 다음이 수식으로:

    ```powerapps-dot
    Set( _selectedCalendarEvent, ThisItem );
    ClearCollect( AttendeeEmailsTemp,
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, ";" ),
            !IsBlank( Result )
        )
    );
    ClearCollect( AttendeeEmails,
        AddColumns( AttendeeEmailsTemp, 
            "InOrg",
            Upper( _userDomain ) = Upper( Right( Result, Len( Result ) - Find( "@", Result ) ) )
        )
    );
    ClearCollect( MyPeople,
        ForAll( AttendeeEmails, If( InOrg, Office365Users.UserProfile( Result ) ) ) 
    );
    Collect( MyPeople,
        ForAll( AttendeeEmails,
            If( !InOrg, 
                { DisplayName: Result, Id: "", JobTitle: "", UserPrincipalName: Result }
            )
        )
    )
    ```

이 목록에서는 각 기능에 대해 설명 **ClearCollect** 작업 않습니다.

- ClearCollect(AttendeeEmailsTemp)
    ```powerapps-dot
    ClearCollect( AttendeeEmailsTemp,
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, ";" ), 
            !IsBlank( Result)
        )
    );
    ```

    이 수식에는 다음 각 세미콜론 개별 주소를 해당 문자열을 분할 및 단일 문자열에 필수 및 선택적 참석자를 연결 합니다. 수식은 다음 해당 집합에서 빈 값을 필터링 하며 이라는 컬렉션에 다른 값을 추가 **AttendeeEmailsTemp**합니다.

- ClearCollect(AttendeeEmails)
    ```powerapps-dot
    ClearCollect( AttendeeEmails,
        AddColumns( AttendeeEmailsTemp, 
            "InOrg",
            Upper( _userDomain ) = Upper( Right( Result, Len(Result) - Find("@", Result) ) )
        )
    );
    ```
    이 수식은 대략적으로 조직에서 참가자 인지 여부를 결정 합니다. 정의 **_userDomain** 단순히 앱을 실행 하는 사용자의 전자 메일 주소에서 도메인 URL입니다. 이 줄은 라는 추가 true/false 열을 만듭니다 **InOrg**를 **AttendeeEmailsTemp** 컬렉션입니다. 이 열에 포함 **true** 하는 경우 **userDomain** 특정 행에서 전자 메일 주소의 도메인 URL을 동일 **AttendeeEmailsTemp**합니다.

    이 방법은 항상 정확 하 고, 아니지만 상당히 닫기 가져옵니다. 예를 들어, 조직에서 특정 참가자와 같은 전자 메일 주소를 있을 Jane@OnContoso.com반면 **_userDomain** contoso.com입니다. 앱 사용자와 jane에 게 동일한 회사에 근무 되었지만 전자 메일 주소에 대 한 약간의 변형이 됩니다. 이러한 경우에이 수식을 사용 하 여 하려는:

    `Upper(_userDomain) in Upper(Right(Result, Len(Result) - Find("@", Result)))`

    그러나이 수식은 일치와 같은 전자 메일 주소 Jane@NotTheContosoCompany.com 사용 하 여는 **_userDomain** 같은 Contoso.com 및 사람들 같은 회사에 작동 하지 않습니다.

- ClearCollect(MyPeople)

    ```powerapps-dot
    ClearCollect( MyPeople,
        ForAll( AttendeeEmails, 
            If( InOrg, 
                Office365Users.UserProfile( Result )
            )
        )
    );
    Collect( MyPeople,
        ForAll( AttendeeEmails,
            If( !InOrg, 
                { 
                    DisplayName: Result, 
                    Id: "", 
                    JobTitle: "", 
                    UserPrincipalName: Result
                }
            )
        )
    );
    ```
    Office 365 프로필을 검색 하려면 사용 해야 합니다 [Office365Users.UserProfile](https://docs.microsoft.com/connectors/office365users/#userprofile) 하거나 [Office365Users.UserProfileV2](https://docs.microsoft.com/connectors/office365users/#userprofile) 작업 합니다. 이러한 작업 사용자의 조직에 있는 참가자에 대 한 모든 Office 365 프로필을 먼저 수집 그런 다음 작업을 조직 외부에서 참가자에 대 한 몇 가지 필드를 추가합니다. 때문에 고유한 작업으로 두 개의 항목을 구분 합니다 **ForAll** 루프 순서를 보장 하지 않습니다. 따라서 **ForAll** 조직 외부에서 참가자를 처음 수집할 수 있습니다. 이 경우에 대 한 스키마 **MyPeople** 만 포함 **DisplayName**합니다 **Id**를 **JobTitle**, 및 **UserPrincipalName** . 그러나 UserProfile 작업 보다 훨씬 다양 한 데이터를 검색합니다. 할 하므로 합니다 **MyPeople** 다른 프로필 전에 Office 365 프로필을 추가할 컬렉션입니다.

    > [!NOTE]
    > 하나만 사용 하 여 동일한 결과 얻을 수 있습니다 **ClearCollect** 함수:

    ```powerapps-dot
    ClearCollect( MyPeople, 
        ForAll(
            AddColumns(
                Filter(
                    Split(
                        ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, 
                        ";"
                    ), 
                    !IsBlank( Result )
                ), 
                "InOrg", _userDomain = Right( Result, Len( Result ) - Find( "@", Result ) )
            ), 
            If( InOrg, 
                Office365Users.UserProfile( Result ), 
                { 
                    DisplayName: Result, 
                    Id: "", 
                    JobTitle: "", 
                    UserPrincipalName: Result, 
                    Department: "", 
                    OfficeLocation: "", 
                    TelephoneNumber: ""
                }
            )
        )
    )
    ```

이 연습을 완료 합니다.

1. 갤러리를 포함 하는 화면을 추가 합니다 **항목** 속성이 **MyPeople**합니다.

1. **OnSelect** 의 속성을 **제목** 에서 제어할를 **CalendarEventsGallery**, 추가 **탐색** 화면에는 함수 이전 단계에서 만들었습니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대 한 참조 설명서](calendar-screen-reference.md)합니다.
* [Office 365 Outlook 커넥터에 자세히 알아보려면](../connections/connection-office365-outlook.md)합니다.
* [Office 365 사용자 커넥터에 자세히 알아보려면](../connections/connection-office365-users.md)합니다.
