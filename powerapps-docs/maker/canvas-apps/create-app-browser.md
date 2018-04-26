---
title: 브라우저에서 앱 만들기 또는 편집 | Microsoft Docs
description: 웹용 PowerApps Studio를 사용하여 브라우저에서 앱을 만들거나 편집합니다.
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/08/2018
ms.author: anneta
ms.openlocfilehash: 4c8b100e4993921c651590c80eda4297345cdd40
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="create-or-edit-apps-in-powerapps-studio-for-web"></a>웹용 PowerApps Studio에서 앱 만들기 또는 편집
웹용 PowerApps Studio에서 앱을 만들고 편집하면 Windows 또는 기타 플랫폼의 브라우저 창에서 열립니다.

## <a name="prerequisites"></a>필수 조건
* PowerApps에 [등록](../signup-for-powerapps.md)합니다.
* [지원되는 브라우저](limits-and-config.md#supported-browsers-for-powerapps-studio-for-web)를 사용하고 있는지 확인합니다.

## <a name="open-powerapps-studio-for-web"></a>웹용 PowerApps Studio 열기
1. [powerapps.com](http://go.microsoft.com/fwlink/p/?LinkId=708209)에 로그인합니다.
2. 왼쪽 아래 모서리에서 **새 앱**을 클릭하거나 탭합니다.

    ![왼쪽 탐색 표시줄의 새 앱](./media/create-app-browser/left-nav.png)

웹용 PowerApps Studio가 브라우저의 새 탭에서 열리며 여기에서 Windows용 PowerApps Studio에서 할 수 있는 것과 같은 방식으로 앱을 만들고 편집할 수 있습니다.

## <a name="known-limitations"></a>알려진 제한 사항
1. **연결을 만듭니다.**

    서비스 인증이 필요한 데이터 원본에 대한 [연결을 만들려면](add-manage-connections.md) [powerapps.com](https://web.powerapps.com)을 사용한 후 웹용 PowerApps Studio에서 앱에 대한 [연결을 추가](add-data-connection.md)합니다.
2. **로컬에서 앱을 편집하고 저장합니다**.

    최상의 결과를 위해 Windows용 PowerApps Studio를 사용하여 로컬에서 앱을 편집하고 저장합니다. 브라우저에서는 로컬 앱에 변경 내용을 저장할 수 없으며 연 파일을 대체하는 대신 새 파일을 저장해야 합니다.
3. **신호 함수를 사용합니다.**

    **[Acceleration 및 Compass](functions/signals.md)** 함수는 게시된 앱에서 정확한 값을 반환하지만 해당 함수는 브라우저에서 앱을 만들거나 수정할 때 0 값을 반환합니다.
4. **데이터를 내보내고 가져옵니다.**

    게시된 앱에서는 [데이터를 내보내고 가져올 수 있지만](controls/control-export-import.md) 브라우저에서 앱을 만들거나 수정할 때는 불가능합니다.
5. **두 세션 간에 컨트롤을 복사합니다.**

    웹용 PowerApps Studio의 세션 중 하나에서 다른 웹용 PowerApps Studio 세션으로 컨트롤을 복사할 수 없습니다.

## <a name="next-steps"></a>다음 단계
* 예를 들어, [Excel](get-started-create-from-data.md) 또는 [SharePoint](app-from-sharepoint.md)에서 데이터로부터 앱을 자동으로 생성합니다.
* 앱이 표시되고 동작하는 방식을 결정하는 [컨트롤을 추가하고 속성을 설정](add-configure-controls.md)하는 방법에 대해 알아봅니다.
* [처음부터 앱을 다시 만들어](get-started-create-from-blank.md) 창의성을 발휘해 보세요.
