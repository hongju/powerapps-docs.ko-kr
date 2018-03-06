---
title: "위임 이해 | Microsoft Docs"
description: "위임을 사용하여 큰 데이터 집합을 효율적으로 처리합니다."
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: gregli
ms.openlocfilehash: b6410a6b392f074c5e5a240e471fa2591e1e135d
ms.sourcegitcommit: 85fadbb6881e1c097970e0566b5832f733cbe9b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2018
---
# <a name="understand-delegation"></a>위임 이해
PowerApps에는 데이터의 테이블을 필터링, 정렬 및 형성하는 강력함 함수 집합이 포함되어 있습니다(단 시간에 **[Filter](functions/function-filter-lookup.md)**, **[Sort](functions/function-sort.md)** 및 **[AddColumns](functions/function-table-shaping.md)** 함수 이름 지정).  이러한 함수를 사용하여 사용자에게 필요한 정보에 대한 집중된 액세스 권한을 제공할 수 있습니다.  데이터베이스 배경 지식이 있는 사람들에게 이러한 함수를 사용하는 것은 데이터베이스 쿼리를 작성하는 것과 같습니다.  

효율적인 앱을 빌드하는 핵심은 장치로 가져와야 하는 데이터의 양을 최소화하는 것입니다.  수백 만 개의 레코드 중에서 일부만 필요하거나, 또는 단일한 집계 값이 수천 개의 레코드를 나타낼 수 있습니다.  또는 아마도 첫 번째 레코드 집합을 검색할 수 있고 나머지 데이터 집합은 사용자가 더 원한다는 제스처를 취할 때 검색됩니다.  집중하면 앱에서 필요한 처리량, 네트워크 대역폭을 현저하게 줄일 수 있어 셀룰러 네트워크를 통해 연결된 휴대폰에서도 사용자를 위해 더 신속하게 응답할 수 있습니다.  

*위임*은 PowerApps 수식의 표현이 네트워크를 통해 이동하는 데이터를 최소화할 필요성을 충족하는 곳입니다.  즉, PowerApps가 로컬에서 처리하기 위해 앱으로 데이터를 이동하는 것이 아니라 데이터의 처리를 데이터 원본으로 위임한다는 것을 의미합니다.  

복잡해지는 상황에서 이 문서가 있는 이유는 PowerApps 수식으로 표현할 수 있는 것 중에 모든 데이터 원본으로 위임할 수 없는 것도 있기 때문입니다.  PowerApps 언어는 광범위한 숫자 및 텍스트 조작 기능과 함께 메모리의 전체 통합 문서에 완벽한 즉시 액세스할 수 있도록 설계된 Excel의 수식 언어를 흉내내고 있습니다.  결과적으로, PowerApps 언어는 SQL Server와 같은 강력한 데이터베이스 엔진을 포함해 대부분 데이터 원본이 지원할 수 있는 것보다 훨씬 풍부합니다.

**큰 데이터 집합을 작업하려면 위임할 수 있는 데이터 원본과 수식을 사용해야 합니다.**  앱 성능을 유지하고 사용자가 필요한 모든 정보에 액세스할 수 있게 하는 유일한 방법입니다. 위임이 가능하지 않은 위치를 플래그한 [파랑 점 제안](delegation-overview.md#blue-dot-suggestions)에 주의하세요.  작은 데이터 집합(500개 레코드 미만)을 사용하려는 경우 수식을 위임할 수 없다면 로컬에서 처리를 수행할 수 있으므로 어떠한 데이터 원본과 수식도 사용할 수 있습니다.  

## <a name="delegable-data-sources"></a>위임 가능한 데이터 원본
위임을 지원하는 데이터 원본의 전체 목록과 범위는 [위임 목록](delegation-list.md)을 참조하세요.

계속해서 기존 데이터 원본에 위임 지원을 추가할 뿐만 아니라, 더 많은 데이터 원본을 추가할 수 있습니다.

내보낸 Excel 통합 문서(“앱에 정적 데이터 추가” 데이터 원본 사용), 컬렉션, 그리고 컨텍스트 변수에 저장된 테이블은 위임이 필요하지 않습니다. 이 모든 데이터는 이미 메모리에 있으며, 전체 PowerApps 언어를 적용할 수 있습니다.

## <a name="delegable-functions"></a>위임 가능 함수
다음 단계는 위임할 수 있는 수식만 사용하는 것입니다. 여기에는 위임할 수 있는 수식 요소가 포함됩니다.  그러나 모든 데이터 원본은 서로 다르며 일부는 이러한 요소를 지원하지 않습니다. 특정 수식에서 파랑 점 제안을 확인하세요.

이러한 목록은 시간이 지남에 따라 변경됩니다. 위임에 더 많은 함수와 연산자를 지원하기 위해 노력하고 있습니다.

### <a name="filter-functions"></a>Filter 함수
**[Filter](functions/function-filter-lookup.md)**, **[Search](functions/function-filter-lookup.md)** 및 **[LookUp](functions/function-filter-lookup.md)**을 위임할 수 있습니다.  

**Filter** 및 **LookUp** 함수 내에서 적합한 레코드를 선택하기 위해 테이블의 열에 다음을 사용할 수 있습니다.

* **[And](functions/function-logicals.md)**(**[&&](functions/operators.md)** 포함), **[Or](functions/function-logicals.md)**(**[||](functions/operators.md)** 포함), **[Not](functions/function-logicals.md)**(**[!](functions/operators.md)** 포함)
* **[In](functions/operators.md)**
* **[=](functions/operators.md)**, **[<>](functions/operators.md)**, **[>=](functions/operators.md)**, **[<=](functions/operators.md)**, **[>](functions/operators.md)**, **[<](functions/operators.md)**
* **[+](functions/operators.md)**, **[-](functions/operators.md)**
* **[TrimEnds](functions/function-trim.md)**
* **[IsBlank](functions/function-isblank-isempty.md)**
* **[StartsWith](functions/function-startswith.md)**
* 컨트롤 속성과 [전역 및 컨텍스트 변수](working-with-variables.md) 등의 모든 레코드 전체에서 동일한 상수 값입니다.

모든 레코드에 대한 상수 값으로 평가하는 수식의 일부를 사용할 수도 있습니다.  예를 들어 **Left( Language(), 2 )**는 레코드의 어떠한 열에도 종속되지 않으므로 모든 레코드에 동일한 값을 반환합니다.  사실상 상수입니다.  컨텍스트 변수, 컬렉션 및 신호의 사용은 상수가 될 수 없으며, **Filter** 및 **LookUp**은 위임되지 않습니다.  

일부 중요한 항목이 위의 목록에서 누락되었습니다.

* **[If](functions/function-if.md)**
* **[*](functions/operators.md)**, **[/](functions/operators.md)**, **[Mod](functions/function-mod.md)**
* **[Concatenate](functions/function-concatenate.md)**(**[&](functions/operators.md)** 포함)
* **[ExactIn](functions/operators.md)**
* 문자 조작 함수: **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Len](functions/function-left-mid-right.md)**, ...
* 신호: **[Location](functions/signals.md)**, **[Acceleration](functions/signals.md)**, **[Compass](functions/signals.md)**, ...
* 일시적: **[Now](functions/function-now-today-istoday.md)**, **[Today](functions/function-now-today-istoday.md)**, **[Rand](functions/function-rand.md)**, ...
* [컬렉션](working-with-variables.md)

### <a name="sorting-functions"></a>정렬 함수
**[Sort](functions/function-sort.md)** 및 **[SortByColumns](functions/function-sort.md)**를 위임할 수 있습니다.  

**Sort**에서 이 수식은 단일 열의 이름에 불과하며 다른 연산자 또는 함수를 포함할 수 없습니다.

### <a name="aggregate-functions"></a>집계 함수
**[Sum](functions/function-aggregates.md)**, **[Average](functions/function-aggregates.md)**, **[Min](functions/function-aggregates.md)** 및 **[Max](functions/function-aggregates.md)**를 위임할 수 있습니다.  지금은 제한된 수의 데이터 원본만 이 위임을 지원합니다. 자세한 내용은 [위임 목록](delegation-list.md)을 확인하세요.

**[CountRows](functions/function-table-counts.md)**, **[CountA](functions/function-table-counts.md)** 및 **[Count](functions/function-table-counts.md)** 등의 계산 함수는 위임할 수 없습니다.

**[StdevP](functions/function-aggregates.md)** 및 **[VarP](functions/function-aggregates.md)** 등의 기타 집계 함수는 위임할 수 없습니다.

### <a name="other-functions"></a>기타 함수
모든 기타 함수는 다음 중요 함수를 포함해 위임을 지원하지 않습니다.

* 테이블을 셰이핑: **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**, ...
* **[First](functions/function-first-last.md)**, **[FirstN](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**
* **[Concat](functions/function-concatenate.md)**
* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**
* **[CountIf](functions/function-table-counts.md)**, **[RemoveIf](functions/function-remove-removeif.md)**, **[UpdateIf](functions/function-update-updateif.md)**
* **[GroupBy](functions/function-groupby.md)**, **[Ungroup](functions/function-groupby.md)**

공통 패턴은 **AddColumns** 및 **LookUp**을 사용하여 하나의 테이블을 다른 테이블로 병합하는 것입니다(일반적인 데이터베이스 용어로 조인).  예:

**AddColumns( Products, "Supplier Name", LookUp( Suppliers, Suppliers.ID = Product.SupplierID ).Name )**

**Products**와 **Suppliers**가 위임 가능한 데이터 원본이고 **LookUp**이 위임 가능한 함수지만, **AddColumns** 함수는 위임 가능하지 않습니다.  전체 수식의 결과는 **Products** 데이터 원본의 첫 부분으로 제한됩니다.  

**LookUp**과 해당 데이터 원본이 위임 가능하므로, **Suppliers**에 대한 매치는 크더라도 데이터 원본의 어디에선가 찾을 수 있습니다.  잠재적인 단점은 **LookUp**이 **Products**에서 이러한 각 첫 레코드에 대한 데이터 원본을 별도로 호출하여 네트워크에서 많은 채터를 유발한다는 것입니다.  **Suppliers**가 너무 작고 자주 바뀌지 않을 경우 앱이 시작되면 **Collect** 호출을 통해 앱에서 데이터 원본을 캐싱할 수 있으며(시작 화면에서 [**OnVisible**](controls/control-screen.md) 사용) 대신, **LookUp**을 수행합니다.  

## <a name="non-delegable-limits"></a>비-위임 가능한 한계
위임할 수 없는 수식은 로컬에서 처리됩니다.  이를 통해 PowerApps 수식 언어의 전체 범위를 사용할 수 있습니다.  하지만 먼저 네트워크를 통해 많은 양의 데이터를 검색해야 할 수 있으므로, 모든 데이터를 장치로 가져와야 하는 수고로움이 있습니다.  시간이 걸려 앱이 느리거나 멈춘다는 인상을 줄 수 있습니다.

이를 방지하기 위해 PowerApps는 로컬에서 처리할 수 있는 데이터 양을 제한할 수 있습니다(500개 레코드).  작은 데이터 집합에 대한 전체 액세스 권한을 계속 유지하고 부분 결과를 확인하여 큰 데이터 집합의 사용을 한정할 수 있도록 이 숫자를 선택했습니다.

사용자에게 혼란을 일으킬 수 있으므로 이 기능을 사용할 때는 각별하게 주의해야 합니다.  예를 들어 수백만 개의 레코드 데이터 원본에 대해 위임할 수 없는 선택 수식과 함께 **Filter** 함수를 고려하세요.  로컬에서 필터링을 수행할 수 있으므로, 수백만 개의 레코드 중 첫 500개의 레코드만 스캔됩니다.  원하는 레코드가 레코드 501, 또는 500,001인 경우 **Filter**로 고려되거나 반환되지 않습니다.

혼란스러울 수 있는 다른 위치는 집계 함수입니다.  이 동일한 수백만 레코드 데이터 원본의 열로 **Average**를 가져갑니다.  **Average**는 아직 위임할 수 없으므로, 첫 500개의 레코드만 평균으로 산정됩니다.  부분 답변은 앱 사용자에 의해 전체 답변으로 잘못 해석될 수 있으므로 주의해야 합니다.

## <a name="blue-dot-suggestions"></a>파랑 점 제안
위임되는 것과 위임되지 않는 것을 더 쉽게 알 수 있도록 제작 환경에서는 수식에 위임할 수 없는 항목이 포함되어 있을 경우 파랑 점 제안을 제공합니다.

파랑 점은 위임 가능한 데이터 원본에서 작용하는 수식에만 표시됩니다.  파랑 점이 보이지 않고 수식이 제대로 위임되지 않을 경우 위의 <a href="#delegable-data-sources">위임 가능한 데이터 원본</a> 목록과 비교하여 데이터 원본 유형을 확인하세요.

## <a name="examples"></a>예
이 예에서는 제품, 특히 과일, **[dbo].[Products]** 이름이 포함된 SQL Server 테이블을 사용합니다.  새 화면에서 PowerApps는 이 데이터 원본과 연결된 기본적인 3개 화면 앱을 만들 수 있습니다.

![3개 화면 앱](media/delegation-overview/products-afd.png)

갤러리의 **Items** 속성에 대해 이 수식을 참고하세요.  **SortByColumns**와 **Search** 함수를 사용하고 있으며, 둘 다 위임 가능합니다.

검색 텍스트 입력 컨트롤에 **"Apple"**을 입력해 보겠습니다.  자세히 관찰해 보니 새 검색에서 새 입력 항목이 처리되는 동안 화면 맨 위에 순간적으로 행진하는 점이 보일 것입니다.  행진하는 점은 SQL Server와 통신하고 있음을 나타냅니다.

![검색 텍스트 입력 컨트롤](media/delegation-overview/products-apple.png)

모두 위임 가능하므로, **[dbo].[Products]** 테이블에 수백만 개의 레코드가 포함되어 있는 경우에도 사용자가 결과를 스크롤할 때 갤러리에서 페이지를 넘기면서 모두 찾을 수 있습니다.

"Apple"과 "Pineapple"이 둘 다 일치하는 검색을 보려고 합니다.  **Search** 함수는 텍스트 열의 어디에서나 검색어를 찾아냅니다.  대신 그렇다면, 과일 이름으로 시작하는 검색어만 찾길 원했다고 말해 보겠습니다.  더 복잡한 검색어로 다른 위임 가능한 함수 **Filter**를 사용할 수 있습니다(간단하게 **SortByColumns** 호출을 제거하려고 합니다).

![SortByColumns 호출 제거](media/delegation-overview/products-apple-bluedot.png)

작동하는 것처럼 보이지만, **"Apples"**만 올바르게 표시되고 **"Pineapple"**은 아닙니다.  그러나 갤러리 옆에 파랑 점이 표시되며 수식 부분에 파란 물결선이 있습니다.  화면 썸네일에서도 파랑 점이 보입니다.  갤러리 옆에 있는 파랑 점 위을 마우스로 가리키면 다음 사항이 보입니다.

![파란색 점을 마우스로 가리키기](media/delegation-overview/products-apple-bluepopup.png)

위임 가능한 데이터 원본인 SQL Server에 위임 가능한 함수인 **Filter**를 사용하고 있더라도 **Filter** 내부에서 사용한 수식은 위임 가능하지 않습니다.  **Mid** 및 **Len**은 어떠한 데이터 원본에도 위임할 수 없습니다.

하지만 가능했습니다.  가능했다고 봐야죠.  그리고 이것이 바로 노랑 위험 아이콘과 빨강 물결 오류 대신 파랑 점인 이유입니다.  **[dbo].[Products]** 테이블에 500개 미만의 레코드가 포함되어 있다면 완벽하게 작용했습니다.   모든 레코드를 장치로 불러 왔으며 **Filter**가 로컬에 적용되었습니다.  

대신 이 테이블에 500개 이상의 레코드가 포함되어 있는 경우에는 *테이블의 첫 500개 레코드에서* **"Apple"** 로 시작하는 과일만 갤러리에 표시됩니다.  **"Apple, Fuji"**가 레코드 501 또는 500,001에 이름으로 나타나면 검색되지 않습니다.
