# harness-biz

Business 부서 데이터 저장소 — CRM, 재무, 마케팅, 법무, 경영, 인사, 그랜트.

## 구조

```
harness-biz/
├── .claude/           # harness-infra 기반
├── data/
│   ├── meta.json      # 부서 메타
│   ├── crm.json       # 고객·거래 파이프라인
│   ├── finance.json   # 재무 현황
│   ├── marketing.json # 캠페인·콘텐츠
│   ├── legal.json     # 계약·컴플라이언스
│   ├── management.json # OKR·회의·의사결정
│   ├── hr.json        # 에이전트 인사·성과
│   └── grants.json    # 그랜트 발굴·신청
└── config/
    └── department.json
```

## helix-co 대시보드 페이지

| 페이지 | 경로 | 데이터 파일 |
|--------|------|-----------|
| CRM | /crm | crm.json |
| Finance | /finance | finance.json |
| Marketing | /marketing | marketing.json |
| Legal | /legal | legal.json |
| Management | /management | management.json |
| HR | /hr | hr.json |
| Grants | /grants | grants.json |
