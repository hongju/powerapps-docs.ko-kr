---
title: DLP(데이터 손실 방지) 정책 관리 | Microsoft Docs
description: PowerApps에 대한 데이터 손실 방지 정책을 관리하는 방법을 연습합니다.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 4faa8a4cc58b138eec4e7dfe8d35b927faf905b7
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42837165"
---
# <a name="manage-data-loss-prevention-dlp-policies"></a>DLP(데이터 손실 방지) 정책 관리
조직의 데이터는 해당 조직의 성공에 중요합니다. 해당 데이터는 의사 결정을 위해 손쉽게 사용할 수 있어야 하지만, 액세스할 수 없는 대상과 공유되지 않도록 보호해야 합니다. 이 데이터를 보호하기 위해 PowerApps를 사용하여 공유 가능한 소비자 커넥터 관련 비즈니스 데이터를 정의하는 DLP(데이터 손실 방지) 정책을 만들고 적용할 수 있습니다. 예를 들어 PowerApps를 사용하는 조직은 SharePoint에 저장된 비즈니스 데이터가 Twitter 피드에 자동으로 게시되기를 원하지 않을 수 있습니다.

DLP 정책을 만들고, 편집하고, 삭제하려면 환경 관리자 또는 Azure Active Directory 테넌트 관리자 권한이 있어야 합니다. 자세한 내용은 [PowerApps에서 환경 관리](environments-administration.md)를 참조하세요.

DLP 정책을 만드는 방법에 대한 지침은 [DLP(데이터 손실 방지) 정책 만들기](create-dlp-policy.md)를 참조하세요.

## <a name="find-a-dlp-policy"></a>DLP 정책 찾기
1. [https://admin.powerapps.com]([https://admin.powerapps.com)에서 관리 센터에 로그인합니다.
2. 탐색 창에서 **데이터 정책**을 클릭하거나 탭합니다. 정책 목록이 긴 경우 **검색** 상자를 사용하여 특정 DLP 정책을 찾을 수 있습니다.

    ![](./media/prevent-data-loss/data-policies.png)

## <a name="edit-a-dlp-policy"></a>DLP 정책 편집
1. 데이터 손실 방지 정책 목록에서, 편집하려는 정책 옆에 있는 연필 아이콘을 클릭하거나 탭합니다.

    ![로그인](./media/prevent-data-loss/3.png)
2. 변경한 후 **정책 저장**을 클릭하거나 탭합니다.

    > [!NOTE]
    > 환경 DLP 정책은 테넌트 전체 DLP 정책을 재정의할 수 없습니다.
    >
    >

    변경 내용을 검토하려면 데이터 손실 방지 정책 목록에서 DLP 정책을 찾아 클릭하거나 탭하여 속성을 검토합니다.

## <a name="delete-a-dlp-policy"></a>DLP 정책 삭제
1. 데이터 손실 방지 정책 목록에서, 삭제하려는 정책 옆에 있는 쓰레기통 아이콘을 클릭하거나 탭합니다.

    ![로그인](./media/prevent-data-loss/3-delete.png)
4. 확인 대화 상자에서 **삭제**를 클릭하거나 탭합니다.

    정책이 삭제되고 더 이상 데이터 손실 방지 정책 목록에 나타나지 않습니다.

## <a name="next-steps"></a>다음 단계
* [환경에 대한 자세한 정보](environments-administration.md)
* [Microsoft PowerApps에 대한 자세한 정보](../maker/canvas-apps/getting-started.md)
