---
title: PowerApps에서 기본 양식에 대한 모델 기반 앱 특수 필드 속성 | Microsoft Docs
description: 기본 양식에 대한 특수 필드 속성 이해
Keywords: Main forms; Special field properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 6ad7e43c-b6a1-48c4-9dfb-ed830142a841
ms.openlocfilehash: 0c4e67b14816ae6eaf100221ac0ac29269000f9b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690244"
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>모델 기반 앱 특수 필드 속성 개요

 모든 필드는 [일반 필드 속성](common-field-properties-legacy.md)에 속성이 나열되어 있지만 특정 필드에는 사례 엔터티의 기본 양식에서 열 수 있는 이러한 권리 유형 필드와 같은 추가 속성이 있습니다.  

![special-properties-dialog](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>조회 필드 속성  
  
> [!NOTE]
>  아래 표에 설명된 옵션은 단일 엔터티 조회 필드에만 사용할 수 있습니다.  
  
|섹션|속성|설명|  
|-------------|--------------|-----------------|  
|**관련 레코드 필터링**|**다음과 같은 경우에만 레코드 표시**|이 옵션을 사용하도록 설정하면 사용자가 레코드를 검색할 때 표시되는 레코드에 추가 필터링이 적용됩니다. 그러면 조회 값을 설정할 때 더 관련성 높은 검색을 제공할 수 있습니다.<br /><br /> 기본적으로 이 옵션은 꺼져 있습니다.<br /><br /> 관련 레코드를 필터링할 때 사용 가능한 관계 조합이 이 다음 표에 나열됩니다.<br /><br /> 첫 번째 목록은 이 조회를 필터링하는 데 사용할 수 있는 모든 잠재적 관계로 채워집니다. 하나를 선택하세요.<br /><br /> 그리고 두 번째 목록은 첫 번째 목록에서 선택된 관련 엔터티를 대상 엔터티에 연결하는 모든 관계로 채워집니다. 하나를 선택하세요.<br /><br /> 여기에 정의된 필터를 사용자 끌 수 있게 하려면 **사용자가 필터를 해제하도록 허용** 확인란을 선택합니다.<br /><br /> 사용자가 조회 값을 설정할 때 **더 많은 레코드 조회** 옵션을 선택하면 이 대화 상자가 표시됩니다.<br /><br /> ![look-up-more-records](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> 조회 필드를 구성할 때 **사용자가 필터를 해제하도록 허용** 옵션을 선택한 경우 사용자에게 필터를 해제하는 확인란이 표시됩니다.  이렇게 하면 사용자가 더 광범위한 레코드를 볼 수 있습니다. 사용자가 이 필터로 정의된 제한된 범위의 레코드만 보도록 하려면 **사용자가 필터를 해제하도록 허용** 확인란을 해제합니다.|  
|**추가 속성**|**조회 대화 상자에 검색 상자 표시**|조회 대화 상자에 검색 상자를 표시하지 않도록 선택할 수 있습니다.|  
||**기본 보기**|이 보기는 사용자가 **더 많은 레코드 조회** 옵션을 선택할 경우 조회 대화 상자에 표시되는 기본 보기를 설정하고, 인라인 검색 결과를 필터링하는 데 사용됩니다.<br /><br /> 이 기본 보기는 또한 인라인 조회 대상에 포함되는 필드를 제어합니다.<br /><br /> 단일 엔터티 형식만 선택할 수 있는 조회의 경우 인라인 조회에 표시되는 필드가 기본 보기에 포함된 처음 두 필드로 설정됩니다. 이 예에서는 **기본 전화** 및 **이메일**이 계정 조회용으로 구성된 기본 보기의 처음 두 열이 됩니다.<br /><br /> 여러 엔터티 유형을 허용하는 시스템 조회의 경우 엔터티 조회 보기의 처음 두 열이 표시됩니다.|  
||**보기 선택기**.|세 가지 옵션 중에서 선택할 수 있습니다.<br /><br /> -   **해제**: 사용자가 다른 보기를 선택하도록 허용하지 않습니다.<br />-   **모든 보기 표시**: 모든 보기를 사용할 수 있습니다.<br />-   **선택된 보기 표시**: 이 옵션을 선택하면 Ctrl 키와 커서를 사용하여 표시할 보기를 선택할 수 있습니다. 엔터티의 조회 보기는 선택 해제할 수 없습니다.|  
  
 **\*가능한 관계 조합**  
  
|첫 번째 목록 관계|두 번째 목록 관계|사용 가능 여부|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|예|  
|N:1|N:1|예|  
|N:1|N:N|예|  
|1:N|1:N|예|  
|1:N|N:1|아니요|  
|1:N|N:N|아니요|  
|N:N|1:N|예|  
|N:N|N:1|아니요|  
|N:N|N:N|아니요|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>두 가지 옵션 필드 속성  
 서식 지정 탭의 두 옵션 필드에는 다음과 같은 서식 지정 옵션이 있습니다.  
  
- **두 개의 라디오 단추**: 레이블이 지정된 두 개의 컨트롤입니다. 하나만 선택할 수 있습니다.  
  
- **확인란**: true 또는 false 값을 설정하는 단일 확인란입니다.  
  
- **목록**: 두 값이 포함된 드롭다운 목록입니다.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>여러 줄 텍스트 필드 속성  
 `Text Area` 서식을 사용하는 여러 줄 텍스트 및 한 줄 텍스트 필드에는 **행 레이아웃** 속성이 있습니다. 이 속성을 사용하면 **행 수** 값을 지정하거나 **여유 공간으로 자동 확장**을 선택할 수 있습니다.  

## <a name="next-steps"></a>다음 단계

[기본 양식 및 해당 구성 요소 사용](use-main-form-and-components.md)
