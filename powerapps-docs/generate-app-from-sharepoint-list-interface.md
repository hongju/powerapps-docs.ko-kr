---
title: "SharePoint 목록 내에서 앱 생성 | Microsoft Docs"
description: "사이트가 온-프레미스에 있거나 클라우드에 있을 때 SharePoint 목록 내에서 항목을 관리하는 세 화면 앱을 생성합니다."
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/21/2017
ms.author: sharik
ms.openlocfilehash: 8ac8fb34f9cdeb0c9e0ce6172938cef33ecccbc5
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="generate-an-app-from-within-sharepoint-using-powerapps"></a>PowerApps를 사용하여 SharePoint 내에서 앱 생성



PowerApps에서는 사용자가 사용자 지정 SharePoint Online 목록의 항목을 관리할 수 있는 앱이 자동으로 생성됩니다. 앱에는 사용자가 다음을 수행할 수 있는 세 개의 화면이 있습니다.

* 목록에서 모든 레코드 찾아보기(**BrowseScreen1**)
* 특정 레코드에 대한 모든 필드 보기(**DetailsScreen1**)
* 레코드 만들기 또는 편집(**EditScreen1**)

SharePoint Online 명령 모음에서 사용자 지정 목록의 앱을 만들 경우 앱이 해당 목록의 보기로 나타납니다. 웹 브라우저뿐 아니라 Windows Phone, iOS 또는 Android 장치에서도 앱을 실행할 수 있습니다.

> [!IMPORTANT]
> PowerApps는 모든 형식의 SharePoint 데이터를 지원하지는 않습니다. 자세한 내용은 [알려진 문제](connections/connection-sharepoint-online.md#known-issues)를 참조하세요.

## <a name="generate-an-app"></a>앱 생성
1. SharePoint Online의 사용자 지정 목록을 열고, 명령 모음에서 **PowerApps**를 클릭하거나 탭한 다음 **앱 만들기**를 클릭하거나 탭합니다.
   
    ![](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)
2. 표시되는 패널에서 앱에 사용할 이름을 입력한 다음 **만들기**를 클릭하거나 탭합니다.
   
    ![](./media/generate-app-from-sharepoint-list-interface/enter-app-name.png)
   
    SharePoint 목록에 따라 자동으로 생성되는 앱을 표시하는 새 탭이 웹 브라우저에 나타납니다.
   
    ![](./media/generate-app-from-sharepoint-list-interface/powerapp-studio-for-web.png)  
3. SharePoint 목록에 대한 브라우저 탭을 클릭하거나 탭한 다음, **열기**를 클릭하거나 탭합니다.
   
    > [!NOTE]
> 앱을 열기 전에 브라우저 창을 새로 고쳐야 할 수 있습니다(예: F5 키 누르기).
   
    ![](./media/generate-app-from-sharepoint-list-interface/open-app-in-browser.png)
   
    앱이 별도 브라우저 탭에서 열립니다.
   
    ![](./media/generate-app-from-sharepoint-list-interface/open-app.png)

## <a name="manage-the-app"></a>앱 관리
![](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* **PowerApps에서 편집**을 클릭하거나 탭하면 웹용 PowerApps Studio에서 앱을 업데이트할 수 있는 별도 브라우저 탭에서 앱이 열립니다.
* **이 보기를 공개로 설정**을 클릭하거나 탭하면 조직의 다른 사람들이 해당 보기를 볼 수 있습니다. 기본적으로 사용자만 본인이 만든 보기를 볼 수 있습니다. 다른 사람이 앱을 편집하도록 허용하려는 경우 [이 항목을 공유](share-app.md)한 다음, **참가자** 사용 권한을 부여해야 합니다.
* **이 보기 제거**를 클릭하거나 탭하면 SharePoint에서 보기가 삭제됩니다. 하지만 사용자가 [해당 항목을 삭제](delete-app.md)하지 않는 한 PowerApps에서 앱은 그대로 남아 있습니다.

## <a name="next-steps"></a>다음 단계
* 목록에 항목을 추가하거나 업데이트하려면 [SharePoint Online 목록에서 앱 열기](open-app-embedded-in-sharepoint.md)의 “앱을 사용하여 목록 관리” 섹션을 참조하세요.
* 찾아보기 화면(기본으로 나타남)을 사용자 지정하려면 [레이아웃 사용자 지정](customize-layout-sharepoint.md)을 참조하세요.
* 세부 정보를 사용자 지정하거나 화면을 편집하려면 [양식 사용자 지정](customize-forms-sharepoint.md)을 참조하세요.
* 앱을 삭제하려면 SharePoint에서 보기를 제거한 다음, PowerApps에서 [해당 앱을 삭제](delete-app.md)합니다.

