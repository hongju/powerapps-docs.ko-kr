---
title: PowerApps로 목록 보기에서 값 대신 사용자 지정 아이콘 표시 | MicrosoftDocs
description: 보기에서 사용자 지정 아이콘 그래픽을 표시하는 방법 알아보기
ms.custom: ''
ms.date: 06/21/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: af866aed-2586-4b6f-bb1c-3519baae3645
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 592d2ad73b192d7f03c552563c4f91d52f3d201d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691327"
---
# <a name="display-custom-icons-instead-of-values-in-list-views"></a>목록 보기에서 값 대신 사용자 지정 아이콘 표시

<a name="GridIcons"></a>   

 PowerApps 환경 관리자 및 사용자 지정자는 보기에 그래픽을 추가하고 JavaScript를 사용하여 열 값을 기반으로 그래픽을 선택하는 데 사용되는 논리를 설정할 수 있습니다. Relationship Insights에서는 일부 열에 텍스트 또는 숫자 값이 아닌 아이콘을 표시하는 목록 보기를 표시하는 기능이 도입되었습니다. 
  
> [!NOTE]
>  표 아이콘은 웹 인터페이스에만 표시됩니다. [!INCLUDE[pn_Outlook_short](../../includes/pn-outlook-short.md)] 또는 모바일 앱에는 표시되지 않습니다.  
  
### <a name="add-custom-graphics-and-javascript-as-web-resources"></a>사용자 지정 그래픽 및 JavaScript를 웹 리소스로 추가  
  
1.  사용자 지정에 필요한 새 그래픽 파일을 만듭니다. 아이콘 크기는 16x16 픽셀을 권장합니다(더 큰 이미지는 축소됨).  
  
2.  어떤 아이콘을 어떤 값에 대해 표시할지 설정하는 JavaScript 함수를 하나 이상 작성합니다. 일반적으로 사용자 지정하려는 각 열에 대해 하나의 함수가 필요합니다. 각 함수는 행 데이터 개체 및 언어(LCID) 코드를 입력으로 받아들여야 하며 이미지 이름 및 도구 설명 텍스트가 포함된 배열을 반환해야 합니다. 함수 예제는 이 항목의 뒷부분에 나오는 [샘플 JavaScript 함수](#SampleJavascript)를 참조하세요.  
  
3.  관리자 권한으로 환경에 로그인하고 [솔루션 탐색기](../model-driven-apps/advanced-navigation.md#solution-explorer)를 엽니다.  
  
4.  **기본 솔루션** 팝업 창이 열립니다. 여기서 **구성 요소** > **웹 리소스**로 이동합니다.  
  
5.  이제 사용자 지정 그래픽을 웹 리소스로 하나씩 업로드합니다. 도구 모음에서 **새로 만들기** 단추를 선택하고 새 웹 리소스를 만듭니다. 리소스를 만들 수 있도록 다른 팝업 창이 열립니다. 다음을 수행합니다.  
  
    1.  새 리소스에 의미 있는 **이름**을 제공합니다. 이 이름은 JavaScript 코드에서 각 그래픽을 참조하는 데 사용합니다.  
  
    2.  **유형**을 그래픽 파일(PNG, JPEG 또는 GIF)을 저장하는 데 사용한 그래픽 형식으로 설정합니다.  
  
    3.  **파일 선택**을 선택하여 파일 브라우저 창을 엽니다. 이것을 사용하여 그래픽 파일을 찾아 선택합니다.  
  
    4.  원하는 경우 **표시 이름** 및/또는 **설명**을 추가합니다.  
  
    5.  **저장**을 선택한 다음, **웹 리소스** 창을 닫습니다.  
  
6.  포함하고 있는 각 그래픽 파일에 대해 이전 단계를 반복합니다.  
  
7.  이제 JavaScript를 최종 웹 리소스로 추가합니다. 도구 모음에서 **새로 만들기**를 선택하고 새 웹 리소스를 만듭니다. 리소스를 만들 수 있도록 다른 팝업 창이 열립니다. 다음을 수행합니다.  
  
    1.  새 리소스에 의미 있는 **이름**을 제공합니다.  
  
    2.  **형식**을 **스크립트(JScript)** 로 설정합니다.  
  
    3.  **텍스트 편집기**(**형식** 설정 옆에 있음)를 선택하여 텍스트 편집기 창을 엽니다. 여기에 Javascript 코드를 붙여넣고 **확인**을 선택하여 저장합니다.  
  
    4.  원하는 경우 **표시 이름** 및/또는 **설명**을 추가합니다.  
  
    5.  **저장**을 선택한 다음, **웹 리소스** 창을 닫습니다.  
  
8.  **기본 솔루션** 팝업 창이 열려 있는 상태에서 **구성 요소** > **엔터티** 트리를 확장하고 사용자 지정할 엔터티를 찾습니다.  
  
9. 엔터티를 확장하고 해당 **보기** 아이콘을 선택합니다.  
  
10. 이제 선택한 엔터티에 대한 보기 목록이 표시됩니다. 목록에서 보기를 선택합니다. 그런 다음 도구 모음에서 **기타 작업** 드롭다운 목록을 열고 **편집**을 선택합니다.  
  
11. 선택한 보기를 편집할 수 있는 컨트롤과 함께 팝업 창이 열립니다. 보기의 일부인 각 열을 보여 줍니다. 대상 열을 선택한 다음, **일반 작업** 상자에서 **속성 변경**을 선택합니다. **열 속성 변경** 대화 상자가 열리고 여기서 다음을 설정합니다.  
  
    - **웹 리소스**: Javascript 함수를 저장하기 위해 만든 웹 리소스의 이름을 지정합니다(목록에서 **찾아보기**로 선택).  
  
    - **함수 이름**: 선택한 열 및 보기를 수정하기 위해 작성한 함수 이름을 입력합니다.  
  
12. **확인**을 선택하여 **열 속성 변경** 대화 상자를 닫습니다.  
  
13. **저장 후 닫기**를 선택하여 보기를 저장합니다.  
  
14. 필요에 따라 각 엔터티, 보기 및 열에 대해 이러한 단계를 반복합니다.  
  
15. 준비되면 **모든 사용자 지정 항목 게시**를 선택하여 변경 내용을 게시합니다. 그런 다음, **기본 솔루션** 창을 닫습니다.  
  
<a name="SampleJavascript"></a>   

### <a name="sample-javascript-function"></a>샘플 JavaScript 함수  
 사용자 지정 아이콘과 도구 설명을 표시하는 JavaScript 함수에는 layoutxml에 지정된 전체 행 개체와 호출 사용자의 LCID(로캘 ID)라는 두 개의 인수가 있어야 합니다. LCID 매개 변수를 사용하면 여러 언어로 도구 설명 텍스트를 지정할 수 있습니다. 환경에서 지원되는 언어에 대한 자세한 내용은 [언어 사용](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) 및 [Dynamics 365에 대한 언어 팩 설치 또는 업그레이드](https://technet.microsoft.com/library/hh699674.aspx)를 참조하세요. 코드에서 사용할 수 있는 로캘 ID(LCID) 값의 목록은 [Microsoft 할당 로캘 ID](https://go.microsoft.com/fwlink/?linkid=829588)를 참조하세요.

  
 미리 정의된 옵션 집합이 제한되어 있는 옵션 집합 유형의 특성에 대해 사용자 지정 아이콘을 추가한다고 가정하면, 지역화 문제를 피하기 위해 레이블 대신 옵션의 정수 값을 사용해야 합니다.  
  
 다음 샘플 코드에서는 opportunityratingcode(Rating) 특성에서 3가지 값(1: 핫, 2: 웜, 3: 콜드) 중 하나를 기반으로 하는 아이콘과 도구 설명을 표시합니다. 또한 샘플 코드는 지역화된 도구 설명 텍스트를 표시하는 방법을 보여 줍니다. 이 샘플이 작동하려면 new_Hot, new_Warm 및 new_Cold라는 이름으로 16x16 이미지가 있는 3개의 이미지 웹 리소스를 만들어야 합니다.  
  
```  
function displayIconTooltip(rowData, userLCID) {      
    var str = JSON.parse(rowData);  
    var coldata = str.opportunityratingcode_Value;  
    var imgName = "";  
    var tooltip = "";  
    switch (parseInt(coldata,10)) { 
        case 1:  
            imgName = "new_Hot";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Hot";  
                    break;  
                default:  
                    tooltip = "Opportunity is Hot";  
                    break;  
            }  
            break;  
        case 2:  
            imgName = "new_Warm";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Warm";  
                    break;  
                default:  
                    tooltip = "Opportunity is Warm";  
                    break;  
            }  
            break;  
        case 3:  
            imgName = "new_Cold";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Cold";  
                    break;  
                default:  
                    tooltip = "Opportunity is Cold";  
                    break;  
            }  
            break;  
        default:  
            imgName = "";  
            tooltip = "";  
            break;  
    }  
    var resultarray = [imgName, tooltip];  
    return resultarray;  
}  
```  
  
 결과적으로 각 행의 값에 따라 **등급** 열에 도구 설명이 있는 아이콘이 표시됩니다. 결과는 다음과 같을 수 있습니다.  
  
 ![사용자 지정 열 그래픽 예제](media/custom-column-graphics-example.png "사용자 지정 열 그래픽 예제")  
 
 ### <a name="see-also"></a>참고 항목
 [뷰 만들기 또는 편집](../model-driven-apps/create-edit-views.md)
