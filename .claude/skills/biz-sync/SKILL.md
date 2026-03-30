---
name: biz-sync
description: Supabase DB에서 CRM·재무·마케팅·법무·경영·인사·그랜트 데이터를 추출하여 data/ 하위 JSON으로 동기화하고 harness-biz 레포에 커밋한다. CRM, finance, marketing, legal, management, HR, grants 요청 시 사용한다.
user-invocable: true
argument-hint: "[crm|finance|marketing|legal|management|hr|grants|all]"
allowed-tools: Read, Write, Edit, Bash, Glob, Grep
---

# Biz Sync

helix-co Supabase DB → harness-biz/data/ JSON 동기화.

## 실행 절차

### Step 1: 대상 파악

`$ARGUMENTS`에서 동기화 대상을 파악한다.
인수 없으면 → `all` 로 처리한다.

### Step 2: 데이터 추출

| 대상 | Supabase 테이블 | 출력 파일 |
|------|----------------|----------|
| crm | contacts, deals | data/crm.json |
| finance | transactions, budgets | data/finance.json |
| marketing | (campaigns) | data/marketing.json |
| legal | contracts | data/legal.json |
| management | objectives, meetings, decisions | data/management.json |
| hr | agents (성과·교육 관점) | data/hr.json |
| grants | (grants) | data/grants.json |

### Step 3: JSON 생성

각 출력 파일의 `summary` 섹션을 집계한다.
`data/meta.json`의 `last_sync`를 현재 시간으로 갱신한다.

### Step 4: 커밋·푸시

```bash
git add data/
git commit -m "sync: <대상> 동기화 (<날짜>)"
git push origin main
```
