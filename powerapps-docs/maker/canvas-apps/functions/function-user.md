---
title: User 함수 | Microsoft Docs
description: PowerApps에서 사용자 함수에 대한 구문을 포함한 참조 정보
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2016
ms.author: gregli
ms.openlocfilehash: 2053f69146bcd952f61916ef9e41150791a243a5
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="user-function-in-powerapps"></a>PowerApps의 사용자 함수
현재 사용자에 대한 정보를 반환합니다.

## <a name="description"></a>설명
**사용자** 함수는 현재 사용자에 대한 정보의 [레코드](../working-with-tables.md#records)를 반환합니다.

| 속성 | 설명 |
| --- | --- |
| **User().Email** |현재 사용자의 전자 메일 주소입니다. |
| **User().FullName** |현재 사용자의 성과 이름이 포함된 전체 이름입니다. |
| **User().Image** |현재 사용자의 이미지입니다. 이미지의 URL 형식은 "blob:*identifier*"입니다. 앱에서 해당 이미지를 표시하려면 **[이미지](../controls/control-image.md)** 컨트롤의 **[이미지](../controls/properties-visual.md)** 속성을 이 값으로 설정합니다. |

> [!NOTE]
> 반환된 정보는 현재 PowerApps 사용자에 대한 내용입니다.  PowerApps 플레이어와 스튜디오에 표시되는 "계정" 정보와 일치하며, 작성된 모든 앱 외부에서 찾을 수 있습니다.  이는 Office 365 또는 다른 서비스의 현재 사용자의 정보와 일치하지 않을 수 있습니다.

## <a name="syntax"></a>구문
**User**()

## <a name="examples"></a>예
현재 PowerApps 사용자는 다음과 같은 정보를 보유합니다.

* 전체 이름: **"John Doe"**
* 이메일 주소: **"john.doe@contoso.com"**
* 이미지: ![](media/function-user/john-doe-picture.png) 

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **User()** |현재 PowerApps 사용자에 대한 모든 정보의 기록입니다. |{ FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678" } |
| **User().Email** |현재 PowerApps 사용자의 전자 메일 주소입니다. |"john.doe@contoso.com" |
| **User().FullName** |현재 PowerApps 사용자의 전체 이름입니다. |"John Doe" |
| **User().Image** |현재 PowerApps 사용자의 이미지 URL입니다.  앱에서 해당 이미지를 표시하려면 **이미지** 컨트롤의 **이미지** 속성을 이 값으로 설정합니다. |"blob:1234...5678"<br><br>및 **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

