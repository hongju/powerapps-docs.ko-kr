---
title: 관리자 고객 데이터에 대한 데이터 통합
description: 앱용 CDS의 관리자에 대한 데이터 통합에서 개인 데이터 식별, 내보내기 및 삭제
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 05/20/2018
ms.author: sabinn
ms.openlocfilehash: 01dafceacff89cb9b3a400caad5dde07a0995f1c
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34754228"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-data-integration-for-common-data-service-for-apps-customer-data"></a>앱용 Common Data Service 고객 데이터에 대해 데이터 통합을 위한 DSR(Data Subject Rights) 요청에 응답

## <a name="introduction-to-dsr-requests"></a>DSR 요청 소개

EU(유럽 연합) GDPR(일반 데이터 보호 규정)은 사람들(규정에서 ‘데이터 주체’)에게 고용주 또는 다른 유형의 기관이나 조직(‘데이터 컨트롤러’ 또는 간단하게 ‘컨트롤러’)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다. GDPR에서 개인 데이터는 식별되거나 식별 가능한 자연인에 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 개인 데이터와 관련된 다음 작업을 수행할 권한을 데이터 주체에게 제공합니다.

- 복사본 얻기
- 수정 요청
- 처리 제한
- 삭제
- 다른 컨트롤러에게 이동할 수 있도록 전자 형식으로 수신

데이터 주체가 개인 데이터에 대한 작업을 수행하도록 컨트롤러에게 공식적으로 요청하는 것을 DSR(Data Subject Rights) 요청이라고 합니다.

이 아티클에서는 Microsoft에서 GDPR에 대비하는 방법을 설명하고, 앱용 CDS에서 관리자 포털을 통해 관리자용 데이터 통합을 사용할 때 GDPR 준수를 지원하기 위해 수행할 수 있는 단계의 예제도 제공합니다. Microsoft 제품, 서비스 및 관리 도구를 사용하여 컨트롤러 고객이 DSR 요청에 대한 응답으로 Microsoft 클라우드에서 개인 데이터를 찾고 액세스하여 이에 대한 조치를 취하는 방법을 알아봅니다.

### <a name="searching-for-and-identifying-personal-data"></a>개인 데이터 검색 및 식별

앱용 CD에서 관리자에 대한 데이터 통합을 사용하면 통합자 응용 프로그램의 모든 사용자가 다음에서 데이터 통합 탭을 사용하여 해당 데이터를 볼 수 있습니다.

[https://admin.powerapps.com/dataintegration](https://admin.powerapps.com/dataintegration)

사용자에 대해 저장된 데이터는 포털에 표시됩니다. 모든 프로젝트는 프로젝트 탭에 표시됩니다.

![프로젝트 탭에서 프로젝트 보기](./media/data-integration-gdpr-dsr/projects-tab.png)

모든 연결 설정은 연결 설정 탭에 표시됩니다.

![연결 설정 탭에서 연결 설정 보기](./media/data-integration-gdpr-dsr/connections-tab.png)

모든 템플릿은 템플릿 탭에 표시됩니다.

![템플릿 탭에서 템플릿 보기](./media/data-integration-gdpr-dsr/templates-tab.png)

## <a name="securing-and-controlling-access-to-personal-information"></a>개인 정보에 대한 액세스 권한 보호 및 제어

앱용 CD의 관리자에 대한 데이터 통합에서 데이터 통합 응용 프로그램에 의해 저장된 데이터는 관리자 포털을 통해서만 액세스할 수 있습니다.

## <a name="deleting-personal-data"></a>개인 데이터 삭제

앱용 CD의 관리자에 대한 데이터 통합에서 데이터와 연결된 사용자는 사용자 작성 데이터, 프로젝트 및 연결 설정을 삭제할 수 있습니다. 해당 개인 데이터를 삭제하기 위해 사용자는 관리자 포털에 로그온할 수 있습니다. [https://admin.powerapps.com](https://admin.powerapps.com)

사용자는 프로젝트 탭으로 이동하고, 프로젝트 옆의 줄임표를 클릭한 다음, 삭제 옵션을 선택하여 프로젝트를 삭제할 수 있습니다.

![줄임표를 클릭하여 프로젝트 삭제](./media/data-integration-gdpr-dsr/projects-del.png)

사용자는 템플릿 탭으로 이동하고, 템플릿 옆의 줄임표를 클릭한 다음, 삭제 옵션을 선택하여 템플릿을 삭제할 수 있습니다.

![줄임표를 클릭하여 템플릿 삭제](./media/data-integration-gdpr-dsr/templates-del.png)

사용자는 연결 설정 탭으로 이동하고, 연결 설정 옆의 줄임표를 클릭한 다음, 삭제 옵션을 선택하여 연결 설정을 삭제할 수 있습니다.

![줄임표를 클릭하여 연결 설정 삭제](./media/data-integration-gdpr-dsr/connsets-del.png)

## <a name="exporting-personal-data"></a>개인 데이터 내보내기

앱용 CD의 관리자에 대한 데이터 통합에서 데이터와 연결된 사용자는 사용자 작성 데이터를 내보낼 수 있습니다. 해당 개인 데이터를 내보내려면 사용자는 관리자 포털에 로그온하면 됩니다.

[https://admin.powerapps.com](https://admin.powerapps.com)

프로젝트 또는 실행 기록을 포함한 프로젝트를 내보내려면 사용자는 프로젝트 탭으로 이동하고, 프로젝트 옆에 있는 줄임표를 클릭한 다음, 원하는 내보내기 옵션을 선택할 수 있습니다.

![줄임표를 클릭하여 프로젝트 내보내기](./media/data-integration-gdpr-dsr/projects-exp.png)

템플릿을 내보내려면 사용자는 템플릿 탭으로 이동하고, 템플릿 옆의 줄임표를 클릭한 다음, 내보내기 옵션을 선택할 수 있습니다.

![줄임표를 클릭하여 템플릿 내보내기](./media/data-integration-gdpr-dsr/templates-exp.png)

연결 설정을 내보내려면 사용자는 연결 설정 탭으로 이동하고, 연결 설정 옆의 줄임표를 클릭한 다음, 내보내기 옵션을 선택하면 됩니다.

![줄임표를 클릭하여 연결 설정 내보내기](./media/data-integration-gdpr-dsr/connsets-exp.png)
