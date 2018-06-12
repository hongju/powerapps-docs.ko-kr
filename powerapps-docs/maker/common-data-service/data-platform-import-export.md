---
title: 앱용 Common Data Service의 데이터 가져오기 또는 내보내기
description: Excel의 Get-Data 및 데이터 내보내기 기능을 사용하여 Excel 또는 CSV 파일의 데이터를 앱용 CDS(Common Data Service)의 엔터티로 대량으로 가져오거나 내보냅니다.
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
ms.openlocfilehash: 7f3e16be5bba1874759e0f9e40dc455f1e29c2bc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697581"
---
# <a name="import-or-export-data-from-the-common-data-service-for-apps"></a>앱용 Common Data Service의 데이터 가져오기 또는 내보내기

Excel 또는 CSV 파일에서 데이터를 대량으로 가져오고 내보내려면 업데이트된 Apps용 CDS(Common Data Service) 환경에 대해 Excel 파일에서 데이터 가져오기 및 데이터 내보내기 기능을 사용하면 됩니다.

두 가지 방법으로 Excel 또는 csv 파일에서 엔터티로 파일을 가져올 수 있습니다.

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>옵션 1: 파일 템플릿을 만들고 수정하여 가져오기

모든 엔터티에는 입력 파일에 있어야 하는 필수 필드가 있습니다. 보다 원활한 방법은 엔터티로 데이터를 가져오기 위해 먼저 엔터티의 데이터를 내보내고 동일한 파일(데이터와 함께 수정됨)을 사용하여 템플릿을 만드는 것이 좋습니다. 그러면 각 엔터티에 대한 필수 필드를 고려해야 하는 시간과 노력을 절감할 수 있습니다.

1. 파일 템플릿 준비

    - CSV에 대한 데이터 내보내기 아래에 설명된 단계를 수행하여 엔터티 데이터를 csv 파일로 내보내기 시작합니다.
    - 기본 키 또는 대체 키를 사용하여 데이터의 고유성을 보장하도록 계획을 정의합니다.
    - 엔터티로 데이터를 가져오기 전에 고유성을 보장하는 방법은 아래 섹션을 참조하세요

1. 데이터를 사용하여 파일 수정

    - Excel 또는 CSV 파일에서 방금 만든 템플릿으로 데이터 복사

1. 파일 가져오기
    - [powerapps.com](https://web.powerapps.com/)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 누릅니다.
    - 데이터를 가져가려는 엔터티를 선택합니다.
    - 맨 위에서 줄임표 또는 메뉴를 클릭하고, **데이터 가져오기**를 선택하고, **Excel에서 데이터 가져오기**를 클릭하거나 누릅니다.

> [!NOTE]
> 둘 이상의 엔터티로 데이터 가져오기 위해 맨 위에 있는 메뉴에서 **데이터 가져오기**를 선택하고, **Excel에서 데이터 가져오기**를 클릭하거나 누릅니다. 여러 엔터티를 선택하고 **다음**을 누를 수 있습니다.

![계정 엔터티에 데이터를 가져오는 예제](./media/data-platform-import-export/import-data-to-account.png)

- 그러면 Excel 또는 CSV 파일을 통해 데이터를 가져오도록 선택할 수 있는 **데이터 가져오기** 화면으로 이동합니다.
- **업로드**를 클릭하거나 누릅니다.
- 파일을 선택하고 프롬프트에 따라 파일을 업로드하기 시작합니다.

![계정 엔터티에 파일을 업로드하는 예제](./media/data-platform-import-export/upload-account.png)

- 파일이 업로드되고 매핑 상태가 녹색이 되면 오른쪽 위 모서리에서 **가져오기**를 클릭합니다. 매핑하는 동안 오류가 발생하면 아래 섹션을 참조하여 매핑 오류로 이동하고 문제를 해결하세요.

![성공적인 매핑 상태 및 가져오기 단추 예제](./media/data-platform-import-export/success-map-imp.png)

- **가져오기가 성공적으로 완료되면** 전체 삽입 및 업데이트를 표시합니다.

![삽입 및 업데이트의 수를 표시하는 성공적인 가져오기 예제](./media/data-platform-import-export/success-imp-insert.png)

> [!NOTE]
> Upsert(업데이트 또는 삽입) 논리를 사용하여 기존의 레코드를 업데이트하거나 새 레코드를 삽입합니다.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>옵션 2: 고유한 원본 파일 가져오기

고급 사용자이며 앱용 Common Data Service 엔터티에 대해 지정된 엔터티의 필수 필드를 사용하는 경우 고유한 Excel 또는 CSV 원본 파일을 정의하고, **파일 가져오기** 아래에서 설명한 단계에 따르면 됩니다.

## <a name="navigating-mapping-errors"></a>매핑 오류 탐색

파일을 업로드한 후에 매핑 오류가 발생하는 경우 **상태 매핑**을 클릭하고 다음 단계를 사용하여 필드 매핑 오류를 검사하고 수정합니다.

- 오른쪽에서 드롭다운을 사용하여 **표시** 아래에서 **매핑되지 않은 필드**, **오류가 발생한 필드** 또는 **필수 필드**를 설명합니다.

> [!TIP]
> 경고를 수신하는지 아니면 오류를 수신하는지에 따라 **필드 매핑**에서 드롭다운 환경을 통해 **매핑되지 않은 필드** 또는 **오류가 발생한 필드**를 검사하기 시작합니다.

![경고로 인해 필드 매핑과 부분 일치하는 예제](./media/data-platform-import-export/partial-match.png)

![필드 매핑 문제를 탐색하는 예제](./media/data-platform-import-export/navigate-mappings.png)

![ 필드 매핑에서 발생한 경고를 검사하고 수정하는 예제](./media/data-platform-import-export/inspect-warnings.png)

- 모든 오류 및/또는 경고를 수정하면 맨 위 오른쪽 모서리에서 **변경 내용 저장**을 클릭합니다. 그러면 **데이터 가져오기** 화면으로 이동하게 됩니다.
- **매핑 상태** 열이 **완료됨**을 녹색으로 나타내면 맨 위 오른쪽 모서리에서 **가져오기**를 클릭합니다.
- **가져오기가 성공적으로 완료됨** 메시지를 수신하면 전체 삽입 및 업데이트를 표시합니다.

## <a name="ensuring-uniqueness-while-importing-data-into-entity-from-excel-or-csv"></a>Excel 또는 CSV에서 엔터티로 데이터를 가져오는 동안 고유성 확인

앱용 Common Data Service 엔터티는 기본 키를 사용하여 CDS 엔터티 테이블 내에 있는 레코드를 고유하게 식별합니다. CDS용 기본 키 엔터티는 GUID(전역적으로 고유한 식별자)이며 레코드 식별을 위한 기본 기초를 형성합니다. CDS 엔터티로 데이터를 가져오는 등의 데이터 작업은 기본 키를 노출합니다.

예제: 계정 엔터티에 대한 기본 키는 accountid입니다.

![accountid를 기본 키로 보여주는 계정 엔터티의 샘플 내보내기 파일](./media/data-platform-import-export/export-pk.png)

경우에 따라 외부 원본에서 데이터를 통합하는 동안 기본 키는 요구 사항을 충족하지 않을 수 있습니다. 이를 위해 CDS를 통해 기본 키 대신 레코드를 고유하게 식별하는 대체 키를 정의할 수 있습니다.

예제: 계정 엔터티에 대해 자연 키 기반 식별을 사용하여 'transactioncurrencyid'를 대체 키로 설정할 수 있습니다(예: 위에 표시된 GUID 값*88c6c893-5b45-e811-a953-000d3a33bcb9* 대신 '미국 달러' 사용). 통화 기호 또는 통화 이름을 키로 선택할 수도 있습니다.

![통화 엔터티의 대체 키를 만드는 예제](./media/data-platform-import-export/create-ak.png)

![통화 이름을 자연 키로 보여주는 계정 엔터티의 샘플 내보내기 파일](./media/data-platform-import-export/export-nk.png)

사용자는 대체 키를 지정한 후에 기본 키를 식별자로 사용할 수 있습니다. 따라서 첫 번째 파일이 여전히 유효한 위의 샘플에서 GUID는 유효한 데이터를 제공합니다.

## <a name="export-data-to-csv"></a>CSV로 데이터 내보내기

표준 엔터티 또는 사용자 지정 엔터티에서 일회성으로 데이터를 내보낼 수 있으며, 한 번에 둘 이상의 엔터티에서 데이터를 내보낼 수 있습니다. 두 개 이상의 엔터티에서 데이터를 내보내는 경우 각 엔터티는 고유한 Microsoft CSV 파일로 내보냅니다.

1. [powerapps.com](https://web.powerapps.com/)에서 **데이터** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 누릅니다.
1. 데이터를 내보내려는 엔터티를 선택합니다.
1. 맨 위에서 줄임표 또는 메뉴를 클릭하고, **내보내기**를 선택하고, **데이터**를 클릭하거나 누릅니다.

    ![계정 엔터티에서 데이터를 내보내는 예제](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > 여러 엔터티에서 데이터를 내보내는 경우 맨 위의 메뉴에서 **내보내기**를 선택하고, **데이터**를 클릭하거나 누릅니다. 여러 엔터티를 선택할 수 있습니다.

1. 내보내기 성공적으로 완료되면 다운로드할 수 있는 CSV 파일에서 관련 링크를 제공하는 **내보낸 데이터를 다운로드**할 수 있습니다.

    ![링크 다운로드 가능한 파일을 포함한 내보내기가 성공했음을 보여주는 샘플 내보내기](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>지원되지 않는 데이터 형식

다음 데이터 형식은 현재 지원되지 않습니다.

- 표준 시간대
- 다중 선택 옵션 설정
- 이미지
