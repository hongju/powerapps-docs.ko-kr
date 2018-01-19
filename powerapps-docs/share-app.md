---
title: "앱 공유 | Microsoft Docs"
description: "다른 사용자에게 앱 실행 또는 수정 권한을 부여하여 앱 공유"
services: 
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/28/2016
ms.author: litran
ms.openlocfilehash: 1d32873009c337a835a047df38b9ef18d5bf2064
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="share-an-app-in-powerapps"></a>PowerApps에서 앱 공유
자신의 비즈니스 요구 사항을 해결하는 앱을 빌드하는 것이 좋지만 PowerApps의 진정한 마법은 해당 앱을 다른 사람들과 공유하는 데 있습니다. 이 항목에서는 특정 사용자 또는 보안 그룹과 앱을 공유하는 방법을 알아보거나 전체 조직과 공유할 수 있습니다.

## <a name="open-the-share-app-screen"></a>공유 앱 화면 열기
앱을 공유하려면 powerapps.com을 열어야 합니다. PowerApps Studio 또는 PowerApps Mobile에서는 앱 공유를 더 이상 지원하지 않습니다.

**PowerApps Studio에서**

* 옵션 1 - **파일** 메뉴에서 **공유**를 클릭하거나 탭합니다.
  
    ![파일 및 공유](./media/share-app/studio-share.png)
* 옵션 2 - **파일** 메뉴에서 **열기**, 앱에 대한 공유 아이콘을 차례로 클릭하거나 탭합니다.
  
    ![줄임표 및 공유](./media/share-app/studio-share-icon.png)

**[powerapps.com](http://web.powerapps.com)에서**

* 왼쪽 탐색 모음에서 **앱**, 줄임표(...), **공유**를 차례로 클릭하거나 탭합니다.
  
   ![포털의 줄임표](./media/share-app/portal-share.png)

## <a name="share-an-app"></a>앱 공유
여기서는 다음 단계에 따라 앱을 공유할 수 있습니다.

1. Azure Active Directory에서 하나 이상의 사용자 또는 보안 그룹의 이름을 지정하거나, 전체 조직과 앱을 공유하도록 지정합니다. 전체 조직과 공유하는 경우 **사용자** 권한만으로 공유할 수 있습니다.
   
    ![powerapps.com에서 사용자 지정](./media/share-app/portal-users.png)
2. 권한 수준을 지정합니다.
   
   * **사용자**: 사용자 또는 그룹은 앱을 실행할 수 있지만 공유할 수는 없습니다.
   * **참가자**: 사용자 또는 그룹은 앱을 실행하고, 사용자 지정하고, 사용자 지정된 버전을 다른 사용자와 공유할 수 있습니다.
     
       ![앱 공유 포털](./media/share-app/portal-permissions.png)
3. **저장**을 클릭하거나 탭합니다.

사용자 또는 그룹에 대한 사용 권한을 변경하려면 이 절차의 1단계를 반복한 후 해당 사용자 또는 그룹의 권한 목록에서 다른 옵션을 지정합니다. 사용자 또는 그룹에 대한 모든 사용 권한을 제거하려면 해당 사용자 또는 그룹에 대한 **x** 아이콘을 클릭하거나 탭합니다.

### <a name="send-email-notification"></a>전자 메일 알림 보내기
앱을 공유할 때 전자 메일을 통해 사용자 또는 보안 그룹에 알릴지 여부를 선택할 수 있습니다. 이 옵션을 선택하면 사용자, 사용자 그룹 또는 보안 그룹에 알리는 전자 메일을 보내게 됩니다. 전자 메일에는 앱에 액세스할 수 있는 링크가 포함됩니다. 필요한 경우 사용자에게 PowerApps 등록 및 설치에 관한 메시지가 표시됩니다.

앱을 공유하도록 결정한 권한에 따라 별도의 전자 메일 템플릿을 보냅니다. **사용자** 권한으로 앱을 공유하면 전자 메일에 앱을 실행하기 위한 링크가 포함됩니다. **참가자** 권한으로 앱을 공유하면 전자 메일에 PowerApps Studio에서 앱을 편집하거나 앱을 실행하기 위한 링크가 포함됩니다.

### <a name="how-do-my-users-see-the-app-i-shared"></a>내 사용자가 공유한 앱을 보려면 어떻게 해야 할까요?
하나 이상의 사용자 또는 보안 그룹과 앱을 공유한 후 앱을 볼 수 있는 방법은 앱을 공유한 권한에 따라 다릅니다.

##### <a name="if-you-shared-app-with-user-permission"></a>'사용자' 권한으로 앱을 공유한 경우
앱을 공유한 사용자는 앱 공유 화면에서 해당 확인란을 선택하면 전자 메일 알림을 받게 됩니다. 전자 메일에서 링크를 클릭하거나 탭하여 [Dynamics 365](http://home.dynamics.com)에서 앱을 실행할 수 있습니다. 곧 유니버설 링크를 지원할 예정입니다. 즉, PowerApps Studio 또는 PowerApps Mobile이 설치되어 있는 경우 이 앱은 PowerApps Studio 또는 PowerApps Mobile에서 열립니다.

또한 사용자는 [Dynamics 365](http://home.dynamics.com)의 AppSource에서 앱을 발견할 수도 있습니다(예: 전자 메일을 보내지 않은 경우). 사용자가 AppSource를 통해 앱을 얻을 수 있는 방법에 대해 [자세히 알아보세요](app-source.md).

##### <a name="if-you-shared-an-app-with-contributor-permission"></a>'참가자' 권한으로 앱을 공유한 경우
앱을 공유한 사용자는 앱 공유 화면에서 해당 확인란을 선택하면 전자 메일 알림을 받게 됩니다. 전자 메일에서는 웹용 PowerApps Studio를 사용하여 편집하기 위해 직접 앱을 여는 링크를 클릭하거나 탭할 수 있습니다. [Dynamics 365](http://home.dynamics.com)에서 앱을 실행하기 위한 링크도 있습니다. 곧 유니버설 링크를 지원할 예정입니다. 즉, PowerApps Studio 또는 PowerApps Mobile이 설치되어 있는 경우 이 앱은 PowerApps Studio 또는 PowerApps Mobile에서 열립니다.

또한 사용자는 [powerapps.com](http://web.powerapps.com)에서 앱을 발견할 수도 있습니다(예: 전자 메일을 보내지 않은 경우). 이는 앱 작성자가 자신이 만들었거나 **참가자** 권한으로 공유된 모든 앱을 탐색하는 홈입니다. 반면 [Dynamics 365](http://home.dynamics.com)는 사용자가 PowerApps 및 기타 비즈니스 앱에서 앱을 빠르게 실행할 수 있는 곳입니다.

## <a name="other-things-to-know"></a>알아야 할 기타 사항
* 앱을 공유하려면 로컬이 아닌 클라우드에 저장해야 합니다.
* 앱을 공유하기 전에 공유하려는 사용자 및 보안 그룹과 각각에 적용하려는 역할(사용자 또는 참가자)을 고려해야 합니다. 그룹에 앱을 공유한 경우 그룹의 기존 회원 및 가입하는 모든 회원이 지정된 사용 권한을 받습니다. 그룹을 떠난 사람은 액세스가 있는 다른 그룹의 회원이거나 명시적으로 사용 권한이 지정된 경우가 아니면 사용 권한을 잃게 됩니다.
* 그룹의 모든 구성원은 앱에 대해 전체 그룹과 동일한 권한을 갖습니다. 하지만 해당 그룹의 한 명 또는 그 이상의 회원에게 더 많은 사용 권한을 지정하여 더 많은 액세스를 허용할 수 있습니다. 예를 들어 사용자 권한으로 보안 그룹 A와 앱을 공유할 수 있습니다. 보안 그룹 A의 모든 구성원은 앱을 실행할 수 있습니다. 이제는 참가자 권한으로 보안 그룹 A에 속한 사용자 B와 앱을 공유합니다. 이제는 보안 그룹 A의 다른 모든 사용자가 앱을 사용할 수 있는 동안 사용자 B는 앱을 편집할 수 있습니다. 그룹의 한 명 또는 그 이상의 회원에 더 적은 사용 권한을 지정한 경우에도, 해당 회원은 전체 그룹에 부여된 사용 권한을 가집니다.
* 전체 조직과 앱을 공유할 수 있지만 모든 사람이 앱에 액세스해야 하는지를 신중하게 고려해야 합니다.
* 공유 앱에 대한 모든 변경 내용은 저장하는 즉시 공유한 사람들에게 전달됩니다. 앱을 개선하는 것은 좋지만, 기능을 제거하거나 많이 변경하면 다른 사람에게도 영향을 미칠 수 있습니다.
* 앱을 공유하기 전에 앱에 의미 있는 이름과 설명을 지정하면 사람들이 어떤 앱인지 알 수 있고 목록에서 쉽게 선택할 수 있습니다. PowerApps Studio의 **파일** 메뉴에서 **앱 설정**을 클릭하거나 탭한 다음 설명을 입력합니다.
  
  ![앱 설명](./media/share-app/description.png)

### <a name="app-sharing-and-the-resources-the-app-uses"></a>앱 공유 및 앱에서 사용하는 리소스
대부분의 앱은 다음 중 적어도 하나의 형식의 리소스에 의존합니다.

* 데이터 원본에 연결
* 온-프레미스 데이터 게이트웨이
* 사용자 지정 커넥터
* Excel 통합 문서 또는 기타 서비스
* 흐름

사용자와 참가자에게는 앱에서 사용하는 모든 데이터 연결 및 게이트웨이에 대한 권한이 필요합니다. 일부 권한은 앱과 함께 암시적으로 제공되지만, 다른 권한은 명시적으로 부여되어야 합니다. 자세한 정보는 [앱 리소스 공유](share-app-resources.md)를 참조하세요.

Common Data Service를 사용하는 앱을 공유하는 경우 Common Data Service에 대한 런타임 권한을 별도로 공유해야 한다고 나타내는 정보 표시줄을 확인합니다. 이 작업을 수행할 수 있는 권한이 없으면 환경 관리자에게 문의하세요. Common Data Service 보안에 대해 [자세히 알아보세요](database-security.md).

![공유 시의 앱 리소스](./media/share-app/app-sharing-resources.png)

### <a name="what-isnt-supported"></a>지원되지 않는 사항
* 보안 그룹에 있지만 메일 그룹에는 공유할 수 없습니다.
* 조직의 사용자와 앱을 공유할 수 있지만, 다른 테넌트의 사용자와는 공유할 수 없습니다.
* [powerapps.com](http://web.powerapps.com)에서는 앱을 공유할 수 있지만, PowerApps Studio에서는 공유할 수 없습니다. (PowerApps Studio에서 공유 아이콘을 클릭하거나 탭하여 [powerapps.com](http://web.powerapps.com)을 엽니다.)
* 앱에 대한 '참가자'('사용자' 아님) 권한이 있는 경우 해당 앱을 다시 공유할 수 있습니다.

