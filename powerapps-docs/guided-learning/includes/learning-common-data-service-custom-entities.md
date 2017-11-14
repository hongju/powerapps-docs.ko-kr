Common Data Service는 가장 작은 상점에서부터 대기업에 이르기까지 모든 비즈니스 고객을 위해 설계되었습니다. 공통 데이터 모델에는 많은 공통 비즈니스 시나리오를 다루는 일단의 표준 엔터티가 포함되어 있으며, 이전 항목에서 필요한 경우 해당 표준 엔터티를 확장할 수 있음을 알았습니다. 그러나 때로는 비즈니스와 관련된 문제를 해결하기 위해 완전히 다른 무언가가 필요합니다. 이 경우 사용자 지정 엔터티가 필요하며, 이 항목에서 사용자 지정 엔터티를 빌드하는 방법을 살펴보겠습니다.

엔터티를 만드는 데에는 다음 두 가지 방법이 있습니다.

* 처음부터 엔터티를 만듭니다. 이는 이 항목에서 수행할 작업입니다.
* 해당 엔터티의 필드와 설정은 복사하지만 데이터는 복사하지 않고 다른 엔터티를 기반으로 하는 엔터티를 만듭니다.

## <a name="creating-an-entity-from-scratch"></a>처음부터 엔터티 만들기
이 예에서는 '제품 검토'라는 사용자 지정 엔터티를 처음부터 만듭니다. 시작하려면 **엔터티** 탭에서 **새 엔터티**를 클릭합니다. **엔터티 이름**(공백이나 특수 문자 없음), 친숙한 **표시 이름** 및 의미 있는 **설명**을 입력합니다. 그런 다음 **다음**을 클릭합니다.

![새 엔터티](./media/learning-common-data-service-custom-entities/new-entity.png)

다음 화면에서는 모든 표준 및 사용자 지정 엔터티에 포함된 5개의 기본 필드가 표시됩니다. 사용자 고유의 필드를 추가하려면 **필드 추가**를 클릭합니다.

![기본 엔터티 필드](./media/learning-common-data-service-custom-entities/default-fields.png)

이 예에서는 다음 네 개 필드를 추가해 보겠습니다.

* **검토 날짜**: 날짜 필드이며 필수 항목입니다.
* **제품 등급**: 정수 필드이며 필수 항목입니다. 여기서는 특정 값(예: 1-5)만 지정할 수 있는 선택 목록을 사용할 수 있지만 지금은 간단하게 유지하겠습니다.
* **검토자 이름**: 텍스트 필드이며 필수 항목이 아닙니다.
* **검토자 설명**: 텍스트 필드이며 필수 항목이 아닙니다. 

엔터티에 만족하면 **만들기**를 클릭합니다. 만들어진 엔터티에는 데이터가 없습니다. 다음 항목에서는 데이터를 가져오는 방법을 보여 주겠습니다.

![사용자 지정 엔터티 필드](./media/learning-common-data-service-custom-entities/custom-fields.png)

## <a name="creating-a-relationship-between-two-entities"></a>두 엔터티 간 관계 만들기
각 검토를 특정 제품과 연결하려고 하므로 ‘제품 검토’ 엔터티와 ‘제품’ 엔터티 간의 관계를 만들어야 합니다. 제품 검토 엔터티의 **관계** 탭에서 **새 관계**를 클릭합니다. 그런 다음 **관련 엔터티**를 선택하고 **이름**, **표시 이름** 및 **설명**을 차례로 입력합니다. **저장**을 클릭하여 관계를 만듭니다.

![엔터티 간 관계 만들기](./media/learning-common-data-service-custom-entities/create-entity-relationship.png)

## <a name="connecting-to-a-custom-entity-in-powerapps-studio"></a>PowerApps Studio에서 사용자 지정 엔터티에 연결
PowerApps Studio에서 사용자 지정 엔터티에 연결하는 것은 표준 엔터티에 연결하는 것과 같습니다. **새로 만들기**를 클릭한 다음 **Common Data Service**에서 **휴대폰 레이아웃**을 클릭합니다. 왼쪽에는 사용할 수 있는 데이터 연결이 표시되고, 오른쪽에는 엔터티 목록이 표시됩니다.

![PowerApps Studio에서 엔터티에 연결](./media/learning-common-data-service-custom-entities/connect-to-custom-entity.png)

다음 항목에서는 Common Data Service에서 데이터를 관리하는 방법에 대해 살펴보겠습니다.

