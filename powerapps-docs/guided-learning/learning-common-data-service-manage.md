---
title: "엔터티 데이터 관리 | Microsoft Docs"
description: "서비스와 Excel에서 데이터 작업"
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: n6RizzixvxM
courseduration: 7m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 807284f05d4233ccf9180f8648f219a4e1eee2b6
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="manage-entity-data"></a>엔터티 데이터 관리
이 항목에서는 Common Data Service의 데이터 관리에 대해 설명합니다. 다른 항목에서 데이터를 가져오고 내보내는 방법을 다루었지만 이제는 Excel에서 데이터로 작업하는 데 더 많은 시간을 보내도록 하겠습니다.

## <a name="import-data-from-excel-or-csv"></a>Excel 또는 CSV에서 데이터 가져오기
이 예에서는 지난 항목에서 만든 제품 검토 엔터티로 Excel 데이터를 가져옵니다. 또한 데이터를 이동하는 일반적인 형식인 CSV 파일에서 데이터를 가져올 수도 있습니다. 다음은 엔터티의 모양을 보여 주며, 강조 표시된 영역은 이 항목에서 중점적으로 다룰 내용입니다.

![제품 검토 엔터티](./media/learning-common-data-service-manage/product-review-entity.png)

엔터티에서 **데이터 가져오기**를 클릭한 다음 가져올 파일로 이동합니다. **매핑 표시**를 클릭하고 Excel 파일의 열이 엔터티의 오른쪽 필드와 연결되어 있는지 확인합니다. 매핑에 만족하면 **변경 내용 저장**을 클릭합니다. 가져오기 주 화면으로 돌아가서 **가져오기**를 클릭합니다.

![Excel에서 데이터 가져오기](./media/learning-common-data-service-manage/import-data.png)

## <a name="export-data-to-excel"></a>Excel로 데이터 내보내기
Common Data Service 외부에서 액세스해야 하는 경우 데이터를 내보냅니다. 엔터티에서 **데이터 내보내기**를 클릭한 다음 zip 파일이 생성될 때까지 기다립니다. zip 파일을 열면 내보낸 데이터를 볼 수 있습니다. 
![Excel로 데이터 내보내기](./media/learning-common-data-service-manage/export-data.png)

## <a name="export-a-template-to-excel"></a>Excel로 템플릿 내보내기
데이터 다운로드 외에도 템플릿을 다운로드할 수 있습니다. 템플릿은 엔터티의 필드와 일치하는 구조이지만 데이터가 없는 Excel 파일입니다. 템플릿을 다운로드한 후 템플릿을 수동으로 또는 프로그래밍 방식으로 채우고 서비스로 다시 가져옵니다. 엔터티에서 **템플릿 내보내기**를 클릭한 다음 원하는 필드를 지정합니다(여기서는 필드 하나만 선택했음). **Excel로 내보내기**를 클릭한 다음 Excel 파일이 생성될 때까지 기다립니다. Excel 파일을 열면 선택한 필드가 있는 내보낸 템플릿을 볼 수 있습니다.

![Excel로 템플릿 내보내기](./media/learning-common-data-service-manage/export-template.png)

## <a name="open-and-work-with-data-in-excel"></a>Excel에서 데이터 열기 및 작업
마지막으로 **Excel에서 열기** 옵션을 살펴보겠습니다. PowerApps 추가 기능이 설치되어 있는 경우 이 옵션을 사용하여 Excel에서 데이터를 탐색하고 편집할 수 있습니다. 엔터티에서 **Excel에서 열기**를 클릭한 다음 해당 파일을 엽니다. 편집 기능을 사용하면 추가 기능을 통해 서비스의 엔터티에 대한 라이브 연결을 설정하고 통합 문서를 채웁니다. 통합 문서에서 직접 편집하여 행을 추가하거나 삭제할 수 있습니다. **게시**를 클릭하여 변경 내용을 저장합니다. 또한 데이터를 새로 고쳐 최신 복사본이 있는지 확인하고, 엔터티에 데이터가 많이 있는 경우 특히 편리한 데이터 필터링을 수행할 수도 있습니다.

![Excel에서 열기](./media/learning-common-data-service-manage/open-excel.png)

Common Data Service에서 데이터를 관리하는 방법, 즉 Excel에서 데이터 가져오기, 내보내기 및 작업을 수행하는 방법에 관한 항목을 마무리지었습니다. 다음 항목에서는 데이터 보안 관리에 대해 설명하겠습니다.

