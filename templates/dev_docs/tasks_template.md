# Tasks: {PROJECT_NAME}

**Input**: `docs/spec-kit/01_spec.md`, `docs/spec-kit/02_plan.md`
**Ticket**: `{TICKET_ID}` | **Date**: {DATE}

> **형식 안내**
> - `[ID]` : 태스크 번호 (T001, T002, ...)
> - `[P]` : 병렬 실행 가능 여부 표시 (🔀 병렬 가능 / 🔒 순서 필수)
> - `[Story]` : 관련 사용자 스토리 (US1, US2, ...)
> - 각 태스크는 **2시간 이내** 완료 가능한 단위로 분할

---

## Phase 1: Setup (공통 인프라)
<!-- 모든 다음 단계에 필요한 공통 환경 설정 -->

- [ ] **T001** 🔒 프로젝트 구조 생성 및 개발 환경 초기화
  - 파일: `{SETUP_FILE_1}`, `{SETUP_FILE_2}`
  - 완료 조건: `{T001_DONE_CONDITION}`

- [ ] **T002** 🔒 의존성 패키지 정의 및 설치
  - 파일: `{DEPENDENCY_FILE}`
  - 완료 조건: `{T002_DONE_CONDITION}`

---

## Phase 2: Foundational (선행 필수 항목)
<!-- ⚠️ CRITICAL: 사용자 스토리 구현 전 반드시 완료해야 할 핵심 인프라 -->

- [ ] **T003** 🔒 {FOUNDATIONAL_TASK_1_TITLE}
  - 파일: `{T003_FILES}`
  - 완료 조건: `{T003_DONE_CONDITION}`

- [ ] **T004** 🔒 {FOUNDATIONAL_TASK_2_TITLE}
  - 파일: `{T004_FILES}`
  - 완료 조건: `{T004_DONE_CONDITION}`

---

## Phase 3: User Story 1 — {US1_TITLE} (Priority: P1) 🎯 MVP

- **Goal**: {US1_GOAL}
- **Independent Test**: {US1_INDEPENDENT_TEST}

- [ ] **T005** 🔀 [US1] {US1_TASK_1_DESCRIPTION}
  - 파일: `{T005_FILES}`
  - 완료 조건: `{T005_DONE_CONDITION}`

- [ ] **T006** 🔀 [US1] {US1_TASK_2_DESCRIPTION}
  - 파일: `{T006_FILES}`
  - 완료 조건: `{T006_DONE_CONDITION}`

- [ ] **T007** 🔒 [US1] 단위 테스트 작성
  - 파일: `{T007_TEST_FILES}`
  - 완료 조건: 테스트 커버리지 {COVERAGE_TARGET}% 이상, 전체 PASS

---

## Phase 4: User Story 2 — {US2_TITLE} (Priority: P2)

- **Goal**: {US2_GOAL}
- **Independent Test**: {US2_INDEPENDENT_TEST}

- [ ] **T008** 🔀 [US2] {US2_TASK_1_DESCRIPTION}
  - 파일: `{T008_FILES}`
  - 완료 조건: `{T008_DONE_CONDITION}`

- [ ] **T009** 🔒 [US2] 단위 테스트 작성
  - 파일: `{T009_TEST_FILES}`
  - 완료 조건: 전체 PASS

<!-- 사용자 스토리별 Phase를 필요한 만큼 추가 -->

---

## Phase N: Integration & Finalization

- [ ] **T-INT-01** 🔒 통합 테스트 실행 및 검증
  - 완료 조건: 모든 Acceptance Scenario PASS

- [ ] **T-INT-02** 🔒 docs/summary.md 작성 및 git commit/push
  - 완료 조건: 원격 브랜치 push 완료

---

## Dependencies & Execution Order

```
T001 → T002 → T003 → T004
                         ↓
              T005, T006 (🔀 병렬) → T007
              T008 (🔀 병렬)        → T009
                                      ↓
                              T-INT-01 → T-INT-02
```

## Estimated Effort

| Phase        | 태스크 수         | 예상 소요 시간     |
| ------------ | ----------------- | ------------------ |
| Setup        | {PHASE1_COUNT}    | {PHASE1_EFFORT}    |
| Foundational | {PHASE2_COUNT}    | {PHASE2_EFFORT}    |
| User Stories | {PHASE3_COUNT}    | {PHASE3_EFFORT}    |
| Integration  | 2                 | {PHASEINT_EFFORT}  |
| **합계**     | **{TOTAL_COUNT}** | **{TOTAL_EFFORT}** |

---

## 추적성 (Traceability)

| 방향 | 산출물 | 비고 |
| ---- | ------ | ---- |
| **Input from** | `docs/spec-kit/02_plan.md` (plan_template) | 구현 계획 |
| **Output to** | 구현 커밋/PR (`{TICKET_ID}`) | 코드 산출물 |

---

## 변경 이력 (Revision History)

| 버전 | 날짜   | 작성자   | 변경 내용 |
| ---- | ------ | -------- | --------- |
| 0.1  | {DATE} | {AUTHOR} | 초안 작성 |
