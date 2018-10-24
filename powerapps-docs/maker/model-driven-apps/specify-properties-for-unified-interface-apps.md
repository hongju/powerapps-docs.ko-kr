---
title: PowerApps에서 모델 기반 통합 인터페이스 앱의 속성 지정 | MicrosoftDocs
description: 앱에 대한 표 컨트롤을 구성하는 방법 알아보기
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 0
topic-status: Drafting
ms.openlocfilehash: 007ac566e317ee99bd85ab0675e5a53839800bb4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691604"
---
# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>모델 기반 통합 인터페이스 앱의 속성 지정

통합 인터페이스 프레임워크는 반응형 디자인 원칙을 사용하여 모든 화면 크기 또는 방향에 대해 최적의 보기 및 상호 작용 경험을 제공합니다. 통합 인터페이스 프레임워크를 사용하는 모델 기반 앱에서 표(보기) 컨트롤은 반응형입니다. 예를 들어 휴대폰 및 작은 뷰포트와 같이 컨테이너의 크기가 감소하면 표가 목록으로 변환됩니다. 

읽기 전용 표 컨트롤은 표가 서로 다른 화면 크기로 재배치되는 방식을 지정합니다. 앱 제작자가 통합 인터페이스 앱으로 작업하는 경우 읽기 전용 표 컨트롤과 사용자 지정 표 및 목록에 대한 속성을 구성할 수 있습니다.
- **카드 양식** 속성: 기본 목록 템플릿 대신 목록에 대해 카드 양식을 사용합니다. 카드 양식은 기본 목록 템플릿보다 목록 항목에 대한 더 많은 정보를 제공합니다.
- **재배치 동작** 속성:이 매개 변수를 사용하여 목록으로 재배치하거나 재배치하지 않을 표를 지정합니다.

## <a name="allow-grid-to-reflow-into-list"></a>표가 목록으로 재배치되도록 허용

읽기 전용 표 컨트롤을 컨트롤 목록에 추가하면 다음 기능을 구성할 수 있습니다. 
- 표가 모바일과 같은 작은 디스플레이의 목록으로 재배치되도록 허용합니다.
- 표 전용 또는 목록 전용으로 렌더링 모드를 지정합니다.  

1. [솔루션 탐색기](advanced-navigation.md#solution-explorer)를 엽니다.
2. 탐색 창에서 **엔터티**를 확장하고 적절한 엔터티(예: **계정** 또는 **연락처**)를 선택한 다음, **컨트롤** 탭에서 **컨트롤 추가**를 선택합니다.

    ![컨트롤 추가 열기](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "컨트롤 추가 열기")

3. 컨트롤 목록에서 **읽기 전용 표**를 선택한 다음, **추가**를 선택합니다.

    컨트롤이 사용 가능한 컨트롤 목록에 추가됩니다.
   
    ![컨트롤 선택](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "컨트롤 선택")
    
4. 표를 읽기 전용으로 만들려는 장치(**웹**, **휴대폰** 또는 **태블릿**)를 선택합니다.

    ![장치 유형 선택](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "장치 선택")

5. **카드 양식** 속성을 구성합니다.

    카드 양식 속성을 사용하여 기본 목록 템플릿 대한 목록 항목을 표시할 수 있습니다. 카드 양식은 기본 목록 템플릿보다 목록 항목에 대한 더 많은 정보를 제공합니다.    

    a. **카드 양식** 옆에 있는 연필 아이콘을 선택합니다.

    ![카드 양식 편집](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "카드 양식 편집")

    b.  **엔터티** 및 **카드 양식** 형식을 선택합니다.

    ![카드 양식 속성](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "카드 양식 속성")

    c. **확인**을 선택합니다.
6. **재배치 동작** 속성을 구성합니다. 
    
    a. **재배치 동작** 옆에 있는 연필 아이콘을 선택합니다.

    ![재배치 동작 편집](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "재배치 동작 편집")

    b. **정적 옵션에 바인딩** 드롭다운에서 표 흐름 형식을 선택합니다.
    |흐름 유형|설명|
    |--------------|--------------------|
    |**재배치**|충분한 표시 공간이 없을 때 표를 목록 모드로 렌더링할 수 있습니다.|
    |**표만**|충분한 표시 공간이 없을 때 표를 목록으로 재배치하도록 제한합니다.|
    |**목록만**|표로 표시할 충분한 공간이 있는 경우 목록으로만 표시합니다.|
    
     ![재배치 동작 속성](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "재배치 동작 속성")

    c. **확인**을 선택합니다.


7.  변경 내용 저장 및 게시합니다. 


## <a name="conditional-image"></a>조건부 이미지
목록의 값 대신 사용자 지정 아이콘을 표시하고 JavaScript를 사용하여 열 값을 기반으로 선택하는 데 사용되는 논리를 설정할 수 있습니다. 조건부 이미지에 대한 자세한 내용은 [목록 보기에 값 대신 사용자 지정 아이콘 표시](../common-data-service/display-custom-icons-instead.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[보기 만들기 또는 편집](create-edit-views.md)