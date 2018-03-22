---
title: 환경 작업 | Microsoft Docs
description: 환경을 전환하고 페이지에서 콘텐츠를 변경하는 방법을 이해합니다.
services: ''
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: 09fdc09e305a0de9cdbc1f7d936db444dbeda321
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>환경 및 Microsoft PowerApps 관련 작업하기
PowerApps를 통해 다양한 환경에서 작업하고 환경을 쉽게 전환할 수 있습니다. 환경 개요에 대한 내용은 환경을 사용하는 이유와 환경을 만들고 관리하는 방법이 자세히 설명된 [환경 개요](../../administrator/environments-overview.md)를 참조하세요. 이 문서의 범위에서는 환경에 대해 다음 토픽을 다룹니다.

* powerapps.com의 환경을 전환하는 방법
* 적합한 환경에서 앱을 만드는 방법
* 적합한 환경에서 앱을 보는 방법

## <a name="switch-the-environment"></a>환경 전환
등록하고 powerapps.com에 처음 로그인하면 기본 환경으로 시작할 수 있습니다. 페이지의 오른쪽 위 모서리를 보면 이를 확인할 수 있습니다.

![기본 환경](./media/working-with-environments/env-dropdown.png)

기본 환경은 모든 사람이 액세스할 수 있습니다. 이 환경에서 앱 개발을 시작할 수 있으며 다른 사용자와 앱을 공유할 수 있습니다. [직접 만든](../../administrator/environments-administration.md) 환경 또는 다른 사용자가 만들었지만 액세스할 수 있는 환경과 같은 다른 환경에 액세스할 수 있습니다. 오른쪽 위 모서리에 있는 환경 드롭다운을 클릭하고 다른 환경을 선택하여 환경을 전환할 수 있습니다. 이 예제에서는 기본 환경에서 환경 1로 전환하고 있습니다.

![환경 전환](./media/working-with-environments/switch-env.png)

다른 환경(예: 환경 1)으로 전환하면 만든 앱을 모두 보거나 이와 같은 새로운 환경에서 액세스할 수 있습니다.

## <a name="create-apps-in-the-right-environment"></a>적합한 환경에서 앱 제작하기
액세스할 수 있는 기존 환경이나 새 환경에서 앱을 제작할 수 있습니다. 하지만 자신만의 환경을 만들려면 특정 플랜이 필요합니다. 자세한 내용은 [이 토픽](../../administrator/pricing-billing-skus.md)을 참조하세요. 앱을 만들기 전에 항상 **앱이 속하는 환경을 선택**해야 합니다. 그렇지 않으면 환경 간에 앱을 이동해야 합니다.

1. [powerapps.com](http://web.powerapps.com)을 사용하는 경우 앱을 만들 환경을 선택합니다. PowerApps Studio 또는 웹용 PowerApps Studio를 사용하는 경우 4단계로 건너뜁니다.

2. **+ 새 앱**을 선택합니다.

3. **PowerApps Studio 열기** 또는 **웹용 PowerApps Studio**를 선택합니다.

4. PowerApps Studio 또는 웹용 PowerApps Studio 를 열 때 오른쪽 위 모서리에서 환경을 다시 선택합니다. 차후에 이 환경을 개선할 수 있지만 현재 버전에서는 새 환경에서 앱을 만들 때마다 이 환경을 선택해야 합니다.

    ![Studio 환경 전환](./media/working-with-environments/studio-switch-env.PNG)

5. **계정** 페이지에서 현재 환경 이름 옆에 있는 **변경**을 선택합니다.

    ![Studio 환경 전환](./media/working-with-environments/studio-env-dropdown.PNG)

6. 앱을 만들 환경을 선택합니다.

    ![Studio 환경 전환](./media/working-with-environments/studio-env-dropdown2.PNG)

7. **신규**를 선택하여 앱을 제작합니다. 그러면 앱이 6단계에서 선택한 환경에 있게 됩니다.

    ![Studio 환경 전환](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>적합한 환경에서 앱 보기
[powerapps.com](http://web.powerapps.com), Windows용 PowerApps Studio에서나 웹용 PowerApps Studio에서 작업 중인지와 관계없이 보이는 앱 목록, 연결 등은 항상 드롭다운 목록에서 선택된 환경에 따라 필터링됩니다. 찾고자 하는 앱이 보이지 않으면 항상 적합한 환경이 선택되어 있는지 확인하세요.

다시 [powerapps.com](http://web.powerapps.com)에서 환경 전환:

![환경 전환](./media/working-with-environments/switch-env.png)

Windows용 PowerApps Studio 또는 웹용 PowerApps Studio에서 환경 전환:

![Studio 환경 전환](./media/working-with-environments/studio-switch-env.PNG)

환경에 대한 자세한 내용은 [이 개요](../../administrator/environments-overview.md)를 참조하세요.
