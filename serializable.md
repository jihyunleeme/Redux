# 왜 type은 string이거나 적어도 serialiable이어야할까? 왜 action 타입은 상수여야할까?

- serializable actions은 state와 마찬가지로 Redux가 정의하는 몇가지 기능들인 타임 트래블 디버깅, 기록, 액션 재실행 같은 것을 가능하게 해준다.
- `type` value에 `Symbol` 또는 `instanceof` 검사를 사용하면 오류 남.
- 문자열은 직렬화 가능하고 그 자체로 설명되므로 나은 선택
- 미들웨어에서 사용하도록 의도된 action이라면 Symbol, Promises, non-serialiable 값을 action에서 사용하는 것은 괜찮다.
- 액션은 스토어에 도달하고 reducer에 전달될때까지만 직렬화 가능하면 됩니다.
- 성능상의 이유로 직렬화 가능한 작업을 안정적으로 시행할 수 없으므로 Redux는 오직 모든 action이 `type`정의된 일반 객체인지 확인합니다.
- 나머지는 사용자에게 달려 있지만 모든 것을 직렬화 가능하게 유지하면 문제를 디버그하고 재현하는 데 도움이된다.
- 일반적으로 사용되는 코드 조각을 캡슐화하고 중앙 집중화하는 것은 프로그래밍의 핵심 개념입니다.
- 어느 곳에서 수동으로 action 개체를 만드는 것은 확실히 가능하지만, 각 `type`값을 직접 작성하고 재사용 가능한 상수를 정의하면 코드를 더 쉽게 유지 관리할 수 있습니다. 상수를 별도의 파일에 넣으면 실수로 잘못된 문자열을 사용하는 일이 없도록 **import문에 오타가 있는지 확인**할 수 있습니다.

- 직렬화(Serialization) : 객체와 데이터 구조를 네트워크나 스토리지(Array buffer나 file 포맷으로)을 통한 전송에 적함한 포맷으로 변환되는 프로세스. 예를 들어, 자바스크립트에서는 함수 `JSON.stiringfy()`을 호출함으로써 object을 JSON 스트링으로 직렬화 할 수 있다.

- 역직렬화(Deseiralization) : 로우 레벨 포맷이(네트워크, 데이터 저장소에 전송됨) 읽을수 있는 객체나 다른 데이터 구조로 변환되는 프로세스. 예를 들어, JavaScript에서는 함수 JSON.parse()를 호출함으로써 JSON 스트링을 객체로 역직렬화 할 수 있다.

- https://redux.js.org/faq/actions#why-should-type-be-a-string-or-at-least-serializable-why-should-my-action-types-be-constants
