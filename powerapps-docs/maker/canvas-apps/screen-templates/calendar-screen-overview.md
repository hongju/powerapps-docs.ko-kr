---
title: 일정 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대한 일정 화면 템플릿의 작동 방식을 이해 하고, 화면을 수정 하고, 앱의 일부로 확장
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
# <a name="overview-of-the-calendar-screen-template-for-canvas-apps"></a>캔버스 앱에 대한 일정 화면 템플릿의 개요

캔버스 앱에서 사용자에게 해당 Office 365 Outlook 계정에서 예정된 이벤트를 표시 하는 일정 화면을 추가 합니다. 해당 일의 이벤트의 목록을 통해 스크롤하여 달력에서 날짜를 선택할 수 있습니다. 정보 목록에 표시, 각 이벤트에 대 한 자세한 세부 정보를 표시 하는 두 번째 화면을 추가, 각 이벤트에 대 한 참가자의 목록을 표시 및 기타 사용자 지정 확인을 변경할 수 있습니다.

[전자 메일](email-screen-overview.md), 조직의 [사람들](people-screen-overview.md)과 사용자의 모임에 초대하려고 하는 사람들의 [가용성](meeting-screen-overview.md)과 같은 Office 365의 다양한 데이터를 표시하는 다른 템플릿 기반 화면을 추가할 수도 있습니다.

개요에서 다음을 설명합니다.
> [!div class="checklist"]
> * 기본 일정 화면을 사용 하는 방법.
> * 수정 하는 방법.
> * 앱에 통합 하는 방법.

이 화면의 기본 기능에 대한 심층 분석에 대해서는 [일정 화면 참조](calendar-screen-reference.md)를 확인합니다.

## <a name="prerequisite"></a>필수 조건

[PowerApps에서 앱을 만들어](../data-platform-create-app-scratch.md) 화면 및 기타 컨트롤을 추가하고 구성하는 방법에 친숙합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 일정 화면을 추가:

1. PowerApps에 [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)한 다음 앱을 만들거나 기존 앱을 PowerApps Studio에서 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 리본의 **홈** 탭에서 **새 화면** > **캘린더**를 선택합니다.

    기본적으로 다음 화면과 비슷합니다.

    ![일정 화면](media/calendar-screen/calendar-initial.png)

1. 데이터를 표시 하려면 화면 위쪽 드롭다운 목록에서 옵션을 선택 합니다.

    ![로드가 완료 되 면 일정 화면](./media/calendar-screen/calendar-screen.png)

몇 가지 유용한 참고 사항:

* 기본적으로 선택된 오늘 날짜는 오른쪽 위 모서리에서 달력 아이콘을 선택하여 쉽게 반환할 수 있습니다.
* 다른 날짜를 선택하면 원을 둘러싸고 밝은 색 사각형(기본 테마가 적용 된 경우 파란색)이 오늘 날짜를 묶습니다.
* 특정 날짜에 대 한 하나 이상의 이벤트를 예약 하면 작은 컬러 원이 달력의 날짜 아래에 나타납니다.
* 하나 이상의 이벤트가 예약 된 날짜를 선택하면 이벤트가 달력 아래 목록에 나타납니다.

## <a name="modify-the-screen"></a>화면 수정

몇 가지 일반적인 방법으로 이 화면의 기본 기능을 수정할 수 있습니다.

* [일정을 지정](calendar-screen-overview.md#specify-the-calendar)합니다.
* [이벤트에 대한 다양한 세부 정보를 표시](calendar-screen-overview.md#show-different-details-about-an-event)합니다.
* [비차단 이벤트를 숨기기](calendar-screen-overview.md#hide-nonblocking-events)합니다.

화면을 추가로 수정하려는 경우 가이드로 [일정 화면 참조](./calendar-screen-reference.md)를 사용합니다.

### <a name="specify-the-calendar"></a>일정 지정

사용자에게 표시 되어야 하는 일정을 이미 알고 있는 경우에 앱을 게시하기 전에 해당 일정을 지정하여 화면을 간소화할 수 있습니다. 이 변경은 일정의 드롭다운 목록이 필요없게 되어 그 목록을 제거할 수 있습니다.

1. 앱에서 기본 화면의 **[OnStart](../controls/control-screen.md)** 속성을 다음 수식으로 설정합니다:

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
    > 이 수식은 일정을 선택 하기 위한 드롭다운 목록의 **OnSelect** 속성 기본값에서 일부를 편집합니다. 해당 컨트롤에 대한 자세한 내용은 [일정 화면 참조](./calendar-screen-reference.md#calendar-drop-down)에서 해당 섹션을 참고합니다.

1. 중괄호를 포함 하여 `{YourCalendarNameHere}`를 표시 하려는 일정의 이름으로 바꿉니다(예를 들어 **일정**).

    > [!IMPORTANT]
    > 다음 단계는 앱에 하나의 일정 화면을 추가하는 것을 가정합니다. 둘 이상을 추가한 경우 컨트롤 이름은(**iconCalendar1**와 같은) 다른 숫자를 사용하여 끝나게 되고 수식을 적절 하게 조정 해야 합니다.

1. **iconCalendar1** 컨트롤의 **Y** 속성에 다음 식으로 설정합니다:

    `RectQuickActionBar1.Height + 20`

1. **LblMonthSelected1** 컨트롤의 **Y** 속성에 다음 식으로 설정합니다:

    `iconCalendar1.Y + iconCalendar1.Height + 20`

1. **LblNoEvents1** 컨트롤의 **Text** 속성에 다음 값으로 설정합니다:

    `"No events scheduled"`

1. **LblNoEvents1**의 **Visible** 속성에 다음 수식으로 설정합니다:

    `CountRows(CalendarEventsGallery1.AllItems) = 0 && _calendarVisible`

1. 이러한 컨트롤을 삭제 합니다.

    - **dropdownCalendarSelection1**
    - **LblEmptyState1**
    - **iconEmptyState1**

1. 일정 화면이 기본 화면이 아니면 앱을 테스트할 수 있도록 기본 화면에서 일정 화면으로 이동하는 단추를 추가 합니다.

    예를 들어 비어 있는 상태에서 만든 앱에 일정 화면을 추가한 경우 **Screen1**에 **Screen2**로 이동하는 단추를 추가합니다.

1. 앱을 저장 한 다음 브라우저 또는 모바일 장치에서 테스트 합니다.

### <a name="show-different-details-about-an-event"></a>이벤트에 대한 다양한 세부 정보 표시

기본적으로 달력아래 **CalendarEventsGallery** 이름의 갤러리는 시작 시간, 기간, 제목 및 각 이벤트의 위치를 보여 줍니다. [Office 365 커넥터](https://docs.microsoft.com/connectors/office365/#calendareventclientreceive)에서 지원하는 모든 필드 (예: 이끌이)를 표시하도록 갤러리를 구성할 수 있습니다.

1. **CalendarEventsGallery**에서, 새 또는 기존 레이블의 **Text** 속성에 `ThisItem`과 마침표를 설정합니다.

    IntelliSense는 선택할 수 있는 필드를 나열 합니다.

1. 원하는 필드를 선택 합니다.

    레이블이 지정 된 정보를 보여 줍니다.

### <a name="hide-nonblocking-events"></a>비차단 이벤트 숨기기

여러 사무실에서, 사무실과 떨어져 있는 경우 팀 멤버는 서로에게 알리기 위해 모임 요청을 보냅니다. 모든 사용자의 일정을 차단하는 것을 방지 하려면 요청을 보내는 사람의 상태를 **다른 일정 없음**으로 설정합니다. 몇 가지 속성을 업데이트하여 일정 및 갤러리에서 이러한 이벤트를 숨길 수 있습니다.

1. **CalendarEventsGallery**의 **Items** 속성을 다음 수식으로 설정합니다:

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

    이 수식에서 **Filter** 함수는 해당 선택한 것과 다른 날짜에 대한 예약된 이벤트 뿐만 아니라 이벤트의 가용성이 다른 일정 없음인 경우를 숨깁니다.

1. 일정에서, **Circle** 컨트롤의 **Visible** 속성을 다음 수식으로 설정합니다:

    ```powerapps-dot
    CountRows(
        Filter(
            MyCalendarEvents,
            DateValue( Text(Start) ) = DateAdd( _firstDayInView, ThisItem.Value, Days ),
            ShowAs <> "Free"
        )
    ) > 0 && !Subcircle1.Visible && Title2.Visible
    ```
    이 수식은 앞의 수식과 동일한 필터가 포함 되어 있습니다. 따라서 이벤트의 가용성이 다른 일정 없음이 아니고 선택한 날짜에 하나 이상의 이벤트를 가지는 경우에만 이벤트 표시기 원이 달력 아래에 나타납니다. 

## <a name="integrate-the-screen-into-an-app"></a>화면을 앱에 통합

일정 화면 자체 오른쪽에 있는 컨트롤의 강력한 번들 이지만 일반적으로 가장 큰, 더 다양 한 응용 프로그램의 일부로 수행 합니다. 이러한 옵션을 추가 하는 등 다양 한 방법으로 더 큰 앱에 이 화면을 통합할 수 있습니다.

* [이벤트 세부 정보 보기](calendar-screen-overview.md#view-event-details).
* [이벤트 참석자 표시](calendar-screen-overview.md#show-event-attendees).

### <a name="view-event-details"></a>이벤트 세부 정보 보기

사용자가 **CalendarEventsGallery**에서 하나의 이벤트를 선택 하는 경우 , 해당 이벤트에 대한 자세한 정보를 보여주는 다른 화면을 열 수 있습니다.

> [!NOTE]
> 이 절차에서는 동적 콘텐츠를 사용하여 갤러리에서 이벤트 세부 정보를 보여 줍니다. 하지만 다른 접근 방식을 수행하여 비슷한 결과를 얻을 수 있습니다. 예를 들어, 일련의 레이블 대신에 자세한 디자인 컨트롤을 사용할 수 있습니다.

1. **EventDetailsScreen**라는 이름의 빈 화면을 추가합니다. 그 화면은 빈 높이 조정 가능 갤러리 및 일정 화면으로 이동하는 단추를 포함합니다.

1. 높이 조정 가능 갤러리에 **레이블**과 **HTML 텍스트** 컨트롤을 추가하고 두 컨트롤의 **AutoHeight** 속성을 **true**로 지정합니다.

    > [!NOTE]
    > PowerApps에서는  HTML 텍스트로 각 이벤트의 메시지 본문을 검색하므로 **HTML 텍스트** 컨트롤에서 해당 콘텐츠를 표시해야 합니다.

1. **HTML 텍스트** 컨트롤의 **Y** 속성을 다음 식으로 설정합니다:

    `Label1.Y + Label1.Height + 20`

1. 스타일 요구에 맞게 필요에 따라 추가 속성을 조정 합니다.

    예를 들어, **HTML 텍스트** 컨트롤 아래 구분선을 추가 할 수 있습니다.

1. 높이 조정 가능 갤러리의 **Items**속성을 다음 수식으로 설정합니다:

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

    이 수식은 **CalendarEventsGallery** 컨트롤에서 사용자가 이벤트를 선택할 때마다 설정되는 **_selectedCalendarEvent**의 필드 값으로 설정 되는 동적 데이터의 갤러리를 만듭니다. 레이블을 더 추가 하 여 더 많은 필드를 포함 하도록 갤러리를 확장할 수 있지만 이 설정은 좋은 출발점을 제공 합니다.

1. 갤러리 항목에서 **레이블** 컨트롤의 **Text** 의 속성을 `ThisItem.Title`으로 설정하고 **HTML 텍스트** 컨트롤의  **HtmlText** 속성을 `ThisItem.Value`으로 설정합니다.

1. **CalendarEventsGallery**에서 **Title** 컨트롤의 **OnSelect** 속성을  다음 수식으로 설정합니다:

    ```powerapps-dot
    Set( _selectedCalendarEvent, ThisItem );
    Navigate( EventDetailsScreen, None )
    ```

    > [!Note]
    > **_selectedCalendarEvent** 변수를 사용하는 대신 **CalendarEventsGallery.Selected**를 사용할 수 있습니다.

### <a name="show-event-attendees"></a>이벤트 참석자 표시

`Office365.GetEventsCalendarViewV2`는 여러 필수 및 선택적 참석자의 세미콜론으로 구분 된 집합을 포함 하는 각 이벤트에 대 한 필드를 검색 하는 작업입니다. 이 절차에서는 참석자의 각 집합을 구문 분석, 조직에 있는 참가자를 확인하고 모든 사용자의 Office 365 프로필을 검색 합니다.

1. 앱에 Office 365 사용자 커넥터가 포함 되지 않은 경우 [추가](../add-data-connection.md)합니다.

1. 모임 참가자의 Office 365 프로필을 검색 하려면  **CalendarEventsGallery**에서 **Title** 컨트롤의 **OnSelect** 속성을 다음 수식으로 설정 합니다:

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

이 목록에서는 **ClearCollect** 작업에 대해 설명합니다.

- ClearCollect(AttendeeEmailsTemp)
    ```powerapps-dot
    ClearCollect( AttendeeEmailsTemp,
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, ";" ), 
            !IsBlank( Result)
        )
    );
    ```

    이 수식에는 단일 문자열에 필수 및 선택적 참석자를 연결한 다음 해당 문자열을 세미콜론으로 각 개별 주소를 분할합니다. 수식은 해당 집합에서 빈 값을 필터링 한 후 다른 값들을 **AttendeeEmailsTemp**이라는 컬렉션에 추가합니다.

- ClearCollect(AttendeeEmails)
    ```powerapps-dot
    ClearCollect( AttendeeEmails,
        AddColumns( AttendeeEmailsTemp, 
            "InOrg",
            Upper( _userDomain ) = Upper( Right( Result, Len(Result) - Find("@", Result) ) )
        )
    );
    ```
    이 수식은 대략적으로 조직에서 참가자 인지 여부를 결정 합니다. **_userDomain**의 정의는 앱을 실행 하는 사용자의 전자 메일 주소에서 단순히 도메인 URL입니다. 이 줄은 **AttendeeEmailsTemp** 컬렉션에 **InOrg**라는 추가 true/false 열을 만듭니다. **userDomain**이 **AttendeeEmailsTemp** 특정 행에서 전자 메일 주소의 도메인 URL가 동일한 경우 이 열에 **true**를 포함합니다   .

    이 방법은 항상 정확 하지는 않지만 상당히 적절합니다. 예를 들어, 조직에서 Jane@OnContoso.com 와 같은 전자 메일 주소를 가지는 특정 참가자는 **_userDomain**이 contoso.com입니다. 앱 사용자와 jane이 동일한 회사에 근무한다면 전자 메일 주소에 대한 약간의 변형이 됩니다. 이러한 경우에 다음 수식을 사용하기를 원할  있습니다:

    `Upper(_userDomain) in Upper(Right(Result, Len(Result) - Find("@", Result)))`

    그러나 다음 수식은 Jane@NotTheContosoCompany.com 같은 전자 메일 주소와 Contoso.com의 **_userDomain**을 매치하여 같은 회사 사람으로 작업하지 않습니다..

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
    Office 365 프로필을 검색 하려면 [Office365Users.UserProfile](https://docs.microsoft.com/connectors/office365users/#userprofile) 또는 [Office365Users.UserProfileV2](https://docs.microsoft.com/connectors/office365users/#userprofile) 작업을 사용해야 합니다  합니다. 이 작업들은 사용자의 조직에 있는 참가자에 대한 모든 Office 365 프로필을 먼저 수집합니다. 그런 다음 조직 외부의 참가자에 대 한 몇 가지 필드를 추가합니다. **ForAll** 루프는 순서를 보장 하지 않기 때문에 고유한 작업으로 두 개의 항목을 구분 합니다. 따라서 **ForAll**은 조직 외부의 참가자를 먼저 수집할 수 있습니다. 이 경우, **MyPeople** 스키마는 **DisplayName**, **Id**, **JobTitle** 및 **UserPrincipalName**만 포함합니다. 그러나 UserProfile 작업은 훨씬 더 다양 한 데이터를 검색합니다. 그래서 다른 프로필 보다 먼저 **MyPeople** 컬렉션을 Office 365 프로필에 추가해야 합니다.

    > [!NOTE]
    > 단지 **ClearCollect** 함수 하나만 사용하여 동일한 결과 얻을 수 있습니다 :

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

이 연습을 완료하기 위해

1. **Items** 속성을 **MyPeople**로 설정한 갤러리를 포함하는 화면을 추가합니다.

1. **CalendarEventsGallery**에서 **Title** 컨트롤의 **OnSelect** 속성에, 이전 단계에서 생성한 화면으로 이동하는 **Navigate** 함수를 추가합니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대한 참조 설명서](calendar-screen-reference.md)를 확인합니다.
* [Office 365 Outlook 커넥터에 자세히 알아봅니다.](../connections/connection-office365-outlook.md)
* [Office 365 사용자 커넥터에 자세히 알아봅니다.](../connections/connection-office365-users.md)
