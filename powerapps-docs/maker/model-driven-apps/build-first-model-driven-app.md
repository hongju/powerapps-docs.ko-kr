---
title: PowerApps를 사용하여 처음부터 첫 번째 모델 기반 앱을 빌드하기 위한 빠른 시작 | Microsoft Docs
description: 간단한 모델 기반 앱을 빌드하는 방법 알아보기
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
ms.openlocfilehash: c1c03202cb95500bb019a3c23a68e0e8d5418cc9
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898401"
---
# <a name="quickstart-build-your-first-model-driven-app-from-scratch"></a>빠른 시작: 처음부터 첫 번째 모델 기반 앱 빌드
모델 기반 앱 디자인은 앱 개발에 대해 구성 요소에 중점을 두는 방법입니다. 이 빠른 시작에서는 [!INCLUDE [powerapps](../../includes/powerapps.md)] 환경에서 사용할 수 있는 표준 엔터티 중 하나를 사용하여 모델 기반 앱을 만드는 방법을 간소화합니다. 

## <a name="sign-in-to-powerapps"></a>PowerApps에 로그인
[PowerApps](https://web.powerapps.com/)에 로그인합니다. [!INCLUDE [powerapps](../../includes/powerapps.md)] 계정이 아직 없다면 **무료 시작** 링크를 선택합니다. 

## <a name="create-your-model-driven-app"></a>모델 기반 앱 만들기

1. 원하는 환경을 선택하거나 [PowerApps 관리 센터](https://admin.powerapps.com/)로 이동하여 새 환경을 만듭니다.
2. 왼쪽 탐색 창에서 **모델 기반**을 선택합니다. 

   ![모델 기반](media/build-first-model-driven-app/choose-design-mode.png)

   > [!IMPORTANT]
   > **모델 기반** 디자인 모드를 사용할 수 없는 경우 [환경을 만들](https://docs.microsoft.com/powerapps/administrator/create-environment)어야 할 수 있습니다.   

3. 왼쪽 창에서 **앱**을 선택한 다음, **앱 만들기**를 선택합니다.

4. **새 앱 만들기** 페이지에서 다음 세부 정보를 입력한 후, **완료**를 선택합니다. 
   - **이름**: *Myfirstapp*과 같은 앱의 이름을 입력합니다. 
   - **설명**: ‘첫 번째 앱’과 같은 앱의 개념이나 수행 작업에 대한 간단한 설명을 입력합니다.
   추가 앱 속성에 대한 자세한 내용은 [앱 만들기](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app)를 참조하세요.
 
   ![Create-new-app](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>앱에 구성 요소 추가
앱 디자이너에서 앱에 구성 요소를 추가합니다.
1. **사이트 맵 디자이너 열기** 화살표를 선택하여 사이트 맵 디자이너를 엽니다. 

   ![Create-new-sitemap](media/build-first-model-driven-app/new-sitemap.png)

2. 사이트 맵 디자이너에서 **새 하위 영역**을 선택하고, 오른쪽 창에서 **속성** 탭을 선택한 후, 다음 속성을 선택합니다.
   - **형식**: 엔터티
   - **엔터티**: 계정

   ![사이트 맵에 구성 요소 추가](media/build-first-model-driven-app/sitemap.png)

3. **저장 후 닫기**를 선택합니다.
4. 앱 디자이너 캔버스에서 **양식**을 선택한 다음, **기본 양식** 그룹 아래의 오른쪽 창에서 **계정** 양식을 선택합니다.

   ![계정 기본 양식](media/build-first-model-driven-app/main-form.png)

5. 앱 디자이너 캔버스에서 **보기**를 선택한 다음, **활성 계정**, **모든 계정** 및 **내 활성 계정** 보기를 선택합니다.

   ![계정 보기](media/build-first-model-driven-app/views.png)

6. 앱 디자이너 캔버스에서 **차트**를 선택한 다음, **산업별 계정** 차트를 선택합니다.
7. 앱 디자이너 도구 모음에서 **저장**을 선택합니다.

    ![앱 디자이너 도구 모음 저장](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>앱 게시
앱 디자이너 도구 모음에서 **게시**를 선택합니다.

앱을 게시한 후에는 앱을 실행하거나 다른 사용자와 공유할 수 있습니다.

![단순 계정 엔터티 앱](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>다음 단계
이 빠른 시작에서는 간단한 모델 기반 앱을 빌드했습니다. 앱을 실행할 때 앱이 어떻게 표시되는지 확인하려면 [빠른 시작: 모바일 장치에서 모델 기반 앱 실행](../../user/run-app-client-model-driven.md)을 참조하세요.
앱을 공유하는 방법을 알아보려면 모델 기반 앱을 공유하는 방법에 대한 자습서인 [모델 기반 앱 공유](share-model-driven-app.md)를 계속 진행하세요.
