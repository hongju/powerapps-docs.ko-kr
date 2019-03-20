---
title: 모임 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대 한 모임 화면 템플릿의 작동 방식을 이해 하 고 고유한 사용 사례에 대 한 화면 확장
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 24f04ff9ce95f603f5f7d4dc7d217146b9eebef8
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459413"
---
# <a name="overview-of-the-meeting-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 모임 화면 템플릿의 개요

캔버스 앱에서 사용자가 만들고 해당 Office 365 Outlook 계정에서 모임 요청을 보낼 수 있는 회의 화면을 추가 합니다. 사용자는 자신의 조직에서 참가자에 대 한 검색 하 고 외부 전자 메일 주소를 추가할 수 있습니다. 테 넌 트 회의실을 Outlook에 작성에 위치를 선택할 수 있습니다.

와 같은 Office 365에서 다양 한 데이터를 표시 하는 다른 템플릿 기반 화면을 추가할 수도 있습니다 [전자 메일](email-screen-overview.md)를 [사람들이](people-screen-overview.md) 조직에 사용자의 [달력](calendar-screen-overview.md)합니다.

이 개요 화면의 고급 기능에 설명 합니다.

이 화면의 기본 기능에 자세히에 대 한 참조를 [모임 화면 참조](meeting-screen-reference.md)합니다.

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 모임 화면을 추가:

1. [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps를 다음 앱을 만들거나 기존 앱을 PowerApps Studio 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 에 **홈** 선택 리본의 탭 **새 화면** > **모임**합니다.

  를 입력 한 모임 화면의 두 탭이 유사 합니다.

  ![모임 화면에서 두 탭](media/meeting-screen/meeting-screen-full-both.png)

몇 가지 유용한 참고 사항:

* 모임 화면에는 앱 사용자를 Outlook에서 모임을 만들 수 있습니다.
  사용자 및 참가자를 추가 하, 필요 회의실 회의를 추가 하는 것입니다.
* 조직에서 사용자를 검색 하려면 "참가자" 아래에 있는 텍스트 입력 상자에 해당 이름을 입력을 시작 합니다.
* 사용자를 검색 하는 경우 상위 15 결과만 반환 됩니다.
* 조직 외부 참가자에 대 한 전자 메일 주소를 추가 하려면 전체, 유효한 메일 주소를 입력 하 고 전자 메일 주소의 오른쪽에 표시 되는 '+' 아이콘을 선택 합니다.
* 회의 만들려면 참석자로 한 명 이상의 사용자를 추가, 제목을 제공 하며 회의 시간을 선택 합니다 **일정** 탭 합니다.
* 모임 요청을 보내면 해당 모임에 대 한 모든 정보가 지워집니다.
* 합니다 **OnSelect** 보내기 아이콘 (오른쪽 위 모서리)의 문은이 수식을 포함 합니다.
    ```powerapps-dot
    Set( _myCalendarName, 
        LookUp( 'Office365'.CalendarGetTables().value, DisplayName = "Calendar" ).Name 
    );
    ```
* "일정" 대부분의 Office 사용자의 일정에 대 한 기본 표시 이름을 이지만 조직 다를 수 있습니다. 그렇다면 조직에 대 한 적절 한 용어에 "일정"을 변경할 수 있습니다.
* 과거에 발생 하는 회의 예약 하려고 시도 하면 오류가 발생 하거나 모임에 20 개가 넘는 사용자를 추가 합니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대 한 참조 설명서](./meeting-screen-reference.md)합니다.
* [Office 365 Outlook 커넥터에 자세히 알아보려면](../connections/connection-office365-outlook.md)합니다.
* [Office 365 사용자 커넥터에 자세히 알아보려면](../connections/connection-office365-users.md)합니다.
