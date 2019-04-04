---
title: SharePoint 연결 개요 | Microsoft Docs
description: SharePoint의 사용 가능한 함수, 응답 및 예제 참조
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/12/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0fbc97e6c2663210bea79cc7236ce784110a4950
ms.sourcegitcommit: c6ad6ba7814c5e7b12c3b7b76bf2e7718bf41b8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58198616"
---
# <a name="connect-to-sharepoint-from-a-canvas-app"></a>캔버스 앱에서 SharePoint에 연결

![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

사용자 지정 목록에서 앱을 자동으로 생성 하려면 SharePoint 사이트에 연결 하거나 기존 앱에 데이터를 추가 하거나 처음부터 앱을 작성 하기 전에 연결을 만듭니다.

- SharePoint Online 사이트 또는 온-프레미스 사이트의 사용자 지정 목록에서 데이터를 표시합니다.
- 이미지를 표시 하 고 (SharePoint Online에 해당) 라이브러리의 비디오 또는 오디오 파일을 재생 합니다.

## <a name="generate-an-app"></a>앱 생성

사용자 지정 목록에서 데이터를 관리하려는 경우 PowerApps는 [3개 화면의 앱을 자동으로 생성](../app-from-sharepoint.md)합니다. 사용자는 첫 번째 화면에서 목록을 찾아보고, 두 번째 화면에서 항목의 세부 정보를 표시하고 세 번째 화면에서 항목을 업데이트하거나 만들 수 있습니다.

> [!NOTE]
> SharePoint 목록에 **선택**, **조회**, 또는 **개인 또는 그룹** 열이 포함된 경우는 이 항목의 뒷부분에 나오는 [갤러리에 데이터 표시](connection-sharepoint-online.md#show-data-in-a-gallery)를 참조하세요.

## <a name="create-a-connection"></a>연결 만들기

1. [PowerApps에 로그인](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)하고, 왼쪽 탐색 모음에서 **데이터** > **연결**을 선택한 후, 왼쪽 위 모퉁이 근처의 **새 연결**을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![데이터 선택 >의 왼쪽된 탐색 모음에서 연결 하 고 왼쪽 위 모서리 근처에서 새 연결을 선택 합니다.](./media/connection-sharepoint-online/new-connection.png)

1. 오른쪽 위 모서리 근처의 검색 상자에 **SharePoint**를 입력하거나 붙여 넣고 **SharePoint**를 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![검색 상자 오른쪽 위 모서리 근처에서 입력 또는 붙여 SharePoint 하 고 SharePoint를 선택 합니다.](./media/connection-sharepoint-online/select-sharepoint.png)

1. 이러한 단계 중 하나를 수행 합니다.

    - SharePoint Online에 연결하려면 **직접 연결(클라우드 서비스)**을 선택하고 **만들기**를 선택한 후, (메시지가 나타나는 경우) 자격 증명을 입력합니다.

        > [!div class="mx-imgBorder"]
        > ![SharePoint Online에 연결 하려면, 직접 연결 (클라우드 서비스)를 선택 합니다.](./media/connection-sharepoint-online/select-online.png)

        연결이 만들어지고 기존 앱에 데이터를 추가 하거나 처음부터 앱을 빌드할 수 있습니다.

    - 온-프레미스 사이트에 연결하려면 **온-프레미스 데이터 게이트웨이를 사용하여 연결**을 선택합니다.

        > [!div class="mx-imgBorder"]
        > ![온-프레미스 사이트에 연결 하려면 선택 * * 온-프레미스 데이터 게이트웨이 사용 하 여 연결)](./media/connection-sharepoint-online/select-onprem.png)

        인증 유형으로 **Windows**를 지정한 다음 자격 증명을 지정합니다. 자격 증명에 도메인 이름이 포함된 경우 *도메인\별칭* 형식으로 지정합니다.

        > [!div class="mx-imgBorder"]
        > ![자격 증명 지정](./media/connection-sharepoint-online/specify-creds.png)

        **게이트웨이 선택** 아래에서 사용하려는 게이트웨이를 선택하고 **만들기**를 선택합니다.

        > [!NOTE]
        > 설치된 온-프레미스 데이터 게이트웨이가 없다면, [게이트웨이를 설치](../gateway-reference.md)하고, 게이트웨이 목록을 새로 고치려면 해당 아이콘을 선택합니다.

        > [!div class="mx-imgBorder"]
        > ![게이트웨이 선택](./media/connection-sharepoint-online/choose-gateway.png)

        연결이 만들어지고 기존 앱에 데이터를 추가 하거나 처음부터 앱을 빌드할 수 있습니다.

## <a name="add-data-to-an-existing-app"></a>기존 앱에 데이터 추가

1. PowerApps Studio에서 업데이트하려는 앱을 열고 **보기** 탭을 선택한 후 **데이터 원본**을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![보기 탭에 선택 하 고 데이터 원본](./media/connection-sharepoint-online/view-data-sources.png)

1. **데이터** 창에서 **데이터 원본 추가** > **SharePoint**를 선택합니다.

1. **SharePoint 사이트에 연결** 아래 **최근에 사용한 사이트** 목록에서 사이트를 선택하거나 사용하려는 사이트의 URL을 입력하거나 붙여넣고 **연결**을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![사이트를 선택 합니다.](./media/connection-sharepoint-online/select-sp-site.png)

1. **목록 선택**에서 사용하려는 문서 또는 하나 이상의 목록의 확인란을 선택한 후 **연결**을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![선택 목록에서를 사용 하려는 하나 이상의 목록 또는 문서에 대 한 확인란을 선택 하 고 연결을 선택](./media/connection-sharepoint-online/select-sp-tables.png)

    일부 목록 형식은 기본적으로 표시되지 않습니다. PowerApps는 탬플릿 기반 목록이 아닌 사용자 지정 목록을 지원합니다.  사용할 목록의 이름이 표시되지 않는 경우 아래쪽으로 스크롤한 다음 **사용자 지정 목록 이름 입력**이 포함된 상자에 목록 이름을 입력합니다.

    > [!div class="mx-imgBorder"]
    > ![사용자 지정 목록 이름 입력을 포함 하는 상자에서 목록의 이름을 입력 합니다.](./media/connection-sharepoint-online/custom-list.png)

    데이터 원본이 앱에 추가됩니다.

## <a name="build-your-own-app-from-scratch"></a>처음부터 고유한 앱 빌드

[처음부터 앱 만들기](../get-started-create-from-blank.md)의 개념을 Excel 대신 SharePoint에 적용합니다.

## <a name="show-list-columns-in-a-gallery"></a>갤러리에서 목록 열 표시

사용자 지정 목록이 이러한 유형의 열을 포함하는 경우, 갤러리에 있는 하나 이상의 **레이블** 컨트롤의 **텍스트** 속성을 설정하기 위해 수식 입력줄을 사용하여 해당 데이터를 갤러리의 컨트롤에서 표시할 수 있습니다.

- **선택** 또는 **조회** 열에 대해 해당 열에 데이터를 표시하도록 **ThisItem.[ColumnName].Value**를 지정합니다.

    예를 들어 이름이 **Location**인 **선택** 열이 있으면 **ThisItem.Location.Value**을, 이름이 **PostalCode**인 **조회** 열이 있으면 **ThisItem.PostalCode.Value**를 지정합니다.

- **개인 또는 그룹** 열에 대해 **ThisItem.[ColumnName].DisplayName**을 지정하여 사용자 또는 그룹의 표시 이름을 표시합니다.

    예를 들어 이름이 **Manager**인 **개인 또는 그룹**을 표시하려면 **ThisItem.Manager.DisplayName**을 지정합니다.

    이메일 주소나 직함 등과 같은 다른 사용자 정보를 표시할 수도 있습니다. 전체 옵션 목록을 표시하려면 **ThisItem.[ColumnName].** 을 지정합니다 (맨 마지막에 마침표 있음).

    > [!NOTE]
    > **CreatedBy** 열에 대해 목록에서 항목을 만든 사용자의 표시 이름을 표시하려면 **ThisItem.Author.DisplayName**을 지정합니다. **ModifiedBy** 열에 대해 목록에서 항목을 변경한 사용자의 표시 이름을 표시하려면 **ThisItem.Editor.DisplayName**을 지정합니다.

- **관리되는 메타데이터** 열에 대해 해당 열에 데이터를 표시하도록 **ThisItem.[ColumnName].Label**을 지정합니다.

    예를 들어 이름이 **Languages**인 **관리되는 메타데이터**가 있으면 **ThisItem.Languages.Label**을 지정합니다.

## <a name="show-data-from-a-library"></a>라이브러리에서 데이터 표시

SharePoint 라이브러리에 몇 개의 이미지가 있는 경우 **드롭다운** 컨트롤을 추가하여 사용자가 표시할 이미지를 지정할 수 있습니다. 비디오 같은 다른 종류의 데이터 및 **갤러리** 컨트롤 같은 다른 컨트롤에도 동일한 원칙을 적용할 수 있습니다.

1. 기존 연결이 없으면 [연결을 만듭니다](#create-a-connection). 그리고 [기존 앱에 데이터를 추가](#add-data-to-an-existing-app)합니다.

1. **드롭다운** 컨트롤을 추가하고 이름을 **ImageList**로 변경합니다.

1. **ImageList**의 **Items** 속성을 **문서**로 설정합니다.

1. 오른쪽 창의 **속성** 탭에서  **Value** 목록을 열고 **이름**을 선택합니다.

     **ImageList**에 라이브러리의 이미지 파일 이름이 나타납니다.

    > [!div class="mx-imgBorder"]
    > ![이미지 목록](./media/connection-sharepoint-online/dropdown-items.png)

1. **이미지** 컨트롤을 추가하고 **image** 속성을 다음 식으로 설정합니다.

    `ImageList.Selected.'Link to item'`

1. F5 키를 선택한 후에 **ImageList**에서 다른 값을 선택합니다.

    지정 된 이미지가 표시 됩니다.

    > [!div class="mx-imgBorder"]
    > ![샘플 이미지](./media/connection-sharepoint-online/golden-honey.png)

SharePoint 라이브러리에서 데이터를 표시하는 더 복잡한 접근 방식을 보여 주는 [샘플 앱을 다운로드](https://pwrappssamples.blob.core.windows.net/samples/spdoclib_blogapp.msapp)할 수 있습니다.

1. 앱을 다운로드한 후, [PowerApps Studio](https://us.create.powerapps.com/studio/#)를 열어 왼쪽 탐색 모음에서 **열기**를 선택한 후 **찾아보기**를 선택합니다.
1. **열기** 대화 상자에서 다운로드한 파일을 찾아서 열고, 이 항목의 처음 두 절차를 수행하여 데이터 원본으로 SharePoint 라이브러리를 추가합니다.

> [!NOTE]
> 기본적으로 이 앱은 [위임 경고](../delegation-overview.md)를 표시하지만, 라이브러리에 500개 미만의 항목이 포함되어 있으면 무시할 수 있습니다.

이 한 화면 앱의 왼쪽 아래 모서리에 있는 목록에는 라이브러리의 모든 파일 보여 줍니다.

- 맨 위쪽에 있는 검색 상자에 하나 이상의 문자를 입력하거나 붙여 넣어 파일을 검색할 수 있습니다.
- 라이브러리에 폴더가 있으면 제목 표시줄 바로 아래 폴더 목록에서 필터 아이콘을 선택하여 파일 목록을 필터링할 수 있습니다.

원하는 파일을 찾으면 오른쪽의 **비디오**, **이미지**, 또는 **오디오** 컨트롤에 표시되도록 선택합니다.

> [!div class="mx-imgBorder"]
> ![샘플 이미지](./media/connection-sharepoint-online/library-app.png)

## <a name="known-issues"></a>알려진 문제

### <a name="lists"></a>목록

PowerApps는 공백을 포함하는 열 이름을 읽을 수 있지만 16진수 이스케이프 코드(**"\_x0020\_"**)를 사용하여 공백을 바꿉니다. 예를 들어 SharePoint의 **"Column Name"** 은 데이터 레이아웃에 표시되거나 수식에 사용될 때 PowerApps에 **"Column_x0020_Name"**으로 나타납니다.

일부 유형의 열은 지원 되며 일부 유형의 열에는 모든 카드 형식을 지원 합니다.

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

### <a name="libraries"></a>라이브러리

- PowerApps에서 라이브러리에 파일을 업로드할 수 없습니다.
- PDF 뷰어 컨트롤의 라이브러리에서 PDF 파일을 표시할 수 없습니다.
- PowerApps Mobile은 **Download** 함수를 지원하지 않습니다.
- 사용자가 PowerApps Mobile 또는 Windows 10 앱에서 앱을 실행하는 경우 갤러리의 라이브러리 콘텐츠를 표시하도록 **Launch** 함수를 사용합니다.

## <a name="next-steps"></a>다음 단계

- [데이터 원본에서 데이터 표시](../add-gallery.md) 방법 알아보기
- [세부 정보 보기 및 레코드 만들기 또는 업데이트](../add-form.md) 방법 알아보기
- 연결할 다른 [데이터 원본](../connections-list.md) 유형 참조
