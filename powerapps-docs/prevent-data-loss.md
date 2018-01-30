---
title: "DLP(데이터 손실 방지) 정책 | Microsoft Docs"
description: "Microsoft PowerApps에 대한 데이터 손실 방지 정책을 소개합니다."
services: 
suite: powerapps
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/28/2016
ms.author: deonhe
ms.openlocfilehash: a9f6bf12672c425a30d05a8072aafd34945eb795
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="data-loss-prevention-dlp-policies"></a>DLP(데이터 손실 방지) 정책

조직의 데이터는 해당 조직의 성공에 중요합니다. 해당 데이터는 의사 결정을 위해 손쉽게 사용할 수 있어야 하지만, 액세스할 수 없는 대상과 공유되지 않도록 보호해야 합니다. Microsoft PowerApps(PowerApps)는 이 데이터를 보호하기 위해 특정 비즈니스 데이터를 공유할 수 있는 소비자 서비스/커넥터를 정의하는 정책을 만들고 적용하는 기능을 제공합니다. 데이터를 공유할 수 있는 방법을 정의하는 이러한 정책을 DLP(데이터 손실 방지) 정책이라고 합니다.  

## <a name="why-create-a-dlp-policy"></a>DLP 정책을 만드는 이유는?
DLP 정책을 만들어 공유할 수 있는 소비자 서비스 비즈니스 데이터를 명확하게 정의합니다. 예를 들어 PowerApps를 사용하는 조직은 SharePoint에 저장된 비즈니스 데이터가 Twitter 피드에 자동으로 게시되기를 원하지 않을 수 있습니다. 이를 방지하기 위해 SharePoint 데이터가 트윗의 원본으로 사용되지 않도록 차단하는 DLP 정책을 만들 수 있습니다.

DLP 정책의 이점:
* 데이터가 조직 전체에서 일관되게 관리되도록 합니다.  
* 중요한 비즈니스 데이터가 실수로 소셜 미디어 사이트와 같은 서비스에 게시되지 않도록 방지합니다.   

## <a name="managing-dlp-policies"></a>DLP 정책 관리
### <a name="prerequisites"></a>필수 조건
DLP 정책을 생성, 편집 또는 삭제하려면 다음 항목이 필요합니다.

* 환경 관리자 또는 테넌트 관리자 권한 - [환경 항목](environments-administration.md)에서 권한에 대해 자세히 알아볼 수 있습니다.

### <a name="create-a-dlp-policy"></a>DLP 정책 만들기
DLP 정책을 만들려면 하나 이상의 환경에 대한 권한이 있어야 합니다.  

다음 단계에 따라 SharePoint 데이터베이스에 저장된 데이터가 Twitter에 게시되지 못하도록 방지하는 DLP 정책을 만듭니다.  

1. [데이터 정책] 탭에서 **새 정책** 링크를 선택합니다.  
   ![로그인](./media/prevent-data-loss/create-policy-1.png)    
2. 열린 페이지 위쪽의 **데이터 정책 이름** 레이블에서 DLP 정책 이름을 *Contoso에 대한 보안 데이터 액세스*로 입력합니다.   
   ![로그인](./media/prevent-data-loss/create-policy-2.png)  
3. **적용 대상** 탭에서 [환경](environments-administration.md)을 선택합니다.  
   ![로그인](./media/prevent-data-loss/create-policy-3.png)  
4. **데이터 그룹** 탭을 선택합니다.  
   ![로그인](./media/prevent-data-loss/create-policy-4.png)  
5. **비즈니스 데이터만** 그룹 상자 안에 있는 **+ 추가** 링크를 선택합니다.    
   ![로그인](./media/prevent-data-loss/create-policy-5.png)  
6. **서비스 추가** 페이지에서 **SharePoint** 및 **Salesforce** 서비스를 선택합니다.  
   ![로그인](./media/prevent-data-loss/create-policy-6.png)  
7. **서비스 추가** 단추를 선택하여 비즈니스 데이터를 공유하도록 허용된 서비스 목록에 선택한 서비스를 추가합니다.    
   ![로그인](./media/prevent-data-loss/create-policy-7.png)  
8. **정책 저장**을 선택합니다.  
   ![로그인](./media/prevent-data-loss/create-policy-8.png)  
9. 잠시 후에 데이터 손실 방지 정책 목록에 새 DLP 정책이 표시됩니다.  
   ![로그인](./media/prevent-data-loss/create-policy-9.png)  
10. **선택 사항** 팀에 전자 메일 또는 기타 통신을 보내어 새 DLP 정책을 지금 사용할 수 있음을 알려줍니다.

축하합니다! 이제 앱에서 SharePoint와 Salesforce 간에 데이터를 공유하지만 다른 서비스와는 데이터를 공유하지 못하도록 차단할 수 있는 DLP 정책을 만들었습니다.  

### <a name="find-a-dlp-policy"></a>DLP 정책 찾기
#### <a name="admins"></a>관리자
관리자는 관리 센터에서 검색 기능을 사용하여 특정 DLP 정책을 찾을 수 있습니다.  

> [!NOTE]
> 관리자는 조직의 사용자가 PowerApps를 만들기 전에 정책을 인식할 수 있도록 모든 DLP 정책을 게시해야 합니다.

#### <a name="makers"></a>작성자
관리자 권한이 없지만 조직의 DLP 정책에 대해 자세히 알아보려면 관리자에게 문의하세요. 또한 [작성자 환경 항목](environments-overview.md)에서도 자세히 알아볼 수 있습니다.  

> [!NOTE]
> 관리자만 DLP 정책을 편집하거나 삭제할 수 있습니다.  

### <a name="edit-a-dlp-policy"></a>DLP 정책 편집
1. https://admin.powerapps.com을 방문하여 관리 센터를 시작합니다.   
2. 시작된 관리 센터에서 왼쪽의 **데이터 정책** 링크를 선택합니다.  
   ![로그인](./media/prevent-data-loss/2.png)  
3. 기존 DLP 정책 목록을 검색하고 편집하려는 정책 옆에 있는 편집 링크를 선택합니다.  
   ![로그인](./media/prevent-data-loss/3.png)  
4. 원하는 대로 변경합니다. 예를 들어 데이터 그룹에서 환경 또는 서비스를 수정할 수 있습니다.  
5. 변경 내용을 저장하려면 **정책 저장**을 선택합니다.  
   ![로그인](./media/prevent-data-loss/create-policy-8.png)  

이제 정책이 업데이트되었습니다. 데이터 손실 방지 정책 목록에서 항목을 찾고 해당 속성을 검토하여 변경 내용이 정책에 적용되었는지 확인할 수 있습니다.   

### <a name="delete-a-dlp-policy"></a>DLP 정책 삭제
1. https://admin.powerapps.com을 방문하여 관리 센터를 시작합니다.    
2. 시작된 관리 센터에서 왼쪽의 **데이터 정책** 링크를 선택합니다.  
   ![로그인](./media/prevent-data-loss/2.png)  
3. 기존 DLP 정책 목록을 검색하고 삭제하려는 정책 옆에 있는 삭제 링크를 선택합니다.  
   ![로그인](./media/prevent-data-loss/3-delete.png)  
4. **삭제** 단추를 선택하여 실제로 해당 정책을 삭제할 것인지 확인합니다.  
   ![로그인](./media/prevent-data-loss/4.png)  

이제 정책이 삭제되었습니다. 왼쪽의 **데이터 정책** 링크를 선택하고 정책 목록을 검토하여 정책이 더 이상 데이터 손실 방지 정책 목록에 표시되지 않음을 확인할 수 있습니다.   

### <a name="dlp-policy-permissions"></a>DLP 정책 권한
테넌트 및 환경 관리자만 DLP 정책을 만들고 수정할 수 있습니다. [환경](environments-administration.md) 항목에서 권한에 대해 자세히 알아보세요.  

## <a name="next-steps"></a>다음 단계
* [환경에 대한 자세한 정보](environments-administration.md)  
* [Microsoft PowerApps에 대한 자세한 정보](getting-started.md)  
* [관리 센터에 대한 자세한 정보](introduction-to-the-admin-center.md)  

