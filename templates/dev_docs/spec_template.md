# Feature Specification: {PROJECT_NAME}

**Feature Branch**: `{TICKET_ID}-{FEATURE_SLUG}`
**Status**: Draft | **Date**: {DATE}
**Ticket**: `{TICKET_ID}` | **Type**: {ISSUE_TYPE}
**Input**: `docs/01_PRD.md` (존재 시)

---

## User Scenarios & Testing
<!-- 각 사용자 스토리는 독립적으로 테스트 가능하고 가치를 전달해야 합니다 -->

### User Story 1 — {US1_TITLE} (Priority: P1) 🎯 MVP
- **설명**: {US1_DESCRIPTION}
- **Why this priority**: {US1_PRIORITY_REASON}
- **Independent Test**: {US1_TEST_METHOD}
- **Acceptance Scenarios**:
  1. **Given** {US1_GIVEN_1}, **When** {US1_WHEN_1}, **Then** {US1_THEN_1}
  2. **Given** {US1_GIVEN_2}, **When** {US1_WHEN_2}, **Then** {US1_THEN_2}

### User Story 2 — {US2_TITLE} (Priority: P2)
- **설명**: {US2_DESCRIPTION}
- **Why this priority**: {US2_PRIORITY_REASON}
- **Independent Test**: {US2_TEST_METHOD}
- **Acceptance Scenarios**:
  1. **Given** {US2_GIVEN_1}, **When** {US2_WHEN_1}, **Then** {US2_THEN_1}

<!-- 필요한 만큼 User Story 섹션을 추가 -->

### Edge Cases (엣지 케이스)
- **EC-001**: {EDGE_CASE_1}
- **EC-002**: {EDGE_CASE_2}

---

## Requirements

### Functional Requirements (기능 요구사항)
- **FR-001**: 시스템은 반드시 {FR_001_CAPABILITY}를 제공해야 함
- **FR-002**: 시스템은 반드시 {FR_002_CAPABILITY}를 제공해야 함
<!-- FR-XXX 형식으로 계속 추가 -->

### Non-Functional Requirements (비기능 요구사항)
- **NFR-001 (성능)**: {NFR_001_PERFORMANCE}
- **NFR-002 (보안)**: {NFR_002_SECURITY}
- **NFR-003 (가용성)**: {NFR_003_AVAILABILITY}

### Key Entities (핵심 데이터 모델, 해당 시)
- **{ENTITY_1}**: {ENTITY_1_DESCRIPTION} — 핵심 속성: {ENTITY_1_KEY_ATTRS}
- **{ENTITY_2}**: {ENTITY_2_DESCRIPTION} — 핵심 속성: {ENTITY_2_KEY_ATTRS}

---

## Success Criteria

### Measurable Outcomes (측정 가능한 지표)
- **SC-001**: {SC_001_METRIC}
- **SC-002**: {SC_002_METRIC}

### Definition of Done
- [ ] 모든 FR-XXX 요구사항 구현 완료
- [ ] 단위 테스트 커버리지 {COVERAGE_TARGET}% 이상
- [ ] Edge Case 시나리오 검증 완료
- [ ] 코드 리뷰 승인

---

## 추적성 (Traceability)

| 방향 | 산출물 | 비고 |
| ---- | ------ | ---- |
| **Input from** | `docs/01_PRD.md` (prd_template) | 제품 요구사항 |
| **Output to** | `docs/spec-kit/02_plan.md` (plan_template) | 구현 계획 |

---

## 변경 이력 (Revision History)

| 버전 | 날짜   | 작성자   | 변경 내용 |
| ---- | ------ | -------- | --------- |
| 0.1  | {DATE} | {AUTHOR} | 초안 작성 |
