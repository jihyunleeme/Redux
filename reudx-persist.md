## redux-persist는 왜 쓸까

페이지가 새로고침 되어도 user token값이 유지되어야했고,
localstorage에 token값을 저장하고 싶었다.
store값을 유지하기 위해 많은 사람들이 redux-persist libarary를 사용하지만 결국 localstorage에 저장하는건데 redux-persist를 굳이 써야해야할까 의구심이 들었다.
persist는 유지하다로 해석하였습니다. 빠른 이해를 돕기위해 약간의 의역이 있습니다.

redux-persist의 주요기능

- `persistGate`의 사용은 자동적으로 컴포넌트 지연을 제공합니다. 컴포넌트의 렌더링을 지연시킨디ㅏ. 상태가 `persisted` 될 때까지 `loading` 컴포넌트 사용과 함께 그 상태가 유지될 때까지
- `persistState, persistReducer, persistObject`와 같은 다양한 유형을 바탕으로 상태 유지시키는 기능을 커스텀 할 수 있다.
- `shallow`와 `deep`레벨을 바탕으로 다른 상태의 initalState를 `AutoMerging`
- 큰 주요 기능 `blacklist`와 `whitelist`
- 얕은 레벨과 깊은 레벨의 유지를 위한 중첩 persistence

https://stackoverflow.com/questions/49222396/why-use-redux-persist-over-manually-persisting-state-to-localstorage

https://haragoo30.medium.com/redux-persist%EB%A5%BC-%EC%86%8C%EA%B0%9C%ED%95%A9%EB%8B%88%EB%8B%A4-94cb7c8d7020
