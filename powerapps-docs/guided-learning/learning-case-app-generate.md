---
title: "앱 생성(Common Data Service) | Microsoft Docs"
description: "Common Data Service에서 3개 화면 앱 생성"
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: Gi5TQF7_pz8
courseduration: 6m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 64e34da9afcecde950094ff40808c99176bccc13
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="generate-an-app-common-data-service"></a>앱 생성(Common Data Service)
이 섹션에서는 Common Data Service에서 *엔터티*를 기반으로 하여 앱을 만듭니다. 엔터티는 수정, 저장, 검색 및 상호 작용할 수 있는 공유 데이터 청크입니다. 엔터티에서 앱을 생성하고, 앱을 사용자 지정하는 방법을 보여 주고, 다른 데이터 원본을 추가하고, 앱에서 흐름을 호출합니다. SharePoint 목록에서 앱을 만드는 방법에 대한 섹션을 이미 완료한 경우 동일한 영역의 일부, 특히 앱 사용자 지정과 관련된 내용을 더 자세히 설명합니다.

IT 부서에서 조직 전체의 하드웨어 및 소프트웨어 문제를 추적하고, 우선 순위를 지정하고, 조치를 취하는 데 사용할 수 있는 사례 관리 앱을 만들겠습니다. 항목을 진행하면서 이러한 앱의 다른 용도에 대해 생각해 볼 수도 있습니다. 앱 데이터를 저장하는 데 적합하기 때문에 Common Data Service의 데이터를 사용하지만 다른 데이터 원본을 사용하더라도 동일한 앱을 빌드할 수 있습니다.

PowerApps에는 빌드할 앱과 동일한 엔터티를 사용하는 보다 복잡한 사례 관리 템플릿이 포함되어 있습니다. 이 섹션을 완료한 후에는 해당 템플릿을 탐색하여 PowerApps에서 빌드할 수 있음을 이해하는 것이 좋습니다.

## <a name="create-a-common-data-service-database"></a>Common Data Service 데이터베이스 만들기
이 앱을 빌드하는 첫 번째 단계는 Common Data Service 데이터베이스가 없는 경우 이 데이터베이스를 만드는 것입니다. *환경*에서 Common Data Service 데이터베이스를 만듭니다. 환경은 앱 및 기타 리소스를 위한 컨테이너이며, 과정의 뒷부분에서 환경에 대해 자세히 설명합니다. *환경 관리자*는 이 단계에 따라 데이터베이스를 만들 수 있습니다. 관리자가 아닌 경우 조직의 관리자에게 문의하세요.

**홈** 탭에서 **데이터베이스 만들기**를 클릭합니다.

![Common Data Service 데이터베이스 만들기](./media/learning-case-app-generate/create-database.png)

데이터베이스에 대한 액세스를 제한할 것인지 또는 계속 열어 둘 것인지를 지정하고 **데이터베이스 만들기**를 클릭합니다.

![Common Data Service에서 액세스 지정](./media/learning-case-app-generate/specify-access.png)

프로세스가 완료되면 공통 데이터 모델에 포함된 표준 엔터티가 모두 표시됩니다. 그 중 일부는 다음과 같습니다.

![Common Data Service 표준 엔터티](./media/learning-case-app-generate/standard-entities.png)

## <a name="generate-an-app-from-the-case-entity"></a>사례 엔터티에서 앱 생성
이제 데이터베이스가 만들어졌으므로 사례 엔터티에 연결하여 앱을 생성합니다. **새 앱**을 클릭한 다음 **웹용 PowerApps Studio**를 클릭합니다.

![웹용 PowerApps Studio의 새 앱](./media/learning-case-app-generate/choose-studio.png)

Common Data Service 엔터티를 위한 휴대폰 앱을 빌드하고 있으므로 **Common Data Service**에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.

![Common Data Service의 휴대폰 앱](./media/learning-case-app-generate/common-phone.png)

다음 화면에서 연결할 연결과 엔터티를 선택한 다음 **연결**을 클릭합니다.

![사례 엔터티에 연결](./media/learning-case-app-generate/connect-entity.png)

**연결**을 클릭하면 PowerApps에서 앱을 생성하기 시작합니다. PowerApps는 유용한 정보를 시작 지점으로 생성할 수 있도록 데이터에 대한 모든 종류의 추론을 만듭니다.

## <a name="view-the-app-in-powerapps-studio"></a>PowerApps Studio에서 앱 보기
PowerApps Studio에서 새로운 3개 화면 앱이 열립니다. 데이터에서 생성된 모든 앱에는 다음과 같은 동일한 화면 집합이 있습니다.

* **찾아보기** 화면: 목록에서 가져온 데이터를 탐색, 정렬, 필터링 및 새로 고침을 수행하고, (+) 아이콘을 클릭하여 항목을 추가할 수 있습니다.
* **세부 정보** 화면: 항목에 대한 세부 정보를 보고 항목을 삭제하거나 편집할 수 있습니다.
* **편집/만들기** 화면: 기존 항목을 편집하거나 새 항목을 만들 수 있습니다.

왼쪽 탐색 모음에서 오른쪽 위 모서리의 아이콘을 클릭하거나 탭하여 썸네일 보기로 전환합니다.

![보기 토글](./media/learning-case-app-generate/toggle-view.png)

각 썸네일을 클릭하거나 탭하여 해당 화면의 컨트롤을 봅니다.

![생성된 앱](./media/learning-case-app-generate/finished-app.png)

다음으로 앱을 더 자세히 살펴보고, 요구 사항에 더 부합하게 앱을 사용자 지정하겠습니다.

