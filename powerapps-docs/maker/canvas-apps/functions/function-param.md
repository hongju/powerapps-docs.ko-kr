---
title: "Download, Launch 및 Param 함수 | Microsoft Docs"
description: "PowerApps의 Download, Launch 및 Param 함수에 대한 참조 정보이며, 구문과 예제를 포함하고 있습니다."
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 4ed646431263e96a079483bc514c8154b6d9b653
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="download-launch-and-param-functions-in-powerapps"></a>PowerApps의 Download, Launch 및 Param 함수
매개 변수를 사용하여 웹 페이지 또는 앱을 다운로드하거나 시작합니다.  

## <a name="description"></a>설명
**Download** 함수는 파일을 웹에서 로컬 장치로 다운로드합니다.  사용자에게 파일을 저장할 위치를 묻는 메시지가 표시됩니다.  **Download**는 파일이 로컬로 저장된 위치를 문자열로 반환합니다.  

**Launch** 함수는 웹 페이지 또는 앱을 시작합니다.  이 함수는 필요에 따라 매개 변수를 앱에 전달할 수 있습니다.  

**Param** 함수는 앱이 시작될 때 해당 앱에 전달된 매개 변수를 검색합니다.  명명된 매개 변수가 전달되지 않은 경우 **Param**에서 *공백*을 반환합니다.

## <a name="syntax"></a>구문
**Download**( *Address* )

* *Address* - 필수 항목이며,  다운로드할 웹 리소스의 주소입니다.

**Launch**( *Address* [, *ParameterName1*, *ParameterValue1*, ... ] )

* *Address* - 필수 항목이며,  시작할 웹 페이지의 주소 또는 앱의 ID입니다.
* *ParameterName(s)* - 선택 항목이며,  매개 변수 이름입니다.
* *ParameterValue(s)* - 선택 항목이며,  앱 또는 웹 페이지에 전달할 매개 변수 값입니다.

**Param**( *ParameterName* )

* *ParameterName* - 필수 항목이며,  앱에 전달된 매개 변수 이름입니다.

