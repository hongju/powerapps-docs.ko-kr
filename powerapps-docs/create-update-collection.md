---
title: "컬렉션 만들기 및 업데이트 | Microsoft Docs"
description: "PowerApps에서 컬렉션 만들기 및 기존 컬렉션에 열 추가"
services: 
suite: powerapps
documentationcenter: 
author: lonu
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/30/2015
ms.author: lonu
ms.openlocfilehash: f0fc171930e190e9530782ee93b27644e36a5978
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="create-and-update-a-collection-in-your-app"></a>앱에서 컬렉션 만들기 및 업데이트
컬렉션을 사용하여 앱에 사용할 수 있는 데이터를 저장합니다. 컬렉션은 유사한 항목의 그룹입니다. 예를 들어, 회사에서 판매하는 모든 제품 이미지를 저장하는 MyImages 컬렉션을 만듭니다. PowerApps 내에서 MyImages 컬렉션을 추가하고 이러한 제품의 모든 그림을 표시하는 앱을 만들 수 있습니다. 또 다른 예로, 제품 및 각 제품의 가격을 나열하는 가격표 컬렉션을 만들 수 있습니다.

PowerApps 내에서 컬렉션을 만들고 사용할 수 있습니다. 이제 시작하겠습니다.

### <a name="prerequisites"></a>필수 조건
* PowerApps에 [등록](signup-for-powerapps.md)하여 [설치](http://aka.ms/powerappsinstall)하고 연 다음 등록 시 사용했던 동일한 자격 증명으로 로그인합니다.
* PowerApps에서 앱을 만들거나 기존 앱을 엽니다.
* PowerApps에서 [컨트롤 구성](add-configure-controls.md)을 어떻게 하는지 알아봅니다.
* 이 단계는 샘플 입력 데이터로 [PriceList.zip](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip) 파일을 사용합니다. zip 파일에는 Excel로 변환할 수 있는 XML 파일이 포함되어 있습니다. 그렇지 않으면 PowerApps에서 자동으로 .zip 파일에 있는 파일을 읽고 성공적으로 가져옵니다. 이 샘플 데이터를 다운로드하여 사용하거나 직접 가져올 수 있습니다.

## <a name="create-a-single-column-collection"></a>단일 열 컬렉션 만들기
다음 단계는 Collect 함수를 사용하는 앱 내에서 컬렉션을 만드는 방법 및 컬렉션에 항목을 추가하는 방법을 보여 줍니다.

1. 앱을 엽니다.
2. **삽입** 탭에서 **텍스트**를 선택한 다음 **텍스트 입력**을 선택합니다.  
   ![][1]  
3. 왼쪽 위 모서리에서 **Text1**을 선택하고 컨트롤 이름을 **대상**으로 바꿉니다.  
   ![][2]  
4. **삽입** 탭에서 **단추**를 선택하여 디자이너에 단추 컨트롤을 추가합니다. 드롭다운 목록에서 **[OnSelect](controls/properties-core.md)** 속성이 나열됩니다. 다음 함수로 설정합니다.  
   
    ```Collect(Destinations, Destination!Text)```
   
    다음과 같아야 합니다.  
    ![][3]  
5. 단추 텍스트를 선택하고 **추가**를 입력합니다.  
   ![][5]  
6. **추가** 단추를 선택하고 텍스트 컨트롤 아래로 이동합니다. 아무 곳이나 이동할 수 있습니다.  
   ![][6]  

이 단계에서는 **대상**이라는 컬렉션을 만들기 위해 컬렉션 함수를 사용했습니다. 또한 단추 컨트롤을 추가했고 선택하면 새 항목을 컬렉션에 추가합니다. 이제 작성한 것을 봅니다.

1. 미리 보기 선택:  
   ![][7]  
2. 상자에 도시 이름을 입력한 다음 **추가** 단추를 선택합니다.
3. 몇 가지 추가 도시 이름을 입력하고 그때마다 **추가** 단추를 선택합니다.
4. **Esc** 키를 눌러 미리 보기 창을 닫습니다.
5. 대상 컬렉션 및 입력한 텍스트 값을 참조합니다. **파일** 탭에서 **컬렉션**을 선택합니다. 입력한 텍스트가 나열됩니다.  
   ![][8]

#### <a name="extra-credit"></a>추가 혜택
이제 목록 상자에 대상 컬렉션을 바인딩하겠습니다.

1. 디자이너로 다시 돌아갑니다.
2. **삽입** 탭에서 **컨트롤**을 선택한 다음 **목록 상자**를 선택합니다.  
   ![][22]  
3. 쉽게 확인할 수 있도록 목록 상자를 이동합니다. 해당 **[Items](controls/properties-core.md)** 속성을 다음 식으로 설정합니다.  
   ```Destinations!Value```  <br/>
   
    이 작업을 수행하면 목록 상자가 대상 컬렉션에 이전에 입력한 항목으로 자동으로 채워집니다.  
   ![][4]  

변경 내용을 미리 봅니다. ![][7] 목록 상자에서 입력한 다양한 도시를 볼 수 있습니다. 텍스트 입력 컨트롤에서 새 도시를 입력하고 **추가** 단추를 선택합니다. 목록 상자는 입력한 새 도시를 포함하도록 자동으로 업데이트됩니다.

## <a name="create-a-multi-column-collection"></a>다중 열 컬렉션 만들기
다음 단계는 Collect 함수를 사용하는 앱 내에서 컬렉션을 만드는 방법 및 컬렉션에 여러 행을 추가하는 방법을 보여 줍니다.

1. **홈** 탭에서 새 화면을 엽니다.
2. **삽입** 탭에서 **텍스트**를 선택한 다음 **텍스트 입력**을 선택합니다.
3. 텍스트 컨트롤의 이름을 **도시**로 바꿉니다.  
   ![][9]  
4. 다른 텍스트 입력 컨트롤을 삽입하고 이름을 **주**로 변경합니다.
5. 둘을 모두 볼 수 있도록 도시 및 주 텍스트 컨트롤을 이동합니다.  
   ![][10]  
   
    **참고**: '텍스트 입력'을 이미지에서 수행된 '도시' 또는 '주'와 같은 것으로 바꿀 수 있습니다.  
6. **삽입** 탭에서 **단추**를 선택합니다. 해당 **[OnSelect](controls/properties-core.md)** 속성을 다음 함수로 설정합니다.  
   ```Collect(Destinations, {Cities:City!Text, States:States!Text})```  
   
    다음과 같아야 합니다.  
    ![][11]  
   
    **참고**: 이 동일한 함수를 사용하여 이 컬렉션에 추가 열을 추가할 수 있습니다. 예를 들어, 도시에 대해 다른 텍스트 입력 컨트롤을 추가하여 도시 열을 추가할 수 있습니다.
   
    `Collect(Destinations, {Cities:City!Text, States:States!Text}, {Countries:Country!Text})`
7. 단추 컨트롤의 이름을 **AddCityStateButton**으로 바꾸고 해당 **[Text](controls/properties-core.md)** 속성을 **도시 및 주 추가**로 설정합니다.  
   ![][12]  

이 단계에서 **대상** 컬렉션에 **도시** 열 및 **주** 열을 추가했습니다. 단추 컨트롤은 컬렉션에 이러한 새 텍스트 항목을 추가합니다. 이제 작성한 것을 봅니다.

1. 미리 보기 선택:  
   ![][7]  
2. 도시 및 주 상자에 텍스트를 입력한 다음 **도시 및 주 추가** 단추를 선택합니다.
3. 몇 가지 도시 및 주를 더 추가합니다.
4. **Esc** 키를 눌러 미리 보기 창을 닫습니다.
5. 대상 컬렉션에 추가한 항목을 보려면 **파일** 탭을 선택한 다음 **컬렉션**을 선택합니다.  
   ![][13]

## <a name="add-columns-to-a-collection"></a>컬렉션에 열 추가
이 연습에는 몇 가지 섹션이 있습니다. 완료되면 컬렉션으로 데이터를 가져오고, 가격 목록에 데이터를 보여 주는 갤러리를 만들고, 제품의 수를 확인하는 슬라이더 컨트롤을 사용하는 방법을 배우게 됩니다.

### <a name="import-the-price-list-and-create-the-collection"></a>가격 목록 가져오기 및 컬렉션 만들기
1. [가격표](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip) zip 파일을 다운로드합니다.
2. **홈** 탭에서 새 화면을 추가합니다.
3. **삽입** 탭에서 **컨트롤**을 선택한 다음 **가져오기**를 선택합니다.  
   ![][14]  
4. **작업** 탭에서 **OnSelect**를 선택합니다. 다음 함수를 입력합니다.  
   
    ```Collect(PriceList, Import1!Data)```  
5. 앱을 미리 봅니다. **데이터 가져오기** 단추를 선택하고, PriceList.zip 파일을 선택하고, **열기**를 선택합니다.
6. 미리 보기 창을 닫습니다.
7. **파일** 탭을 선택하고, **컬렉션**을 선택합니다. 가져온 가격표 항목이 나열됩니다.  
   ![][15]

### <a name="add-the-gallery-to-show-the-collection-items"></a>컬렉션 항목을 표시하도록 갤러리 추가
1. 디자이너로 다시 돌아갑니다.
2. **삽입** 탭에서 **갤러리**를 선택하고, **사용자 지정 갤러리**로 스크롤한 다음 **세로**를 선택합니다.    
   ![][16]  
3. 갤러리의 이름을 **PriceGallery**로 바꾸고 **[Items](controls/properties-core.md)** 속성을 **가격표**로 설정합니다.  
   ![][18]  
4. 가격표 갤러리를 **데이터 가져오기** 컨트롤 아래로 이동합니다. 갤러리 테두리를 선택하고 클릭한 다음 끌기를 사용하여 세 개의 사각형이 표시되도록 갤러리 크기를 조정합니다.
5. 갤러리에서 첫 번째 사각형을 선택하고 세 개의 레이블을 추가합니다(**삽입** 탭 > **레이블**).
6. 첫 번째 사각형 위쪽의 행에 있는 레이블의 크기를 조정하고 정렬합니다. 갤러리는 다음과 유사하게 표시됩니다.  
   ![][19]
7. 각 레이블의 **[Text](controls/properties-core.md)** 속성을 다음 식으로 설정합니다.  
   
   | 레이블 | 텍스트 속성을 다음으로 설정 |
   | --- | --- |
   | Label1 |``ThisItem!Name`` |
   | Label2 |``Text(ThisItem!Price, "$#")`` |
   | Label3 |``ThisItem!Maker`` |
   
    이렇게 하면 레이블은 가격표 컬렉션 내에서 이름, 가격 및 메이커 값으로 자동으로 업데이트됩니다.
8. 레이블 및 갤러리의 크기를 조정하여 모든 추가 공백을 제거합니다. 화면은 다음과 비슷하게 표시됩니다.  
   ![][17]

### <a name="add-the-quantity-slider-and-update-the-collection"></a>수량 슬라이더 추가 및 컬렉션 업데이트
1. **삽입** 메뉴에서 **컨트롤**을 선택하고 **슬라이더**를 선택합니다. 슬라이더의 이름을 **OrderQty**로 바꾸고, 갤러리 아래로 이동합니다.
2. 단추를 추가하고, 해당 **[Text](controls/properties-core.md)** 속성을 **추가**로 설정하고, **OrderQty** 슬라이더 아래로 이동합니다. 앱은 다음과 유사하게 표시됩니다.  
   ![][20]
3. **추가** 단추의 **[OnSelect](controls/properties-core.md)** 속성을 다음 식으로 설정합니다.  
   
    ```Collect(OrderList, {Name:PriceGallery!Selected!Name, Qty:OrderQty!Value, Cost:OrderQty!Value*LookUp(PriceList, PriceGallery!Selected!Name in Name, Price)});SaveData(OrderList, "orderfile")```  
   
    **참고** 이 절차의 뒷부분에서 이 단추를 선택하면 **OrderList**라는 컬렉션을 만들고 저장합니다. 컬렉션은 갤러리에 입력하는 제품의 이름, 슬라이더로 선택하는 수량 및 제품의 가격으로 수량을 곱하여 계산되는 총 비용을 포함합니다.
4. **화면** 탭을 선택하고 **[OnVisible](controls/control-screen.md)** 속성을 다음 식으로 설정합니다.  
   
    ```If(IsEmpty(PriceList), LoadData(PriceList, "pricefile"));If(IsEmpty(OrderList), LoadData(OrderList, "orderfile"))```

이제 작성한 것을 봅니다.

1. **미리 보기**를 엽니다.
2. 갤러리에서 제품을 선택하고, 슬라이더를 원하는 수량으로 이동한 다음 **추가** 단추를 선택합니다.  
   
   > [!IMPORTANT]
   > 제품을 선택하면 해당 제품은 선택한 것을 표시하도록 강조 표시되지 않습니다. 갤러리를 만들었을 때 이 기능을 추가하지 않았습니다. 제품을 클릭하는 것이 선택한다는 것을 알고 있습니다.  
   > 
   > 
3. 이 단계를 반복하여 두 개 이상의 제품을 추가합니다. **ESC** 키를 눌러 미리 보기 창을 닫습니다.
4. **파일** 탭에서 **컬렉션**을 선택하여 만든 **OrderList** 컬렉션의 미리 보기를 표시합니다.  
   ![][21]

> [!TIP]
> 순서 목록에서 모든 항목을 제거하려면 단추를 추가하고, 해당 **[Text](controls/properties-core.md)** 속성을 **지우기**로 설정하고, 해당 **[OnSelect](controls/properties-core.md)** 속성을 다음 식으로 설정합니다.  
> ```Clear(OrderList);SaveData(OrderList, "orderfile")```  
> 한 번에 하나의 항목을 제거하려면 갤러리에 **OrderList** 컬렉션을 표시한 다음 해당 갤러리에 있는 레이블의 **[OnSelect](controls/properties-core.md)** 속성을 다음 식으로 설정합니다.  
> ```Remove(OrderList, ThisItem);SaveData(OrderList, "orderfile")```
> 
> 

## <a name="tips-and-tricks"></a>팁과 요령
* 언제든지 미리 보기 단추(![][7])를 선택하여 차트를 보고 데이터로 표시되는 방식을 볼 수 있습니다.
* 앱을 디자인할 때 컨트롤의 크기를 조정하고, 클릭한 다음 끌기를 사용하여 이동할 수 있습니다.

## <a name="what-you-learned"></a>학습 내용
이 항목에서는 다음을 수행했습니다.

* Collect() 함수를 사용하여 앱 내에서 컬렉션을 만들었습니다.
* 또한 단추 컨트롤을 추가했고 선택하면 단추는 새 항목을 컬렉션에 추가합니다.
* 목록 상자를 사용하여 컬렉션에 항목을 추가했습니다.
* 슬라이더 컨트롤을 추가하여 컬렉션 내의 항목을 업데이트했습니다.

[1]: ./media/create-update-collection/insertmenu-inputtext.png
[2]: ./media/create-update-collection/renametext.png
[3]: ./media/create-update-collection/buttononselect.png
[4]: ./media/create-update-collection/listboxpreview.png
[5]: ./media/create-update-collection/buttontext.png
[6]: ./media/create-update-collection/buttonundertext.png
[7]: ./media/create-update-collection/preview.png
[8]: ./media/create-update-collection/existingcollections.png
[9]: ./media/create-update-collection/renametext-city.png
[10]: ./media/create-update-collection/citystate.png
[11]: ./media/create-update-collection/buttononselectcitystate.png
[12]: ./media/create-update-collection/buttononcitystate.png
[13]: ./media/create-update-collection/existingcollectionscitystate.png
[14]: ./media/create-update-collection/import.png
[15]: ./media/create-update-collection/pricelistcollection.png
[16]: ./media/create-update-collection/portrait.png
[17]: ./media/create-update-collection/resizedgallery.png
[18]: ./media/create-update-collection/galleryitems.png
[19]: ./media/create-update-collection/gallerylabels.png
[20]: ./media/create-update-collection/slider.png
[21]: ./media/create-update-collection/existingcollectionsorderlist.png
[22]: ./media/create-update-collection/listbox.png
