---
title: "템플릿에서 앱 만들기 | Microsoft Docs"
description: "템플릿 기반의 앱을 자동으로 만들어 저장하기 위한 단계별 지침입니다."
services: 
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/03/2017
ms.author: sharik
ms.openlocfilehash: e8479535098bfd07121d618bc293628c67773b1c
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="create-and-run-an-app-from-a-template"></a>템플릿에서 앱 만들고 실행
특정 시나리오에 대한 템플릿 기반의 앱을 자동으로 만든 다음 앱을 실행하여 기본 동작을 파악합니다. 앱을 사용자 지정한 다음 저장하여 다른 사용자와 공유하는 방법에 대해 알아보세요.

## <a name="prerequisites"></a>필수 조건
* PowerApps에 [등록](signup-for-powerapps.md)하여 [설치](http://aka.ms/powerappsinstall)하고 연 다음 등록 시 사용했던 동일한 자격 증명으로 로그인합니다.

    > [!NOTE]
> 이 기능을 사용하려면 릴리스 2.0.510 이상을 실행해야 합니다. 릴리스를 확인하려면 왼쪽 가장자리의 **파일** 메뉴를 열고, **계정**을 클릭하거나 탭한 다음 **제품 정보** 아래를 확인합니다.

* DropBox, OneDrive, Google 드라이브 등과 같은 클라우드 저장소 계정입니다.

## <a name="create-an-app"></a>앱 만들기
1. Windows용 PowerApps Studio 또는 웹용 PowerApps Studio에서 **새로 만들기**(화면 왼쪽 가장자리 근처)를 클릭하거나 탭합니다.

    ![파일 메뉴의 새 옵션](./media/get-started-test-drive/file-new.png)
2. **앱 템플릿** 타일에서 **휴대폰 레이아웃**을 클릭하거나 탭합니다.

   > [!NOTE]
> 태블릿 레이아웃에 대한 템플릿에서 앱을 만들 수도 있지만 이 자습서는 휴대폰 옵션을 중점적으로 다룹니다.

   ![태블릿 또는 휴대폰 전용 앱을 만드는 옵션](./media/get-started-test-drive/phone-app.png)

   템플릿 목록이 나타납니다.

3. 클라우드 저장소 계정에 대한 연결을 만들지 않은 경우:

   1. 화면 하단에서 **선택**을 클릭하거나 탭합니다.

       ![템플릿 보기 내 연결을 만드는 옵션](./media/get-started-test-drive/add-connection.png)
   2. 사용하려는 계정을 클릭하거나 탭합니다.

       ![템플릿에서 앱을 만들기 위한 연결 목록](./media/get-started-test-drive/store-data.png)
   3. 자격 증명을 제공한 다음 **사용**을 클릭하거나 탭하여 액세스 권한을 부여합니다.

       화면 하단 부근에 연결이 나타납니다.

4. 템플릿 목록에서 템플릿을 클릭하거나 탭한 다음 오른쪽 아래 모서리 부근의 **사용**을 클릭하거나 탭합니다.

    ![PowerApps 템플릿 열기](./media/get-started-test-drive/open-template.png)

    샘플 데이터가 클라우드 저장소 계정에 복사되고 해당 앱이 만들어지면 해당 홈 페이지가 나타납니다.

## <a name="run-the-app"></a>앱 실행
템플릿의 앱은 대부분의 시간을 사용자 지정에 사용할 기본 작업 영역에서 열립니다. 해당 앱을 변경하기 전에 **미리 보기** 모드에서 앱이 어떻게 작동하는지 알아보려면 이 섹션의 단계를 따르세요.

> [!TIP]
> 기본 작업 영역에서 앱을 설계하고 개발한 다음 다른 사용자와 공유하기 전에 먼저 **미리 보기** 모드에서 앱을 테스트하세요.

1. PowerApps를 사용해 보지 않은 경우 소개 둘러보기 화면을 살펴봅니다. 그렇지 않으면 **건너뛰기**를 클릭하거나 탭합니다.

    ![둘러보기 화면 열기](./media/get-started-test-drive/quick-tour.png)

    나중에 오른쪽 위 모서리의 물음표 아이콘을 클릭하거나 탭한 다음 **소개 둘러보기**를 클릭하거나 탭하면 언제든지 둘러보기를 시작할 수 있습니다.

2. 왼쪽 탐색 모음에서 위쪽 가장 가까이에 있는 화면을 클릭하거나 탭합니다.

3. F5 키를 누르거나, 오른쪽 위 모서리에서 오른쪽 화살표를 클릭하거나 탭하여 해당 앱을 **미리 보기** 모드로 엽니다.

    ![미리 보기 모드 열기 단추](./media/get-started-test-drive/open-preview.png)

    앱은 앱의 기능을 보여 주기 위해 샘플 데이터로 미리 채워집니다. 예를 들어, 비용 예측 앱의 경우 일정을 만들고 특정 크기의 방에 특정 바닥 제품을 설치하는 비용을 예상하는 데이터가 포함되어 있습니다.

4. 해당 앱의 기본 동작을 탐색하고, 클라우드 계정에서 해당 데이터에 대한 변경 내용이 반영되고 있는지 확인합니다.

    예를 들어, 일정을 확인하고 비용 예측 앱에서 예상 비용을 만듭니다.

5. PowerApps 제목 표시줄 아래에서 오른쪽 위 모서리의 **'X'** 아이콘을 선택하여 기본 작업 영역으로 돌아갑니다.

    ![미리 보기 모드 닫기 단추](./media/get-started-test-drive/close-preview.png)

## <a name="customize-the-app"></a>앱 사용자 지정
이 앱을 비롯하여 모든 앱을 다음과 같은 방법으로 사용자 지정할 수 있습니다.

* [화면 크기, 방향 또는 둘 다 변경](set-aspect-ratio-portrait-landscape.md)
* [다른 데이터 원본 추가](add-data-connection.md)
* [하나 이상의 화면 추가](add-screen-context-variables.md)
* [다른 컨트롤 추가 및 구성](add-configure-controls.md)
* [앱의 동작 방식 변경](working-with-formulas.md)

## <a name="next-steps"></a>다음 단계
1. Ctrl-S를 눌러 앱 이름을 지정한 다음 **저장**을 클릭하거나 탭하여 앱을 클라우드에 저장합니다.
2. 조직의 다른 사용자와 [앱을 공유](share-app.md)합니다.

    > [!NOTE]
> 앱을 공유하기 전에 공유하려는 사용자에게 해당 데이터에 대한 액세스 권한이 있는지 확인합니다. 예를 들어, 클라우드 저장소 계정의 경우 [Excel 또는 다른 파일을 공유](share-app-data.md)해야 합니다.
