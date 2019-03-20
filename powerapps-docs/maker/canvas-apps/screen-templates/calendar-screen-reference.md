---
title: 캔버스 앱에 대 한 달력 화면 템플릿에 대 한 참조 | Microsoft Docs
description: PowerApps의 캔버스 앱에 대 한 달력 화면 템플릿을 작동 하는 방법의 세부 정보를 이해 합니다.
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
ms.openlocfilehash: abf88db2bfb97a6541ee638ba8be5af27c20bc5f
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459577"
---
# <a name="reference-information-about-the-calendar-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 달력 화면 템플릿에 대 한 참조 정보

PowerApps의 캔버스 앱에 대 한 중요 한 각 달력 화면 템플릿의 컨트롤 화면의 전체 기본 기능에 기여 하는 방법을 이해 합니다. 이 심층 동작 수식 및 컨트롤 사용자 입력에 응답 하는 방법을 결정 하는 다른 속성의 값을 표시 합니다. 이 화면의 기본 기능의 간략 한 설명을에 대 한 참조를 [달력 화면 개요](calendar-screen-overview.md)합니다.

이 항목에서는 몇 가지 중요 한 컨트롤을 강조 표시 하 고 다양 한 속성을 수식 또는 식에 설명 (같은 **항목** 하 고 **OnSelect**) 이러한 컨트롤은 설정 됩니다.

- [달력 드롭다운 (dropdownCalendarSelection)](#calendar-drop-down)
- [달력 아이콘 (iconCalendar)](#calendar-icon)
- [이전 달 펼침 단추 (iconPrevMonth)](#previous-month-chevron)
- [다음 개월 펼침 단추 (iconNextMonth)](#next-month-chevron)
- [달력 갤러리 (MonthDayGallery) (+ 자식 컨트롤)](#calendar-gallery)
- [이벤트 갤러리 (CalendarEventsGallery)](#events-gallery)

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="calendar-drop-down"></a>드롭다운 달력

![dropdownCalendarSelection 컨트롤](media/calendar-screen/calendar-dropdown.png)

- 속성: **항목**<br>
    값: `Office365.CalendarGetTables().value`

    이 값은 앱 사용자의 Outlook 일정을 검색 하는 커넥터 작업입니다. 볼 수 있습니다 [값](https://docs.microsoft.com/connectors/office365/#entitylistresponse[table]) 이 작업을 검색 하는 합니다.

- 속성: **OnChange**<br>값: `Select(dropdownCalendarSelection)`

    사용자 컨트롤의 함수 목록에서 옵션을 선택 하는 경우 **OnSelect** 속성 실행 합니다.

- 속성: **OnSelect**<br>
    값: **경우** 다음 코드 블록에 나타나는 함수 및 그 후 코드 블록에 표시 되는 여러 추가 기능을 합니다.

   처음에만 사용자가 옵션 드롭다운 목록에서 앱을 연 후 수식 실행 중이 부:

    ```powerapps-dot
    If( IsBlank( _userDomain ),
        UpdateContext( {_showLoading: true} );
        Set( _userDomain, Right( User().Email, Len( User().Email ) - Find( "@", User().Email ) ) );
        Set( _dateSelected, Today() );
        Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days ) );  
        Set( _firstDayInView, DateAdd( _firstDayOfMonth, -(Weekday(_firstDayOfMonth) - 1), Days ) );
        Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )  
    );
    ```

    위의 코드는 다음 변수를 정의합니다.
    
  - **\_userDomain**: 앱 사용자의 회사 도메인, 사용자의 전자 메일 주소에 반영 되어 있습니다.
  - **\_dateSelected**: 기본적으로 현재 날짜입니다. 달력 갤러리가이 날짜를 강조 하 고 해당 날짜에 대 한 예약 된 이벤트를 이벤트 갤러리에 표시 됩니다.
  - **\_firstDayOfMonth**: 현재 달의 첫 번째 날입니다. 때문에 `(Today + (1 - Today)) = Today - Today + 1 = 1`이 **DateAdd** 함수는 항상 해당 월의 첫 번째 날을 반환 합니다.
  - **\_firstDayInView**: 달력 갤러리를 표시할 수 있는 첫 번째 날입니다. 이 값 월 일요일에 시작 하지 않는 한 월의 첫날와는 다릅니다. 값을 이전 월의 주를 표시 하지 않으려면  **\_firstDayInView** 는 `_firstDayOfMonth - Weekday(_firstDayOfMonth) + 1`합니다.
  - **\_lastDayOfMonth**: 하루를 뺀 다음 달의 첫째 요일로 현재 월의 마지막 날입니다.

   다음 함수는 **경우** (뿐 아니라 처음으로 사용자가 앱을 열)의 일정 드롭 다운 목록에서 옵션을 선택할 때마다 함수가 실행:

    ```powerapps-dot
    Set( _calendarVisible, false );
    UpdateContext( {_showLoading: true} );
    Set( _myCalendar, dropdownCalendarSelection2.Selected );
    Set( _minDate, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days )
    );
    Set(_maxDate, 
        DateAdd(
            DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days ), 
            40, 
            Days
        )
    );
    ClearCollect( MyCalendarEvents, 
        'Office365'.GetEventsCalendarViewV2( _myCalendar.Name, 
            Text( _minDate, UTC ), 
            Text( _maxDate, UTC )
        ).value
    );
    UpdateContext( {_showLoading: false} );
    Set( _calendarVisible, true )
    ```

    위의 코드는 이러한 변수 및 하나의 컬렉션을 정의합니다.

    - **\_calendarVisible**: 로 **false** 새 선택 영역을 로드 되는 동안 달력 나타나지 않도록 합니다.
    - **\_showLoading**: 로 **true** 로드 표시기를 새 선택 영역을 로드 하는 동안 표시 되도록 합니다.
    - **\_myCalendar**: 현재 값으로 설정 합니다 **달력 드롭다운** 컨트롤을 올바른 일정에서 이벤트를 검색 합니다.
    - **\_minDate**: 동일한 값으로 설정할  **\_firstDayInView**합니다. 이 변수는 이벤트 이미 Outlook에서 검색 되었으며 앱에서 캐시를 결정 합니다.
    - **\_maxDate**: 일정에서 볼 수 있는 마지막 날을 설정 합니다. 공식은 `_firstDayInView + 40`합니다. 일정의 경우 최대 41 일을 표시 하므로  **\_maxDate** 변수에서 항상 볼 수 있는 마지막 날을 반영 하 고 이벤트 이미 Outlook에서 검색 되었으며 앱에서 캐시를 결정 합니다.
    - **MyCalendarEvents**: 이르기까지 선택한 달력에서 사용자의 이벤트의 컬렉션으로 설정  **\_minDate** 하려면  **\_maxDate**합니다.
    - **\_showLoading**: 로 **false**;  **\_calendarVisible** 로 설정 되어 **true** 등등 로드 되 면 합니다.

## <a name="calendar-icon"></a>달력 아이콘

![iconCalendar 컨트롤](media/calendar-screen/calendar-today-icon.png)

- 속성: **OnSelect**<br>
    값: 네 **설정** 오늘 날짜에 일정 갤러리를 다시 설정 하는 함수:

    ```powerapps-dot
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days) );
    Set( _firstDayInView, DateAdd(_firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days));
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )
    ```

    앞의 코드는 적절 한 달력 보기를 표시 하는 데 필요한 모든 날짜 변수를 다시 설정 합니다.

    - **\_dateSelected** 오늘날으로 다시 설정 됩니다.
    - **\_firstDayOfMonth** 현재 월의 첫째 날에 다시 설정 됩니다.
    - **\_firstDayInView** 현재 월을 선택한 경우 첫 번째 날 볼 수 있는으로 다시 설정 됩니다.
    - **\_lastDayOfMonth** 현재 월의 마지막 날짜를 다시 설정 됩니다.

    합니다 [ **달력 드롭 다운** ](#calendar-drop-down) 이 항목의 섹션에서는 이러한 변수를 자세히 설명 합니다.

## <a name="previous-month-chevron"></a>이전 달 펼침 단추

![iconPrevMonth 컨트롤](media/calendar-screen/calendar-back.png)

- 속성: **OnSelect**<br>값: 네 **설정할** 함수 및 **경우** 이전 달 달력 갤러리에 표시 하는 함수:

    ```powerapps-dot
    Set( _firstDayOfMonth, DateAdd( _firstDayOfMonth, -1, Months ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days )
    );
    Set( _lastDayOfMonth, DateAdd(DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    If( _minDate > _firstDayOfMonth,
        Collect( MyCalendarEvents,
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name,
                Text( _firstDayInView, UTC ), 
                Text( DateAdd( _minDate, -1, Days ), UTC )
            ).value
        );
        Set( _minDate, _firstDayInView )
    )
    ```

    > [!NOTE]
    > 에 대 한 정의가  **\_firstDayOfMonth**합니다  **\_firstDayInView**, 및  **\_lastDayOfMonth** 거의 일치 하는 에 [달력 드롭다운](#calendar-drop-down) 이 항목의 섹션입니다.

    앞의 코드의 첫 세 줄에는 이전 달 펼침 단추를 선택할 때마다 실행 합니다. 코드를 적절 한 달력 보기를 표시 하는 데 필요한 변수를 설정 합니다. 나머지 코드에는 사용자는 선택한 일정에 대 한 이번 달 이전에 선택한 하지 않은 경우에 실행 됩니다.

    이 경우  **\_minDate** 이전 달 표시 되 면 표시 되는 1 일입니다. 사용자가 아이콘을 선택 하기 전에  **\_minDate** 현재 달의 23 특수 가능한 최소 값입니다. (토요일 3 월 1 일 작아지면  **\_firstDayInView** 년 3 월은 2 월 23.) 즉, 사용자 이번 달에 아직 선택 하지 않은 경우  **\_minDate** 새 보다 크면  **\_firstDayOfMonth**, 및 **경우** 함수에서 반환 **true**합니다. 코드 실행 및 컬렉션 변수 업데이트 됩니다.

    - **MyCalendarEvents** 사용 하 여 선택한 일정에서 이벤트를 검색 합니다 [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) 작업 합니다. 날짜 범위는 합니다  **\_firstDayInView** 날짜와  **\_minDate** -1입니다. 때문에 **MyCalendarEvents** 이미에 이벤트를 포함 합니다  **\_minDate** 날짜 최 댓 값이 새 날짜 범위에서의 해당 날짜부터 1을 뺍니다.

    - **\_minDate** 현재로 설정 된  **\_firstDayInView** 이벤트 검색 된 첫 번째 날짜 이기 때문에 있습니다. 사용자는 이전 달 펼침 단추를 선택 하 여이 날짜를 반환 하는 경우는 **하는 경우** 함수에서 반환 **false**;이 보기에 대 한 이벤트에 이미 캐시 되므로 코드를 실행 하지 않습니다  **MyCalendarEvents**합니다.

## <a name="next-month-chevron"></a>다음 개월 펼침 단추

![iconNextMonth 컨트롤](media/calendar-screen/calendar-forward.png)

- 속성: **OnSelect**<br>
    값: 네 **설정할** 함수 및 **경우** 다음달 달력 갤러리에 표시 하는 함수:

    ```powerapps-dot
    Set( _firstDayOfMonth, DateAdd( _firstDayOfMonth, 1, Months ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days ) );
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    If( _maxDate < _lastDayOfMonth,
        Collect( MyCalendarEvents, 
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name, 
                Text( DateAdd( _maxDate, 1, Days ), UTC ), 
                DateAdd( _firstDayInView, 40, Days )
            ).value
        );
        Set( _maxDate, DateAdd( _firstDayInView, 40, Days) )    
    )
    ```

    > [!NOTE]
    > 에 대 한 정의가  **\_firstDayOfMonth**합니다  **\_firstDayInView**, 및  **\_lastDayOfMonth** 거의 일치 하는 에 [달력 드롭다운](#calendar-dropdown) 이 항목의 섹션입니다.

    사용자가 다음 개월 펼침 단추를 선택할 때 실행할 앞의 코드의 첫 세 줄 적절 한 달력 보기를 표시 하는 데 필요한 변수를 설정 합니다. 나머지 코드에는 사용자는 선택한 일정에 대 한 이번 달 이전에 선택한 하지 않은 경우에 실행 됩니다.

    이 경우  **\_maxDate** 이전 달 표시 되 면 표시 되는 마지막 날짜입니다. 사용자가 다음 개월 펼침 단추를 선택 하기 전에  **\_maxDate** 13 다음 달의 최대 수 값입니다. (2 월 1 일 적을 경우에 비-윤년 일요일  **\_maxDate** 는 3 월 13 일 상태인  **\_firstDayInView** + 40 일.) 즉, 사용자 이번 달에 아직 선택 하지 않은 경우  **\_maxDate** 새 보다 크면  **\_lastDayOfMonth**, 및 **경우** 함수 반환 **true**합니다. 코드 실행 및 컬렉션 변수 업데이트 됩니다.

    - **MyCalendarEvents** 사용 하 여 선택한 일정에서 이벤트를 검색 합니다 [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) 작업 합니다. 날짜 범위는  **\_maxDate** + 1 일 및  **\_firstDayInView** + 40 일 합니다. 때문에 **MyCalendarEvents** 이미에 이벤트를 포함 합니다  **\_minDate** 날짜 1이 새 날짜 범위의 최소값에 해당 날짜에 추가 됩니다. **\_firstDayInView** + 40는 수식을  **\_maxDate**이므로 두 번째 날짜 범위에는 단지 새  **\_maxDate**합니다.

    - **\_maxDate** 로 설정 된  **\_firstDayInView** + 40 일 어제 이기 때문에 이벤트를 검색 합니다. 사용자는 다음 달 펼침 단추를 선택 하 여이 날짜를 반환 하는 경우는 **하는 경우** 함수에서 반환 **false**;이 보기에 대 한 이벤트에 이미 캐시 되므로 코드를 실행 하지 않습니다  **MyCalendarEvents**합니다.

## <a name="calendar-gallery"></a>달력 갤러리

![MonthDayGallery 컨트롤](media/calendar-screen/calendar-month-gall.png)

- 속성: **항목**<br>
    값: `[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,
    20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41]`
  
  최악의 시나리오에서는 일정 보기 42 전체 일을 표시 해야 하기 때문에 달력 갤러리의 항목에 대 한 0부터 41 집합이 사용 됩니다. 이 달의 첫 번째 토요일에 나타나고 해당 월의 마지막 일요일에 발생 하는 경우 발생 합니다. 이 경우 달력 월의 첫 번째를 포함 하는 행의 이전 월 6 일 및 월의 마지막이 포함 된 행에 다음 달부터 6 일 보여 줍니다. 선택한 월 수 있는 30 42 고유 값입니다.

- 속성: **WrapCount**<br>
    값: `7`

  이 값은 7 일 주를 반영 합니다.

### <a name="title-control-in-the-calendar-gallery"></a>달력 갤러리에서 제목 컨트롤

![MonthDayGallery 제목 컨트롤](media/calendar-screen/calendar-month-text.png)

- 속성: **텍스트**<br>
    값: `Day( DateAdd( _firstDayInView, ThisItem.Value, Days ) )`

    이전에 설명한 대로  **\_firstDayInView** 으로 정의 됩니다 (**\_firstDayOfMonth** -해당 요일 값) + 1입니다. 이 없음을 알 수  **\_firstDayInView** 은 항상 일요일, 및  **\_firstDayOfMonth** 의 첫 번째 행은 항상 **MonthDayGallery**합니다. 이러한 두 가지 사실을 때문  **\_firstDayInView** 의 첫 번째 셀에는 항상 **MonthDayGallery**합니다. **ThisItem.Value** 에서 해당 셀의 수를 **MonthDayGallery** 항목 속성입니다. 따라서 수행  **\_firstDayInView** 시작 지점으로 각 셀의 증가값을 표시  **\_firstDayInView** + 해당 셀 값에 해당 합니다.

- 속성: **채우기**<br>
    값: 하나의 **경우** 함수:

    ```powerapps-dot
    If( DateAdd( _firstDayInView, ThisItem.Value ) = Today() && 
                DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected, 
            RGBA( 0, 0, 0, 0 ),
        DateAdd( _firstDayInView, ThisItem.Value) = Today(), 
            ColorFade( Subcircle.Fill, 0.67 ),
        Abs( Title.Text - ThisItem.Value) > 10,
            RGBA( 200, 200, 200, 0.3 ),
        RGBA( 0, 0, 0, 0 )
    )
    ```

  설명에 설명 된 대로 합니다 **텍스트** 속성인 `DateAdd(_firstDayInView, ThisItem.Value)` 표시 셀의 일자를 나타냅니다. 앞의 코드를이 고려 합니다 이러한 비교를 수행 합니다.
  1. 셀의 값이 오늘 날짜 이며이 셀에 해당 하는 경우  **\_dateSelected**, 채우기 값을 제공 하지 않습니다.
  1. 셀의 값이 현재 날짜와 일치 하지 않습니다 하지만  **\_dateSelected**를 제공 합니다 **ColorFade** 채우기입니다.
  1. 일반 마지막 비교 하지 않습니다. 것 (화면 수) 및 항목 수를 셀 항목의 값 셀에 실제 텍스트 값과 비교 합니다.<br>

      더 잘 이해, 2018 년 9 월는 것이 좋습니다 on a 토요일 시작 하 고 일요일에 끝나는 월. 첫 번째 행에서 달력 26 일 년 8 월 및 9을의 첫 번째 월 31 일을 통해 표시 하는 예제의 경우 및 `Abs(Title.Text - ThisItem.Value) = 26` 9 월 1 일까 지. 그런 다음 `Abs(Title.Text - ThisItem.Value) = 5`합니다. 여섯 번째 통해 30 년 9 월 및 10 월 1 일을 표시 하는 일정에서 마지막 행까지 5에서 계속 유지 됩니다. 에 `Abs(Title.Text - ThisItem.Value)` 30 년 9 월에 대 한 5은 계속 있지만 35 년 10 월 날짜에 대 한 됩니다.<br>

      이 패턴은: 으로 이전 달의 표시 된 날짜에 대 한 `Abs(Title.Text - ThisItem.Value)` 은 항상 같습니다는 `Title.Text` 디스플레이에서 첫 번째 요일 값입니다. 다음 달에 표시 되는 일에 대 한 `Abs(Title.Text - ThisItem.Value)` 은 항상 같습니다 합니다 **MonthDayGallery** 항목 1 뺀 값 (이 경우 10 월 1 일)에서 그 달의 첫째 셀의 값입니다. 및 현재 선택 된 월에 표시 된 날짜에 대 한 가장 중요 한 점은 `Abs(Title.Text - ThisItem.Value)` 에서 1 뺀 그 달의 첫 번째 항목의 값과 항상 됩니다 하 고는 이전 예제와 같이 5를 초과할 수 없습니다. 수식으로 쓸 완벽 하 게 유효 하므로 `Abs(Title.Text - ThisItem.Value) > 5`합니다.

      이 문은 현재 선택한 월의 날짜 값 벗어났는지 여부를 확인 합니다. 인 경우 **채우기** 를 부분적으로 불투명 회색으로 표시 됩니다.

    > [!NOTE]
    > 삽입 하 여 자신에 대 한 마지막 비교의 유효성을 검사할 수 있습니다는 **레이블을** 컨트롤 갤러리 및 설정에 해당 **텍스트** 속성을이 값:<br>`Abs(Title.Text - ThisItem.Value)`에 대한 답변에 설명되어 있는 단계를 성공적으로 완료하면 활성화됩니다.

- 속성: **Visible**<br>
    값:

    ```powerapps-dot
    !(
        DateAdd( _firstDayInView, ThisItem.Value, Days ) - 
            Weekday( DateAdd( _firstDayInView, ThisItem.Value,Days ) ) + 1 
        > _lastDayOfMonth
    )
    ```

    위의 문에서 셀이 현재 선택 된 월의 일 없음 발생 하는 행에 있는지 여부를 확인 합니다. 날짜 값에서 날짜의 요일 값을 차감 하 고 항상 1을 더하는 반환 하는 행의 첫 번째 항목에 거주 하는 일을 기억 하십시오. 따라서이 문은 볼 수 있는 월의 마지막 날 이후 행의 첫 번째 날 인지 확인 합니다. 이 경우 전체 행을 다음 월의 일에는 표시 되지 않습니다.

- 속성: **OnSelect**<br>
    값: A **설정** 설정 하는 함수는  **\_dateSelected** 선택된 된 셀의 날짜 변수:

    ```powerapps-dot
    Set( _dateSelected, DateAdd( _firstDayInView, ThisItem.Value, Days ) )
    ```

### <a name="circle-control-in-the-calendar-gallery"></a>달력 갤러리에서 원 컨트롤

![MonthDayGallery 원 컨트롤](media/calendar-screen/calendar-month-event.png)

- 속성: **Visible**<br>
    값: 선택한 날짜에 대 한 예약 된 모든 이벤트가 여부를 결정 하는 수식을 합니다 **Subcircle** 및 **제목** 컨트롤이 표시 됩니다.

    ```powerapps-dot
    CountRows(
        Filter( MyCalendarEvents, 
            DateValue( Text( Start ) ) = DateAdd( _firstDayInView, ThisItem.Value, Days )
        )
    ) > 0 && !Subcircle.Visible && Title.Visible
    ```

    **원** 컨트롤이 표시 되는지 경우 합니다 **시작** 해당 셀의 날짜에 해당 하는 모든 이벤트에 대 한 필드 경우는 **제목** 컨트롤은 표시 경우에  **Subcircle** 컨트롤이 표시 되지 않습니다. 즉,이 날에 하나 이상의 이벤트가 발생 하 고이 선택 되지 않은 경우이 컨트롤이 표시 됩니다. 선택한 경우에 해당 날짜에 대 한 이벤트에 표시 됩니다는 **CalendarEventsGallery** 제어 합니다.

### <a name="subcircle-control-in-the-calendar-gallery"></a>달력 갤러리에서 subcircle 컨트롤

![MonthDayGallery Subcircle 컨트롤](media/calendar-screen/calendar-month-selected.png)

- 속성: **Visible**<br>
    값:

    ```powerapps-dot
    DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected && Title.Visible
    ```

  **Subcircle** 컨트롤을 표시할지  **\_dateSelected** 셀의 날짜에 해당 하는 및 **제목** 컨트롤이 표시 됩니다. 즉,이 컨트롤에 셀이 현재 선택 된 경우 표시 됩니다.

## <a name="events-gallery"></a>이벤트 갤러리

![CalendarEventsGallery 컨트롤](media/calendar-screen/calendar-events-gall.png)

- 속성: **항목**<br>
    값: 정렬 하 고 이벤트 갤러리를 필터링 하는 수식:

    ```powerapps-dot
    SortByColumns(
        Filter( MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = Text( _dateSelected, DateTimeFormat.ShortDate )
        ),
        "Start"
    )
    ```

   합니다 **MyCalendarEvents** 사이의 모든 이벤트를 포함 하는 컬렉션  **\_minDate** 하 고  **\_maxDate**합니다. 선택한 날짜에 대 한 이벤트를 표시 하려면 필터에 적용 됩니다 **MyCalendarEvents** 시작 날짜는 해당 하는 이벤트를 표시할 **\ _dateSelected**합니다. 항목이 다음 순서 대로 배치 하는 시작 날짜별으로 정렬 됩니다.

## <a name="next-steps"></a>다음 단계

- [이 화면에 자세히 알아보기](./calendar-screen-overview.md)
- [PowerApps에서 Office 365 Outlook 커넥터에 자세히 알아보기](../connections/connection-office365-outlook.md)
- [PowerApps에서 Office 365 사용자 커넥터에 자세히 알아보기](../connections/connection-office365-users.md)
