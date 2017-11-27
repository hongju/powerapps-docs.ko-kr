---
title: "사용자 지정 엔터티 삭제 및 데이터 지우기 | Microsoft Docs"
description: "사용자 정의 엔터티를 삭제하고 모든 데이터를 지웁니다."
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: 2c0dbc172ee7354bc94670f9bb6993d33fca8f2c
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="delete-a-custom-entity"></a>사용자 지정 엔터티 삭제
사용자 지정 엔터티를 삭제할 수 있으나, 표준 엔터티는 삭제할 수 없습니다.

1. [powerapps.com](https://web.powerapps.com)에서 **Common Data Service** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다. 목록 위의 검색 창에서 하나 이상의 문자를 입력하여 엔터티 목록을 필터링할 수 있습니다.
2. 엔터티 목록에서 삭제할 엔터티를 클릭하거나 탭한 다음, 오른쪽 위 모서리에 있는 휴지통 아이콘을 클릭하거나 탭합니다.
3. 나타나는 대화 상자에서 **삭제**를 클릭하거나 탭하여 엔터티를 삭제합니다.

## <a name="notes"></a>참고
* 엔터티를 삭제하면 해당 엔터티 정의 및 엔터티에 포함된 데이터 전체를 모두 삭제합니다.
* 해당 앱에서 사용되는 엔터티를 삭제하는 경우 앱이 중단될 수도 있습니다.
* 엔터티 A에 엔터티 B에 대한 [조회 필드](data-platform-entity-lookup.md)가 있는 경우, 엔터티 A를 삭제하려면 엔터티 B를 삭제해야 할 수 있습니다.

