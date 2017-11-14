데이터, 즉 Excel, 온-프레미스 원본(예: SQL Server) 및 클라우드 원본(예: Salesforce 및 SharePoint Online)의 데이터는 비즈니스 응용 프로그램과 프로세스의 핵심입니다. 데이터는 고객, 영업, 직원 및 기타 여러 가지 사항과 관련될 수 있지만, 데이터가 비즈니스에 매우 중요하며 PowerApps에서 빌드한 앱에서 중요한 역할을 수행한다는 것이 공통된 주제입니다. 지금까지의 과정에서 다양한 유형의 데이터 원본을 살펴보았으며, Microsoft Common Data Service를 먼저 소개했습니다. 이 섹션에서는 자세한 정보를 가져오고, 이점에 대해 설명하며, 서비스를 사용하는 방법을 보여 주는 데 약간의 시간을 보내도록 하겠습니다.

## <a name="understanding-the-service"></a>서비스 이해
여기서는 두 가지 다이어그램을 그려 보겠습니다. 먼저 첫 번째 다이어그램, 즉 Microsoft 비즈니스 응용 프로그램 플랫폼의 구성 요소를 보았을 것입니다. 이 시점까지 PowerApps에 대해 분명히 알고 있겠지만 Microsoft Flow, Power BI 또는 기타 구성 요소를 사용했을 수도 있습니다. Common Data Service, 커넥터 및 게이트웨이는 이러한 모든 구성 요소와 관련이 있습니다. 현재 Common Data Service는 주로 PowerApps와 Microsoft Flow에서 사용되지만 적절한 때에 다른 구성 요소에도 사용할 수 있습니다.

![비즈니스 플랫폼 다이어그램](./media/learning-common-data-service/business-platform.png)

Common Data Service가 적용되는 위치를 이해했으므로 이제 구성 요소를 살펴보겠습니다. Common Data Service를 계층 구조로 생각해 보세요. 맨 아래 수준에서 이 서비스는 확장성과 안정성이 뛰어난 방식으로 데이터를 저장하고 여러 응용 프로그램에서 사용할 수 있도록 데이터를 제공합니다. 다음 수준은 응용 프로그램과 비즈니스 프로세스에서 사용되는 엔터티, 즉 계정, 연락처, 제품 및 판매 주문과 같은 엔터티를 를 많이 포함하는 공통 데이터 모델입니다. 표준 엔터티를 확장하고 비즈니스 요구에 맞게 사용자 지정 엔터티를 만들 수 있습니다.

![Common Data Service 아키텍처 다이어그램](./media/learning-common-data-service/architecture.png)

엔터티는 단지 필드 이름, 데이터 형식 등을 설명하는 메타데이터와 여기에 저장하는 데이터의 조합일 뿐입니다. Access 또는 다른 데이터베이스를 알고 있다면 엔터티는 테이블과 매우 비슷합니다. 다음 항목에서 엔터티에 대해 더 자세히 살펴보겠지만, 이제는 Common Data Service에서 엔터티 데이터로 작업할 때 다음과 같은 이점을 고려해 보세요.

* **손쉬운 관리**: 메타데이터와 데이터는 모두 클라우드에 저장됩니다. 저장 방법에 대한 자세한 내용은 신경쓰지 않아도 됩니다.
* **손쉬운 공유**: PowerApps에서 권한을 관리하기 때문에 동료와도 데이터를 쉽게 공유할 수 있습니다.
* **손쉬운 보안**: 사용자가 액세스 권한을 부여받은 경우에만 볼 수 있도록 데이터가 안전하게 저장됩니다. 역할 기반 보안을 통해 조직 내에서 여러 사용자의 엔터티에 대한 액세스를 제어할 수 있습니다.
* **풍부한 메타데이터**: PowerApps에서 데이터 형식과 관계를 직접 활용합니다. 예를 들어 필드 형식 URL을 정의하면 데이터가 앱 내에서 하이퍼링크로 표시됩니다.
* **생산성 도구**: Microsoft Excel 및 Outlook용 추가 기능에서 엔터티를 사용하여 생산성을 높이고 데이터에 액세스할 수 있도록 합니다.
* **선택 목록**: 다양한 표준 선택 목록 집합에서 선택 목록을 포함하여 엔터티와 앱 내에서 드롭다운을 빠르게 제공합니다.

## <a name="create-a-common-data-service-database"></a>Common Data Service 데이터베이스 만들기
*환경*에서 Common Data Service 데이터베이스를 만듭니다. 과정에서 초기 환경에 대해 알아보았습니다. 간단히 요약하자면 환경은 Common Data Service와 같은 앱 및 기타 리소스를 위한 컨테이너입니다. 각 환경마다 연결된 서비스 인스턴스 하나가 있을 수 있습니다. 환경 관리자가 환경에 서비스를 추가하려면 다음 단계를 수행합니다.

**홈** 탭에서 **데이터베이스 만들기**를 클릭합니다.

![Common Data Service 데이터베이스 만들기](./media/learning-common-data-service/create-database.png)

데이터베이스에 대한 액세스를 제한할 것인지 여부를 지정하고 **내 데이터베이스 만들기**를 클릭합니다.

![Common Data Service에서 액세스 지정](./media/learning-common-data-service/specify-access.png)

프로세스가 완료되면 공통 데이터 모델에 포함된 표준 엔터티가 모두 표시됩니다. 그 중 일부는 다음과 같습니다.

![Common Data Service 표준 엔터티](./media/learning-common-data-service/standard-entities.png)

이전에 데이터베이스로 작업하지 않은 경우 이 항목 중 일부에 대해 익숙하지 않을 수도 있습니다. 그러나 일반적인 개념은 매우 간단합니다. 즉 Common Data Service는 데이터를 저장하고 계정, 연락처, 제품 및 판매 주문과 같은 공통 엔터티 측면에서 데이터를 처리하기 위한 안전하고 신뢰할 수 있는 방법을 제공합니다. 다음 항목에서는 엔터티에 대해 자세히 살펴보겠습니다.

