---
title: '미리 보기 기능: 앱용 Common Data Service와 함께 SQL API 데이터 공급자를 위한 Azure Cosmos DB 사용 | MicrosoftDocs'
description: 가상 엔터티에서 사용할 SQL API 데이터 공급자를 위한 Azure Cosmos DB를 구성하는 방법에 대해 알아봅니다.
keywords: SQL API
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: ''
topic-status: Drafting
ms.openlocfilehash: fa45376dff85205a0dfbf28334c678293528d00e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696540"
---
# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>미리 보기 기능: Azure Cosmos DB SQL API 데이터 공급자 요구 사항

이 항목에서는 SQL API 데이터 공급자를 위한 Azure Cosmos DB에 대한 요구 사항과 가상 엔터티에서 SQL API 데이터 공급자를 위한 Azure Cosmos DB를 사용할 때의 모범 사례를 구성하고 권장하는 방법에 대해 설명합니다. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Azure Cosmos DB란?

Azure Cosmos DB는 업무용 응용 프로그램을 위한 전역적으로 분산된 Microsoft의 다중 모델 데이터베이스 서비스입니다. 스키마 없는 JSON 데이터에 비해 일관된 짧은 대기 시간과 풍부하고 친숙한 SQL 쿼리 기능을 제공합니다. 자세한 정보: [Azure Cosmos DB 소개: SQL API](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)

## <a name="requirements"></a>요구 사항

- Azure Cosmos DB를 포함하는 Azure 구독.
- Azure Cosmos DB SQL API 컬렉션.
- Azure Cosmos DB 데이터베이스 유형은 SQL이어야 합니다. 

## <a name="data-type-mapping"></a>데이터 형식 매핑

다음 JSON 구조를 가진 *Orders*라고 명명된 컬렉션에 Azure Cosmos DB 문서가 있다고 가정합니다.

![SQL API 문서용 JSON 예제입니다.](media/documentdbexample.png)

이 표는 앱용 Common Data Service를 사용하여 *Orders* 컬렉션의 SQL API 문서에 대한 데이터 유형 매핑을 나타냅니다.

|SQL API 데이터|앱용 CDS|
|--|--|
|`id`|기본 키|
|`name`|단일 줄 텍스트|
|`quantity`|정수|
|`orderid`|한 줄 텍스트|
|`ordertype`|옵션 집합|
|`amount`|10진수 또는 통화|
|`delivered`|두 가지 옵션|
|`datetimeoffset`|날짜 및 시간|

> [!NOTE]
> - 밑줄(_) 접두사가 있는 특성은 SQL API에 의해 생성됩니다.
> - SQL API 문서에서 선택적으로 구성되고 **비즈니스 필수**로 앱용 CDS에 매핑된 특성으로 인해 런타임 오류가 발생합니다.
> - id 특성 값은 guid여야 합니다.
> - SQL API에서 날짜를 사용하는 방법에 대한 자세한 내용은 [Azure Cosmos DB에서 날짜 작업](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/)을 참조하세요.

## <a name="supported-sql-query-filtering"></a>지원되는 SQL 쿼리 필터링

SQL 쿼리 필터링은 다음 연산자를 지원합니다. 

- 비교 연산자:`<`,`>`,`<=`, `>=`,`!=`
- 논리 연산자: `and`, `or` 
- 연산자 설정: `in`, `not in`
- 문자열 연산자: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> 동일한 연산자의 사용은 해당하는 `contains`/`begins with`/`ends with` 연산자로 변환됩니다. SQL API는 [Like(Transact SQL)](/sql/t-sql/language-elements/like-transact-sql) 항목에 설명된 대로 패턴 인수를 지원하지 않습니다. SQL API 데이터 공급자를 위한 Azure Cosmos DB는 단일 특수 사례 `Like('[aA]%')`를 `BeginsWith('a')` 또는 `BeginsWith('A')`로 변환할 수 있습니다. SQL API의 문자열 비교는 대/소문자를 구분합니다.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>SQL API 데이터 공급자를 위한 Azure Cosmos DB를 사용하여 데이터 원본 추가

1. [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview)로 이동하여 **지금 가져오기**를 선택하고 지침에 따라 v9x 이상을 사용하여 응용 프로그램을 환경에 추가합니다.
2. 솔루션이 설치된 후 환경에 로그인하고 **설정** > **관리** > **가상 엔터티 데이터 원본**으로 이동합니다.
3. 작업 도구 모음에서 **새로 만들기**를 선택하고 **데이터 공급자 선택** 대화 상자에서 **SQL API 데이터 공급자를 위한 Azure Cosmos DB**를 선택한 다음, **확인**을 선택합니다.
![SQL API 데이터 공급자를 위한 Azure Cosmos DB를 선택합니다.](media/createdatasource.png)
1. 다음 정보를 입력한 다음, **저장 및 닫기**를 선택합니다.

    |필드|설명|
    |--|--|
    |**Name**|데이터 원본을 설명하는 이름을 입력합니다.|
    |**컬렉션 이름**|가상 엔터티에서 노출하려는 데이터를 포함하는 Azure Cosmos DB 데이터베이스 컬렉션의 id입니다.  |
    |**인증 키**|Azure Cosmos DB 계정의 기본 또는 보조 키입니다. Azure Cosmos DB 계정에서 **키** 설정 아래의 Azure 관리자 포털에서 키를 찾을 수 있습니다.|
    |**URI**|Azure Cosmos DB 컬렉션이 있는 리소스 그룹의 URI입니다. URI는 `https://contoso/documents.azure.com:443`과 유사하게 형성됩니다. Azure Cosmos DB 계정에 대한 **키** 설정 아래의 Azure 관리자 포털에서 URI를 찾을 수 있습니다. |
    |**시간 초과(초)**|데이터 요청 시간 초과 전에 Azure Cosmos DB 서비스에서 응답을 기다리는 시간(초)을 입력합니다. 예를 들어, 시간 초과가 발생하기 전에 최대 30초까지 기다리려면 30을 입력합니다. 기본 시간 초과는 120초입니다.|

    ![SQL API 데이터 공급자를 사용하여 데이터 원본을 만듭니다.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>모범 사례 및 제한 사항

- Azure Cosmos DB를 데이터 원본으로 사용하는 경우 다음 사항에 유의하세요.
   - 각 Azure Cosmos DB 데이터 원본은 단일 가상 엔터티에만 연결할 수 있습니다.
   - Azure Cosmos DB에서 동일한 컬렉션에 여러 데이터 원본을 연결할 수 있습니다.
- 엔터티별로 컬렉션의 데이터를 분할할 수 없습니다.
- Azure Cosmos DB 데이터베이스는 스키마를 필요로 하지 않지만 Azure Cosmos DB 내의 데이터는 예측 가능한 스키마를 사용하여 구성되어야 합니다. 
- SQL API 데이터 공급자를 위한 Azure Cosmos DB는 프로젝션, 필터링 및 정렬 연산자의 쿼리 변환을 구현하지만 결합 작업을 지원하지 않습니다.
- SQL API를 사용하여 단일 열에 의해서만 필터링할 수 있습니다.

## <a name="see-also"></a>참고 항목

[외부 데이터 원본의 데이터를 포함하는 가상 엔터티 만들기 및 편집](create-edit-virtual-entities.md)
