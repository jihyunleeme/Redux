# createApi

## `extraReducers`

Redux의 중요 컨셉중 하나는 각각의 slice reducer가 그것의 상태 slice를 "소유"하고 있다는 것이다. 그리고 그것은 많은 slice 리듀서가 독립적으로 같은 action type에 반응할수있게한다. `extraReducers`는 `createSlice`가 생성한 action 외에 다른 action type에 반응하도록 한다.

`extraReducers`로 지정된 case reducer는 extraReducers"외부" 작업을 참조하기 위한 것이므로 slice.actions에서 생성된 action이 없습니다

`extraReducers`와 마찬가지로 이 case reducers 리듀서는 `createReducer`로 전달되고, 안전하게 상태를 "변경"할 수 있습니다.

`reducers`와 `extraReducers`의 두 필드가 동일한 action 유형 문자열로 끝나는 경우, reducers의 그 기능은 해당 action 유형을 처리하는 데 사용됩니다.

## `extraReducers` builder callback 노테이션

extraReducers을 사용하는데 권장되는 사용 방법은 ActionReducerMapBuilder 인스턴스 받는 콜백을 사용하는 것 입니다.

이 빌더 표기법은 matcher 리듀서와 기본 case redecer를 슬라이스에 추가하는 유일한 방법이기도 합니다.
