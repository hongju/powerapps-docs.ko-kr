---
title: "Excel에서 엔터티 데이터 열기 | Microsoft Docs"
description: "Excel에서 대화형 보기 및 편집 작업을 위해 엔터티 데이터를 엽니다."
services: powerapps
documentationcenter: na
author: chrisgarty
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: d559774c65ee2db99f891e41472f6110e330bfc1
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="open-entity-data-in-excel"></a>Excel에서 엔터티 데이터 열기
Microsoft Excel에서 엔터티 데이터를 열어서 Microsoft PowerApps Excel 추가 기능을 사용하여 데이터를 빠르고 쉽게 보고 편집할 수 있습니다. PowerApps Excel 추가 기능은 Microsoft Excel 2016에서 사용할 수 있습니다.

> [!NOTE]
> AD FS(Active Directory Federation Services)를 사용하도록 Microsoft Azure AD(Azure Active Directory) 테넌트가 구성된 경우 올바르게 Excel 추가 기능으로 로그인이 되도록 2016년 5월자로 업데이트가 적용되어 있는지 확인해야 합니다.

## <a name="open-entity-data-in-excel"></a>Excel에서 엔터티 데이터 열기
1. [powerapps.com](https://web.powerapps.com)에서 **Common Data Service** 섹션을 확장하고 왼쪽 탐색 창에서 **엔터티**를 클릭하거나 누릅니다. 모든 엔터티가 표시됩니다.
2. 관심이 있는 엔터티의 오른쪽에 있는 줄임표(...)를 클릭합니다.
3. **Excel에서 열기**를 클릭한 다음 생성된 통합 문서를 엽니다. 이 통합 문서에는 엔터티에 대한 바인딩 정보, 사용자 환경에 대한 포인터 및 PowerApps Excel 추가 기능에 대한 포인터가 포함되어 있습니다.  
4. Excel에서 PowerApps Excel 추가 기능을 실행하려면 **편집 사용**을 클릭합니다. Excel 추가 기능은 Excel 창 오른쪽의 창에서 실행됩니다.
5. PowerApps Excel 추가 기능을 처음 실행하는 경우 **이 추가 기능 신뢰**를 클릭하면 Excel 추가 기능을 실행할 수 있습니다.
6. 로그인을 묻는 메시지가 표시되면 **로그인**을 클릭한 다음 [powerapps.com](https://web.powerapps.com)에서 사용했던 동일한 자격 증명을 사용하여 로그인합니다. Excel 추가 기능은 이전 로그인 컨텍스트를 사용하며 가능한 경우 자동으로 로그인하도록 해줍니다. 따라서 Excel 추가 기능의 오른쪽 위에 있는 사용자 이름을 확인합니다.

Excel 추가 기능의 경우 선택한 엔터티에 대한 데이터를 자동으로 읽어줍니다. Excel 추가 기능에서 읽어줄 때까지 통합 문서에 데이터가 없음을 참고하세요.

## <a name="view-and-refresh-entity-data-in-excel"></a>Excel에서 엔터티 데이터 보기 및 새로 고침
Excel 추가 기능이 통합 문서로 엔터티 데이터를 읽은 후 Excel 추가 기능에서 **새로 고침**을 클릭하여 언제든지 데이터를 업데이트할 수 있습니다.

## <a name="edit-entity-data-in-excel"></a>Excel에서 엔터티 데이터 편집
Excel 추가 기능에서 **게시**를 클릭하여 필요에 따라 엔터티 데이터를 변경한 다음 다시 게시할 수 있습니다.

레코드를 편집하려면 워크시트에서 셀을 선택한 다음 셀 값을 변경합니다.

새 레코드를 추가하려면 다음 단계 중 하나를 따릅니다.

* 워크시트에서 아무 곳이나 클릭한 다음 Excel 추가 기능에서 **새로 만들기**를 클릭합니다.
* 워크시트의 마지막 행을 클릭한 다음 커서가 해당 행의 마지막 열 밖으로 이동하고 새 행이 생성될 때까지 Tab 키를 누릅니다.
* 워크시트 바로 아래에 있는 행을 클릭하고 셀에서 데이터 입력을 시작합니다. 해당 셀에서 포커스를 이동하는 경우 워크시트는 새 행을 포함하도록 확장됩니다.

레코드를 삭제하려면 다음 단계 중 하나를 따릅니다.

* 삭제할 워크시트 행 옆의 행 번호를 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 클릭합니다.
* 삭제할 워크시트 행을 마우스 오른쪽 단추로 클릭한 다음 **삭제** > **테이블 행**을 클릭합니다.

## <a name="add-or-remove-columns"></a>열 추가 또는 제거
디자이너를 사용하여 워크시트에 자동으로 추가된 열을 조정할 수 있습니다.

1. **옵션** 단추(톱니바퀴 기호)를 클릭한 다음 **디자인 사용** 확인란을 선택하여 Excel 추가 기능의 데이터 원본 디자이너를 활성화합니다.
2. Excel 추가 기능에서 **디자인**을 클릭합니다. 모든 데이터 원본이 나열됩니다.
3. 데이터 원본 옆의 **편집** 단추(연필 기호)를 클릭합니다.
4. 필요에 따라 **선택한 필드** 필드에서 목록을 조정합니다.
   * **사용 가능한 필드** 필드에서 **선택한 필드** 필드로 필드를 추가하려면 필드를 클릭한 다음 **추가**를 클릭합니다. 또는 필드를 두 번 클릭합니다.
   * **선택한 필드** 필드에서 필드를 제거하려면 필드를 클릭한 다음 **제거**를 클릭합니다. 또는 필드를 두 번 클릭합니다.
   * 필드의 순서를 변경하려면 **선택한 필드** 필드에서 필드를 클릭한 다음 **위로** 또는 **아래로**를 클릭합니다.
5. **업데이트**를 클릭하여 데이터 원본에 변경 내용을 적용한 다음 **수행**을 클릭하여 디자이너를 종료합니다. 필드(열)를 추가한 경우 **새로 고침**을 클릭하여 업데이트된 데이터 집합을 가져옵니다.

## <a name="troubleshooting"></a>문제 해결
몇 가지 간단한 단계를 통해 해결될 수 있는 몇 가지 문제가 있습니다.

* Excel 추가 기능으로 메타데이터를 로드하는 동안 "사용할 수 없음" 메시지를 받는 경우 Excel 추가 기능에 로그인한 계정에 대상 Common Data Service 데이터베이스를 사용할 수 있는 권한이 없는 것입니다. 이 문제를 해결하려면 올바른 사용자 이름이 Excel 추가 기능의 오른쪽 상단에 나타나는지 확인합니다. 필요한 경우 Excel 추가 기능의 오른쪽 상단에 있는 사용자 이름을 클릭하여 로그아웃한 후 다시 로그인합니다.
* 로그인 프로세스 중에 빈 웹 페이지가 열린다면 계정에 AD FS가 필요하지만 추가 기능을 실행하는 Excel 버전이 로그인 대화 상자를 로드할 수 있는 최신 버전이 아닌 것입니다. 필요에 따라 사용 중인 Excel 버전을 업데이트합니다. Excel 버전을 업데이트하려면 [Office 배포 도구](https://technet.microsoft.com/library/jj219422.aspx)를 사용하여 [지연된 채널에서 현재 채널로 이동](https://technet.microsoft.com/library/mt455210.aspx)합니다.

여기에 설명되지 문제가 발생하는 경우 [지원 페이지](https://powerapps.microsoft.com/support/)를 통해 문의하세요.

## <a name="next-steps"></a>다음 단계
* [엔터티에서 필드 관리](data-platform-manage-fields.md)
* [엔터티 간의 관계 정의](data-platform-entity-lookup.md)
* [Common Data Service 데이터베이스를 사용하여 앱 생성](data-platform-create-app.md)
* [Common Data Service 데이터베이스를 사용하여 앱을 처음부터 만들기](data-platform-create-app-scratch.md)

