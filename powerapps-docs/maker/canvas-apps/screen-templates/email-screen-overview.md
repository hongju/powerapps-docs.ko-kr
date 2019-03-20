---
title: 전자 메일 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대 한 전자 메일 화면 템플릿의 작동 방식을 이해 하 고 고유한 사용 사례에 대 한 화면 확장
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/29/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a1aad5ca9e8c7f8b55b1645b04d6c8dc0b9c707b
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459554"
---
# <a name="overview-of-the-email-screen-template-for-canvas-apps"></a>캔버스 앱에 대 한 전자 메일-화면 템플릿 개요

캔버스 앱에서 사용자가 Office 365 Outlook 계정에서 전자 메일을 보낼 수 있는 전자 메일 화면을 추가 합니다. 사용자가 해당 조직에서 받는 사람에 게 검색 하 고도 외부 전자 메일 주소를 추가 합니다. 이미지-첨부 파일 지원을 추가 하 고, 검색 갤러리에 표시 되는 사용자 데이터를 변경 하 고, 다른 사용자 지정을 만들 수 있습니다.

예: 사용자의 Office 365에서 다른 데이터를 표시 하는 다른 템플릿 기반 화면을 추가할 수도 있습니다 [달력](calendar-screen-overview.md), [사람들이](people-screen-overview.md) 조직에서와 [가용성](meeting-screen-overview.md) 의 사람들이 사용자 회의를 초대 하려고 할 수 있습니다.

이 개요에 설명 합니다.
> [!div class="checklist"]
> * 기본 전자 메일 화면을 사용 하는 방법입니다.
> * 수정 하는 방법.
> * 앱에 통합 하는 방법.

이 화면의 기본 기능에 자세히에 대 한 참조를 [전자 메일 화면 참조](email-screen-reference.md)합니다.

## <a name="prerequisite"></a>필수 조건

추가할 때 화면 및 기타 컨트롤을 구성 하는 방법 익히는 [PowerApps에서 앱을 만드는](../data-platform-create-app-scratch.md)합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 전자 메일 화면을 추가:

1. [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps를 다음 앱을 만들거나 기존 앱을 PowerApps Studio 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 에 **홈** 선택 리본의 탭 **새 화면** > **메일**합니다.

    기본적으로 화면 다음과 비슷합니다.

    ![전자 메일 화면](media/email-screen/email-screen-full.png)

몇 가지 유용한 참고 사항:

* 조직에서 사용자를 검색 하려면 해당 이름을 "To" 아래에 있는 텍스트 입력된 상자에 입력을 시작 합니다.
* 사용자를 검색할 때 상위 15 결과만 반환 됩니다.
* 조직 외부 전자 메일 받는 사람에 게 전자 메일 주소를 추가 하려면 전체, 유효한 메일 주소를 입력 하 고의 오른쪽에 표시 되는 '+' 아이콘을 선택 합니다.
* 명 이상의 받는 사람으로 추가 하 고 전자 메일을 보내려면 제목을 입력 해야 합니다.
* 전자 메일을 보내면 받는 사람 목록 뿐만 아니라 제목 줄 및 메시지 본문의 내용은 모두 삭제 됩니다.

## <a name="modify-the-screen"></a>화면을 수정

몇 가지 일반적인 방법으로이 화면의 기본 기능을 수정할 수 있습니다.

* [이미지-첨부 파일 지원 추가](email-screen-overview.md#add-image-attachment-support)
* [사용자에 대 한 다양 한 데이터를 표시 합니다.](email-screen-overview.md#show-different-data-for-people)

추가 화면을 수정 하려는 경우 사용 합니다 [전자 메일 화면 참조](./email-screen-reference.md) 가이드로 합니다.

> [!IMPORTANT]
> 다음 단계는 하나의 전자 메일 화면 앱을 추가한 것을 가정 합니다. 둘 이상 컨트롤 이름을 추가한 경우 (같은 **iconMail1**) 다른 숫자를 사용 하 여 종료 되 고 수식을 적절 하 게 조정 해야 합니다.

### <a name="add-image-attachment-support"></a>이미지-첨부 파일 지원 추가

이 전자 메일을 사용 하 여 단일 이미지를 첨부 파일로 보낼 수가 있습니다.

1. 에 **삽입** 탭을 선택 **Media**를 선택한 후 **그림 추가**합니다.
1. 새 컨트롤의 **Y** 속성을이 식:

    `TextEmailMessage1.Y + TextEmailMessage1.Height + 20`
    
1. 사용 하 여 합니다 **AddMediaWithImage** 컨트롤이 삽입, 210 보다 작은 수를 높이 설정 합니다.
1. 컨트롤 트리 보기에서 선택 **AddMediaWithImage** > **...**   >  **순서** > **맨 뒤로 보내기**합니다.
   컨트롤의 앞에 위치한에서 이렇게 합니다 **PeopleBrowseGallery** 제어 합니다.
1. 변경 된 **높이** 속성을 **EmailPeopleGallery** 을 다음이 수식으로:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery1.TemplateHeight + EmailPeopleGallery1.TemplatePadding * 2 ) *
            RoundUp( CountRows( EmailPeopleGallery1.AllItems ) / 2, 0 ), 
        304
    )
    ```

1. 설정 된 **ShowScrollbar** 속성을 **EmailPeopleGallery** 이 식:

    ```EmailPeopleGallery1.Height >= 304```
    
    이 푸시에서 최대 높이 방지 합니다 **AddMediaWithImage** 제어 페이지 해제 합니다.
    
1. 변경 된 **OnSelect** 의 속성을 **iconMail** 컨트롤을 다음이 수식으로:

    ```powerapps-dot
    Set( _emailRecipientString, Concat(MyPeople, Mail & ";") );
    If( IsBlank( UploadedImage1 ),
        'Office365'.SendEmail( _emailRecipientString, 
            TextEmailSubject1.Text, 
            TextEmailMessage1.Text, 
            { Importance: "Normal" }
        ),
        'Office365'.SendEmail( _emailRecipientString, 
            TextEmailSubject1.Text, 
            TextEmailMessage1.Text, 
            {
                Importance: "Normal",
                Attachments: Table(
                    {
                        Name: "Image.jpg", 
                        ContentBytes: UploadedImage1.Image
                    }
                )
            }
        )
    );
    Reset( TextEmailSubject1 );
    Reset( TextEmailMessage1 );
    Reset( AddMediaButton1 );
    Clear( MyPeople )
    ```
    
    이 수식은 업로드 된 이미지를 확인합니다. 없는 경우 다음 사용 하 여 동일한 `Office365.SendEmail` 이전과 같이 작업 합니다. 이미지의 경우 첨부 파일 테이블의 첨부 파일로 추가 됩니다.
    추가 전자 메일을 보낸 후 **재설정** 작업이 수행 됩니다 **AddMediaButton** 업로드 된 이미지를 제거 합니다.
> [!NOTE]
> 둘 이상의 전자 메일 첨부를 추가 하려면 첨부 파일 테이블에 레코드를 추가 합니다.

### <a name="show-different-data-for-people"></a>사용자에 대 한 다양 한 데이터를 표시 합니다.

이 화면을 사용 합니다 [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) 조직에서 사용자를 검색 하는 작업 새로운 각 이벤트에 표시에 대 한 추가 필드를 제공 합니다 **PeopleBrowseGallery** 제어 합니다. 갤러리에서 필드를 변경 하거나 추가 간단 합니다.

1. 에 **PeopleBrowseGallery** 제어, 수정 또는 추가 선택 되도록 하는 레이블을 선택 합니다.

1. 사용 하 여 해당 **텍스트** 속성을 선택 하 고 수식 입력줄에서 사용 하 여 내용을 바꾸기 `ThisItem.`

    IntelliSense에는 선택할 수 있는 필드의 목록을 보여 줍니다.

1. 원하는 필드를 선택 합니다.

    합니다 **텍스트** 속성을 업데이트 `ThisItem.{FieldSelection}`합니다.

## <a name="integrate-the-screen-into-an-app"></a>화면을 앱에 통합

전자 메일 화면 자체 오른쪽에 있는 컨트롤의 강력한 번들 이지만 일반적으로 가장 큰, 더 다양 한 응용 프로그램의 일부로 수행 합니다. 다양 한 등의 방법으로 더 큰 앱에이 화면을 통합할 수 있습니다 [일정 화면을 연결할](email-screen-overview.md#linking-to-the-calendar-screen)합니다.

### <a name="linking-to-the-calendar-screen"></a>일정 화면에 연결

"이벤트 참석자 표시" 섹션에 설명 된 단계를 수행 [달력 화면 개요](./calendar-screen-overview.md#show-event-attendees) 그러나 마지막 단계를 설정 합니다 **탐색** 메일 화면을 열려면 함수. 이러한 단계를 완료 한 후 합니다 **MyPeople** 사용자는 선택한 이벤트에 참석 하는 사람들에 게 전자 메일을 보낼 수 있는 컬렉션을 채웁니다.

> [!NOTE]
> 이 전자 메일 보내기는 Outlook에서 실제 이벤트에서 별도 전자 메일을 보냅니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대 한 참조 설명서](./email-screen-reference.md)합니다.
* [PowerApps에서 Office 365 사용자 커넥터에 자세히 알아보려면](../connections/connection-office365-users.md)합니다.
* [PowerApps에서 사용 가능한 모든 연결 참조](../connections-list.md)합니다.