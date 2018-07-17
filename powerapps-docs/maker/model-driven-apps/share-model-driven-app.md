---
title: PowerApps와 모델 기반 앱 공유를 위한 자습서 | Microsoft Docs
description: 이 자습서에서는 모델 기반 앱을 공유하는 방법을 알아봅니다.
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 134ae4dfb5fe111c4c40e96efa1e79a3993c4a46
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899758"
---
# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>자습서: PowerApps와 모델 기반 앱 공유

[!INCLUDE [powerapps](../../includes/powerapps.md)] 앱은 공유를 위해 역할 기반 보안을 사용합니다. 역할 기반 보안의 기본 개념은 보안 역할이 앱 내에서 수행할 수 있는 작업 집합을 정의하는 권한을 포함하는 것입니다. 모든 앱 사용자는 하나 이상의 미리 정의된 또는 사용자 지정 역할에 할당되어야 합니다. 또는 역할을 팀에 할당할 수도 있습니다. 사용자 또는 팀이 이러한 역할 중 하나에 할당되면 해당 역할에 연결된 권한 집합이 해당 개인이나 팀 멤버에게 부여됩니다. 

이 자습서에서는 다른 사용자가 사용할 수 있도록 모드 기반 앱을 공유하는 작업을 수행합니다. 다음 방법을 알아봅니다.
- 사용자 지정 보안 역할 만들기
- 사용자 지정 보안 역할에 사용자 할당
- 앱에 보안 역할 할당

## <a name="prerequisites"></a>필수 조건
앱을 공유하려면 [!INCLUDE [powerapps](../../includes/powerapps.md)] 환경 관리자 또는 시스템 관리자 역할이 있어야 합니다. 

## <a name="sign-in-to-powerapps"></a>PowerApps에 로그인
[PowerApps](https://powerapps.microsoft.com/)에 로그인합니다. [!INCLUDE [powerapps](../../includes/powerapps.md)] 계정이 아직 없다면 **무료 시작** 링크를 선택합니다.

## <a name="share-an-app"></a>앱 공유 
이 자습서에서는 개와 고양이에게 서비스를 제공하는 애완 동물 미용 사업을 하는 Contoso 회사를 다룹니다. 애완 동물 미용 사업을 추적하기 위한 사용자 지정 엔터티가 포함된 앱이 이미 생성되고 게시되었습니다. 이제 애완 동물 미용 직원이 사용할 수 있도록 앱을 공유해야 합니다. 앱을 공유하기 위해 관리자 또는 앱 작성자는 사용자 및 앱에 하나 이상의 보안 역할을 할당합니다. 

## <a name="create-or-configure-a-security-role"></a>보안 역할 만들기 또는 구성
[!INCLUDE [powerapps](../../includes/powerapps.md)] 환경에는 앱을 사용하는 데 필요한 최소한의 비즈니스 데이터에 대한 액세스를 제공하는 보안 모범 사례 목표에 맞게 정의된 액세스 수준을 가진 일반 사용자 작업을 나타내는 [미리 정의된 보안 역할](#about-predefined-security-roles)이 포함됩니다. Contoso 애완 동물 미용 앱은 사용자 지정 엔터티를 기반으로 합니다.  사용자 지정 엔터티이므로 사용자가 작업하기 전에 권한을 명시적으로 지정해야 합니다. 이렇게 하려면 다음 중 하나를 수행하도록 선택할 수 있습니다.
- 기존의 미리 정의된 보안 역할을 확장하여 사용자 지정 엔터티를 기반으로 하는 레코드에 대한 권한을 포함시킵니다. 
- 앱 사용자의 권한을 관리할 목적으로 사용자 지정 보안 역할을 만듭니다. 

애완 동물 미용 기록을 유지 관리할 환경이 Contoso 비즈니스가 실행하는 다른 앱에도 사용되므로, 애완 동물 미용 앱과 관련된 사용자 지정 보안 역할이 생성됩니다. 또한 서로 다른 두 개의 액세스 권한 집합이 필요합니다.
- 애완 동물 미용 기술자는 보안 역할에 읽기, 쓰기 및 추가 권한이 부여되도록 다른 레코드를 읽고 업데이트하고 첨부하기만 하면 됩니다. 
- 애완 동물 미용 일정 관리자는 애완 동물 미용 기술자가 가지고 있는 모든 권한과 더불어 만들기, 추가, 삭제 및 공유 기능을 필요로 하기 때문에 보안 역할이 만들기, 읽기, 쓰기, 추가, 삭제, 할당 및 공유 권한을 가집니다.

액세스 및 범위 권한에 대한 자세한 내용은 [보안 역할](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles)을 참조하세요.

## <a name="create-a-custom-security-role"></a>사용자 지정 보안 역할 만들기
1. [!INCLUDE [powerapps](../../includes/powerapps.md)] 사이트에서 **모델 기반** > **앱** > **...** > **링크 공유**를 선택합니다.
2. **이 앱 공유** 대화 상자의 **보안 역할 만들기**에서 **보안 설정**을 선택합니다.
3. **설정** 페이지에서 **새로 만들기**를 선택합니다.  

4. 보안 역할 설계자에서 읽기, 쓰기 또는 삭제와 같은 작업과 해당 작업을 수행할 범위를 선택합니다. 범위는 사용자가 특정 작업을 수행할 수 있는 환경 계층 구조 내에서 깊이 또는 높이를 결정합니다. **역할 이름** 상자에 *애완 동물 미용 기술자*를 입력합니다.
5. **사용자 지정 엔터티** 탭을 선택한 다음, 원하는 사용자 지정 엔터티를 찾습니다. 이 예에서는 **애완 동물**이라는 사용자 지정 엔터티가 사용됩니다. 
6. **애완 동물** 행에서 ![조직 전역 범위](media/share-model-driven-app/organizational-scope-privilege.png)가 선택될 때까지 **읽기, 쓰기, 추가**
   ![새 보안 역할](media/share-model-driven-app/custom-security-role.png)을 각각 네 번 선택합니다.
7. 애완 동물 미용 앱은 계정 엔터티와도 관계가 있으므로 ![조직 전역 범위](media/share-model-driven-app/organizational-scope-privilege.png)가 선택될 때까지 **핵심 레코드** 탭을 선택하고 **계정** 행에서 **읽기**를 네 번 선택합니다. 
8. **저장 후 닫기**를 선택합니다. 
9. 보안 역할 설계자에서 **역할 이름** 상자에 *애완 동물 미용 일정 관리자*를 입력합니다. 
10. **사용자 지정 엔터티** 탭을 선택한 다음, **애완 동물** 엔터티를 찾습니다. 
11. **애완 동물** 행에서 ![조직 전역 범위](media/share-model-driven-app/organizational-scope-privilege.png)가 선택될 때까지 **만들기, 읽기, 쓰기, 삭제, 추가, 추가 대상, 할당, 공유**를 각각 네 번 선택합니다.
12. 애완 동물 미용 앱은 계정 엔터티와도 관계가 있고 일정 관리자가 레코드를 만들고 수정할 수 있어야 하므로, ![조직 전역 범위](media/share-model-driven-app/organizational-scope-privilege.png)가 선택될 때까지 **핵심 레코드** 탭을 선택하고 **계정** 행에서 다음 각 권한을 네 번 선택합니다. 
    **만들기, 읽기, 쓰기, 삭제, 추가, 추가 대상, 할당, 공유**
13. **저장 후 닫기**를 선택합니다.

## <a name="assign-security-roles-to-users"></a>사용자에게 보안 역할 할당
보안 역할은 액세스 수준 및 권한 집합을 통해 데이터에 대한 사용자의 액세스를 제어합니다. 특정 보안 역할에 포함된 액세스 수준 및 사용 권한의 조합은 사용자의 데이터 보기 및 사용자와 해당 데이터의 상호 작용에 대한 제한을 설정합니다.

> [!IMPORTANT]
> 모델 기반 앱을 사용하려면 환경의 모든 앱 사용자에게는 할당한 추가 보안 역할에 관계 없이 적어도 Common Data Service 사용자 보안 역할이 있어야 합니다. 대부분의 경우 Common Data Service 사용자 보안 역할은 앱을 사용하는 데 필요한 기본 작업을 수행할 충분한 권한을 제공합니다.
> Common Data Service 사용자 보안 역할이 있는 사용자에게는 소유한 사용자에 관계 없이 모든 계정, 연락처 및 연결 표준 엔터티 레코드에 대한 읽기 및 쓰기 액세스 권한도 있습니다. 앱 사용자에게 이러한 레코드에 대한 권한을 부여하지 않으려면 사용자 지정 보안 역할을 만듭니다. Common Data Service 사용자 보안 역할을 복사하고 적절한 권한을 제거하는 것이 가장 쉬운 방법입니다. 자세한 내용은 [보안 역할 복사](https://docs.microsoft.com/dynamics365/customer-engagement/admin/copy-security-role)를 참조하세요.

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>애완 동물 미용 기술자에게 보안 역할 할당 
1. **이 앱 공유** 대화 상자의 **보안 역할에 사용자 할당**에서 **보안 사용자**를 선택합니다.
2. 표시된 목록에서 애완 동물 미용사를 선택합니다.
3. **역할 관리**를 선택합니다.

    ![역할 관리](media/share-model-driven-app/select-users-for-security-roles.png)

4. **사용자 역할 관리** 대화 상자에서 이전에 만든 **애완 동물 미용 기술자** 보안 역할을 선택한 다음, **확인**을 선택합니다.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>애완 동물 미용 일정 관리자에게 보안 역할 할당 
1. **이 앱 공유** 대화 상자의 **보안 역할에 사용자 할당**에서 **보안 사용자**를 선택합니다.
2. 표시된 목록에서 애완 동물 미용 일정 관리자를 선택합니다.
3. **역할 관리**를 선택합니다.
4. **사용자 역할 관리** 대화 상자에서 이전에 만든 **애완 동물 미용 일정 관리자** 보안 역할을 선택한 다음, **확인**을 선택합니다.


## <a name="add-security-roles-to-the-app"></a>앱에 보안 역할 추가
그런 다음, 하나 이상의 보안 역할을 앱에 할당해야 합니다. 사용자는 할당된 보안 역할을 기반으로 앱에 액세스할 수 있습니다.
1. **이 앱 공유** 대화 상자의 **앱에 보안 역할 추가** 아래에서 **내 앱**을 선택합니다.
2. Contoso 애완 동물 미용 앱의 앱 타일 오른쪽 아래에서 **더 많은 옵션(...)** 을 선택한 다음, **역할 관리**를 선택합니다.

    ![앱의 역할 관리](media/share-model-driven-app/manage-roles.png)

4. **역할** 섹션에서 모든 보안 역할 또는 선택된 역할에 대한 앱 액세스 권한 부여 여부를 선택할 수 있습니다. 이전에 만든 **애완 동물 미용 일정 관리자** 및 **애완 동물 미용 기술자** 역할을 선택합니다.

    ![앱의 보안 역할 선택](media/share-model-driven-app/app-security-roles.png)

5. **저장**을 선택합니다.
 
## <a name="share-the-link-to-your-app"></a>앱에 대한 링크 공유
1. **이 앱 공유** 대화 상자의 **사용자와 직접 앱에 대한 링크 공유**에서 표시된 URL을 복사합니다.
 
2. **닫기**를 선택합니다.
3. SharePoint 사이트에 게시하거나 이메일을 통해 전송하는 등의 방법으로 사용자가 액세스할 수 있도록 특정 위치에 앱 URL을 붙여넣습니다.

![링크 공유](media/share-model-driven-app/share-model-driven-URL.PNG)

앱 설계자의 **속성** 탭에서도 앱 URL을 찾을 수 있습니다. 
    
![앱 URL 복사](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>미리 정의된 보안 역할 정보
이러한 미리 정의된 역할은 [!INCLUDE [powerapps](../../includes/powerapps.md)] 환경에서 사용할 수 있습니다.


|보안 역할  |*권한  |설명 |
|---------|---------|---------|
|환경 작성자     |  없음       | Microsoft Flow를 사용하여 앱, 연결, 사용자 지정 API, 게이트웨이 및 흐름을 포함한 환경과 관련된 새 리소스를 만들 수 있습니다. 그러나 환경 내의 데이터에 액세스할 수 있는 권한은 없습니다. 자세한 정보: [환경 개요](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|시스템 관리자     |  만들기, 읽기, 쓰기, 삭제, 사용자 지정, 보안 역할       | 보안 역할 만들기, 수정 및 할당을 포함하여 환경을 사용자 지정하거나 관리하기 위한 모든 권한을 가집니다. 환경의 모든 데이터를 볼 수 있습니다. 자세한 정보: [사용자 지정에 필요한 권한](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|시스템 사용자 지정자     | 만들기(자체), 읽기(자체), 쓰기(자체), 삭제(자체), 사용자 지정         | 환경을 사용자 지정하기 위한 전체 권한을 가집니다. 그러나 작성한 환경 엔터티에 대한 레코드만 볼 수 있습니다. 추가 정보: [사용자 지정에 필요한 권한](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Common Data Service 사용자     |  읽기, 만들기(자체), 쓰기(자체), 삭제(자체)       | 환경 내에서 앱을 실행하고 자신이 소유한 레코드에 대한 일반적인 작업을 수행할 수 있습니다.        |
|대리자     | 다른 사용자를 대신하여 작업 수행        | 코드가 다른 사용자의 권한으로 실행되거나 다른 사용자를 가장할 수 있습니다.  일반적으로 레코드에 대한 액세스를 허용하기 위해 다른 보안 역할과 함께 사용됩니다. 추가 정보: [다른 사용자 가장](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*권한은 달리 지정되지 않는 한 전역 범위입니다.

## <a name="next-steps"></a>다음 단계
[빠른 시작: 모바일 장치에서 모델 기반 앱 실행](../../user/run-app-client-model-driven.md)



