---
title: Excel에서 앱 생성 | Microsoft Docs
description: PowerApps를 사용하여 클라우드 저장소 계정에 저장된 Excel 파일을 사용하는 앱을 자동으로 생성
services: ''
suite: powerapps
documentationcenter: na
author: AFTOWen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.custom: mvc
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 6556e16fef3908a77be02f270fdb25f2f01ed4b4
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="generate-an-app-from-excel-in-powerapps"></a>PowerApps의 Excel에서 앱 생성
이 항목에서는 Excel 테이블의 데이터를 사용하여 PowerApps에서 첫 번째 앱을 자동으로 생성합니다. Excel 파일을 선택하고, 앱을 생성한 다음, 생성하는 앱을 실행합니다. 생성된 모든 앱은 레코드를 검색하고, 레코드 세부 정보를 표시하고, 레코드를 만들거나 업데이트하는 화면을 포함합니다. 앱을 생성하여 Excel 데이터를 사용하는 작업 중인 앱을 신속하게 가져온 다음, 필요에 맞게 앱을 사용자 지정할 수 있습니다. 

Excel 파일은 OneDrive, Google Drive 또는 Dropbox와 같은 클라우드 저장소 계정에 있어야 합니다. 이 항목에서는 비즈니스용 OneDrive를 사용합니다.

이 항목을 수행하려면 Excel에서 [바닥재 견적](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx) 파일을 다운로드하고, [클라우드 저장소 계정](connections/cloud-storage-blob-connections.md)에 저장합니다. 또는 데이터가 [테이블로 포맷](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664)된 경우 사용자 고유의 Excel 파일을 사용할 수 있습니다. 

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="generate-the-app"></a>앱 생성
1. [PowerApps](https://web.powerapps.com)에 로그인합니다.

    ![PowerApps 홈 페이지](./media/get-started-create-from-data/sign-in.png)

1. **이러한 앱 만들기** 아래에서 **데이터로 시작** 위를 마우스로 가리킨 다음, **이 앱 만들기**를 선택합니다.

    ![앱 만들기 옵션](./media/get-started-create-from-data/make-this-app.png)

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