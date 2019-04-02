---
title: 캔버스 앱에 대한 일정 화면 템플릿에 대한 참조 | Microsoft Docs
description: PowerApps의 캔버스 앱에 대한 일정 화면 템플릿을 작동 하는 방법의 세부 정보를 이해 합니다.
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
# <a name="reference-information-about-the-calendar-screen-template-for-canvas-apps"></a>캔버스 앱에 대한 일정 화면 템플릿에 대한 참조 정보

PowerApps의 캔버스 앱에 대한 일정 화면 템플릿의 각 중요한 컨트롤이 화면의 전체 기본 기능에 기여 하는 방법을 이해 합니다. 이 깊이 있는 정보는 컨트롤이 사용자 입력에 응답 하는 방법을 결정 하는 다른 속성의 값과 동작 수식을 표시합니다. 이 화면의 기본 기능의 간략한 설명에 대해서는 [일정 화면 개요](calendar-screen-overview.md)를 참조합니다.

이 항목에서는 몇 가지 중요 한컨트롤을 강조 표시 하 고 각 컨트롤의 다양한 속성(**Items**와 **OnSelect** 같은)에 설정하는 수식 또는 식을 설명합니다.

- [달력 드롭다운 (dropdownCalendarSelection)](#calendar-drop-down)
- [달력 아이콘 (iconCalendar)](#calendar-icon)
- [이전 달 펼침 단추 (iconPrevMonth)](#previous-month-chevron)
- [다음 달 펼침 단추 (iconNextMonth)](#next-month-chevron)
- [달력 갤러리 (MonthDayGallery) (+ 자식 컨트롤)](#calendar-gallery)
- [이벤트 갤러리 (CalendarEventsGallery)](#events-gallery)

## <a name="prerequisite"></a>필수 조건

[PowerApps에서 앱을 만들어](../data-platform-create-app-scratch.md) 화면 및 기타 컨트롤을 추가하고 구성하는 방법에 친숙합니다.

## <a name="calendar-drop-down"></a>달력 드롭다운 

![dropdownCalendarSelection 컨트롤](media/calendar-screen/calendar-dropdown.png)

- 속성: **Items**<br>
    값: `Office365.CalendarGetTables().value`

    이 값은 앱 사용자의 Outlook 일정을 검색 하는 커넥터 작업입니다. 이 작업이 검색 하는 [값](https://docs.microsoft.com/connectors/office365/#entitylistresponse[table])을 확인할 수 있습니다.

- 속성: **OnChange**<br>값: `Select(dropdownCalendarSelection)`

    사용자가 목록에서 옵션을 선택 하는 경우  컨트롤의 **OnSelect** 속성의 함수가 실행됩니다.

- 속성: **OnSelect**<br>
    값: 다음 코드 블록에 나타나는 **If** 함수 및 그 후 코드 블록에 표시 되는 여러 추가 함수입니다.

   사용자가 앱을 연 후 드롭다운 목록에서 옵션을 선택한 처음에만 구동되는 수식의 일부입니다.:

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
    
  - **\_userDomain**: 사용자의 전자 메일 주소에 반영 되어 있는 앱 사용자의 회사 도메인입니다.
  - **\_dateSelected**: 기본적으로 현재 날짜입니다. 달력 갤러리가 이 날짜를 강조 하 고 해당 날짜에 예약 된 이벤트가 이벤트 갤러리에 표시 됩니다.
  - **\_firstDayOfMonth**: 현재 달의 첫 번째 날입니다. `(Today + (1 - Today)) = Today - Today + 1 = 1` 때문에 **DateAdd** 함수는 항상 해당 월의 첫 번째 날을 반환 합니다.
  - **\_firstDayInView**: 달력 갤러리를 표시할 수 있는 첫 번째 날입니다. 이 값은 월이 일요일에 시작 하지 않는다면 월의 첫날과는 다릅니다. 이전 월의 주를 표시 하지 않으려면  **\_firstDayInView** 값은 `_firstDayOfMonth - Weekday(_firstDayOfMonth) + 1` 입니다.
  - **\_lastDayOfMonth**: 다음 달의 첫날에서 하루를 뺀 현재 월의 마지막 날입니다.

   **If** 함수 이후 함수는 일정 드롭 다운 목록에서 옵션을 선택할 때마다(사용자가 앱을 열때 처음만이 아닌) 실행됩니다:

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

    - **\_calendarVisible**: 새 선택이 로드 되는 동안 달력이 나타나지 않도록 **false**로 설정 합니다.
    - **\_showLoading**: 새 선택이 로드 하는 동안 로딩 표시기를 표시 되도록 **true**로 설정 합니다.
    - **\_myCalendar**: 올바른 일정에서 이벤트를 검색하도록 **일정 드롭다운** 컨트롤의 현재 값으로 설정 합니다.
    - **\_minDate**: **\_firstDayInView** 와 동일한 값으로 설정합니다. 이 변수는 이미 Outlook에서 검색 되고 앱에서 캐시된 이벤트를 결정 합니다.
    - **\_maxDate**: 일정에서 볼 수 있는 마지막 날을 설정 합니다. 수식은 `_firstDayInView + 40`합니다. 일정의 경우 최대 41 일을 표시 하므로  **\_maxDate** 변수에서 항상 볼 수 있는 마지막 날을 반영 하고 이미 Outlook에서 검색 되고 앱에서 캐시된 이벤트를 결정 합니다.
    - **MyCalendarEvents**:  **\_minDate**에서  **\_maxDate**까지 범위로 선택된 달력에서 사용자의 이벤트들 컬렉션으로 설정 합니다.
    - **\_showLoading**: **false**로 설정합니다;  모두 로드되면 **\_calendarVisible**을 **true**로 설정 합니다.

## <a name="calendar-icon"></a>달력 아이콘

![iconCalendar 컨트롤](media/calendar-screen/calendar-today-icon.png)

- 속성: **OnSelect**<br>
    값: 오늘 날짜로 일정 갤러리를 다시 설정 하는 4가지 **Set**함수 입니다:

    ```powerapps-dot
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days) );
    Set( _firstDayInView, DateAdd(_firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days));
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )
    ```

    앞의 코드는 적절 한 달력 보기를 표시 하는 데 필요한 모든 날짜 변수를 다시 설정 합니다.

    - **\_dateSelected** 오늘로 다시 설정 됩니다.
    - **\_firstDayOfMonth** 현재 월의 첫째 날로 다시 설정 됩니다.
    - **\_firstDayInView** 현재 월을 선택한 경우 볼 수 있는 첫 번째 날로 다시 설정 됩니다.
    - **\_lastDayOfMonth** 현재 월의 마지막 날짜로 다시 설정 됩니다.

    이 항목의 [ **달력 드롭 다운** ](#calendar-drop-down) 섹션에서는 이러한 변수를 자세히 설명 합니다.

## <a name="previous-month-chevron"></a>이전 달 펼침 단추

![iconPrevMonth 컨트롤](media/calendar-screen/calendar-back.png)

- 속성: **OnSelect**<br>값: 달력 갤러리에 이전 달을 표시 하는 4가지 **Set** 함수 및 **If**함수입니다:

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
    > **\_firstDayOfMonth**, **\_firstDayInView** 및 **\_lastDayOfMonth**에 대한 정의는 이 항목의 [달력 드롭다운](#calendar-drop-down) 섹션과 거의 일치 합니다.

    앞의 코드의 첫 세 줄은 이전 달 펼침 단추를 선택할 때마다 실행 합니다. 코드는 적절한 달력 보기를 표시 하는 데 필요한 변수를 설정 합니다. 나머지 코드는 사용자가 선택한 일정에 대해 이번 달 이전을 선택하지 않은 경우에 실행 됩니다.

    이 경우  **\_minDate**는 이전 달이 표시 되면 나타나는 1 일입니다. 사용자가 아이콘을 선택 하기 전에  **\_minDate**는 현재 달 23일의 가능한 최소 값입니다. (3월 1일이 토요일이면, 3월의 **\_firstDayInView**는 2 월 23.) 즉, 사용자가 이번 달에 아직 선택 하지 않은 경우  **\_minDate**가 **\_firstDayOfMonth**보다 크면, 및 **If** 함수는 **true**를 반환합니다. 코드가 실행되고 컬렉션 및 변수가 업데이트 됩니다.

    - **MyCalendarEvents**는 선택한 일정에서 [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) 작업으로 이벤트를 검색 합니다. 날짜 범위는 **\_firstDayInView** 날짜에서  **\_minDate** -1 까지입니다. **MyCalendarEvents**는 이미 **\_minDate**에 이벤트를 포함하고 있기 때문에, 새 날짜 범위에서의 최대값을 위해 해당 날짜에서 1을 뺍니다.

    - **\_minDate**는 검색된 이벤트의 첫 번째 날짜 이기 때문에 현재 **\_firstDayInView**로 설정됩니다. 사용자가 이전 달 펼침 단추를 선택 하여 이 날짜를 반환 하는 경우, **If** 함수에서 **false**를 반환합니다;이 보기에 대한 이벤트에 이미 **MyCalendarEvents**에 캐시 되므로 코드를 실행 하지 않습니다.

## <a name="next-month-chevron"></a>다음 달 펼침 단추

![iconNextMonth 컨트롤](media/calendar-screen/calendar-forward.png)

- 속성: **OnSelect**<br>
    값: 달력 갤러리에 다음 달을 표시 하는 4가지 **Set** 함수 및 **If**함수입니다:

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
    > **\_firstDayOfMonth**, **\_firstDayInView** 및 **\_lastDayOfMonth**에 대한 정의는 이 항목의 [달력 드롭다운](#calendar-drop-down) 섹션과 거의 일치 합니다.

    사용자가 다음 월 펼침 단추를 선택할 때 실행되는 앞의 코드의 첫 세 줄은 적절 한 달력 보기를 표시 하는 데 필요한 변수를 설정 합니다. 나머지 코드는 사용자가 선택한 일정에 대해 이번 달 이전을 선택하지 않은 경우에 실행 됩니다.

    이 경우  **\_maxDate**은 이전 달이 표시 될때 나타나는 마지막 날짜입니다. 사용자가 다음 월 펼침 단추를 선택 하기 전에  **\_maxDate**는 다음 달 13일의 가능한 최대 값입니다. (비-윤년 2월 1일이 일요일이면, **\_maxDate**는 **\_firstDayInView** + 40일인 3월 13일입니다.) 즉, 사용자가 이번 달에 아직 선택 하지 않은 경우  **\_maxDate**가 **\_lastDayOfMonth** 보다 크면, **If** 함수는 **true**를 반환 합니다. 코드가 실행되고 컬렉션 및 변수가 업데이트 됩니다.

    - **MyCalendarEvents**는 선택한 일정에서 [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) 작업으로 이벤트를 검색 합니다. 날짜 범위는 **\_maxDate** + 1일에서  **\_firstDayInView** + 40일까지 입니다. 때문에 **MyCalendarEvents**는 이미 **\_minDate**에 이벤트를 포함하고 있기 때문에, 새 날짜 범위의 최소값을 위해 해당 날짜에 1이 추가 됩니다. **\_firstDayInView** + 40는 **\_maxDate**를 위한 수식이므로 범위의 두 번째 날짜는 단지 새 **\_maxDate**가 됩니다.

    - **\_maxDate**는 검색된 이벤트가 어제이기 때문에 **\_firstDayInView** + 40일로 설정됩니다. 용자가 다음 달 펼침 단추를 선택 하여 이 날짜를 반환 하는 경우, **If** 함수에서 **false**를 반환합니다;이 보기에 대한 이벤트에 이미 **MyCalendarEvents**에 캐시 되므로 코드를 실행 하지 않습니다.

## <a name="calendar-gallery"></a>달력 갤러리

![MonthDayGallery 컨트롤](media/calendar-screen/calendar-month-gall.png)

- 속성: **Items**<br>
    값: `[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,
    20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41]`
  
  최악의 시나리오에서 일정 보기는 42 전체 일을 표시 해야 하기 때문에 달력 갤러리의 항목에 0부터 41 집합이 사용 됩니다. 이 달의 첫 번째가 토요일에 나타나고 해당 월의 마지막이 일요일에 나타나는 경우 발생 합니다. 이 경우 달력은 월의 첫 번째를 포함 하는 이전 월 6일을 표시하고 월의 마지막이 포함 된 다음 달부터 6일을 보여 줍니다. 이것은 42개의 고유한 값이고 그중 30은 선택한 월을 위한 것입니다.

- 속성: **WrapCount**<br>
    값: `7`

  이 값은 7일 주를 반영 합니다.

### <a name="title-control-in-the-calendar-gallery"></a>달력 갤러리에서 제목 컨트롤

![MonthDayGallery 제목 컨트롤](media/calendar-screen/calendar-month-text.png)

- 속성: **Text**<br>
    값: `Day( DateAdd( _firstDayInView, ThisItem.Value, Days ) )`

    이전에 설명한 대로 **\_firstDayInView**은 (**\_firstDayOfMonth** -해당 요일 값) + 1로 정의 됩니다. 이것은 **\_firstDayInView**은 항상 일요일, **\_firstDayOfMonth**는 항상 **MonthDayGallery**의 첫 번째 행을 의미합니다. 이러한 두 가지 사실로, **\_firstDayInView**는 항상  **MonthDayGallery**의 첫 번째 셀이 됩니다. **ThisItem.Value**는 **MonthDayGallery** Item 속성에서 그 셀의 수입니다. 따라서  **\_firstDayInView** 시작 지점으로 잡으면, 각 셀은 각각의 셀 값으로**\_firstDayInView** +의 증가값을 표시 합니다.

- 속성: **Fill**<br>
    값: 하나의 **If** 함수:

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

 **텍스트** 속성의 설명에 논의된 대로, `DateAdd(_firstDayInView, ThisItem.Value)`는 표시 셀에서 일자를 나타냅니다. 이 점을 감안하여, 앞의 코드는 이러한 비교를 수행 합니다.
  1. 셀의 값이 오늘 날짜 이고 이 셀이 **\_dateSelected**과 동등한 경우, 채우기 값을 제공 하지 않습니다.
  1. 셀의 값이 오늘 날짜 이지만 **\_dateSelected**과 동등하지 않은 경우, **ColorFade** 채우기를 제공합니다.
  1. 마지막은 비교 하지 않습니다. 셀의 실제 텍스트 값과 셀 항목의 값(화면 수 및 항목 수)을 비교 합니다.<br>

      더 잘 이해하기 위해, 토요일에 시작되고 일요일에 끝나는 2018 년 9월을 예로 듭니다. 이 경우, 달력은 첫 번째 행에서 9월 1일과 8월 26일에서 31일까지를 표시하고 9월 1일까지는 `Abs(Title.Text - ThisItem.Value) = 26`이 됩니다. 그런 다음 `Abs(Title.Text - ThisItem.Value) = 5`이 됩니다. 9월 30일과 10월 1일에서 6일까지 표시하는 달력의 마지막 행까지 5가 계속 유지 됩니다. 9월 30일까지 `Abs(Title.Text - ThisItem.Value)`는 5가 되지만 10월에는 35가 됩니다.<br>

      이것은 패턴입니다: 이전 달의 표시 된 날짜에 대해서는, `Abs(Title.Text - ThisItem.Value)`는 표시된 첫 번째의 `Title.Text` 와 항상 동일합니다. 다음 달에 표시 되는 날짜에 대해서는, `Abs(Title.Text - ThisItem.Value)`는 그 달의 첫째 셀(이 경우, 10월 1일)에서 1을 뺀 **MonthDayGallery** 항목 값과 항상 동일합니다. 그리고 가장 중요한 현재 선택된 월에 표시 된 날짜에 대해서는, `Abs(Title.Text - ThisItem.Value)` 는 그 달의 첫 번째 항목의 값에서 1을 뺀 값과 항상 동일하며 이전 예제와 같이 5를 초과할 수 없습니다. 그래서 `Abs(Title.Text - ThisItem.Value) > 5`가 수식으로 완벽하게 유효합니다.

      이 구문은 현재 날짜 값이 선택한 월을 벗어났는지 여부를 확인 합니다. 그 경우 **Fill**은 부분적으로 불투명 회색으로 표시 됩니다.

    > [!NOTE]
    > 갤러리에 **레이블을** 컨트롤을 추가하고 Text 속성에 해당 값을 설정하여 마지막 비교의 유효성을 검사할 수 있습니다:<br>`Abs(Title.Text - ThisItem.Value)`

- 속성: **Visible**<br>
    값:

    ```powerapps-dot
    !(
        DateAdd( _firstDayInView, ThisItem.Value, Days ) - 
            Weekday( DateAdd( _firstDayInView, ThisItem.Value,Days ) ) + 1 
        > _lastDayOfMonth
    )
    ```

    위의 구문에서 셀이 현재 선택 된 월의 일자에 없는 행에 있는지 여부를 확인 합니다. 날짜 값에서 날짜의 요일 값을 차감 하 고 항상 1을 더하면 유효한 날의 행에서 첫 번째 항목을 반환하게 됩니다. 따라서 이 구문은 행의 첫 번째 날이 보기 가능한 월의 마지막 날 이후 인지 여부를 확인 합니다. 이 경우,  전체 행이 다음 월의 일을포함하므로 표시 되지 않습니다.

- 속성: **OnSelect**<br>
    값: **\_dateSelected** 변수에 선택된 셀의 날짜을 설정하는 **Set** 함수입니다:

    ```powerapps-dot
    Set( _dateSelected, DateAdd( _firstDayInView, ThisItem.Value, Days ) )
    ```

### <a name="circle-control-in-the-calendar-gallery"></a>달력 갤러리에서 원 컨트롤

![MonthDayGallery 원 컨트롤](media/calendar-screen/calendar-month-event.png)

- 속성: **Visible**<br>
    값: 선택한 날짜에 대해 어떤 이벤트가 예약되었는지와 Subcircle, Title 컨트롤이 표시되는지 여부를 결정하는 수식입니다.

    ```powerapps-dot
    CountRows(
        Filter( MyCalendarEvents, 
            DateValue( Text( Start ) ) = DateAdd( _firstDayInView, ThisItem.Value, Days )
        )
    ) > 0 && !Subcircle.Visible && Title.Visible
    ```

    해당 셀의 날짜가 어떤 이벤트의 **시작** 필드와 동일하며, **Title** 컨트롤이 표시되고 **Subcircle** 컨트롤이 표시되지 않는 경우 **Circle** 컨트롤이 표시 됩니다. 즉,이 날에 하나 이상의 이벤트가 발생 하고, 선택 되지 않은 경우에는 컨트롤이 표시 됩니다. 선택된다면, 해당 날짜에 대한 이벤트는  **CalendarEventsGallery** 컨트롤에 표시됩니다.

### <a name="subcircle-control-in-the-calendar-gallery"></a>달력 갤러리에서 subcircle 컨트롤

![MonthDayGallery Subcircle 컨트롤](media/calendar-screen/calendar-month-selected.png)

- 속성: **Visible**<br>
    값:

    ```powerapps-dot
    DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected && Title.Visible
    ```

  **Subcircle** 컨트롤은 **\_dateSelected**와 셀의 날짜가 동일하며 **Title** 컨트롤이 표시되는 경우 표시 됩니다. 즉, 이 컨트롤은 셀이 현재 선택 된 경우 표시 됩니다.

## <a name="events-gallery"></a>이벤트 갤러리

![CalendarEventsGallery 컨트롤](media/calendar-screen/calendar-events-gall.png)

- 속성: **Items**<br>
    값: 이벤트 갤러리를 정렬하고 필터링 하는 수식입니다:

    ```powerapps-dot
    SortByColumns(
        Filter( MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = Text( _dateSelected, DateTimeFormat.ShortDate )
        ),
        "Start"
    )
    ```

   **MyCalendarEvents** 컬렉션은 **\_minDate**와 **\_maxDate** 사이의 모든 이벤트를 포함 합니다. 선택한 날짜에 대한 이벤트를 표시하려면 시작 날짜가 **\_dateSelected** 와 동일한 이벤트를 표시하기 위해 **MyCalendarEvents**에 필터가 적용됩니다. 항목들은 순서 대로 배치하기 위해 시작 날짜별로 정렬 됩니다.

## <a name="next-steps"></a>다음 단계

- [이 화면에 자세히 알아보기](./calendar-screen-overview.md)
- [PowerApps에서 Office 365 Outlook 커넥터에 자세히 알아보기](../connections/connection-office365-outlook.md)
- [PowerApps에서 Office 365 사용자 커넥터에 자세히 알아보기](../connections/connection-office365-users.md)
