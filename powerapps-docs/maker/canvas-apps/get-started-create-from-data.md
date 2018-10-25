---
title: Excel에서 캔버스 앱 생성 | Microsoft Docs
description: PowerApps를 사용하여 클라우드 저장소 계정에 저장된 Excel 파일을 사용하는 캔버스 앱을 자동으로 생성
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3d29387c907808f90225f1ff67257d289de2b0a9
ms.sourcegitcommit: 2300de0a0486187762f830068c872116d5b04c32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49806136"
---
# <a name="generate-a-canvas-app-from-excel-in-powerapps"></a>PowerApps의 Excel에서 캔버스 앱 생성

이 항목에서는 Excel 테이블의 데이터를 사용하여 PowerApps에서 첫 번째 캔버스 앱을 자동으로 생성합니다. Excel 파일을 선택하고, 앱을 생성한 다음, 생성하는 앱을 실행합니다. 생성된 모든 앱은 레코드를 검색하고, 레코드 세부 정보를 표시하고, 레코드를 만들거나 업데이트하는 화면을 포함합니다. 앱을 생성하여 Excel 데이터를 사용하는 작업 중인 앱을 신속하게 가져온 다음, 필요에 맞게 앱을 사용자 지정할 수 있습니다. 

Excel 파일은 OneDrive, Google Drive 또는 Dropbox와 같은 클라우드 저장소 계정에 있어야 합니다. 이 항목에서는 비즈니스용 OneDrive를 사용합니다.

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="prerequisites"></a>필수 조건

이 항목을 정확히 수행하려면 Excel에서 [바닥재 견적](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx) 파일을 다운로드하고, [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 저장합니다.

> [!IMPORTANT]
> 사용자 고유의 Excel 파일을 사용할 수 있지만 데이터는 테이블로 형식이 지정돼야 합니다. 자세한 내용은 [테이블 형식 지정](how-to-excel-tips.md)을 참조합니다. 

## <a name="generate-the-app"></a>앱 생성

1. [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)에 로그인합니다.

1. **고유한 앱 만들기** 아래에서 **데이터로 시작**을 마우스로 가리킨 다음, **이 앱 만들기**를 선택합니다.

    ![앱 만들기 옵션](./media/get-started-create-from-data/start-from-data.png)

1. **데이터와 함께 시작** 아래의 클라우드 저장소 계정에 대한 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.

    ![앱 만들기 옵션](./media/get-started-create-from-data/odfb-tile.png)

1. 메시지가 표시되면 **연결**을 클릭하거나 탭하고, 해당 계정에 대한 자격 증명을 제공합니다.

1. **Excel 파일 선택** 아래에서 **FlooringEstimates.xlsx**를 찾아 클릭하거나 탭합니다. 

1. **표 선택** 아래에서 **FlooringEstimates**를 클릭하거나 탭한 후 **연결**을 클릭하거나 탭합니다.

    ![앱 만들기 옵션](./media/get-started-create-from-data/choose-table.png)

## <a name="run-the-app"></a>앱 실행

1. F5 키를 눌러(또는 오른쪽 위 모서리의 재생 아이콘을 클릭하거나 탭하여) 미리 보기를 엽니다.

    ![미리 보기 열기](./media/get-started-create-from-data/open-preview.png)

1. 오른쪽 위 모서리 근처의 정렬 아이콘을 클릭하거나 탭하여 정렬 순서를 전환합니다.

    ![정렬 아이콘](./media/get-started-create-from-data/sort-icon.png)

1. 검색 창에서 하나 이상의 문자를 입력하거나 붙여넣어 목록을 필터링합니다.

1. 더하기 아이콘을 클릭하거나 탭하여 레코드를 추가하고, 원하는 데이터를 추가한 다음, 확인 표시 아이콘을 클릭하거나 탭하여 변경 내용을 저장합니다.

1. 추가한 레코드에 대한 다음 화살표를 클릭하거나 탭하고, 연필 아이콘을 클릭하거나 탭하여 레코드를 편집하고, 하나 이상의 필드를 업데이트한 다음, 확인 표시 아이콘을 클릭하거나 탭하여 변경 내용을 저장합니다.

1. 추가한 레코드에 대한 다음 화살표를 클릭하거나 탭하고, 연필 아이콘을 클릭하거나 탭하여 레코드를 편집하고, 하나 이상의 필드를 업데이트한 다음, 취소 아이콘을 클릭하거나 탭하여 변경 내용을 취소합니다.

1. 추가한 레코드에 대한 다음 화살표를 클릭하거나 탭한 다음, 휴지통 아이콘을 클릭하거나 탭하여 해당 레코드를 삭제합니다.

## <a name="next-steps"></a>다음 단계

사용자의 요구 사항에 맞게 기본 찾아보기 화면을 사용자 지정합니다. 예를 들어 범주별이 아닌 제품 이름별로 목록을 정렬 및 필터링할 수 있습니다.

> [!div class="nextstepaction"]
> [기본 찾아보기 화면을 사용자 지정합니다](customize-layout-sharepoint.md).
