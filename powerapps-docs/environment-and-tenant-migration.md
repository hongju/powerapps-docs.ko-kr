---
title: "환경 및 테넌트 간에 앱 마이그레이션 | Microsoft Docs"
description: "환경 및 테넌트 간에 앱 마이그레이션"
services: 
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: jamesol
ms.openlocfilehash: 2d25e6ddbaf15991655ffa94bbf9578946504f0e
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="environment-and-tenant-app-migration-through-packaging"></a>패키징을 통해 환경 및 테넌트 앱 마이그레이션
패키징을 사용하여 한 환경에서 다른 환경으로 리소스를 마이그레이션하는 방법을 알아봅니다. 이러한 환경은 동일한 테넌트 내 또는 다른 테넌트 간일 수 있습니다.

## <a name="the-scenario"></a>시나리오
리소스를 마이그레이션하려는 한 가지 일반적인 시나리오는 테스트 또는 개발 환경 및 프로덕션 환경이 있는 곳입니다. 개발자 및 테스터는 자신의 환경에서 앱에 대한 전체 액세스가 있어야 합니다. 하지만 프로덕션으로 새 앱을 마이그레이션할 시기가 되면 해당 환경은 업데이트 및 변경을 위한 사용 권한에 대한 엄격한 제어를 갖습니다.

다른 시나리오는 각 고객이 자신의 고유 환경 및 데이터를 갖는 곳입니다. 새 고객이 추가되면 고객을 위해 새 환경이 만들어지고 해당 환경으로 앱을 마이그레이션합니다.

## <a name="which-resources-can-i-migrate-through-packaging"></a>패키징을 통해 마이그레이션할 수 있는 리소스는 무엇인가요?
앱을 내보낼 때 앱에 대한 종속 리소스도 패키지로 내보내집니다.  처음으로 모든 가능한 리소스 종류의 하위 집합만 아래 표에 설명된 대로 지원됩니다.

| 리소스 종류 | 지원됨 | 가져오기 옵션 |
| --- | --- | --- |
| 앱 |예 |앱을 환경으로 가져오기 위한 두 가지 옵션이 있습니다. <ol><li><b>새로 만들기</b> – 패키지를 가져오는 환경에 새 앱으로 앱이 생성됩니다.</li> <li><b>업데이트</b> - 앱이 이미 환경에 있고 이 패키지를 가져오는 경우 업데이트됩니다.</li></ol> |
| 흐름 |예 |흐름을 환경으로 가져오기 위한 두 가지 옵션이 있습니다. <ol><li><b>새로 만들기</b> – 패키지를 가져오는 환경에 새 흐름으로 흐름이 생성됩니다.</li> <li><b>업데이트</b> - 흐름이 이미 환경에 있고 이 패키지를 가져오는 경우 업데이트됩니다.</li></ol> <div> <i>참고: 흐름이 종속되는 모든 리소스는 내보내지는 앱 패키지 내에 포함되고 가져오는 패키지로 구성되어야 합니다.</i> |
| CDS 엔터티 사용자 지정 및 선택 목록 |예 |환경에서 CDS 엔터티 또는 선택 목록을 가져오기 위한 두 가지 옵션이 있습니다. <ol><li><b>덮어쓰기</b> - 동일한 이름의 리소스가 있는 경우 이 가져오기가 대체됩니다. 일치하는 리소스가 없는 경우 새 리소스가 생성됩니다. <li><b>병합</b> - 이름이 같은 엔터티 또는 선택 목록이 있으면 새 필드 또는 엔터티가 추가되지만 누락된 필드 또는 항목은 제거되지 않습니다.</li></ol> |
| 사용자 지정 커넥터 |아니요 |앱이 사용자 지정 커넥터에 종속되는 경우 현재 패키지의 일부로 커넥터 내보내기를 지원하지 <b>않습니다</b>. <p></p> 사용자 지정 커넥터를 사용하는 앱이 있는 경우 현재 유일한 옵션은 대상 환경에서 커넥터를 수동으로 다시 만들거나 업데이트하고 패키지를 가져올 때 해당 커넥터를 선택하는 것입니다. |
| 연결 |아니요 |앱이 연결에 종속되는 경우(예: 자격 증명으로 SQL 연결) 현재 패키지의 일부로 연결 또는 자격 증명 내보내기를 지원하지 않습니다. <p></p> 공유 연결(예: SQL)을 사용하는 앱이 있는 경우 현재 유일한 옵션은 대상 환경에서 적절한 자격 증명으로 해당 연결을 수동으로 다시 만들고 패키지를 가져올 때 해당 연결을 선택하는 것입니다. |
| CDS 사용자 지정 역할 및 권한 집합 |아니요 |사용자 지정 CDS 역할 및/또는 사용 권한 집합 내보내기는 현재 지원되지 않으므로 현재 유일한 옵션은 대상 환경에서 이러한 엔터티를 수동으로 다시 만드는 것입니다. |
| 게이트웨이 |아니요 |게이트웨이는 기본(및 {테넌트 이름}(미리 보기)에서) 환경에서만 지원되므로 내보내기/마이그레이션은 지원되지 않습니다. |
| CDS 데이터 행 |아니요 |CDS 엔터티에서 내보내기 행은 현재 지원되지 않으므로 현재 유일한 옵션은 새 환경에서 CDS 스키마 변경 내용이 적용된 후 수동으로 데이터를 [내보내고 가져오는](data-platform-export-data.md) 것입니다. |

## <a name="how-do-i-get-access-to-packaging-for-my-app"></a>이 앱의 패키징에 대한 액세스를 어떻게 가져오나요?
앱을 내보내는 기능은 앱에 대해 "편집할 수 있는" 권한이 있는 사용자에게 제공됩니다.

앱을 가져오는 기능은 대상 환경에서 "환경 만들기" 권한이 있는 사용자에게 제공됩니다.

사용자는 앱을 내보내거나 가져오기 위해 PowerApps 요금제 2 또는 PowerApps 요금제 2 평가판 라이선스가 있어야 합니다.

*참고: 패키징이 미리 보기 상태인 동안 유효한 PowerApps 라이선스가 있는 사용자는 해당 앱 및 환경에 대한 패키징을 사용해 볼 수 있습니다.*

## <a name="exporting-an-app"></a>앱 내보내기
1. http://web.powerapps.com에서 **앱**을 클릭하거나 탭하고, 마이그레이션하려는 앱에 대한 줄임표를 선택한 다음 **내보내기(미리 보기)**를 선택합니다.
   
    ![내보내기 선택](./media/environment-and-tenant-migration/select-export.png)
2. 내보내기 패키지 페이지가 열릴 때 패키지에 대한 이름 및 설명을 입력합니다.
   
    ![패키지 세부 정보 검토](./media/environment-and-tenant-migration/package-details.png)
3. '패키지 콘텐츠 검토' 섹션 내에서 필요에 따라 설명 또는 메모를 추가하거나 패키지 가져오기 중에 대상 환경으로 각 개별 리소스를 가져오는 방식에 대한 설정을 변경할 수 있습니다.
   
    ![패키지 콘텐츠 구성](./media/environment-and-tenant-migration/export-package-content.png)
4. **내보내기** 선택 작업을 완료하면 패키지 파일이 몇 초 내에 다운로드를 시작합니다.

## <a name="importing-an-app"></a>앱 가져오기
1. http://web.powerapps.com에서 **앱**을 클릭하거나 탭한 다음 **패키지 가져오기(미리 보기)**를 선택합니다.
   
    ![가져오기 선택](./media/environment-and-tenant-migration/select-import.png)
2. **업로드**를 선택하고 가져오려는 앱 패키지 파일을 선택합니다.
   
    ![패키지 파일 선택](./media/environment-and-tenant-migration/select-file.png)
3. 패키지가 업로드되면 패키지 콘텐츠를 검토하고 각 항목에 대한 렌치 아이콘을 선택하고 필요한 정보를 입력하여 빨간색 아이콘으로 표시된 모든 항목에 대한 추가 입력을 제공해야 합니다.
   
    ![패키지 콘텐츠 검토](./media/environment-and-tenant-migration/import-package-content.png)
4. 필요한 모든 정보를 제공한 후 **가져오기**를 선택합니다.
   
    ![업데이트된 패키지된 콘텐츠](./media/environment-and-tenant-migration/import-package-content-dirty.png)
5. 가져오기가 완료되면 가져오기 작업의 성공 여부를 간략하게 설명하는 페이지(아래와 유사)로 자동으로 이동됩니다.
   
    ![가져오기 결과 검토](./media/environment-and-tenant-migration/import-results.png)

> **참고** 앱을 가져오고 있으며 기존 앱을 **업데이트**하도록 선택한 경우 새 변경 내용은 응용 프로그램의 초안으로 저장됩니다.  응용 프로그램의 다른 모든 사용자가 사용할 수 있도록 해당 변경 내용을 [게시](http://powerapps.microsoft.com/tutorials/save-publish-app/#publish-an-app)해야 합니다.
> 
> 

## <a name="known-limitations"></a>알려진 제한 사항
| 제한 사항 | 상태 |
| --- | --- |
| 3개 이상의 리소스를 포함하는 앱 패키지 가져오기를 완료하는 데 몇 분 정도 걸린다고 보고되었습니다. |이것은 알려진 문제이며 수정 사항이 곧 제공될 예정입니다. |

