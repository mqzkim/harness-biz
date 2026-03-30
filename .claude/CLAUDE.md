# Business Department

CRM·재무·마케팅·법무·경영·인사·그랜트 비즈니스 운영 데이터 관리.

## 라우팅

→ `routing.md`

## 참조

| 파일 | 내용 |
|------|------|
| `config/department.json` | 부서 설정 (색상, 스코프, 페르소나, 테이블 매핑) |
| `data/meta.json` | 동기화 상태 (last_sync, version) |
| `~/.claude/references/workspace-context.md` | 워크스페이스 전체 구조 |

## 데이터 흐름

```
Supabase DB → biz-sync skill → data/*.json → GitHub → helix-co /api/biz
```
