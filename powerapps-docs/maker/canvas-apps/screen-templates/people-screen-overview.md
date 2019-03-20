---
title: 사용자 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대 한 사용자 화면 템플릿의 작동 원리 및 고유한 사용 사례에 대 한 화면을 확장 하는 방법 이해
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
ms.openlocfilehash: 85da6f5414cc25d1145f0fa8910e8c78bfb74533
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459439"
---
# <a name="overview-of-the-people-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 사용자 화면 템플릿의 개요

캔버스 앱에서 사용자가 조직 내 사용자를 검색할 수 있는 사용자 화면을 추가 합니다. 사용자 수에 대 한 검색를 선택한 컬렉션에 사용자를 추가 합니다. 검색 결과 갤러리에 표시, 사용자 선택 항목을 사용 하 여 전자 메일 보내기 및 다른 사용자 지정 데이터 유형을 변경할 수 있습니다.

와 같은 Office 365에서 다양 한 데이터를 표시 하는 다른 템플릿 기반 화면을 추가할 수도 있습니다 [전자 메일](email-screen-overview.md), 사용자의 [달력](calendar-screen-overview.md), 및 [가용성](meeting-screen-overview.md) 사람의 사용자 수 모임에 초대 하려고 합니다.

이 개요에 설명 합니다.
> [!div class="checklist"]
> * 기본 사용자 화면을 사용 하는 방법입니다.
> * 화면을 수정 하는 방법.
> * 앱에 화면을 통합 하는 방법입니다.

이 화면의 기본 기능에 자세히에 대 한 참조를 [사용자 화면 참조](people-screen-reference.md)합니다.

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 사용자 화면을 추가:

1. [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps를 다음 앱을 만들거나 기존 앱을 PowerApps Studio 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 에 **홈** 선택 리본의 탭 **새 화면** > **사람들이**합니다.

    기본적으로 화면 다음과 비슷합니다.

    ![초기 사용자 상태 화면](media/people-screen/people-screen-empty.png)

1. 사용자에 대 한 검색을 시작 하려면 맨 위에 있는 텍스트 입력란을 선택 하 고 동료 직원의 이름을 입력 하기 시작 합니다. 검색 결과 텍스트 입력된 상자 아래에 나타납니다.

    ![사용자 화면 검색 상태](media/people-screen/people-browse-gall-full.png)

1. 에 추가 됩니다 검색 결과에서 개인을 선택 합니다 **MyPeople** 컬렉션입니다. 선택한 사용자의 컬렉션을 노출 검색 표시줄 입력된 값의 다시 설정 됩니다.

    ![사용자 화면 컬렉션 결과](media/people-screen/people-people-gall-full.png)

## <a name="modify-the-screen"></a>화면을 수정

이 화면에서 기본 기능을 수정할 수 있습니다 [사용자에 대 한 다양 한 데이터를 보여 주는](people-screen-overview.md#show-different-data-for-people)합니다.

추가 화면을 수정 하려는 경우 사용 합니다 [사용자 화면 참조](./people-screen-reference.md) 가이드로 합니다.

### <a name="show-different-data-for-people"></a>사용자에 대 한 다양 한 데이터를 표시 합니다.

이 화면을 사용 합니다 [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) 조직에서 사용자를 검색 하는 작업 새로운 각 이벤트에 표시에 대 한 추가 필드를 제공 합니다 **UserBrowseGallery** 제어 합니다. 갤러리에서 필드를 변경 하거나 추가 간단한 프로세스입니다.

1. 에 **UserBrowseGallery**, 수정 또는 추가 선택 되도록 하는 레이블을 선택 합니다.

1. 사용 하 여 해당 **텍스트** 속성을 선택 하 고 수식 입력줄에서 사용 하 여 내용을 바꾸기 `ThisItem.`

    IntelliSense에는 선택할 수 있는 필드의 목록을 보여 줍니다.

1. 원하는 필드를 선택 합니다.

    합니다 **텍스트** 속성을 업데이트 해야 `ThisItem.{FieldSelection}`합니다.

## <a name="integrate-the-screen-into-an-app"></a>화면을 앱에 통합

사용자 화면 자체 오른쪽에 있는 컨트롤의 강력한 번들 이지만 일반적으로 가장 큰, 더 다양 한 응용 프로그램의 일부로 수행 합니다. 다양 한 등의 방법으로 더 큰 앱에이 화면을 통합할 수 있습니다 [사람의 목록 캐시를 사용 하 여](people-screen-overview.md#use-your-cached-list-of-people)입니다.

### <a name="use-your-cached-list-of-people"></a>사용자는 캐시 된 목록 사용

사용자 화면에서 사용자 선택 항목을 캐시 합니다 **MyPeople** 컬렉션입니다. 사용자 조회에 대 한 비즈니스 시나리오를 호출 해야, 해야이 컬렉션을 사용 하는 방법을 알아야 합니다. 여기에서 과정을이 화면에서는 전자 메일 화면에 연결 및 사용자에 게 전자 메일을 보내는 방법 합니다 **MyPeople** 컬렉션입니다. 방법에 대 한 통찰력을 얻을 수도 [전자 메일 화면](./email-screen-overview.md) 작동 합니다.

1. Office 365 Outlook 데이터 소스를 선택 하 여 앱에 추가 합니다 **뷰** 탭을 선택 하 **데이터 원본** > **데이터 원본 추가**, 사무실 찾고 365 outlook 커넥터입니다. 선택 해야 할 수 있습니다 **새 연결** 찾을 수 있습니다.
1. 사용자 화면을 삽입 한 후 새 빈 화면을 삽입 합니다. 해당 화면 내에서 뒤로 화살표 아이콘을, 두 텍스트 입력 상자 및 보내기 아이콘을 추가 합니다.
1. 화면 이름 바꾸기 **EmailScreen**에 뒤로 화살표 아이콘 **BackIcon**, 한 텍스트 입력 상자 **SubjectLine**를 다른 **MessageBody**, 및를 보내기 아이콘 **SendIcon**합니다.
1. 설정 된 **OnSelect** 속성을 **BackIcon** 에 `Back()`입니다.
1. 설정 된 **OnSelect** 속성을 **SendIcon** 을 다음이 수식으로:

    ```powerapps-dot
    Office365.SendEmail( 
        Concat( MyPeople, UserPrincipalName & ";" ), 
        SubjectLine.Text, 
        MessageBody.Text 
    )
    ```
    
    여기에서는 Outlook 커넥터를 사용 하는 전자 메일을 보내려고 합니다. 전달 `Concat(MyPeople, UserPrincipalName & ";")` 으로 받는 사람 목록입니다. 이 수식은 모든에서 전자 메일 주소를 연결 합니다 **MyPeople** 세미콜론으로 구분 된 단일 문자열 컬렉션입니다. 즐겨 찾는 전자 메일 클라이언트의 "To" 줄에 세미콜론으로 구분 된 전자 메일 주소 문자열을 작성 하는 데 다르지 않습니다.
    * 전달 `SubjectLine.Text` 메시지의 제목으로 및 `MessageBody.Text` 메시지의 본문으로 합니다.
1. 사용자 화면 오른쪽 위 모서리에서 삽입 된 **메일** 아이콘입니다.
   적합 한 항목을 아이콘 색을 변경 합니다.
1. 설정 합니다 **OnSelect** 의 속성을 **SendIcon** 에 `Navigate( EmailScreen, None )`.

    이제는 사용자, 작성, 전자 메일 메시지를 선택한 다음 보냅니다 두 화면 앱을 해야 합니다. 모든 사용자에 게는 앱이 전송 이메일 조심 해야 하지만, 테스트를 자유롭게 추가할 합니다 **MyPeople** 컬렉션입니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대 한 참조 설명서](./people-screen-reference.md)합니다.
* [Office 365 Outlook 커넥터에 자세히 알아보려면](../connections/connection-office365-outlook.md)합니다.
* [Office 365 사용자 커넥터에 자세히 알아보려면](../connections/connection-office365-users.md)합니다.
