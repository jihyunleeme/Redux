# Actions

- actions은 앱에서 발생하는 것을 설명하는 일반 개체이다.
- 데이터를 변경하려는 의도를 설명하는 유일한 방법으로 사용됩니다. - **액션이 디스패치해야 하는 객체인 것은 상용구(boilerplate)가 아니라 Redux 의 기본 설계 선택 중 하나라는 것이 중요**합니다 .

- Flux와 유사하다고 주장하는 프레임워크가 있지만 액션 객체의 개념이 없습니다.
- 예측 가능하다는 측면에서 이것은 Flux 또는 Redux에서 한 발짝 뒤로 물러난 것입니다.
- 직렬화 가능한 일반 개체 action이 없으면 사용자 세션을 기록 및 재생하거나 시간 여행으로 핫 리로딩을 구현하는 것이 불가능합니다 .
- 데이터를 직접 수정하려 한다면, Redux가 필요하지 않습니다.

https://redux.js.org/usage/reducing-boilerplate#actions