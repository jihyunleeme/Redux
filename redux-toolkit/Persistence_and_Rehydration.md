# Persistence and Rehydration

RTK Query는 `createApi`에 `extractRehydrationInfo` 옵션을 통해 재수화를 지원한다. 매 dispatch된 action을 전달하는 기능. `undefined` 보다는 무언가를 반환한다면, 반환 값은 이행(fulfilled)이나 오류 쿼리를 재수화하는데 사용됩니다.

> ❗ 정보!  
> 일반적으로 API 슬라이스를 유지하는 것은 권장되지 않으며 대신 **`Cache-Control` 헤더**와 같은 메커니즘은 브라우저에서 사용하여 캐시 동작을 정의해야 합니다. 사용자가 일정 시간 동안 페이지를 방문하지 않은 경우 api slice를 유지하고 재수화 하는 것은 API 슬라이스를 유지하고 재수화하면 항상 사용자에게 매우 오래된 데이터가 남을 수 있습니다. 그럼에도 불구하고 이를 처리할 브라우저 캐시가 없는 Native App과 같은 환경에서, 지속성이 여전히 실행 가능한 옵션일 수 있습니다.
