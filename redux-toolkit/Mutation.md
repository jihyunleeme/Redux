# Mutations
## Overview
Mutations은 서버로 데이터를 전송하거나 로컬 캐쉬에 변경사항을 적용하는데 사용된다. Mutations은 또한 data를 cache를 무효화 하거나 re-fetch를 강제할수있다.

## Mutation Endpoints 정의하기
Mutation Endpoint는 `createApi`의 `endpoints` 영역 내에서 객체를 반환하고, `build.mutation()` 메소드를 사용하는 필드를 규정함으로써 정의됩니다.

Mutation endpoints는 URL을 구성하는 `query` 콜백(모든 URL 쿼리 매개변수 포함) 또는 임의의 비동기 논리를 수행하고 결과를 반환할 수 있는 queryFn콜백 을 정의해야 합니다. 콜백 은 queryURL, 사용할 HTTP 메서드 및 요청 본문을 포함하는 개체를 반환할 수도 있습니다.

콜백이 URL을 생성하기 위해 추가 데이터가 필요한 경우 query단일 인수를 사용하도록 작성해야 합니다. 여러 매개변수를 전달해야 하는 경우 단일 "옵션 개체" 형식으로 전달하십시오.

돌연변이 엔드포인트는 또한 결과가 캐시되기 전에 응답 내용을 수정하고, "태그"를 정의하여 캐시 무효화를 식별하고, 캐시 항목이 추가 및 제거될 때 추가 논리를 실행하기 위해 캐시 항목 수명 주기 콜백을 제공할 수 있습니다.