# Implementation Plan: {PROJECT_NAME}

**Branch**: `feature/{TICKET_ID}` | **Date**: {DATE} | **Spec**: `docs/spec-kit/01_spec.md`
**Ticket**: `{TICKET_ID}` | **Type**: {ISSUE_TYPE}

---

## Summary
<!-- 명세서에서 추출한 주요 요구사항 및 기술적 접근 방식 요약 (3~5줄) -->
{SUMMARY}

---

## Technical Context

| 항목                     | 내용                    |
| ------------------------ | ----------------------- |
| **Language/Version**     | {LANGUAGE_VERSION}      |
| **Primary Dependencies** | {PRIMARY_DEPS}          |
| **Storage**              | {STORAGE_STRATEGY}      |
| **Testing**              | {TESTING_FRAMEWORK}     |
| **Target Platform**      | {TARGET_PLATFORM}       |
| **Performance Goals**    | {PERFORMANCE_GOALS}     |
| **Constraints**          | {TECHNICAL_CONSTRAINTS} |

---

## Constitution Check
*GATE: 설계 원칙(Constitution) 준수 여부 확인*

<!-- constitution.md 또는 프로젝트 기본 설계 원칙 파일이 있다면 먼저 읽고 준수 여부를 기술 -->
- **SOLID 원칙**: {SOLID_COMPLIANCE}
- **레이어 분리**: {LAYER_SEPARATION}
- **에러 처리 전략**: {ERROR_HANDLING_STRATEGY}
- **보안 고려사항**: {SECURITY_CONSIDERATIONS}

---

## Project Structure

### Documentation
```text
docs/
├── spec-kit/
│   ├── 01_spec.md
│   ├── 02_plan.md
│   └── 03_tasks.md
└── {OTHER_DOCS}
```

### Source Code
```text
{SOURCE_DIR}/
├── {MODULE_1}/
│   ├── {FILE_1}          # {FILE_1_DESCRIPTION}
│   └── {FILE_2}          # {FILE_2_DESCRIPTION}
└── {MODULE_2}/
    └── {FILE_3}          # {FILE_3_DESCRIPTION}
```

---

## Implementation Approach

### Phase 순서 및 접근 방식
1. **Setup**: {SETUP_APPROACH}
2. **Core Implementation**: {CORE_APPROACH}
3. **Testing**: {TESTING_APPROACH}
4. **Integration**: {INTEGRATION_APPROACH}

### Key Technical Decisions
<!-- 중요한 기술적 결정과 그 이유 -->
- **결정 1**: {DECISION_1} — 이유: {DECISION_1_REASON}
- **결정 2**: {DECISION_2} — 이유: {DECISION_2_REASON}

---

## Complexity Tracking
<!-- 설계 원칙 위반이나 복잡한 결정에 대한 정당성 기술 (필요 시) -->
- {COMPLEXITY_NOTE_1}

---

## References
- Spec: `docs/spec-kit/01_spec.md`
- 티켓: `{TICKET_ID}`
- 관련 문서: `docs/02_SRS.md`, `docs/03_Architecture.md`
