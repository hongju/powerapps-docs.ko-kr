---
title: EncodeUrl 및 PlainText 함수 | Microsoft Docs
description: PowerApps의 EncodeUrl 및 PlainText 함수에 대한 구문과 예제를 포함한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9956332c35b4df2773b2634cb7f66d2ea96469e4
ms.sourcegitcommit: 1b8578e38a09220ac66c5123644714139fc3c9e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2019
ms.locfileid: "57800448"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>PowerApps의 EncodeUrl 및 PlainText 함수
문자열을 인코딩하고 디코딩합니다.

## <a name="description"></a>설명
합니다 **EncodeUrl** 함수 % 및 16 진수 숫자로 사용 하 여 특정 영숫자가 아닌 문자를 대체 하는 URL 문자열을 인코딩합니다.  

합니다 **일반 텍스트** HTML 및 XML 태그에 특정 태그를 적절 한 기호로 같은 변환 함수를 제거 합니다.

* **&amp;nbsp;**
* **&amp;quot;**

이러한 함수의 반환 값은 인코딩되거나 디코딩된 문자열입니다. 이 함수는 모든 HTML 및 XML 태그를 제거 하지 않습니다. 

## <a name="syntax"></a>구문
**EncodeUrl**( *String* )

* *String* - 필수 항목입니다.  인코딩할 URL입니다.

**PlainText**( *String* )

* *String* - 필수 항목이며, HTML 및 XML 태그를 제거할 문자열입니다.

## <a name="examples"></a>예
텍스트 갤러리에 RSS 피드를 표시한 다음, 해당 갤러리의 레이블에 있는 **[Text](../controls/properties-core.md)** 속성을 **ThisItem.description**으로 설정하면 레이블에 다음 예제와 같이 원시 HTML 또는 XML 코드가 표시됩니다.

    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>

레이블의 **[Text](../controls/properties-core.md)** 속성을 **PlainText(ThisItem.description)** 로 설정하면 텍스트가 다음 예제와 같이 나타납니다.

    We have done an unusually "deep" globalization and localization.
