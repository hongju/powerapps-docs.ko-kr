---
title: 지원 센터 PowerApps 샘플 설치 및 구성 | Microsoft Docs
description: 지원 센터 PowerApps 샘플 설치 및 구성에 대한 단계별 지침입니다.
services: ''
suite: powerapps
documentationcenter: na
author: caburk
manager: ''
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/08/2018
ms.author: caburk
ms.openlocfilehash: be5a2f1994a55abf6936ded4dfddf84d145115c5
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="install-and-configure-the-help-desk-powerapps-sample"></a>지원 센터 PowerApps 샘플 설치 및 구성

지원 센터 PowerApps 샘플 설치 및 구성에 대한 단계별 지침입니다.

이 단계를 완료하는 데 소요되는 예상 시간: **10-15분**

이 프로세스의 데모를 보려면 이 비디오를 시청하세요.

[![지원 센터 설치 비디오](./media/help-desk-install/help-desk-install-video.png)](https://youtu.be/z4cdtD6hB_4 )

## <a name="help-desk-powerapps-sample-overview"></a>지원 센터 PowerApps 샘플 개요
지원 센터는 최종 사용자를 지원 전문가와 연결하는 사용자에게 친숙한 환경을 제공합니다. 신속하게 가장 중요한 질문에 대한 답변을 찾고 열려 있는 티켓의 진행 상황을 추적하고 이전 요청의 세부 정보를 검토하세요. 이 앱을 사용자에게 맞게 설정하려면 약간의 설정 작업이 필요합니다.

![지원 센터 PowerApp의 시작 화면](./media/help-desk-install/Login-screen.png)

지원 센터 PowerApp 샘플을 사용하는 방법을 보려면 이 비디오를 시청하세요.

[![지원 센터 데모 비디오](./media/help-desk-install/help-desk-demo-video.png)](https://youtu.be/sl5fXwwnvzI)

## <a name="prerequisites"></a>필수 조건

- PowerApps에 [등록](https://web.powerapps.com/)합니다.

## <a name="create-the-helpdesk-sharepoint-list"></a>지원 센터 SharePoint 목록 만들기

이 목록은 지원 센터 티켓을 저장합니다.

1. 웹 브라우저를 열고 https://portal.office.com으로 이동하세요.
2. 목록을 만들 수 있는 권한을 가진 계정으로 로그인합니다.
3. 지원 센터 목록을 배치할 사이트 컬렉션으로 이동합니다.
4. 웹 페이지의 오른쪽 맨 위 부분에 있는 **기어 아이콘**을 클릭합니다.
5. **앱 추가**를 클릭합니다.
6. **앱 찾기** 텍스트 상자에 **사용자 지정**을 입력합니다.
7. **검색 아이콘**을 클릭합니다.
8. **사용자 지정 목록** 앱을 클릭합니다.
9. **이름** 텍스트 상자에 **지원 센터**를 입력합니다.

    > [!IMPORTANT]
    > 목록에 다른 이름을 선택하는 경우 설치 및 구성 프로세스 중에 지원 센터를 볼 때마다 다른 이름으로 대체해야 하므로 해당 이름을 적어 두세요.

10. **만들기**를 클릭합니다.

### <a name="create-description-column"></a>설명 열 만들기

1. **열 만들기**를 클릭합니다.
2. **열 이름** 텍스트 상자에 **설명**을 입력합니다.
3. **이 열의 정보 유형** 라디오 단추 목록에서 **여러 줄의 텍스트**를 선택합니다.
4. **이 열에 정보가 포함되어야 함** 라디오 단추 목록에서 **예**를 선택합니다.
5. **허용할 텍스트 유형 지정** 라디오 단추 목록에서 **일반 텍스트**를 선택합니다.
6. **확인**을 클릭합니다.

### <a name="create-category-column"></a>범주 열 만들기

1. **열 만들기**를 클릭합니다.
2. **열 이름** 텍스트 상자에 **범주**를 입력합니다.
3. **이 열의 정보 유형** 라디오 단추 목록에서 **선택**을 선택합니다.
4. **별도의 줄에 각 선택 입력** 텍스트 상자에서 별도의 줄에 각각 다음 값을 입력합니다. 
    - 노트북 / PC 장비 문제
    - 노트북 / PC 소프트웨어 문제
5. **고유 값 적용** 라디오 단추 목록에서 **아니요**를 선택합니다.
6. **사용 중인 선택 표시** 라디오 단추 목록에서 **드롭 다운 메뉴**를 선택합니다.
7. **기본값** 텍스트 상자에서 **노트북 / PC 장비 문제**를 입력합니다.
8. **확인**을 클릭합니다.

### <a name="create--complete-column"></a>열 완료율(%) 만들기

1. **열 만들기**를 클릭합니다.
2. **열 이름** 텍스트 상자에 **연 완료율(%)** 을 입력합니다.
3. **이 열의 정보 유형** 라디오 단추 목록에서 **숫자(1, 10, 100)** 를 선택합니다.
4. **이 열에 정보가 포함되어야 함** 라디오 단추 목록에서 **아니요**를 선택합니다.
5. **확인**을 클릭합니다.

### <a name="create-priority-column"></a>우선 순위 열 만들기

1. **열 만들기**를 클릭합니다.
2. **열 이름** 텍스트 상자에 **우선 순위**를 입력합니다.
3. **이 열의 정보 유형** 라디오 단추 목록에서 **선택**을 선택합니다.
4. **별도의 줄에 각 선택 입력** 텍스트 상자에서 별도의 줄에 각각 다음 값을 입력합니다. 
    - 높음
    - 중간
    - 낮음
5. **고유 값 적용** 라디오 단추 목록에서 **아니요**를 선택합니다.
6. **사용 중인 선택 표시** 라디오 단추 목록에서 **드롭 다운 메뉴**를 선택합니다.
7. **기본값** 텍스트 상자에 **낮음**을 입력합니다.
8. **확인**을 클릭합니다.

### <a name="create-taskstatus-column"></a>TaskStatus 열 만들기

1. **열 만들기**를 클릭합니다.
2. **열 이름** 텍스트 상자에 **TaskStatus**를 입력합니다.
3. **이 열의 정보 유형** 라디오 단추 목록에서 **선택**을 선택합니다.
4. **별도의 줄에 각 선택 입력** 텍스트 상자에서 별도의 줄에 각각 다음 값을 입력합니다. 
    - 시작되지 않음
    - 진행 중
    - 완료됨
    - 연기됨
    - CSR에서 대기 중
5. **고유 값 적용** 라디오 단추 목록에서 **아니요**를 선택합니다.
6. **사용 중인 선택 표시** 라디오 단추 목록에서 **드롭 다운 메뉴**를 선택합니다.
7. **기본값** 텍스트 상자에 **시작되지 않음**을 입력합니다.
8. **확인**을 클릭합니다.

### <a name="create-assignedto-column"></a>AssignedTo 열 만들기

1. **열 만들기**를 클릭합니다.
2. **열 이름** 텍스트 상자에 **AssignedTo**를 입력합니다.
3. **이 열의 정보 유형** 라디오 단추 목록에서 **개인 또는 그룹**을 선택합니다.
4. **이 열에 정보가 포함되어야 함** 라디오 단추 목록에서 **아니요**를 선택합니다.
5. **다중 선택 허용** 라디오 단추 목록에서 **아니요**를 선택합니다.
6. **확인**을 클릭합니다.

### <a name="edit-title-column"></a>‘제목’ 열 편집

1. **제목** 열 링크를 클릭합니다.
2. **이 열에 정보가 포함되어야 함** 라디오 단추 목록에서 **아니요**를 선택합니다.
3. **확인**을 클릭합니다.

## <a name="download-the-help-desk-powerapp"></a>지원 센터 PowerApp 다운로드

1.  웹 브라우저에서 http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/helpdesk/docs/HelpDesk(SP_List).zip으로 이동합니다.
2.  PowerApps 패키지를 다운로드하여 컴퓨터에 저장 합니다.

## <a name="create-connections"></a>연결 만들기

1.  웹 브라우저에서 https://web.powerapps.com으로 이동합니다.
2.  등록 시 사용한 동일한 자격 증명을 제공하여 로그인합니다.
3.  왼쪽 메뉴에서 **연결**을 선택합니다.
    
### <a name="create-office-365-outlook-connection"></a>Office 365 Outlook 연결 만들기

1.  **+ 새 연결**을 클릭합니다.
2.  **검색** 텍스트 상자에 **Office 365 Outlook**을 입력합니다.
3.  목록에서 **Office 365 Outlook**을 선택합니다.
4.  **만들기**를 클릭합니다.
5.  팝업 창에서 로그인하는 데 사용한 계정을 선택합니다.

### <a name="create-sharepoint-connection"></a>SharePoint 연결 만들기

1.  **+ 새 연결**을 클릭합니다.
2.  **검색** 텍스트 상자에 **Outlook**을 입력합니다.
3.  목록에서 **SharePoint**를 선택합니다.
4.  **만들기**를 클릭합니다.
5.  팝업 창에서 로그인하는 데 사용한 계정을 선택합니다.

### <a name="create-office-365-users-connection"></a>Office 365 사용자 연결 만들기

1.  **+ 새 연결**을 클릭합니다.
2.  **검색** 텍스트 상자에 **Office 365 사용자**를 입력합니다.
3.  목록에서 **Office 365 사용자**를 선택합니다.
4.  **만들기**를 클릭합니다.
5.  팝업 창에서 로그인하는 데 사용한 계정을 선택합니다.

## <a name="import-the-help-desk-powerapp"></a>지원 센터 PowerApp 가져오기

1.  웹 브라우저에서 https://web.powerapps.com으로 이동합니다.
2.  등록 시 사용한 동일한 자격 증명을 제공하여 로그인합니다.
3.  왼쪽 메뉴에서 **앱**을 선택합니다. 
4.  **패키지(미리 보기) 가져오기**를 클릭합니다.
    
    ![패키지 가져오기 화면](./media/help-desk-install/import-package.png)

5.  **업로드** 단추를 클릭하고 이전 단계에서 다운로드한 PowerApp 패키지를 선택합니다.
6.  **앱** 및 **흐름** 리소스 유형의 **가져오기 설정**을 **새로 만들기**로 설정합니다.
7.  **SharePoint** 및 **Outlook** 연결의 **가져오기 설정**을 **가져올 때 선택**으로 설정합니다.
    
    ![설정 가져오기 화면](./media/help-desk-install/import-settings.png)

8.  **SharePoint 연결**의 **빨간색 아이콘**을 클릭합니다.
9.  연결 목록에서 사용자 이름이 있는 항목을 클릭합니다.

    ![설정 가져오기 화면](./media/help-desk-install/import-settings-sharepoint.png)

10. **저장**을 클릭합니다.
11.  **Office 365 Outlook 연결**의 **빨간색 아이콘**을 클릭합니다.
12.  연결 목록에서 사용자 이름이 있는 항목을 클릭합니다.

    ![설정 가져오기 화면](./media/help-desk-install/import-settings-office365outlook.png)

13. **저장**을 클릭합니다.

    > [!TIP] 
    > 완료되면 다음과 같은 화면이 표시됩니다.

    ![설정 가져오기 화면](./media/help-desk-install/import-settings-done.png)

14. **가져오기**를 클릭하고 프로세스가 완료될 때까지 기다립니다.

    ![설정 가져오기 화면](./media/help-desk-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-list"></a>SharePoint 목록을 사용하도록 PowerApp 구성

1. 웹 브라우저에서 **앱**을 클릭합니다.
2. 지원 센터 PowerApps 옆에 있는 **줄임표**를 클릭합니다.
3. **웹에서 편집**을 클릭합니다.
4. **허용**을 클릭합니다.

### <a name="delete-connections"></a>연결 삭제

1. **보기**를 클릭합니다.
2. **데이터 원본**을 클릭합니다.
3. **데이터** 창에서 **지원 센터** 옆에 있는 **줄임표**를 클릭합니다.
4. **제거**를 클릭합니다.

### <a name="helpdesk-list"></a>지원 센터 목록

1. **보기**를 클릭합니다.
2. **데이터 원본**을 클릭합니다.
3. **데이터** 창에서 **+ 데이터 원본 추가**를 클릭합니다.
4. **SharePoint**를 선택합니다.
5. **만들기**를 클릭합니다.
6. **최근에 사용한 사이트** 목록에서 지원 센터 목록을 만든 SharePoint 사이트를 선택합니다.

    > [!TIP] 
    > 사이트가 목록에 나타나지 않을 경우 텍스트 상자에 SharePoint 사이트 URL을 입력하고 **이동**을 클릭합니다.

7. 목록 맨 위에 있는 **검색** 텍스트 상자에 **지원 센터**를 입력합니다.
8. **지원 센터** 목록 옆에 있는 확인란을 선택합니다.
9. **연결**을 클릭합니다.

### <a name="update-admin-list"></a>업데이트 관리자 목록

1. **LoginScreen**을 선택합니다.
2. 드롭다운 메뉴에서 **OnStart**를 선택합니다.
3. 수식 창을 확장하고 **AdminList** 컬렉션을 찾습니다.
4. **user@microsoft.com**을 지원 센터 관리자로 바꿉니다.

    ![업데이트 관리자 목록](./media/help-desk-install/Change-admin.png)
    
    > [!TIP] 
    > 1 초과 관리자가 있는 경우 관리자를 구분하려면 쉼표를 사용하세요.  예: "admin1@microsoft.com","admin2@microsoft.com".

5. **파일**을 클릭합니다.
6. **저장**을 클릭합니다.
7. **게시**를 클릭합니다.
8. **이 버전 게시**를 클릭합니다.

## <a name="modify-the-flow"></a>흐름 수정

1.  왼쪽 메뉴에서 **흐름**을 클릭합니다.
2.  로그인하라는 메시지가 표시되면 등록 시 사용한 동일한 자격 증명을 제공하여 로그인합니다.
3.  최상위 메뉴에서 **내 흐름**을 선택합니다.
4.  **HelpDeskFlow** 흐름 옆에 있는 **연필 아이콘**을 클릭합니다. 
 
    ![흐름 편집 화면](./media/help-desk-install/edit-flow.png)

5.  **항목 가져오기** 작업을 확장합니다. 
6.  자신이 만든 지원 센터 SharePoint 목록에 맞게 **사이트 주소** 및 **목록 이름**을 변경합니다.
    
    ![흐름 편집 화면](./media/help-desk-install/edit-flow-getitems.png)

    > [!TIP] 
    > 수동으로 입력할 필요 없이 드롭다운 목록에서 선택할 수 있습니다.

7.  **스위치**를 확장합니다.
8.  **시작되지 않은** 경우를 확장합니다.
9.  **이메일 보내기** 작업을 확장합니다.
10. 지원 센터 관리자 이메일에 맞게 **수신자**를 변경합니다.

    ![흐름 편집 화면](./media/help-desk-install/edit-flow-condition-send-email.png) 

11. **흐름 업데이트**를 클릭합니다.

## <a name="play-the-powerapp"></a>PowerApp 재생

1. 웹 브라우저에서 **앱**을 클릭합니다.
2. 지원 센터 PowerApps 옆에 있는 **줄임표**를 클릭합니다.
3. **열기**를 클릭합니다. 

지원 센터 PowerApp 샘플을 사용하는 방법을 보려면 이 비디오를 시청하세요.

[![지원 센터 데모 비디오](./media/help-desk-install/help-desk-demo-video.png)](https://youtu.be/sl5fXwwnvzI)

##<a name="next-steps"></a>다음 단계
- [SharePoint 목록 양식 사용자 지정](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/customize-list-form)
- [컨트롤 추가 및 구성](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/add-configure-controls)
- [SharePoint 목록 또는 라이브러리에 대한 권한 편집 및 관리](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)
 
