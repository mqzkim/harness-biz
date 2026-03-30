# Business Department

CRM·재무·마케팅·법무·경영·인사·그랜트 비즈니스 운영 데이터 관리.

## 데이터 흐름

```
harness-biz/data/ → GitHub Raw API → helix-co /api/biz → Dashboard Pages
```

## 라우팅

→ `routing.md`

## 출력 규칙

- 모든 출력은 `data/` 하위 JSON 파일로 저장
- `meta.json`의 `last_sync` 필드를 항상 갱신
