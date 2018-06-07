---
title: SharePoint 목록 내에서 앱 생성 | Microsoft Docs
description: 사이트가 온-프레미스에 있거나 클라우드에 있을 때 SharePoint 목록 내에서 항목을 관리하는 세 화면 앱을 생성합니다.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 51a13472407c5483eed7cc2c202e46855905157d
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329413"
---
# <a name="generate-an-app-from-within-sharepoint-using-powerapps"></a>PowerApps를 사용하여 SharePoint 내에서 앱 생성

PowerApps에서는 사용자가 사용자 지정 SharePoint Online 목록의 항목을 관리할 수 있는 앱이 자동으로 생성됩니다. 앱에는 사용자가 다음을 수행할 수 있는 세 개의 화면이 있습니다.

* 목록에서 모든 레코드 찾아보기(**BrowseScreen1**)
* 특정 레코드에 대한 모든 필드 보기(**DetailsScreen1**)
* 레코드 만들기 또는 편집(**EditScreen1**)

SharePoint Online 명령 모음에서 사용자 지정 목록의 앱을 만들 경우 앱이 해당 목록의 보기로 나타납니다. 웹 브라우저뿐 아니라 iOS 또는 Android 장치에서도 앱을 실행할 수 있습니다.

> [!IMPORTANT]
> PowerApps는 모든 형식의 SharePoint 데이터를 지원하지는 않습니다. 자세한 내용은 [알려진 문제](connections/connection-sharepoint-online.md#known-issues)를 참조하세요.

## <a name="generate-an-app"></a>앱 생성
1. SharePoint Online의 사용자 지정 목록을 열고, 명령 모음에서 **PowerApps**를 클릭하거나 탭한 다음 **앱 만들기**를 클릭하거나 탭합니다.

    ![앱 만들기](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)

2. 표시되는 패널에서 앱에 사용할 이름을 입력한 다음 **만들기**를 클릭하거나 탭합니다.

    ![앱 이름 지정](./media/generate-app-from-sharepoint-list-interface/app-name.png)

    SharePoint 목록에 따라 자동으로 생성되는 앱을 표시하는 새 탭이 웹 브라우저에 나타납니다. 앱이 PowerApps Studio에 나타나며 여기에서 사용자 지정할 수 있습니다.

    ![기본 앱](./media/generate-app-from-sharepoint-list-interface/default-app.png)  
3. SharePoint 목록에 대한 브라우저 탭을 클릭하거나 탭한 다음, **열기**를 클릭하거나 탭합니다.

> [!NOTE]
> 앱을 열기 전에 브라우저 창을 새로 고쳐야 할 수 있습니다(예: F5 키 누르기).

앱이 별도 브라우저 탭에서 열립니다.

## <a name="manage-the-app"></a>앱 관리
![명령 모음](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* **PowerApps에서 편집**을 클릭하거나 탭하면 PowerApps Studio에서 앱을 업데이트할 수 있는 별도 브라우저 탭에서 앱이 열립니다.

* **이 보기를 공개로 설정**을 클릭하거나 탭하면 조직의 다른 사람들이 해당 보기를 볼 수 있습니다. 기본적으로 사용자만 본인이 만든 보기를 볼 수 있습니다. 다른 사람이 앱을 편집하도록 허용하려는 경우 [이 항목을 공유](share-app.md)한 다음, **편집 가능** 사용 권한을 부여해야 합니다.

* **이 보기 제거**를 클릭하거나 탭하면 SharePoint에서 보기가 삭제됩니다. 하지만 사용자가 [해당 항목을 삭제](delete-app.md)하지 않는 한 PowerApps에서 앱은 그대로 남아 있습니다.

## <a name="next-steps"></a>다음 단계
* 기본 [갤러리](customize-layout-sharepoint.md), [양식](customize-forms-sharepoint.md) 및 [카드](customize-card.md)를 사용자 지정합니다.
