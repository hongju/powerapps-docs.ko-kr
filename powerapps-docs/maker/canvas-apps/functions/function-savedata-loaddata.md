---
title: SaveData 및 LoadData 함수 | Microsoft Docs
description: PowerApps의 SaveData 및 LoadData 함수에 대한 구문을 비롯한 참조 정보
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3fb23fec6f6885a55b054889b90fed0c5efafd5e
ms.sourcegitcommit: bdee274ce4ae622f7af5f208041902e66e03d1b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2019
ms.locfileid: "57800356"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>PowerApps의 SaveData 및 LoadData 함수
[컬렉션](../working-with-data-sources.md#collections)을 저장하고 다시 로드합니다.

## <a name="description"></a>설명
**SaveData** 함수는 나중에 이름으로 사용할 컬렉션을 저장합니다.  

**LoadData** 함수는 이전에 **SaveData**를 사용하여 저장한 이름으로 컬렉션을 다시 로드합니다. 이 함수는 다른 원본에서 컬렉션을 로드하는 데 사용할 수 없습니다.  

데이터를 캐시 하 여 응용 프로그램 시작 성능 향상을 위해 이러한 함수를 사용 합니다 **[App.OnStart](../controls/control-screen.md#additional-properties)** 수식에 첫 번째 실행 후 후속 실행에서 로컬 캐시를 다시 로드 합니다. 추가할 이러한 함수를 사용할 수도 있습니다 [간단한 오프 라인 기능](../offline-apps.md) 앱.

PowerApps Studio 앱을 제작 하는 경우 또는 웹 플레이어에서 앱을 실행 하는 경우에 브라우저 내에서 이러한 함수를 사용할 수 없습니다. 앱을 테스트 하려면 iPhone 또는 Android 장치에서 PowerApps Mobile 실행 합니다.

이러한 함수는 메모리 내 컬렉션에서 작동 하기 때문 사용 가능한 앱 메모리 양으로 제한 됩니다. 사용 가능한 메모리는 장치 및 운영 체제, PowerApps 플레이어를 사용 하는 메모리 및 화면 및 컨트롤 측면에서 앱의 복잡성에 따라 달라질 수 있습니다. 겨우 몇 메가바이트의 데이터를 저장 하는 경우 앱이 실행 되도록를 예상 하는 장치에서 예상된 된 시나리오가 사용 하 여 앱을 테스트 합니다. 일반적으로 사용 가능한 메모리의 30 및 메가바이트 사이인 되어야 합니다.  

**LoadData**는 컬렉션을 만들지 않습니다. 함수는 기존 컬렉션을 채우기만 합니다. 먼저 **[Collect](function-clear-collect-clearcollect.md)** 를 사용하여 올바른 [열](../working-with-tables.md#columns)이 있는 컬렉션을 만들어야 합니다. 로드 된 데이터 컬렉션에 추가 됩니다. 사용 된 **[지우기](function-clear-collect-clearcollect.md)** 빈 컬렉션을 시작 하려는 경우 먼저 함수입니다.

스토리지는 암호화되어 로컬 디바이스의 비공개 위치에 다른 사용자 및 다른 앱과 격리되어 있습니다.

## <a name="syntax"></a>구문
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Collection* - 필수 항목입니다.  저장하거나 로드할 컬렉션입니다.
* *Name* - 필수 항목입니다.  스토리지 이름입니다. 동일한 데이터 집합을 저장하고 로드하려면 동일한 이름을 사용해야 합니다. 네임스페이스는 다른 앱이나 사용자와 공유되지 않습니다.
* *IgnoreNonexistentFile* - 선택 항목입니다. **LoadData** 함수가 일치하는 파일을 찾을 수 없을 때 오류를 표시하거나 무시할지 나타내는 부울(**true**/**false**) 값입니다. **false**를 지정하면 오류가 표시됩니다. **true**를 지정하면 오류가 무시되고, 오프라인 시나리오에 유용합니다. **SaveData**는 디바이스가 오프라인인 경우 (즉, **Connection.Connected** 상태가 **false**인 경우) 파일을 만들 수 있습니다.

## <a name="examples"></a>예

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100})),LoadData(LocalTweets, "Tweets", true))** |디바이스가 연결되어 있으면 Twitter 서비스에서 LocalTweets 컬렉션을 로드하고, 그렇지 않으면 로컬 파일 캐시에서 컬렉션을 로드합니다. |콘텐츠는 디바이스가 온라인 또는 오프라인 상태인지 여부에 관계없이 렌더링됩니다. |
| **SaveData(LocalTweets, "Tweets")** |LocalTweets 컬렉션을 디바이스의 로컬 파일 캐시로 저장합니다. |데이터는 **LoadData**가 컬렉션에 로드할 수 있도록 로컬에 저장됩니다. |

