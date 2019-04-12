---
title: 사용자 화면 템플릿 | Microsoft Docs
description: 캔버스 앱에 대한 사용자 화면 템플릿의 작동 원리 및 고유한 사용 사례에 대한 화면을 확장하는 방법 이해
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
# <a name="overview-of-the-people-screen-template-for-canvas-apps"></a>캔버스 앱의 사용자 화면 템플릿 개요

캔버스 앱에서 사용자가 조직 내 사용자를 검색할 수 있는 사용자 화면을 추가합니다. 앱 사용자는 사용자를 검색, 선택하고 컬렉션에 사용자를 추가할 수있습니다. 검색 결과 갤러리에 나타나는 데이터 형식을 변경하고, 사용자를 선택하여 전자 메일을 보내고, 기타 사용자 지정을 할 수 있습니다.

사용자의 Office 365에서 [전자 메일](email-screen-overview.md), 사용자의 [일정](calendar-screen-overview.md) 및 모임에 초대하려는 사용자의 [가용성](meeting-screen-overview.md)과 같은 다른 데이터를 표시하는 또 다른 템플릿 기반 화면을 추가할 수도 있습니다.

개요에서는 다음을 설명합니다.
> [!div class="checklist"]
> * 기본 사용자 화면을 사용하는 방법.
> * 화면을 수정 하는 방법.
> * 앱에 화면을 통합하는 방법.

이 화면의 기본 기능의 자세한 내용은 [사용자 화면 참조](people-screen-reference.md)를 확인합니다.

## <a name="prerequisite"></a>필수 조건

[PowerApps에서 앱을 만들어](../data-platform-create-app-scratch.md) 화면 및 기타 컨트롤을 추가하고 구성하는 방법에 친숙합니다.

## <a name="default-functionality"></a>기본 기능

템플릿에서 사용자 화면을 추가:

1. PowerApps에 [로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)한 다음 PowerApps Studio에서 앱을 만들거나 기존 앱을 엽니다.

    이 항목에서는 전화 앱을 보여주지만 태블릿 앱에 동일한 개념이 적용 됩니다.

1. 리본의 **홈** 탭에서 **새 화면** > **사용자**를 선택합니다.

    기본적으로 다음 화면과 비슷합니다.

    ![초기 사용자 상태 화면](media/people-screen/people-screen-empty.png)

1. 사용자 검색을 시작하려면 맨 위에 있는 텍스트 입력란을 선택하고 동료 직원의 이름을 입력하기 시작 합니다. 검색 결과가 텍스트 입력 상자 아래에 나타납니다.

    ![사용자 화면 검색 상태](media/people-screen/people-browse-gall-full.png)

1. 검색 결과에서 각각을 선택하게 되면, **MyPeople** 컬렉션에 추가됩니다. 검색 입력 값은 다시 설정되고, 선택한 사용자의 컬렉션이 나타납니다.

    ![사용자 화면 컬렉션 결과](media/people-screen/people-people-gall-full.png)

## <a name="modify-the-screen"></a>화면 수정

[사용자의 다양한 데이터를 보여줌으로써](people-screen-overview.md#show-different-data-for-people) 이 화면의 기본 기능을 변경할 수 있습니다.

추가로 수정하려는 경우 가이드로 [사용자 화면 참조](./people-screen-reference.md)를 확인합니다.

### <a name="show-different-data-for-people"></a>사용자의 다양한 데이터 표시

이 화면을 사용 합니다 [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) 조직에서 사용자를 검색 하는 작업 새로운 각 이벤트에 표시에 대 한 추가 필드를 제공 합니다 **UserBrowseGallery** 제어 합니다. 갤러리에서 필드를 변경 하거나 추가 간단한 프로세스입니다.

1. **UserBrowseGallery**에서 변경하려는 레이블을 선택하거나 추가하여 선택합니다.

1. **Text** 속성이 선택된 상태에서, 수식 입력줄에서 내용을 `ThisItem.`으로 바꿉니다.

    IntelliSense는 선택할 수 있는 필드의 목록을 보여줍니다.

1. 원하는 필드를 선택 합니다.

    **Text** 속성을 `ThisItem.{FieldSelection}`으로 업데이트합니다.

## <a name="integrate-the-screen-into-an-app"></a>화면을 앱에 통합

사용자 화면은 그 자체로도 컨트롤의 강력한 번들이지만 일반적으로 더 큰, 더 다기능의 응용 프로그램의 일부로 수행됩니다. [캐시된 사용자 목록을 이용하는 것](people-screen-overview.md#use-your-cached-list-of-people)을 포함하여 다양한 방법으로 더 큰 앱에 이 화면을 통합할 수 있습니다.

### <a name="use-your-cached-list-of-people"></a>캐시된 사용자 목록 이용

사용자 화면은 **MyPeople** 컬렉션에서 사용자 선택을 캐시합니다. 비즈니스 시나리오에서 사용자 조회가 필요하면, 이 컬렉션을 사용하는 방법을 알아야 합니다. 여기에서, 이 화면에서 기본 전자 메일 화면에 연결하고 **MyPeople** 컬렉션의 사용자에게 전자 메일을 보내는 방법을 알아 봅니다. 또한 [전자 메일 화면](./email-screen-overview.md) 작동 방법에 대한 통찰력을 얻을 수 있습니다.

1. **보기** 탭을 선택하고, **데이터 원본** > **데이터 원본 추가**를 선택하여, Office 365 outlook 커넥터를 찾아 Office 365 Outlook 데이터 원본을 앱에 추가합니다. 이를 찾으려면 **새 연결**을 선택해야 할 수 있습니다.
1. 사용자 화면을 삽입한 후 새 빈 화면을 삽입합니다. 해당 화면 내에서 뒤로 화살표 아이콘, 두 텍스트 입력 상자 및 보내기 아이콘을 추가합니다.
1. 화면의 이름을 **EmailScreen**으로, 뒤로 화살표 아이콘 이름을 **BackIcon**으로, 한 텍스트 입력 상자의 이름을 **SubjectLine**으로, 다른 텍스트 입력 상자의 이름을 **MessageBody**로, 보내기 아이콘 이름을 **SendIcon**으로 변경합니다.
1. **BackIcon**의 **OnSelect** 속성을 `Back()`으로 설정합니다.
1. **SendIcon**의 **OnSelect** 속성을 다음 수식으로 설정합니다.

    ```powerapps-dot
    Office365.SendEmail( 
        Concat( MyPeople, UserPrincipalName & ";" ), 
        SubjectLine.Text, 
        MessageBody.Text 
    )
    ```
    
    여기에서는 Outlook 커넥터를 사용하여 전자 메일을 보내려고 합니다. 받는 사람 목록으로 `Concat(MyPeople, UserPrincipalName & ";")`을 전달합니다. 이 수식은 **MyPeople** 컬렉션의 모든 전자 메일 주소를 세미콜론으로 구분된 단일 문자열로 연결합니다. 자주 사용하는 전자 메일 클라이언트의 "To" 줄에 세미콜론으로 구분된 전자 메일 주소 문자열을 작성하는 것과 다르지 않습니다.
    * 메시지의 제목으로 `SubjectLine.Text`를 전달하고 메시지의 본문으로 `MessageBody.Text`를 전달합니다.
1. 사용자 화면 오른쪽 위 모서리에서 **Mail** 아이콘을 삽입합니다.
   적절하게 아이콘 색을 변경합니다.
1. **SendIcon**의 **OnSelect**의 속성을 `Navigate( EmailScreen, None )`로 설정합니다.

    이제 사용자를 선택하고, 전자 메일 메시지를 작성한 다음 보내는 두 화면으로 구성된 앱이 완성되었습니다. 자유롭게 테스트할 수 있지만 앱은 **MyPeople** 컬렉션의 모든 사용자에게 전자 메일을 보내기 때문에 테스트할 때 조심해야 합니다.

## <a name="next-steps"></a>다음 단계

* [이 화면에 대한 참조 설명서 보기](./people-screen-reference.md)
* [Office 365 Outlook 커넥터에 대해 자세히 알아보기](../connections/connection-office365-outlook.md)
* [Office 365 사용자 커넥터에 대해 자세히 알아보기](../connections/connection-office365-users.md)
