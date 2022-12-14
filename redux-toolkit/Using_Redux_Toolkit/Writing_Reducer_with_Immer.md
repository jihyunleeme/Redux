# Writing Reducers with Immer

[공식문서](https://redux-toolkit.js.org/usage/immer-reducers)를 읽고 정리한 내용입니다.

리덕스 툴킷의 `createReducer`, `createSlice`는 "mutating"이라는 syntax를 사용해서 불변하는 업데이트 로직을 더 간단하게 작성하도록 자동으로 `Immer`을 내부에 사용합니다. 이는 대부분의 리듀서 실행을 단순화하는데 도움이 됩니다.

Immer는 그 자체로 추상레이어이기 때문에 왜 리덕스 툴킷이 Immer를 사용하는지, 어떻게 올바르게 사용하는지 이해하는것이 중요합니다.

<br/>

## 불변성과 리덕스

불변성의 기본

자바스크립트 object와 array는 기본적으로 모두 mutable. object를 생성하면 그 필드의 내용을 바꿀수있다. array를 만들면 그 내용을 바꿀수 있음.

object, array의 변경.
메모리에 동일한 object나 array 참조지만, object의 내용은 변경되었다.

**값을 불변하게 업데이트 하기위해, 코드는 objects/arrays의 복사본을 만들고 그 복사본을 수정해야한다.**

기존 array의 변경하는 대신에 새로운 복사본 array를 반환하는 array 메소드 뿐만 아니라 자바스크립트의 object / array spread 연산자를 사용해서 수동으로 변경할수 있다.

```js
// ❌ state를 직접 변경 금지
state.value = 123;

// ⭕ copy해서 안전
return {
  ...state,
  value: 123,
};
```
