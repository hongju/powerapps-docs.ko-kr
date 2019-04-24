---
title: 오프라인에서 사용 가능한 캔버스 앱 개발 | Microsoft Docs
description: 온라인에 있든 오프라인에 있든 사용자 생산성을 유지할 수 있도록 오프라인에서 사용 가능한 캔버스 앱을 개발합니다.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9922c64769aeacd9b9b65cc3039b091ac7fe353
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61538362"
---
# <a name="develop-offline-capable-canvas-apps"></a>오프라인에서 사용 가능한 캔버스 앱 개발

모바일 앱 개발자 권한으로 직면하는 가장 일반적인 시나리오 중 하나는 제한된 연결 또는 연결되지 않았을 때 사용자가 생산성을 사용해야 하는 경우입니다. PowerApps에는 오프라인에서 사용 가능한 캔버스 앱을 개발하는 데 도움이 되는 기능 및 동작의 집합이 있습니다. 당신은 할 수 있어요:

* 오프라인 상태에서 PowerApps Mobile을 시작합니다.
* 오프라인에서 개발한 앱을 실행합니다.
* [연결](../canvas-apps/functions/signals.md#connection) 신호 개체를 사용하여 앱이 오프라인 상태인지, 온라인 상태인지, 요금제 연결인지를 확인합니다.
* [컬렉션](../canvas-apps/create-update-collection.md)을 사용하고 오프라인에서 기본 데이터 스토리지에 [LoadData 및 SaveData](../canvas-apps/functions/function-savedata-loaddata.md)와 같은 기능을 활용합니다.

## <a name="limitations"></a>제한 사항

**LoadData** 하 고 **SaveData** 로컬 장치에 적은 양의 데이터를 저장 하는 간단한 메커니즘이를 결합 합니다. 이러한 함수를 사용 하 여 앱에 간단한 오프 라인 기능을 추가할 수 있습니다.  

이러한 함수는 메모리 내 컬렉션에서 작동 하기 때문 사용 가능한 앱 메모리 양으로 제한 됩니다. 사용 가능한 메모리는 장치, 운영 체제, PowerApps Mobile이 사용 하는 메모리 및 화면 및 컨트롤 측면에서 앱의 복잡성에 따라 달라질 수 있습니다. 겨우 몇 메가바이트의 데이터를 저장 하는 경우는 예상 실행 장치에 필요한 시나리오를 사용 하 여 앱을 테스트 합니다. 일반적으로 사용 가능한 메모리의 30 및 메가바이트 사이인 되어야 합니다.  

함수는 또한 하지 자동으로 병합 충돌을 해결할 오프 라인 장치에서 연결을 반환 하는 식을 작성 하는 경우 저장 되는 데이터와 다시 연결을 처리 하는 방법에 대 한 구성 작성자 달려 경우.

오프 라인 시나리오에 대 한 기능을 확장 하기 위해 노력 하 합니다. 사용할 수 있게 되면 여기와 [PowerApps 블로그](https://powerapps.microsoft.com/blog/)에서 업데이트 내용을 확인합니다.

## <a name="how-to-build-offline-capable-apps"></a>오프라인에서 사용 가능한 앱을 빌드하는 방법

오프라인 시나리오에서 가장 먼저 고려할 점은 앱에서 데이터를 사용하는 방법입니다. PowerApps의 앱은 주로 SharePoint, Office 365 및 Common Data Service와 같이 플랫폼에서 제공하는 [커넥터](../canvas-apps/connections-list.md)의 집합을 통해 데이터에 액세스합니다. 앱이 RESTful 엔드포인트를 제공하는 모든 서비스에 액세스할 수 있도록 사용자 지정 커넥터를 빌드할 수 있습니다. Web API 또는 Azure Functions와 같은 서비스일 수 있습니다. 이러한 모든 커넥터는 인터넷을 통해 HTTPS를 사용합니다. 즉, 사용자가 서비스에서 제공하는 데이터 및 모든 기능에 액세스하려면 온라인 상태여야 합니다.

![커넥터를 포함하는 PowerApps 앱](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>오프라인 데이터 처리
PowerApps의 가장 흥미로운 측면 중 하나는 데이터 원본에 관계 없이 일관된 방식으로 데이터를 필터, 검색, 정렬, 집계 및 조작할 수 있는 해당 집합의 기능 및 수식입니다. 원본은 앱의 메모리 내 컬렉션부터 SharePoint 목록, SQL Databases 및 Common Data Service까지의 범위에 이릅니다. 이러한 일관성을 사용하면 앱 대상을 쉽게 변경하여 다른 백 엔드를 사용할 수 있습니다. 또한 무엇보다도 앱 논리를 거의 변경하지 않고 데이터를 관리하기 위해 로컬 컬렉션을 사용할 수 있습니다. 실제로 로컬 컬렉션은 오프라인 데이터를 처리하기 위한 기본 메커니즘입니다.

## <a name="building-an-offline-twitter-app"></a>오프라인에서 Twitter 앱 빌드
앱 개발의 오프라인 측면에 초점을 두기 위해 Twitter에 기반한 간단한 시나리오를 보여줍니다. 오프라인 상태로 유지되는 동안 Twitter 게시물을 읽고 트윗을 제출할 수 있도록 하는 앱을 빌드합니다. 앱이 온라인 상태가 되면 앱은 트윗을 게시하고 로컬 데이터를 다시 로드합니다.

고급 수준에서 앱은 다음 작업을 수행합니다.

1. 앱 시작 시(첫 번째 화면의 **OnVisible** 속성에 따라):

   * 디바이스가 온라인 상태인 경우 직접 Twitter 커넥터에 액세스하여 데이터를 인출하고 해당 데이터를 사용하여 컬렉션을 채웁니다.
   * 디바이스가 오프라인 상태인 경우 [LoadData](../canvas-apps/functions/function-savedata-loaddata.md)를 사용하여 로컬 캐시 파일에서 데이터를 로드했습니다.
   * 온라인으로 Twitter에 직접 게시하고 로컬 캐시를 새로 고칠 경우 사용자가 트윗을 제출할 수 있습니다.
2. 5분마다 온라인 상태인 경우:

   * 로컬 캐시에 있는 모든 트윗을 게시합니다.
   * 로컬 캐시를 새로 고치고 [SaveData](../canvas-apps/functions/function-savedata-loaddata.md)를 사용하여 저장합니다.

### <a name="step-1-create-a-new-phone-app"></a>1 단계: 새 전화 앱 만들기
1. PowerApps Studio를 엽니다.
2. **새로 만들기** > **비어 있는 앱** > **휴대폰 레이아웃**을 클릭하거나 누릅니다.

    ![비어 있는 앱, 휴대폰 레이아웃](./media/offline-apps/blank-app.png)

### <a name="step-2-add-a-twitter-connection"></a>2 단계: Twitter 연결 추가

1. **콘텐츠** > **데이터 원본**을 클릭하거나 누르고 **데이터 원본** 패널에서 **데이터 원본 추가**를 선택합니다.

2. **새 연결**을 클릭하거나 누르고, **Twitter**를 선택하고, **만들기**를 클릭하거나 누릅니다.

3. 자격 증명을 입력하고 연결을 만듭니다.

    ![Twitter 연결 추가](./media/offline-apps/twitter-connection.png)

### <a name="step-3-load-tweets-into-a-localtweets-collection-on-app-startup"></a>3 단계: 앱 시작 시 LocalTweets 컬렉션으로 트 윗 로드
앱에서 **Screen1**의 **OnVisible** 속성을 선택하고, 다음 수식을 복사합니다.

```powerapps-dot
If( Connection.Connected,
    ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 100} ) );
        UpdateContext( {statusText: "Online data"} ),
    LoadData(LocalTweets, "Tweets", true);
        UpdateContext( {statusText: "Local data"} )
);
LoadData( LocalTweetsToPost, "LocalTweets", true );
SaveData( LocalTweets, "Tweets" )
```

![트윗을 로드하는 수식](./media/offline-apps/load-tweets.png)

이 수식은 디바이스가 온라인 상태인지를 확인합니다.

* 디바이스가 온라인 상태인 경우 **LocalTweets** 컬렉션에 "PowerApps"라는 검색 단어를 포함하는 최대 100개의 트윗을 로드합니다.
* 디바이스가 오프라인 상태인 경우 사용할 수 있다면 "트윗"이라는 파일에서 로컬 캐시를 로드합니다.

### <a name="step-4-add-a-gallery-and-bind-it-to-the-localtweets-collection"></a>4단계: 갤러리 추가 및 LocalTweets 컬렉션에 바인딩

1. 새로운 유연한 높이 갤러리를 삽입 합니다. **삽입** > **갤러리** > **유연한 높이 비워 두면**합니다.

2. **항목** 속성을 **LocalTweets**으로 설정합니다.

3. 4개의 **레이블**을 추가하고, 각 트윗에서 데이터를 표시하고, **텍스트** 속성을 다음으로 설정합니다.
   * **ThisItem.TweetText**
   * **ThisItem.UserDetails.FullName & " \@" & ThisItem.UserDetails.UserName**
   * **"RT: " & ThisItem.RetweetCount**
   * **Text(DateTimeValue(ThisItem.CreatedAtIso), DateTimeFormat.ShortDateTime)**
4. **이미지** 컨트롤을 추가하고, **이미지** 속성을 **ThisItem.UserDetails.ProfileImageUrl**로 설정합니다.

### <a name="step-5-add-a-connection-status-label"></a>5단계: 연결 상태 레이블 추가
새 **레이블** 컨트롤을 삽입하고 **텍스트** 속성을 다음 수식으로 설정합니다.

```If( Connection.Connected, "Connected", "Offline" )```

이 수식은 디바이스가 온라인 상태인지를 확인합니다. 이러한 경우 레이블 텍스트가 "연결됨"이고, 그렇지 않으면 "오프라인"입니다.

### <a name="step-6-add-a-text-input-to-compose-new-tweets"></a>6 단계: 새 트 윗을 작성 하는 텍스트 입력 추가

1. "NewTweetTextInput"이라는 새 **텍스트 입력** 컨트롤을 삽입합니다.

2. 텍스트 입력의 **재설정** 속성을 **resetNewTweet**으로 설정합니다.

### <a name="step-7-add-a-button-to-post-the-tweet"></a>7 단계: 트 윗을 게시 하는 단추 추가
1. **단추** 컨트롤을 추가하고 **Text** 속성을 "트윗"으로 설정합니다.
2. **OnSelect** 속성을 다음 수식으로 설정합니다.

    ```powerapps-dot
    If( Connection.Connected,
        Twitter.Tweet( "", {tweetText: NewTweetTextInput.Text} ),
        Collect( LocalTweetsToPost, {tweetText: NewTweetTextInput.Text} );
            SaveData( LocalTweetsToPost, "LocalTweetsToPost" )
    );
    UpdateContext( {resetNewTweet: true} );
    UpdateContext( {resetNewTweet: false} )
    ```  

이 수식은 디바이스가 온라인 상태인지를 확인합니다.

* 디바이스가 온라인 상태인 경우 해당 텍스트를 즉시 트윗합니다.
* 디바이스가 오프라인 상태인 경우 **LocalTweetsToPost** 컬렉션에서 트윗을 캡처하고, 앱에 저장합니다.

그런 다음 수식은 텍스트 상자에서 텍스트를 다시 설정합니다.

### <a name="step-8-add-a-timer-to-check-for-tweets-every-five-minutes"></a>8 단계: 5 분 마다 트 윗을 확인 하도록 타이머 추가
새 **타이머** 컨트롤을 추가합니다.

* **기간** 속성을 300000으로 설정합니다.

* **자동 시작** 속성을 true로 설정합니다.

* **OnTimerEnd**를 다음 수식으로 설정합니다.

    ```powerapps-dot
    If( Connection.Connected,
        ForAll( LocalTweetsToPost, Twitter.Tweet( "", {tweetText: tweetText} ) );
        Clear( LocalTweetsToPost);
        Collect( LocalTweetsToPost, {tweetText: NewTweetTextInput.Text} );
        SaveData( LocalTweetsToPost, "LocalTweetsToPost" );
        UpdateContext( {statusText: "Online data"} )
    )
    ```

이 수식은 디바이스가 온라인 상태인지를 확인합니다. 그러한 경우 앱은 **LocalTweetsToPost** 컬렉션에 있는 모든 항목을 트윗합니다. 그런 다음 컬렉션을 지웁니다.

이제 앱이 완료되었으므로 테스트하기 전에 모양을 확인하겠습니다. 앱이 왼쪽에서는 연결된 상태이고 오른쪽에서는 오프라인이며 다시 온라인 상태가 되면 하나의 트윗을 게시할 준비가 된 상태입니다.

![온라인 및 오프라인 모드에서 완성된 앱](./media/offline-apps/finished-app.png)

## <a name="testing-the-app"></a>앱 테스트
다음 단계를 사용하여 앱을 테스트합니다.

1. 온라인 상태인 모바일 디바이스에서 PowerApps를 실행합니다. 디바이스에 앱을 다운로드할 수 있도록 온라인 상태가 되면 앱을 한 번 이상 실행해야 합니다.
2. Twitter 앱을 시작합니다.
3. 트윗이 로드되면 상태가 **연결됨**으로 표시됩니다.
4. PowerApps를 완전히 닫습니다.
5. 디바이스를 비행기 모드로 설정하여 오프라인 상태인지 확인합니다.
6. PowerApps를 실행합니다. 이제 Twitter 앱을 오프라인으로 실행할 수 있고 온라인 상태로 이 디바이스에서 이전에 실행한 다른 모든 앱에 액세스할 수 있습니다. (예: PowerApps은 디바이스에 아직 다운로드되지 않은 앱을 숨깁니다.)
7. 앱을 다시 실행합니다.
8. **오프라인** 상태에서 연결 상태를 올바르게 반영하는 방법을 확인합니다.
9. 새 트윗을 작성합니다. 로컬로 **LocalTweetsToPost** 컬렉션에 저장됩니다.
10. 비행기 모드를 종료합니다. 타이머가 트리거된 후에 앱은 트윗을 게시합니다.

이 문서를 통해 오프라인 앱을 빌드하기 위해 PowerApps에 있는 기능을 살펴보세요. 언제든지 [포럼](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1)에 피드백을 보내고 [PowerApps 커뮤니티 블로그](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog)에서 오프라인 앱의 예제를 공유해 주세요.

