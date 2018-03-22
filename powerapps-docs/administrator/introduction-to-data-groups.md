---
title: 데이터 그룹 | Microsoft Docs
description: Microsoft PowerApps용 데이터 그룹을 소개합니다.
services: powerapps
suite: powerapps
documentationcenter: na
author: manasmams
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 19b341d72ccc29194b2987b8489ff74ad7798f37
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="learn-all-about-data-groups"></a>데이터 그룹에 대해 모두 알아보기
데이터 그룹은 [DLP(데이터 손실 방지) 정책](prevent-data-loss.md) 내에서 서비스를 범주화하는 단순한 방법입니다. 사용 가능한 두 데이터 그룹에는 **비즈니스 데이터만**과 **비즈니스 데이터 허용 안 됨** 그룹이 있습니다. 조직은 특정 데이터 그룹에 배치되는 서비스를 자유롭게 결정할 수 있습니다. 서비스를 분류하는 좋은 방법은 조직에 미치는 영향력에 따라 그룹에 배치하는 것입니다. 기본적으로 모든 서비스는 **비즈니스 데이터 허용 안 됨** 데이터 그룹에 배치됩니다. 관리 센터에서 DLP 정책의 수정을 만들거나 수정할 때 데이터 그룹의 서비스를 관리합니다.

## <a name="how-data-is-shared-between-data-groups"></a>데이터 그룹 간에 데이터를 공유하는 방식
서로 다른 그룹에 있는 서비스 간에 데이터를 공유할 수 없습니다. 예를 들어 SharePoint와 Salesforce를 **비즈니스 데이터만** 그룹에 배치하고 Facebook과 Twitter를 **비즈니스 데이터 허용 안 됨** 그룹에 배치하면 SharePoint와 Facebook 사이에 데이터를 이동하는 PowerApp을 만들 수 없습니다. 서로 다른 그룹의 서비스 간에 데이터를 공유할 수 없지만, 특정 그룹 내 서비스 간에 데이터는 공유할 수 있습니다. 따라서 이전 예로 돌아가서 SharePoint와 Salesforce가 동일한 데이터 그룹에 배치되었으므 최종 사용자가 만드는 PowerApps는 SharePoint와 Salesforce 간에 데이터를 공유할 수 있습니다. 핵심 요점은 다른 그룹의 서비스는 데이터를 공유할 수 없지만, 특정 그룹의 서비스는 데이터를 공유할 수 있다는 것입니다.

또한, 하나는 데이터 그룹이 *기본* 그룹으로 지정되어야 합니다. 처음에 **비즈니스 데이터 허용 안 됨** 그룹은 *기본* 그룹이며 모든 서비스가 데이터 그룹에 있습니다. 관리자는 기본 데이터 그룹을 **비즈니스 데이터만** 데이터 그룹으로 변경할 수 있습니다. > [!NOTE]
> PowerApps에 추가되는 새로운 서비스는 지정된 *기본* 그룹에 배치됩니다. 이러한 이유로 **비즈니스 데이터 허용 안 됨**을 기본 그룹으로 유지하고 조직이 데이터 데이터를 새 서비스와 공유하도록 허용함으로써 발생하는 영향을 평가한 후에 서비스를 **비즈니스 데이터만** 그룹으로 수동으로 추가하는 것이 좋습니다.

## <a name="add-services-to-a-data-group"></a>데이터 그룹에 서비스 추가
이 연습에서는 SharePoint와 Salesforce를 데이터 손실 방지(DLP) 정책의 **비즈니스 데이터만** 데이터 그룹에 추가하려고 합니다.

1. DLP 정책의 **비즈니스 데이터만** 그룹 상자 내부에 있는 **+ 추가** 링크를 선택합니다.    
   ![이미지 추가](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. SharePoint와 Salesforce를 선택하고 **서비스 추가**를 선택하여 비즈니스 데이터만 그룹에 둘 다 추가합니다.    
   ![서비스 이미지 추가](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. 맨 위의 메뉴에서 **정책 저장**을 선택합니다.  
   ![정책 저장](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. SharePoint와 Salesforce는 이제 비즈니스 데이터만 그룹에 있습니다.  
   ![업데이트된 비즈니스 데이터 그룹](./media/introduction-to-data-groups/add-to-data-group-3.png)   

이 연습에서는 SharePoint와 Salesforce를 DLP 정책의 **비즈니스 데이터만** 데이터 그룹에 추가했습니다. DLP 정책의 환경에 속하는 사람 중 한 명이 SharePoint 또는 Salesforce와 **비즈니스 데이터 허용 안 됨** 데이터 그룹의 서비스 간에 앱 공유 데이터를 만들 경우 해당 앱은 실행할 수 없습니다.

## <a name="remove-services-from-a-data-group"></a>데이터 그룹에서 서비스 제거
모든 서비스는 사용 가능한 데이터 그룹 중 하나에 있어야 하므로, 특정 그룹에서 서비스를 제거하려면 해당 서비스를 다른 그룹에 추가한 후 정책을 저장하면 됩니다.  

## <a name="change-the-default-data-group"></a>기본 데이터 그룹 변경
이 연습에서는 **비즈니스 데이터 허용 안 됨** 데이터 그룹의 기본 데이터 그룹을 **비즈니스 데이터만** 데이터 그룹으로 변경하려고 합니다.  

> [!IMPORTANT]
> PowerApps에 추가되는 새로운 서비스는 지정된 *기본* 그룹에 배치됩니다. 이러한 이유로 **비즈니스 데이터 허용 안 됨**을 기본 그룹으로 유지하고 서비스를 **비즈니스 데이터만** 그룹으로 수동으로 추가하는 것이 좋습니다.

1. 기본 데이터 그룹으로 지정하려는 데이터 그룹의 오른쪽 모서리에 있는 **...**를 선택합니다.    
   ![기본 그룹 변경](./media/introduction-to-data-groups/default-data-group-0.png)  
2. **기본 그룹으로 설정**을 선택합니다.  
   ![기본 그룹 변경](./media/introduction-to-data-groups/default-data-group-1.png)   
3. 맨 위의 메뉴에서 **정책 저장**을 선택합니다.  
   ![기본 그룹 변경](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. 이제 데이터 그룹이 기본 데이터 그룹으로 지정되어 있습니다.  
   ![기본 그룹 변경](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>다음 단계
* [DLP(데이터 손실 방지) 정책에 대한 자세한 정보](prevent-data-loss.md)
* [환경에 대한 자세한 정보](environments-overview.md)
* [Microsoft PowerApps에 대한 자세한 정보](../maker/canvas-apps/getting-started.md)
