---
title: PowerApps에 구성 요소가 있는 사용자 지정 엔터티를 만드는 자습서 | Microsoft Docs
description: PowerApps 앱과 함께 사용할 엔터티를 만들고 구성하기 위한 단계별 지침이 포함된 자습서
author: Mattp123
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: tutorial
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: c587ed6488ae498e3ec662016ee1d028023e4095
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168254"
---
# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>자습서: PowerApps에 구성 요소가 있는 사용자 지정 엔터티 만들기

[!INCLUDE [powerapps](../../includes/powerapps.md)]를 사용하여 해당 조직의 산업, 명칭 및 고유한 비즈니스 프로세스에 잘 맞게 앱을 조정합니다. [!INCLUDE [powerapps](../../includes/powerapps.md)] 앱 개발에는 기본 제공되는 표준 엔터티 추가 또는 사용자 지정 엔터티 만들기가 포함됩니다. 엔터티는 추적하려는 정보를 회사 이름, 위치, 제품, 메일 및 전화 등의 속성을 포함하는 레코드의 형태로 정의합니다. 

이 자습서에서는 엔터티를 만든 다음, 필드, 관계, 뷰 및 양식 등의 주요 구성 요소를 추가하거나 사용자 지정합니다. 다음 방법을 알아봅니다.

- 사용자 지정 엔터티 만들기
- 엔터티에 사용자 지정 필드 추가
- 엔터티 관계 추가
- 뷰 사용자 지정 
- 양식 사용자 지정

이 자습서에서는 개와 고양이를 꾸미는 애완 동물 미용 사업을 하는 Contoso 회사를 다룹니다. Contoso는 직원이 다양한 장치에서 사용할 수 있는 클라이언트 및 애완 동물 추적용 앱이 필요합니다.

## <a name="prerequisites"></a>필수 조건

[PowerApps](https://powerapps.microsoft.com/)에 로그인합니다. [!INCLUDE [powerapps](../../includes/powerapps.md)] 계정이 아직 없다면 [powerapps.com](https://web.powerapps.com)에서 **무료 시작** 링크를 선택합니다.

## <a name="create-a-custom-entity"></a>사용자 지정 엔터티 만들기

1. 왼쪽 탐색 창에서 **데이터**를 확장하고 **엔터티**를 선택한 다음, **새 엔터티**를 선택합니다.
    ![새 엔터티](media/create-custom-entity/create-new-entity.png)
2. 오른쪽 창에서 다음 값을 입력한 후, **다음**을 선택합니다.
  - **표시 이름**: *애완 동물* 
  - **설명**: *애완 동물 서비스를 추적하는 사용자 지정 엔터티*
3. **엔터티 저장**을 선택합니다.

## <a name="add-and-customize-fields"></a>추가 및 사용자 지정 필드
 
1. **필드** 탭에서 **기본 이름** 필드를 선택합니다.
2. 오른쪽 창에서 **기본 이름** 필드를 다음과 같이 변경합니다. 
  - **표시 이름**을 **기본 이름**에서 *애완 동물 이름*으로 변경합니다.
  - **검색 가능**을 선택합니다.  
  
    ![기본 필드 변경](media/create-custom-entity/primary-field.png)
3. **완료**를 선택합니다.
4. 엔터티 설계자 도구 모음의 **필드** 탭에서 **추가** 필드를 선택합니다. **필드 속성** 창에서 다음 값과 옵션을 입력하거나 선택합니다.
  - **표시 이름**. *종*
  - **데이터 형식**. *옵션 집합*
  - **옵션 집합**. *새 옵션 집합*
5. 옵션 집합 만들기

  a. **새 항목 추가**를 선택합니다. 
  
  b. **새 옵션**을 *개*로 교체합니다. 
   
  c. **새 항목 추가**를 선택합니다. 
    
  d.  **새 옵션**을 *고양이*로 교체합니다. 
    
  e. **저장**을 선택합니다. 

  ![새 옵션 집합](media/create-custom-entity/optionset-add-items.png)

6. **검색 가능**을 선택한 다음, **완료**를 선택합니다.

7. 엔터티 설계자 도구 모음에서 **필드 추가**를 선택합니다. **필드 속성** 창에서 다음 값을 입력하거나 선택한 다음, **완료**를 선택합니다.
  - **표시 이름**. *브리드*
  - **데이터 형식**. *텍스트*
  - **검색 가능**. *예*

8. 엔터티 설계자 도구 모음에서 **필드 추가**를 선택합니다. 

9. **필드 속성** 창에서 다음 값을 입력하거나 선택한 다음, **완료**를 선택합니다. 
  - **표시 이름**. *약속 날짜*
  - **데이터 형식**. *날짜 및 시간*

10. **엔터티 저장**을 선택합니다.

## <a name="add-a-relationship"></a>관계 추가

1. **관계** 탭을 선택하고 엔터티 설계자 도구 모음에서 **관계 추가**를 선택한 다음, **다 대 일**을 선택합니다. 
2. 오른쪽 창의 **관련** 목록에서 **계정**을 선택합니다.
3. **완료**를 선택합니다.
4. **엔터티 저장**을 선택합니다.

다 대 일 관계를 추가할 때 데이터 형식이 **조회**인 **계정** 필드는 **필드** 탭의 필드 목록에 자동으로 추가됩니다. ![계정 조회 필드](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>뷰 사용자 지정

1. **뷰** 탭을 선택한 다음, **활성 애완 동물** 뷰를 선택합니다. **활성 애완 동물** 뷰가 표시되지 않으면 **필터 제거**를 선택합니다.
2. 뷰 설계자에서 **열 추가**를 선택하고 다음 열을 선택한 다음, **확인**을 선택합니다.
  - 계정
  - 약속 날짜 
  - 브리드 
  - 종
3. **만든 날짜** 열을 선택하고 **제거**를 선택한 다음, **확인**을 선택하여 열 제거를 확인합니다.
4. 열을 정렬하려면 이동하려는 열을 선택한 다음, 뷰가 다음과 같을 때까지 <- 및 -> 화살표 단추를 사용합니다.
    ![활성 애완 동물 뷰](media/create-custom-entity/active-pets-view.png)
5. 뷰 설계자 도구 모음에서 **저장 후 닫기**를 선택합니다.  

## <a name="model-driven-apps-only-customize-the-main-form"></a>모델 기반 앱만 해당: 기본 양식 사용자 지정

캔버스 앱에서 애완 동물 엔터티만 사용하려면 이 단계를 건너뜁니다. 

1. [!INCLUDE [powerapps](../../includes/powerapps.md)] 왼쪽 탐색 창에서 **모델 기반**을 선택합니다.
2. 왼쪽 탐색 창에서 **데이터**를 확장하고 **엔터티**를 선택한 다음, **애완 동물**을 선택합니다.
3. **양식** 탭을 선택한 다음, **기본** 양식 유형 옆의 **정보**를 선택합니다.
    ![기본 양식 편집](media/create-custom-entity/main-form-edit.png)
4. 양식 편집기에서 필드 탐색기 창에 있는 **종**, **브리드**, **예약 날짜** 및 **계정** 필드를 다음과 같은 양식이 표시될 때까지 양식 캔버스의 일반 섹션으로 끌어다 놓습니다.
    ![기본 양식에 대한 필드 선택](media/create-custom-entity/main-form-edit2.png) 
5. **저장**을 선택합니다.
6. **게시**를 선택합니다.
7. **저장 및 닫기**를 선택하여 폼 디자이너를 닫습니다.

## <a name="add-the-custom-entity-to-an-app"></a>앱에 사용자 지정 엔터티 추가

이제 엔터티를 캔버스 또는 모델 기반 앱을 빌드하는 데 사용할 준비가 되었습니다. 

## <a name="next-steps"></a>다음 단계

이 자습서에서는 유용한 앱을 만드는 데 사용할 수 있는 엔터티를 만드는 방법을 배웠습니다. 
- 모델 기반 앱 만드는 방법을 알아보려면 [첫 번째 모델 기반 앱 빌드](../model-driven-apps/build-first-model-driven-app.md)를 참조합니다.
- 캔버스 앱을 만드는 방법을 알아보려면 [새로 앱 만들기](../canvas-apps/get-started-create-from-blank.md)를 참조하세요.
