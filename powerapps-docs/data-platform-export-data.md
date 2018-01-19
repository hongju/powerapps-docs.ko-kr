---
title: "데이터 가져오기 또는 내보내기 | Microsoft Docs"
description: "엔터티를 가져오거나 내보냅니다."
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
ms.openlocfilehash: 880881b31362d38ed0d44126245dd96d2a74150f
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="import-or-export-data-from-the-common-data-service"></a>Common Data Service의 데이터 가져오기 또는 내보내기
두 가지 방법 중 하나로 Common Data Service 안팎으로 데이터를 이동할 수 있습니다.

* 일회성으로 대량 가져오기 또는 내보내기를 하려면 여러 엔터티의 경우 Microsoft Excel을 사용할 수 있습니다.
* Dynamics 365 또는 Salesforce 같은 다른 서비스 또는 Excel 파일로 단일 엔터티에 대한 지속적인 데이터 가져오기 또는 내보내기를 하려는 경우입니다. [Microsoft Flow](https://flow.microsoft.com)를 사용하여 지속적인 가져오기 또는 내보내기를 설정할 수 있습니다.

## <a name="import-or-export-data-once"></a>한 번 데이터 가져오기 또는 내보내기
### <a name="import-data-from-excel"></a>Excel에서 데이터 가져오기
1. [powerapps.com](https://web.powerapps.com)에서 **Common Data Service** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 누릅니다.
2. **새 엔터티** 옆의 줄임표(...)를 클릭하거나 탭한 후 **데이터 가져오기**를 클릭하거나 탭합니다.
3. 데이터를 가져와 저장할 엔터티를 선택한 후 **다음**을 클릭하거나 탭합니다.
4. **검색**을 클릭하거나 탭합니다. 데이터를 가져오려는 파일을 선택합니다.
5. **매핑 상태**가 녹색으로 체크 표시된 상태로 **일치**하지 않은 경우, Excel 파일에서 열과 엔터티 필드 간의 매핑을 지정해야 합니다. 열을 매핑하는 방법:
   1. **매핑 표시**를 클릭하거나 탭합니다.
   2. Excel 파일에서 각 엔터티 필드에 대해 일치하는 열을 선택합니다.
   3. **변경 내용 저장**을 클릭하거나 탭합니다.
6. **가져오기**를 클릭합니다.

### <a name="export-data-to-excel"></a>Excel로 데이터 내보내기
표준 엔터티 또는 사용자 지정 엔터티에서 일회성으로 데이터를 내보낼 수 있으며, 한 번에 둘 이상의 엔터티에서 데이터를 내보낼 수 있습니다. 두 개 이상의 엔터티에서 데이터를 내보내는 경우 각 엔터티는 고유의 Microsoft Excel 파일로 이동됩니다.

1. [powerapps.com](https://web.powerapps.com)의 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 탭합니다.
2. **새 엔터티** 옆의 줄임표(...)를 클릭하거나 탭한 후 **데이터 내보내기**를 클릭하거나 탭합니다.
3. 데이터를 내보내려는 엔터티를 선택한 후 **Excel로 내보내기**를 클릭하거나 탭합니다.
4. **내보내기 완료**가 표시되면 **내보낸 데이터 다운로드**를 클릭하거나 탭하여 데이터를 다운로드합니다.

## <a name="use-microsoft-flow-to-set-up-ongoing-import-or-export"></a>Microsoft Flow를 사용하여 지속적인 가져오기 또는 내보내기 설정
단일 표준 엔터티 또는 사용자 지정 엔터티에 대한 지속적인 가져오기 또는 내보내기를 한 번에 설정할 수 있습니다. 연결할 수 있는 가능한 위치는 다음을 포함합니다.

* Dynamics 365
* Salesforce
* 모든 클라우드 파일 공급자에 저장된 Microsoft Excel 파일
* 클라우드 및 온-프레미스에 있는 Microsoft SQL 데이터베이스
* 자신의 시스템에 연결하기 위해 정의한 사용자 지정 커넥터

지금 데이터를 가져오거나 내보내기 위해 사용하는 Microsoft Flow는 전체 동기화 서비스가 아닙니다. 개체는 하나의 서비스에 추가될 때 다른 시스템으로 보내집니다. 하지만 이는 개체가 한 시스템에서 삭제되어도 다른 시스템에서는 삭제되지 않는다는 의미입니다.

가져오려는 개체에 대한 기존 템플릿의 존재 여부에 따른 가져오기 설정 방법. 템플릿이 존재하는 경우 한 시스템에서 다른 시스템으로 데이터를 복사하도록 설정할 수 있습니다. 자세한 내용은 [Microsoft Common Data Service를 사용하는 흐름 만들기](https://flow.microsoft.com/documentation/common-data-model-intro/)를 참조하세요. 한편, 이러한 템플릿이 존재하지 않는 경우, 데이터베이스를 사용할 수 있는 흐름을 만들어야 합니다. 자세한 내용은 [처음부터 흐름을 새로 만드는 방법](https://flow.microsoft.com/documentation/get-started-logic-flow/)을 참조하세요.

