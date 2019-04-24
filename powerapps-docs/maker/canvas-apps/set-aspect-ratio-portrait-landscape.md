---
title: 캔버스 앱의 화면 크기 및 방향 변경 | Microsoft Docs
description: PowerApps에서 캔버스 앱의 화면 크기 및 방향과 같은 설정을 변경하는 단계별 지침
author: evchaki
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2018
ms.author: evchaki
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c4d9f648a4519ef30887d8d0739d7dc3d940555b
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61536043"
---
# <a name="change-screen-size-and-orientation-of-a-canvas-app-in-powerapps"></a>PowerApps에서 캔버스 앱의 화면 크기 및 방향 변경
화면 크기와 방향을 변경하여 캔버스 앱을 사용자 지정합니다.

## <a name="prerequisites"></a>필수 조건

앱 만들기 또는 편집에 대 한 하나를 열어 선택한 후 **앱 설정** 에 **파일** 메뉴.

## <a name="change-screen-size-and-orientation"></a>화면 크기 및 방향 변경
1. **앱 설정** 아래에서 **화면 크기 + 방향**을 선택합니다.

    ![앱의 화면 크기 및 방향을 변경하는 옵션](./media/set-aspect-ratio-portrait-landscape/size-orientation.png)

1. 에 **방향을** 목록에서 **세로** 또는 **가로**합니다.

1. (태블릿 앱에만 해당) 아래 **가로 세로 비율**, 다음이 단계 중 하나를 수행 합니다.

    - 이 앱에 대 한 대상 장치와 일치 하는 비율을 선택 합니다.
    - 선택 **사용자 지정** 사용자 고유의 크기를 50 3840 사이의 50 2160 사이 높이 지정 합니다.

    ![태블릿 앱의 가로 세로 비율 변경](./media/set-aspect-ratio-portrait-landscape/aspect-tablet.png)
    
1. 아래 **에 맞게 크기 조정**를 지정 **에** 또는 **해제**합니다.

    이 설정은 기본적으로 켜져 앱 화면 장치에서 사용 가능한 공간에 맞게 조정 되도록 합니다. 앱에서이 설정을 표시 되는 경우 **너비** 속성과 일치 해당 **DesignWidth**, 및 앱의 **높이** 일치 하는 **DesignHeight**.

    이 설정을 해제 하면 앱이는 실행 되 고 모든 사용 가능한 공간을 차지 하는 장치의 가로 세로 비율을 조정 합니다. 앱이 조정 하지 않습니다 하 고 결과적으로, 화면 자세한 정보를 표시할 수 있습니다.

    이 설정을 해제 된 경우 **가로 세로 비율 고정** 자동으로 해제 되어 사용 하지 않도록 설정 합니다. 또한 합니다 **너비** 모든 화면 속성 `Max(App.Width, App.DesignWidth)`, 및 해당 **높이** 속성 `Max(App.Height, App.DesignHeight)` 앱 실행 되는 창의 크기를 추적 하 합니다. 이 변경으로 다양 한 장치 및 창 크기에 응답 하는 앱을 만들 수 있습니다. 자세한 정보: [반응 형 레이아웃 만들기](create-responsive-layout.md)

1. **가로 세로 비율 고정** 아래에서 **고정** 또는 **해제**를 지정합니다.

    이 설정이 켜져 있으면 앱 화면 방향 및 장치에 관계 없이 2-3 단계에 지정 된 가로 세로 비율 유지 됩니다. 예를 들어, 웹 브라우저에서 실행 중인 휴대폰 앱을 창에 입력 하는 대신 각 면에 어두운 색 막대를 보여 주는 휴대폰의 비율을 유지 합니다.

    이 설정이 off 인 경우 앱에는 실행 (이므로 필요한 경우 UI를 왜곡) 장치의 가로 세로 비율을 조정 합니다.

1. **방향 고정** 아래에서 **고정** 또는 **해제**를 지정합니다.

    앱의 방향을 잠그는 경우 앱에 지정 된 방향을 유지 됩니다. 앱을 다른 방향의 화면 되는 장치에서 실행 중인 경우 앱 잘못 표시 하 고 원치 않는 결과가 나타날 수 있습니다. 앱의 방향을 해제 하면, 실행 되는 장치의 화면 방향으로 조정 합니다.

    앱의 방향을 사용 하 여 수정할 수도 있습니다 **사용 앱 사용자 환경을 포함** 에 **고급 설정**합니다. 이 기능은 왼쪽 위 포함 되 고 호스팅 캔버스의 배경색이 흰색으로 변경 하는 경우 앱을 맞춥니다.

1. **적용**을 선택하여 변경 내용을 저장합니다.

## <a name="next-step"></a>다음 단계
**파일** 메뉴에서 **저장**을 선택하여 새롭게 설정된 앱을 다시 게시합니다.