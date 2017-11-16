---
title: "환경 | Microsoft Docs"
description: "앱, 연결 및 기타 리소스를 위한 컨테이너 작업"
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: 32olG9uCmBU
courseduration: 8m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 3f17dd94359f9c6d20464662a860fd9f784991c3
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="powerapps-environments"></a>PowerApps 환경
지금까지의 과정을 따랐다면 web.powerapps.com에서 작업하는 데 약간의 시간을 보냈습니다. 특히 알고 있는지 여부에 상관 없이 특정 *환경*에서 작업하는 데 전체 시간을 보냈습니다. 환경은 단순히 앱과 기타 리소스를 그룹화한 것이며, 잠시 후에 자세히 살펴보겠습니다. web.powerapps.com에서 화면의 오른쪽 위를 보면 현재 환경을 보여 주는 드롭다운 메뉴가 있습니다.

![환경 선택](./media/learning-manage-environments/environment-picker.png)

PowerApps를 처음 사용하는 경우 이 시점에서 기본 환경만 있을 수 있습니다. 사용할 수 있는 다른 환경이 있는지 확인하려면 메뉴를 클릭하거나 탭합니다.

## <a name="why-use-environments"></a>환경을 사용하는 이유는?
환경은 Microsoft Flow의 데이터 연결 및 흐름과 같은 앱 및 기타 리소스의 컨테이너입니다. 이는 비즈니스 요구 사항에 따라 항목을 그룹화하는 방법입니다. 기본 환경 외에도 추가 환경을 만드는 데에는 몇 가지 이유가 있습니다.

* **부서별로 분리된 앱 개발**: 대기업에서는 각 부서마다 서로 다른 환경에서 작업할 수 있습니다.
* **ALM(Application Lifecycle Management) 지원**: 개발 중인 앱과 이미 완료하여 공유한 앱에 대해 별도의 환경을 갖출 수 있습니다.
* **데이터 액세스 관리**: 각 환경에는 자체의 Common Data Service 데이터베이스가 있을 수 있으며 다른 데이터 연결은 환경에 따라 다릅니다(즉 환경 간에 공유되지 않음).

환경은 앱 작성자와 PowerApps 관리자에게만 관련이 있음을 명심해야 합니다. 앱을 사용자와 공유하는 경우 해당 사용자는 올바른 권한을 가지고 있는 동안에는 앱을 실행할 수 있습니다. 앱이 어떤 환경에서 제공되는지에 대해서는 걱정할 필요가 없습니다.

## <a name="create-an-environment"></a>환경 만들기
지금까지 이 과정에서는 앱 작성자에 집중했지만 관리자는 환경을 만들고 관리합니다. 관리자가 아닌 경우 환경 설정에 대해 관리자에게 문의할 때 이 정보가 도움이 될 수 있습니다. PowerApps 관리 센터에서 **환경**, **새 환경**을 차례로 클릭하거나 탭합니다. **새 환경** 화면에서 환경 이름을 입력하고, 지역을 선택하고, 환경에 대한 Common Data Services 데이터베이스를 만들지 여부를 선택한 다음 **환경 만들기**를 클릭하거나 탭합니다.

![환경 만들기](./media/learning-manage-environments/create-environment.png)

이것으로 끝입니다. 이제는 새로운 환경에서 작업할 수 있습니다. web.powerapps.com으로 돌아가면 환경 드롭다운 메뉴에서 새 환경이 표시됩니다.

## <a name="manage-access-to-an-environment"></a>환경에 대한 액세스 관리
환경에 액세스할 수 있는 사용자는 다음과 같습니다.

* **환경 관리자**: 환경에 대한 모든 권한을 가집니다.
* **환경 작성자**: 모든 앱을 보고, 앱을 만들고, Common Data Service를 사용할 수 있습니다(다른 권한이 적용됨).

관리자는 **환경** 탭에서 환경에 대한 액세스 권한을 부여합니다. 먼저 환경을 클릭하거나 탭합니다. 다른 사용자(이 예에서는 **환경 작성자**)를 추가하려면 **환경 역할**, **환경 작성자**를 차례로 클릭하거나 탭합니다. 여기서 사용자 또는 그룹을 역할에 추가하고 **저장**을 클릭합니다.

![환경 액세스 관리](./media/learning-manage-environments/environment-access.png)

이제는 환경의 이점과 환경을 만드는 방법을 이해하고 환경에 대한 액세스 권한을 부여합니다. 관리자 역할을 맡지 않더라도 이 기능이 작동하는 방식을 알아 두면 도움이 됩니다. 이제 앱 관리 섹션의 끝 부분에 있으며, Common Data Service에 초점을 맞춘 다음 섹션인 "데이터 관리"로 이동할 준비가 되었습니다.

