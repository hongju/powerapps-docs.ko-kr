---
title: PowerApps의 엔터티 개요 | MicrosoftDocs
description: PowerApps 포털을 사용하여 엔터티를 만들고 편집하는 방법 알아보기
ms.custom: ''
ms.date: 07/25/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: ''
caps.latest.revision: 0
ms.author: matp
manager: kvivek
ms.openlocfilehash: 1c45941a7b00e9393aab429d2573b2e48964a4de
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39695996"
---
# <a name="entity-relationships-overview"></a>엔터티 관계 개요

엔터티 관계는 엔터티 레코드가 다른 엔터티 또는 동일한 엔터티 레코드에 연결될 수 있는 방법을 정의합니다. 엔터티 관계에는 두 가지 유형이 있습니다.
- **일대다 관계**. 일대다 엔터티 관계에서 참조(관련) 엔터티 레코드는 참조된(기본) 단일 엔터티 레코드와 연결할 수 있습니다. 참조된 엔터티 레코드는 "부모"라고도 하고 참조하는 엔터티의 레코드를 "자식"이라고도 합니다.  다대일 관계는 일대다 관계에 대한 자식 관점일 뿐입니다.
- **다대다 관계**. 다대다 엔터티 관계에서 많은 엔터티 레코드는 다른 많은 엔터티 레코드와 연결할 수 있습니다. 다대다 관계를 사용하여 관련된 레코드는 동료로 간주될 수 있으며 관계는 상호적입니다. 

## <a name="see-also"></a>참고 항목
[엔터티 간 관계 만들기](data-platform-entity-lookup.md) <br/>
[PowerApps 포털을 사용하여 앱용 Common Data Service에서 다대다 엔터티 관계 만들기](create-edit-nn-relationships-portal.md)