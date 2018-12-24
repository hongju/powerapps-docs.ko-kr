---
title: SaveData 및 LoadData 함수 | Microsoft Docs
description: PowerApps의 SaveData 및 LoadData 함수에 대한 구문을 비롯한 참조 정보
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
ms.openlocfilehash: 5aa9992b9371724c77bcc1d2baf439bb2d7b9dab
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864330"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>PowerApps의 SaveData 및 LoadData 함수
[컬렉션](../working-with-data-sources.md#collections)을 저장하고 다시 로드합니다.

## <a name="description"></a>설명
**SaveData** 함수는 나중에 이름으로 사용할 컬렉션을 저장합니다.  

**LoadData** 함수는 이전에 **SaveData**를 사용하여 저장한 이름으로 컬렉션을 다시 로드합니다. 이 함수는 다른 원본에서 컬렉션을 로드하는 데 사용할 수 없습니다.  

**LoadData**는 컬렉션을 만들지 않습니다. 함수는 기존 컬렉션을 채우기만 합니다. 먼저 **[Collect](function-clear-collect-clearcollect.md)** 를 사용하여 올바른 [열](../working-with-tables.md#columns)이 있는 컬렉션을 만들어야 합니다.

저장소는 암호화되어 로컬 디바이스의 비공개 위치에 다른 사용자 및 다른 앱과 격리되어 있습니다.  

## <a name="syntax"></a>구문
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Collection* - 필수 항목입니다.  저장하거나 로드할 컬렉션입니다.
* *Name* - 필수 항목입니다.  저장소 이름입니다. 동일한 데이터 집합을 저장하고 로드하려면 동일한 이름을 사용해야 합니다. 네임스페이스는 다른 앱이나 사용자와 공유되지 않습니다.
* *IgnoreNonexistentFile* - 선택 항목입니다. **LoadData** 함수가 일치하는 파일을 찾을 수 없을 때 오류를 표시하거나 무시할지 나타내는 부울(**true**/**false**) 값입니다. **false**를 지정하면 오류가 표시됩니다. **true**를 지정하면 오류가 무시되고, 오프라인 시나리오에 유용합니다. **SaveData**는 장치가 오프라인인 경우 (즉, **Connection.Connected** 상태가 **false**인 경우) 파일을 만들 수 있습니다.

## <a name="examples"></a>예

| 수식 | 설명 | 결과 |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100})),LoadData(LocalTweets, "Tweets", true))** |디바이스가 연결되어 있으면 Twitter 서비스에서 LocalTweets 컬렉션을 로드하고, 그렇지 않으면 로컬 파일 캐시에서 컬렉션을 로드합니다. |콘텐츠는 디바이스가 온라인 또는 오프라인 상태인지 여부에 관계없이 렌더링됩니다. |
| **SaveData(LocalTweets, "Tweets")** |LocalTweets 컬렉션을 디바이스의 로컬 파일 캐시로 저장합니다. |데이터는 **LoadData**가 컬렉션에 로드할 수 있도록 로컬에 저장됩니다. |

