---
title: 모임 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대한 모임 화면 템플릿의 작동 방식을 이해하고 고유한 사용 사례에 대한 화면 확장
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
# <a name="overview-of-the-meeting-screen-template-for-canvas-apps"></a>캔버스 앱에 대한 모임 화면 템플릿의 개요

캔버스 앱에서 사용자가 해당 Office 365 Outlook 계정에서 모임 요청을 만들고 보낼 수 있는 모임 화면을 추가합니다. 사용자는 자신의 조직에서 참석자를 검색하고 외부 전자 메일 주소를 추가할 수 있습니다. Outlook에서 만든 회의실이 테넌트에 있는 경우, 위치를 선택할 수 있습니다.

[전자 메일](email-screen-overview.md), 조직의 [사람들](people-screen-overview.md) 및 사용자의 [일정](calendar-screen-overview.md)과 같은 다양한 데이터를 표시하는 다른 템플릿 기반 화면을 Office 365에서 추가할 수도 있습니다.

개요에서는 화면의 높은 수준 기능에 대해 설명합니다.

이 화면의 기본 기능에 자세한 내용은 [모임 화면 참조](meeting-screen-reference.md)에서 확인합니다.

## <a name="prerequisite"></a>필수 조건

[PowerApps에서 앱을 만들어](../data-platform-create-app-scratch.md) 화면 및 기타 컨트롤을 추가하고 구성하는 방법에 친숙합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 모임 화면을 추가:

1. PowerApps에 [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)한 다음 PowerApps Studio에서 앱을 만들거나 기존 앱을 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 리본의 **홈** 탭에서 **새 화면** > **모임**을 선택합니다.

  값을 채우면, 모임 화면의 두 탭은 다음과 유사합니다.

  ![모임 화면에서 두 탭](media/meeting-screen/meeting-screen-full-both.png)

몇 가지 유용한 참고 사항:

* 모임 화면에서 앱 사용자가 Outlook에서 모임을 만들 수 있습니다.
  사용자는 참석자를 검색하여 추가하고 필요 시 모임에 회의실을 추가할 수도 있습니다.
* 조직의 사용자를 검색 하려면 "참석자" 아래에 있는 텍스트 입력 상자에 해당 이름을 입력합니다.
* 사용자를 검색 하는 경우 상위 15 결과만 반환 됩니다.
* 조직 외부 참석자에 대한 전자 메일 주소를 추가하려면, 전체 유효한 메일 주소를 입력하고 전자 메일 주소의 오른쪽에 표시되는 '+' 아이콘을 선택합니다.
* 모임을 만들려면, 최소한 한 명 이상의 참석자를 추가해야 하고, 제목을 제공해야 하며 **일정** 탭에서 모임 시간을 선택해야 합니다.
* 모임 요청을 보내면, 해당 모임에 대한 모든 정보가 지워집니다.
* 보내기 아이콘(오른쪽 위 모서리)의 **OnSelect** 구문은 다음 수식을 포함합니다.
    ```powerapps-dot
    Set( _myCalendarName, 
        LookUp( 'Office365'.CalendarGetTables().value, DisplayName = "Calendar" ).Name 
    );
    ```
* 대부분의 Office 사용자의 일정에 대한 기본 표시 이름이 "일정"이지만, 조직에 따라 다를 수 있습니다. 그렇다면 "일정"을 해당 조직에 적절한 용어로 변경할 수 있습니다.
* 과거 시점의 회의를 예약하려고 하거나 모임에 20명이 넘는 사용자를 추가하려고 하면 오류가 발생합니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대한 참조 설명서](./meeting-screen-reference.md)를 봅니다.
* [Office 365 Outlook 커넥터에 대해 자세히 알아봅니다.](../connections/connection-office365-outlook.md)
* [Office 365 사용자 커넥터에 대해 자세히 알아봅니다.](../connections/connection-office365-users.md)
