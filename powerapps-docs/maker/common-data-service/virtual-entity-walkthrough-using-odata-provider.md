---
title: 앱용 Common Data Service에서 OData 데이터 공급자를 사용하여 가상 엔터티 연습 | MicrosoftDocs
description: 가상 엔터티와 함께 OData v4 데이터 공급자를 사용하는 방법 알아보기
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: ''
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: ebdd8f80aad2d353d017626b7c403da93803c19b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691596"
---
# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>OData v4 데이터 공급자를 사용하여 가상 엔터티 연습

모델 기반 앱 또는 Dynamics 365 for Customer Engagement의 서비스 영역 내에서 외부 데이터 원본의 티켓 정보에 액세스하려고 한다고 가정해 보겠습니다. 이 간단한 연습에서는 런타임에 OData 웹 서비스에서 티켓 데이터를 검색하는 외부 스키마에 매핑된 필드가 있는 가상 엔터티를 모델링합니다.

## <a name="data-source-details"></a>데이터 원본 세부 정보

이 연습에 사용된 데이터 원본에는 OData v4 웹 서비스가 있으므로 사용자 환경에 포함된 OData v4 데이터 공급자를 사용할 수 있습니다.

웹 서비스 URL: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> 이 연습에 사용된 웹 서비스 URL은 작동하는 웹 서비스가 아닙니다.

이 연습에서는 다음 3개의 필드가 포함된 단일 가상 엔터티가 필요합니다.

|외부 필드 이름 |외부 데이터 형식 |가상 엔터티 데이터 형식 |용도 |
|---------|---------|---------|---------|
|TicketID |`Edm.Guid` |기본 키 |엔터티에 대한 기본 키 |
|Title  |`Edm.String` |한 줄 텍스트 |티켓의 제목 |
|심각도 |`Edm.Int32`| 정수 |티켓의 심각도를 나타내는 0-4의 숫자 값 |

외부 데이터 원본 티켓 엔터티의 OData 메타데이터:

```xml
<EntityType Name="Ticket">
  <Key>
    <PropertyRef Name="TicketID" />
  </Key>
  <Property Name="TicketID" Nullable="false" Type="Edm.Guid" />
  <Property Name="Title" Type="Edm.String" />
  <Property Name="Severity" Nullable="false" Type="Edm.Int32" />
</EntityType>
```

## <a name="create-the-data-source"></a>데이터 원본 만들기

OASIS OData(Open Data Protocol) 샘플 웹 서비스를 사용하는 OData v4 데이터 공급자에 대한 데이터 원본을 만듭니다.

1. **설정** > **관리** > **가상 엔터티 데이터 원본**으로 이동합니다.
1. **새로 만들기**를 선택하고 **OData v4 데이터 공급자**를 선택한 다음, **확인**을 선택합니다.
1. 다음 정보를 입력하거나 선택합니다.

    |필드|값|
    |--|--|
    |**Name**|Contoso 예제 데이터 원본|
    |**URL**|`http://contosowebservice.azurewebsites.net/odata` |
    |**시간 제한**|30|
    |**인라인 카운트 반환**|True|

다른 필드는 그대로 두고 **저장 후 닫기**를 선택합니다.

> [!TIP]
> 사용자 고유의 웹 서비스를 사용하는 경우 URL을 웹 브라우저에 붙여넣어 유효한지 확인합니다. 

## <a name="open-solution-explorer"></a>솔루션 탐색기 열기

사용자가 만드는 모든 사용자 지정 엔터티의 이름 부분은 사용자 지정 접두사입니다. 이는 작업 중인 솔루션의 솔루션 게시자를 기반으로 설정됩니다. 사용자 지정 접두사에 관심이 있는 경우 이 엔터티에 대해 원하는 사용자 지정 접두사가 있는 관리되지 않는 솔루션에서 작업하는지 확인해야 합니다. 자세한 정보: [솔루션 게시자 접두사 변경](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>가상 엔터티 만들기

1. 솔루션 탐색기의 왼쪽 탐색 창에서 **엔터티**를 선택한 다음, 기본 창에서 **새로 만들기**를 선택합니다.
2. **엔터티: 새로 만들기** 양식에서 **가상 엔터티** 옵션을 선택한 후 다음 정보를 입력합니다. 

    |필드|값|
    |--|--|
    |**데이터 원본**|Contoso 예제 데이터 원본|
    |**표시 이름**.|티켓|
    |**복수 이름**|티켓|
    |**Name**|new_ticket|
    |**외부 이름**|티켓|
    |**외부 컬렉션 이름**|티켓|
    |**노트(첨부 파일 포함)**|선택됨|
    |**활동**|선택됨|

1. **이 엔터티를 표시하는 영역** 옆에서 **서비스**를 선택한 다음, **저장**을 선택합니다(단, 엔터티 양식은 닫지 마세요).
    ![티켓 엔터티 정의](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>가상 엔터티에 대한 필드 만들기

**엔터티: 티켓** 페이지의 왼쪽 탐색 창에서 **필드**를 선택합니다. 이 연습의 일환으로 두 개의 기존 필드를 편집하고 세 번째 필드를 추가합니다.

> [!IMPORTANT]
> 외부 이름은 대/소문자를 구분합니다. 올바른 이름을 사용하는지 확인하려면 웹 서비스 메타데이터를 참조하세요.
> Nullable 값이 false이면 특성이 필수임을 나타냅니다. 기본 키 필드는 항상 시스템 필수 필드입니다.

1. **new_ticketid** 필드를 열고 다음 특성을 여기에 표시된 값을 변경합니다. **외부 이름**: TicketID  ![TicketID 필드](media/ticketid-field.png)
1. **저장 후 닫기**를 선택합니다.
1. **new_name** 필드를 열고 다음 특성을 여기에 표시된 값을 포함하도록 변경합니다.
    - **표시 이름**: 제목
    - **외부 이름**: 제목 ![제목 필드](media/title-field.png)
1. **저장 후 닫기**를 선택합니다.
1. **새로 만들기**를 선택하고 **필드: 티켓에 대해 새로 만들기** 페이지에서 다음 정보를 입력합니다.

    |필드|값|
    |--|--|
    |**표시 이름**.|심각도|
    |**Name**|new_severity|
    |**외부 이름**|심각도|
    |**필드 요구 사항**|업무상 필수|
    |**데이터 형식**|정수|
    |**최솟값**|0|
    |**최댓값**|4|

  ![심각도 필드](media/severity-field.png)
1. **저장 후 닫기**를 선택합니다.

## <a name="add-the-fields-to-the-main-form"></a>기본 양식에 필드 추가

1. 티켓 엔터티 창에서 **양식**을 선택합니다.
1. 기본 양식에서 **심각도** 필드를 오른쪽에서 **제목** 필드 아래 **일반** 섹션의 양식으로 끌어다 놓습니다. 
    ![기본 양식에 심각도 필드 추가됨](media/drop-severity-field.png)
1. 티켓 엔터티 창에서 **저장 후 닫기**를 선택합니다.

## <a name="configure-the-default-view"></a>기본 보기 구성

1. 솔루션 탐색기의 왼쪽 창에서 **엔터티 티켓** 아래에서 **보기**를 선택합니다.
1. **모든 티켓** 보기를 엽니다.
1. **일반 작업** 창에서 **열 추가**를 선택합니다.
    ![보기에 대한 열 추가](media/addcolumns.png)
1. **심각도**를 선택한 다음, **확인**을 선택합니다.
1. **보기: 모든 티켓** 창에서 **저장 후 닫기**를 선택합니다.
1. 솔루션 탐색기 창에서 **모든 사용자 지정 게시**를 선택합니다.
    ![모든 사용자 지정 게시](media/publishall.png)
1. 모든 사용자 지정 항목이 게시된 후에는 솔루션 탐색기 창을 닫습니다.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>Dynamics 365 고객 참여를 사용하여 실행 중인 가상 엔터티 보기

1. **서비스** > **확장** > **티켓**으로 이동합니다.
    
    ![티켓 영역](media/ticket-area.png)

    **모든 티켓** 보기가 표시됩니다. **서비스** 영역에서 엔터티를 보려면 브라우저를 새로 고쳐야 할 수 있습니다.

    ![모든 티켓 보기](media/all-tickets-view.png)
1. **티켓** 레코드를 열어 주어진 레코드에 대한 **제목** 및 **심각도** 필드를 포함하는 양식을 봅니다.
    ![티켓 레코드](media/ticket-record.png)

### <a name="see-also"></a>참고 항목

[OData v4 데이터 공급자 구성, 요구 사항 및 모범 사례](virtual-entity-odata-provider-requirements.md)<br />
[외부 데이터 원본의 데이터를 포함하는 가상 엔터티 만들기 및 편집](create-edit-virtual-entities.md)
