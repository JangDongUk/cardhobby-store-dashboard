# 카드하비 스마트스토어 대시보드

스마트스토어 매출/마케팅 데이터를 시각화한 운영 대시보드

---

## 주요 기능

### 📊 데이터 시각화
- KPI 카드 6개 — 총 매출 / 주문 수 / 전환율 / 방문자 / 신규 주문 / 재구매 주문
- 직전 기간 대비 증감률 자동 계산 및 표시
- 매출 트렌드 / 카테고리 / 브랜드 / 시리즈 / 채널 / 요일별 차트
- 광고비 & ROAS 추이
- 키워드 성과 TOP 리스트 + 상세 테이블
- 상품별 매출 테이블 + 매출 비중 바
- 운영 메모 타임라인

### 🧠 의사결정 보조
- **이번 기간 핵심 리포트** — 핵심 요약 / 확인 필요 신호 / 추천 액션 자동 생성
- **상품 집중도 진단** — 상위 3개 상품 매출 비중 및 집중도 상태 (높음 / 주의 / 분산 양호)
- **신규/재구매 비율 카드** — 가로 stacked bar + 고객 구조 진단 및 CRM 액션 문구
- **차트별 인사이트 문장** — 각 차트 하단에 운영 문장 자동 생성
- **이 기간 운영 메모** — 매출 트렌드 근처에 관련 메모 요약 표시

### ⚙️ 편의 기능
- 기간 필터 — 일 / 주 / 월 / 년 / 직접 설정
- 빠른 선택 버튼 — 오늘 / 어제 / 최근 7일 / 최근 30일 / 전체
- 이전 / 다음 기간 이동 버튼
- 매출 트렌드 막대 클릭 → 해당 날짜 드릴다운 + 이전 기간으로 돌아가기
- 현재 조회 기간 + 일수 상시 표시
- 라이트 / 다크 모드 토글 (선택값 자동 저장)
- Google Sheets API 연동 — 접이식 설정 배너

---

## 데이터 구조 (Google Sheets)

| 시트명 | 주요 컬럼 |
|--------|-----------|
| `daily_summary` | date, order_count, sales, visitor, pageview, conversion_rate, new_order_count, returning_order_count, notes |
| `product_daily` | date, product_id, product_name, price, order_count, quantity, sales, category, series, brand, language |
| `channel_daily` | date, product_name, channel, keyword, orders |
| `ad_daily` | date, channel, device, cost, clicks, orders, sales, roas |

---

## 기술 스택

- HTML + JavaScript (단일 파일)
- [Chart.js 4.4.1](https://www.chartjs.org/)
- Google Sheets API v4
- GitHub Pages 배포

---

## 업데이트 기록

| 날짜 | 내용 |
|------|------|
| 2026-03-04 | 최초 배포 |
| 2026-03-05 | 요일별 패턴, 키워드 성과 추가 |
| 2026-03-11 | UI 리뉴얼, 라이트/다크 모드, 드릴다운, 시리즈별 매출 섹션 추가 |
| 2026-06-17 | UI 전면 개선 — KPI 그룹화, 차트 인사이트, 필터 UX 개선 (빠른 선택 / 이전·다음 / 드릴다운 뒤로가기) |
| 2026-06-17 | 의사결정 보조 영역 추가 — 핵심 리포트, 상품 집중도, 신규/재구매 비율 카드 |
| 2026-06-17 | 키워드 섹션 축소 (차트 접이식), 운영 메모 매출 트렌드 연결 |
| 2026-06-17 | 총 매출 전체 금액 표시, 필터 영역 가독성 개선 |
