---
title: 파워 쿼리를 사용하여 Common Data Service의 엔터티에 데이터를 추가하기 위한 빠른 시작 | Microsoft Docs
description: 파워 쿼리를 사용하여 다른 데이터 원본에서 앱용 Common Data Service의 새로운 엔터티 또는 기존 엔터티에 데이터를 추가하는 것에 대한 단계별 지침이 포함된 빠른 시작입니다.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: anneta
ms.openlocfilehash: 77906602fad6708857a6c34f44d1bc3c7c258f6c
ms.sourcegitcommit: aa2d0166dccb38100183c093f293233b46f3669d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2018
---
# <a name="quickstart-add-data-to-an-entity-in-the-common-data-service-by-using-power-query"></a>빠른 시작: 파워 쿼리를 사용하여 Common Data Service의 엔터티에 데이터 추가
이 절차에서는 [앱용 Common Data Service](data-platform-intro.md)에서 엔터티를 만들고 파워 쿼리를 사용하여 OData 피드에서 해당 엔터티를 데이터로 채웁니다. 일부 기술을 사용하여 이러한 온라인 및 온-프레미스 원본의 데이터를 다음 항목 간에 통합할 수 있습니다.

* SQL Server
* Salesforce
* IBM DB2
* Access
* Excel
* Web API
* OData 피드
* 텍스트 파일

또한 새로운 엔터티 또는 기존 엔터티에 로드하기 전에 데이터를 필터링, 변환 및 결합할 수 있습니다.

PowerApps에 대한 라이선스가 없으면 [무료로 등록](../signup-for-powerapps.md)할 수 있습니다.

## <a name="prerequisites"></a>필수 조건
이 토픽을 수행하려면 엔터티를 만들 수 있는 [환경](../canvas-apps/working-with-environments.md)으로 전환해야 합니다.

## <a name="specify-the-source-data"></a>원본 데이터 지정

1. [PowerApps](https://web.powerapps.com)에 로그인한 다음, 왼쪽 가장자리 근처 **데이터**에 아래쪽 화살표를 클릭하거나 탭합니다.

    ![PowerApps 홈페이지](./media/data-platform-cds-newentity-pq/sign-in.png)

1. 표시되는 목록에서 **데이터 통합**을 클릭하거나 탭한 다음, 창의 오른쪽 위 모서리 근처에 있는 **새 프로젝트**를 클릭하거나 탭합니다.

1. 데이터 원본 목록에서 **OData**를 클릭하거나 탭합니다.

    ![OAuth 커넥터 선택](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. **연결 설정**에서 이 URL을 입력하거나 붙여넣은 다음, **다음**을 선택합니다.<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. 테이블 목록에서 **고객** 확인란을 선택한 다음, **다음**을 클릭하거나 탭합니다.

    ![Customers 테이블 선택](./media/data-platform-cds-newentity-pq/select-table.png)

1. (선택 사항) 포함할 열을 선택하거나, 하나 이상의 방법으로 테이블을 변경하거나, 인덱스 또는 조건부 열을 추가하거나, 기타 항목을 변경하여 필요에 따라 스키마를 수정합니다.

1. 왼쪽 아래 모서리에서 **다음**을 클릭하거나 탭합니다.

## <a name="specify-the-target-entity"></a>대상 엔터티 지정
1. **설정 로드**에서 **새 엔터티로 로드**를 선택합니다.

    ![새 엔터티의 이름 지정](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    새 엔터티에 다른 이름 또는 표시 이름을 지정할 수 있지만 이 자습서를 정확하게 수행하려면 기본값을 그대로 둡니다.

1. **주 이름 필드** 목록에서 **ContactName**을 클릭하거나 탭한 다음, 오른쪽 아래 모서리에서 **다음**을 클릭하거나 탭합니다.

    다른 기본 이름 필드를 지정하고, 원본 테이블의 다른 열을 만드는 엔터티의 각 필드 또는 둘 다에 매핑할 수 있습니다. 이 자습서를 정확하게 수행하려면 기본 열 매핑을 유지합니다.

1. **부하 상태**가 **완료됨**인 경우 오른쪽 아래 모서리에 있는 **완료**를 선택합니다.

1. **데이터**(왼쪽 가장자리 근처)에서 **엔터티**를 선택하여 데이터베이스의 엔터티 목록을 표시합니다.

    OData 피드에서 만든 **고객** 엔터티가 사용자 지정 엔터티로 나타납니다.

    ![표준 및 사용자 지정 엔터티 목록](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> 파워 쿼리를 사용하여 데이터를 기존 엔터티에 추가하는 경우 해당 엔터티의 모든 데이터를 덮어씁니다.

**기존 엔터티에 로드**를 선택하는 경우 **고객** 테이블에서 데이터를 추가하는 엔터티를 지정할 수 있습니다. 예를 들어 데이터를 Common Data Service가 제공하는 **계정** 엔터티에 추가할 수 있습니다. **원본 열**에서 **계정** 엔터티의 **이름** 열에 추가해야 하는 **고객** 테이블의 **ContactName** 열에 있는 해당 데이터를 지정할 수 있습니다.

![새 엔터티의 이름 지정](./media/data-platform-cds-newentity-pq/existing-entity.png)

이 기능에 대해 매우 기대하고 있으며 사용자의 의견을 기다리고 있습니다. 이 기능에 대한 [제안 및 의견을 보내주세요](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).

[사용 권한에 대한 오류 메시지](data-platform-cds-newentity-troubleshooting-mashup.md)가 표시되면 관리자에게 문의하세요.