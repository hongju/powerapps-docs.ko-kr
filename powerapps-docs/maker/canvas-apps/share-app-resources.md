---
title: 앱에서 사용하는 리소스 공유 | Microsoft Docs
description: 앱 공유 시 앱에서 공유한 리소스를 공유하는 방법을 알아봅니다.
author: archnair
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/28/2016
ms.author: archanan
ms.openlocfilehash: 09d4f26139ae33195c666a2eb71d70e02b035f69
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2018
ms.locfileid: "39194892"
---
# <a name="share-app-resources"></a>앱 리소스 공유
[앱을 공유](share-app.md)하기 전에 다음 중 한 개 이상과 같이 주로 사용하려는 리소스 유형을 고려합니다.

* 데이터 원본에 연결
* 온-프레미스 데이터 게이트웨이
* 사용자 지정 커넥터
* Excel 통합 문서 또는 기타 서비스
* 흐름

이러한 리소스 중 일부는 앱을 공유할 때 자동으로 함께 공유됩니다. 다른 리소스는 앱을 예상대로 작동하기 위해 사용자나 앱을 공유하려는 사용자가 추가 단계를 수행해야 합니다.

또한 연결, 사용자 지정 커넥터 및 온-프레미스 데이터 게이트웨이를 전체 조직과 공유할 수도 있습니다.

## <a name="connections"></a>연결
SQL Server와 같은 일부 유형의 연결은 자동으로 공유되지만 사용자가 앱에서 데이터 원본에 대한 자체 연결을 만들어야 합니다.

[powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 연결을 자동으로 업데이트할 것인지 결정할 수 있으며 공유 권한을 업데이트할 수 있습니다. 왼쪽 탐색 모음에서 **관리**를 클릭하거나 탭한 다음 **연결**을 클릭하거나 탭하고 연결을 클릭하거나 탭합니다. **공유** 탭이 나타나면 연결이 자동으로 공유됩니다.

  ![연결 정보 페이지의 공유 탭](./media/share-app-resources/shared-connections.png)

## <a name="on-premises-data-gateways"></a>온-프레미스 데이터 게이트웨이
온-프레미스 원본의 데이터가 포함된 앱을 만들어 공유하는 경우 [온-프레미스 데이터 게이트웨이](gateway-management.md) 자체와 해당 게이트웨이에 대한 특정 연결 형식이 자동으로 공유됩니다. 자동으로 공유되지 않는 모든 연결은 이전 섹션에 설명된 대로 수동으로 공유하거나 앱에서 사용자에게 자체 연결을 만들지 묻는 메시지를 표시하도록 할 수 있습니다. 게이트웨이가 구성된 연결을 표시하는 방법:

1. [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)을 열고 왼쪽 탐색 창에서 **관리**를 클릭하거나 탭한 후 **게이트웨이**를 클릭하거나 탭합니다.
2. 게이트웨이를 클릭하거나 탭한 다음 **연결**을 클릭하거나 탭합니다.

> [!NOTE]
> 수동으로 하나 이상의 연결을 공유하는 경우 이러한 상황을 다시 공유해야 할 수 있습니다.

* 온-프레미스 데이터 게이트웨이를 이미 공유한 앱에 추가합니다.
* 공유한 앱 중 온-프레미스 데이터 게이트웨이가 있는 사용자 집합 또는 그룹을 변경합니다.

## <a name="custom-connectors"></a>사용자 지정 커넥터
사용자 지정 커넥터를 사용하는 앱을 공유하면 자동으로 공유되지만 사용자가 해당 앱에 대한 연결을 직접 만들어야 합니다.

[powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에서 사용자 지정 커넥터에 대한 권한을 보거나 업데이트할 수 있습니다. 왼쪽 탐색 모음에서 **관리**를 클릭하거나 탭한 다음 **연결**을 클릭하거나 탭하고 오른쪽 상단 모서리의 **새 연결**을 클릭하거나 탭합니다. **사용자 지정**, 사용자 지정 커넥터를 차례로 클릭하거나 탭하여 관련 세부 정보를 표시합니다.

## <a name="excel-workbooks"></a>Excel 통합 문서
공유한 앱에서 일부 사용자에게 액세스 권한이 없는 데이터를 사용하는 경우(예: 클라우드 저장소 계정의 Excel 통합 문서), [데이터를 공유](share-app-data.md)합니다.

## <a name="flows"></a>흐름
흐름을 포함하는 앱을 공유하는 경우 앱을 실행하는 사용자에게 흐름을 사용하는 모든 연결을 확인 또는 업데이트할 것인지 묻는 메시지가 표시됩니다. 또한 흐름을 만든 사용자만 해당 매개 변수를 사용자 지정할 수 있습니다. 예를 들어 사용자가 지정한 주소로 메일을 보내는 흐름을 만든다면 다른 사용자가 해당 주소를 변경할 수 없습니다.

