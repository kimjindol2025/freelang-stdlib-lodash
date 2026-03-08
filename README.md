# freelang-stdlib-lodash

FreeLang v2 stdlib — npm **lodash** 완전 대체 구현  
배열 / 객체 / 문자열 / 함수유틸 / 타입체크 / 수학 함수 모음

## 카테고리별 함수

| 카테고리 | 함수 수 | 주요 함수 |
|----------|---------|-----------|
| 배열 (Array) | 32개 | chunk, uniq, groupBy, sortBy, flatMap... |
| 객체 (Object) | 19개 | get, set, pick, omit, merge, cloneDeep... |
| 문자열 (String) | 14개 | camelCase, snakeCase, truncate, escape... |
| 함수유틸 (Function) | 8개 | debounce, memoize, once, partial... |
| 타입체크 (Lang) | 10개 | isArray, isEmpty, isEqual... |
| 수학 (Number) | 3개 | clamp, inRange, random |

## 사용법

```fl
import "stdlib/lodash"

// 배열
let chunks  = chunk([1,2,3,4,5], 2)        // [[1,2],[3,4],[5]]
let unique  = uniq([1,2,1,3,2])            // [1,2,3]
let grouped = groupBy(users, fn(u) { return u.role })

// 객체 (점 표기법 경로 지원)
let name = get(user, "profile.name", "익명")
let slim = pick(user, ["id", "name", "email"])
let deep = cloneDeep(config)

// 문자열
let key  = camelCase("my-api-key")        // myApiKey
let safe = escape("<script>alert(1)</script>")

// 함수유틸
let debouncedSave = debounce(save, 300)
let cached        = memoize(expensiveCalc)
let notNull       = negate(isNull)
```

## 중복 처리

FreeLang 내장 빌트인(`arr.*`, `str.*`, `math.*`)과 겹치는 함수는  
별도 재구현 없이 lodash 호환 래퍼로 노출됩니다.
