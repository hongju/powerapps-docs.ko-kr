---
title: 모델 기반 샘플 앱
description: 모델 기반 샘플 앱을 가져오고, 사용자 지정 및 제거하는 방법을 이해합니다.
documentationcenter: na
author: caburk
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: caburk
ms.openlocfilehash: c9525827c7e8e48c0f5e68e3608c9b6b9f630121
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31831266"
---
# <a name="model-driven-sample-apps"></a>모델 기반 샘플 앱

[powerapps.com](https://powerapps.com)에서, 샘플 앱을 사용하여 디자인 기술을 알아보고 고유 앱을 개발하는 경우 적용할 수 있는 개념을 검색합니다. 각 샘플 앱은 가상 데이터를 사용하여 실제 업무 시나리오를 보여줍니다. 

자세한 내용은 각 샘플 앱에 대한 설명서를 확인해 보세요. 

![모금 행사 샘플 앱](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>샘플 앱 가져오기

모델 기반 샘플 앱을 재생하거나 편집하기 위해 먼저 앱을 Common Data Service 데이터베이스로 프로비전해야 합니다. 먼저 평가판 환경 및 데이터베이스를 만들고, **샘플 앱 및 데이터를 포함**했는지 확인합니다.

![데이터베이스 만들기](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> 이 옵션은 데이터베이스에서 사용 가능한 모든 샘플 앱을 설치합니다. 샘플 앱은 교육 및 데모용이며, 프로덕션 데이터베이스에 설치하는 것은 권장하지 않습니다. 

## <a name="customize-a-sample-app"></a>샘플 앱 사용자 지정

1. [powerapps.com](https://powerapps.com)에 로그인하고 디자인 모드에 대해 **모델 기반**을 선택합니다. 

    ![디자인 모드 선택](media/overview-model-driven-samples/choose-design-mode.png)

2. 홈페이지에서 샘플 앱을 마우스로 가리키고 **사용자 지정**을 클릭합니다.
3. 앱을 사용자 지정하기 위한 여러 옵션을 제공하는 앱 디자이너가 열립니다. 
4. 추가 사용자 지정 옵션은 포털의 왼쪽 탐색 창에서 **고급**을 클릭합니다.

## <a name="remove-sample-apps-and-data"></a>샘플 앱 및 데이터 제거 
- 샘플 앱을 삭제하려면 해당하는 [관리 솔루션](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution)도 삭제해야 합니다. 
- 솔루션을 삭제하면 앱에 대한 사용자 지정 엔터티별 샘플 데이터도 삭제됩니다.
- 샘플 앱을 사용자 지정한 경우 솔루션을 삭제하기 전에 제거해야 하는 [종속성](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components)이 있을 수 있습니다.

### <a name="steps"></a>단계
1. [PowerApps 관리 포털](https://admin.powerapps.com)에 로그인합니다.

2. 환경을 선택합니다.

3. **Dynamics 365 관리 센터**를 클릭합니다. 

    ![Dynamics 365 관리 센터](media/overview-model-driven-samples/admin-center.png)

4. 목록에서 데이터베이스를 선택하고 **열기**를 클릭합니다.

    ![데이터베이스 선택](media/overview-model-driven-samples/select-database.png)

5. **설정/솔루션**으로 이동합니다.

6. 삭제할 앱에 대한 솔루션을 선택하고 **삭제**를 클릭합니다.

    ![솔루션삭제](media/overview-model-driven-samples/delete-solution.png)

*Maker 포털에서 **고급**을 클릭하여 솔루션 목록으로 이동하고 .dynamics.com/ 뒤에 있는 URL에서 모든 항목을 삭제합니다.*

> [!IMPORTANT]
> 영향에 대해 알지 못하는 경우 다른 시스템 솔루션을 삭제하지 마십시오.

## <a name="install-or-uninstall-sample-data"></a>샘플 데이터 설치 또는 제거
1. 위의 1-4단계를 수행합니다.
2. **설정/데이터 관리/샘플 데이터**로 이동합니다.
3. 샘플 데이터가 설치되어 있는 경우 제거 옵션을 사용할 수 있습니다. 그렇지 않을 경우 설치 옵션을 사용할 수 있습니다. 

    ![샘플 데이터 삭제](media/overview-model-driven-samples/remove-sample-data.png)




