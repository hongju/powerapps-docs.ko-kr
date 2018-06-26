---
title: SharePoint 연결 개요 | Microsoft Docs
description: SharePoint의 사용 가능한 함수, 응답 및 예제 참조
author: sarafankit
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2017
ms.author: ankitsar
ms.openlocfilehash: 8a49e0e4e866e7e9eda4834904ee84c082140376
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803308"
---
# <a name="connect-to-sharepoint-from-powerapps"></a>PowerApps에서 SharePoint 연결
![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

SharePoint 사이트에 연결하여 목록에서 앱을 자동으로 만들고 처음부터 앱을 구축하거나 기존 앱을 업데이트합니다.

## <a name="known-issues"></a>알려진 문제
라이브러리가 아닌 사용자 지정 목록에서 데이터를 추가할 수 있습니다. 또한 일부 열 형식이 지원되지 않으며 일부 열은 모든 카드 형식을 지원하지 않습니다.

| 열 형식 | 지원 | 기본 카드 |
| --- | --- | --- |
| 한 줄 텍스트 |예 |보기 텍스트  |
| 여러 줄 텍스트 |예 |보기 텍스트  |
| 선택 |예 |보기 조회<br>편집 조회<br>다중 선택 보기<br>다중 선택 편집 |
| 번호 |예 |보기 백분율<br>보기 등급<br>보기 텍스트  |
| 통화 |예 |보기 백분율<br>보기 등급<br>텍스트 보기 |
| 날짜 및 시간 |예 |보기 텍스트  |
| 조회 |예 |보기 조회<br>편집 조회<br>다중 선택 보기<br>다중 선택 편집 |
| 부울(Yes/No) |예 |보기 텍스트 <br>보기 설정/해제 |
| 개인 또는 그룹 |예 |보기 조회<br>편집 조회<br>다중 선택 보기<br>다중 선택 편집 |
| 하이퍼링크 |예 |보기 URL<br>보기 텍스트  |
| 그림 |예(읽기 전용) |보기 이미지<br>보기 텍스트  |
| 첨부 파일 |예(읽기 전용) |첨부 파일 보기|
| 계산됨 |예(읽기 전용) | |
| 작업 결과 |아니요 | |
| 외부 데이터 |아니요 | |
| 관리되는 메타데이터 |예(읽기 전용) | |
| 등급 |아니요 | |

공백을 포함한 열은 PowerApps에서 읽을 수 있지만 공백은 16진 이스케이프 코드 **"\_x0020\_"** 으로 대체됩니다. 예를 들어 SharePoint의 **"Column Name"** 은 데이터 레이아웃에 표시되거나 수식에 사용될 때 PowerApps에 **"Column_x0020_Name"** 으로 나타납니다.

## <a name="prerequisites"></a>필수 조건
1. PowerApps에 [등록](../../signup-for-powerapps.md)합니다.

1. 등록 시 사용한 동일한 자격 증명을 제공하여 PowerApps에 [로그인](http://web.powerapps.com)합니다.

1. 왼쪽 가장자리 부근에서 **앱**을 선택한 다음, 배너에서 **앱 만들기**를 선택합니다.

## <a name="create-an-app"></a>앱 만들기
* SharePoint 목록의 데이터를 기준으로 [앱을 자동으로 생성](../app-from-sharepoint.md)합니다.

    해당 앱에는 기본적으로 3개의 화면이 있는데 레코드를 검색하고, 레코드에 대한 세부 정보를 표시하며, 레코드를 생성 또는 업데이트하기 위한 화면들입니다. 앱을 생성한 후에는 [찾아보기 화면](../customize-layout-sharepoint.md) 및 [세부 정보 및 편집 화면](../customize-forms-sharepoint.md)을 필요에 따라 사용자 지정하고자 할 수 있습니다.

    **참고**: SharePoint 목록에 **선택**, **조회** 또는 **개인 또는 그룹** 열이 포함된 경우 이 항목의 뒷부분에 나오는 [갤러리에 데이터 표시](connection-sharepoint-online.md#show-data-in-a-gallery)를 참조하세요.

* [SharePoint에 연결](../connect-to-sharepoint.md)하고 [앱을 처음부터 만들기](../get-started-create-from-blank.md)의 개념을 검토하고 Excel 대신 SharePoint에 적용하여 자체 앱을 처음부터 만듭니다.

## <a name="add-a-sharepoint-list-to-an-existing-app"></a>SharePoint 목록을 기존 앱에 추가
1. PowerApps Studio에서 업데이트할 앱을 엽니다.

2. 리본의 **보기** 탭에서 **데이터 원본**을 클릭하거나 탭합니다.

3. 오른쪽 창에서 **데이터 원본 추가**를 클릭하거나 탭합니다.

    ![데이터 원본 추가](./media/connection-sharepoint-online/add-data-source.png)

4. **새 연결**, **SharePoint**, **연결**을 차례로 클릭하거나 탭합니다.

    ![SharePoint 연결 추가](./media/connection-sharepoint-online/add-sharepoint.png)

5. 연결할 SharePoint 사이트의 유형을 지정합니다.

    ![연결 유형 지정](./media/connection-sharepoint-online/choose-type.png)

   * **직접 연결(클라우드 서비스)** 을 클릭하거나 탭하여 SharePoint Online에 연결합니다.

   * **온-프레미스 데이터 게이트웨이를 사용하여 연결**을 클릭하거나 탭하여 온-프레미스 SharePoint 사이트에 연결합니다.

       인증 유형으로 **Windows**를 지정한 다음 자격 증명을 지정합니다. 자격 증명에 도메인 이름이 포함된 경우 *도메인\별칭* 형식으로 지정합니다.

       ![자격 증명 지정](./media/connection-sharepoint-online/specify-creds.png)

       **참고**: 온-프레미스 데이터 게이트웨이를 설치하지 않은 경우 [게이트웨이를 설치](../gateway-reference.md)한 다음 아이콘을 클릭하거나 탭하여 게이트웨이 목록을 새로 고칩니다.

       **게이트웨이 선택** 아래에서 사용하려는 게이트웨이를 클릭하거나 탭합니다.

       ![게이트웨이 선택](./media/connection-sharepoint-online/choose-gateway.png)

6. **연결**을 클릭 하거나 탭합니다.

7. **SharePoint 사이트에 연결**에서 **최근 사이트** 목록의 항목을 클릭하거나 탭하고(또는 사용할 사이트의 URL을 입력하거나 붙여 넣고) **이동**을 클릭하거나 탭합니다.

    ![SharePoint 사이트 선택](./media/connection-sharepoint-online/select-sp-site.png)

8. **목록 선택**에서 사용할 하나 이상의 목록에 대해 확인란을 선택한 다음 **연결**을 클릭하거나 탭합니다.  

    ![SharePoint에서 테이블 선택](./media/connection-sharepoint-online/select-sp-tables.png)

    일부 목록 형식은 기본적으로 표시되지 않습니다. 사용할 목록의 이름이 표시되지 않는 경우 아래쪽으로 스크롤한 다음 **사용자 지정 목록 이름 입력**이 포함된 상자에 목록 이름을 입력합니다.

    ![SharePoint의 사용자 지정 목록](./media/connection-sharepoint-online/custom-list.png)

    데이터 원본이 앱에 추가됩니다.

    ![앱에 추가된 데이터 원본 목록](./media/connection-sharepoint-online/data-sources-list.png)

## <a name="show-data-in-a-gallery"></a>갤러리에 데이터 표시
갤러리에서 이 열 형식의 데이터를 표시하려면 수식 입력줄을 사용하여 하나 이상의 **레이블** 컨트롤의 **Text** 속성을 설정합니다.

* **선택** 또는 **조회** 열에 대해 해당 열에 데이터를 표시하도록 **ThisItem.[ColumnName].Value**를 지정합니다.

    예를 들어 이름이 **Location**인 **선택** 열이 있으면 **ThisItem.Location.Value**을, 이름이 **PostalCode**인 **조회** 열이 있으면 **ThisItem.PostalCode.Value**를 지정합니다.

* **개인 또는 그룹** 열에 대해 **ThisItem.[ColumnName].DisplayName**을 지정하여 사용자 또는 그룹의 표시 이름을 표시합니다.

    예를 들어 이름이 **Manager**인 **개인 또는 그룹**을 표시하려면 **ThisItem.Manager.DisplayName**을 지정합니다.

    이메일 주소나 직함 등과 같은 다른 사용자 정보를 표시할 수도 있습니다. 전체 옵션 목록을 표시하려면 **ThisItem.[ColumnName].** 을 지정합니다 (맨 마지막에 마침표 있음).

    **참고**: **CreatedBy** 열에 대해 목록에서 항목을 만든 사용자의 표시 이름을 표시하려면 **ThisItem.Author.DisplayName**을 지정합니다. **ModifiedBy** 열에 대해 목록에서 항목을 변경한 사용자의 표시 이름을 표시하려면 **ThisItem.Editor.DisplayName**을 지정합니다.

* **관리되는 메타데이터** 열에 대해 해당 열에 데이터를 표시하도록 **ThisItem.[ColumnName].Label**을 지정합니다.

    예를 들어 이름이 **Languages**인 **관리되는 메타데이터**가 있으면 **ThisItem.Languages.Label**을 지정합니다.

## <a name="next-steps"></a>다음 단계
* [데이터 원본에서 데이터 표시](../add-gallery.md) 방법 알아보기
* [세부 정보 보기 및 레코드 만들기 또는 업데이트](../add-form.md) 방법 알아보기
* 연결할 다른 [데이터 원본](../connections-list.md) 유형 참조
