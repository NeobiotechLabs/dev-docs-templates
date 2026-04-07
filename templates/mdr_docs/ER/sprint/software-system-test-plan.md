# Software System Test Plan & Protocol: {PRODUCT_NAME} v{VERSION}

<!-- AI AGENT 작성 지침
이 문서는 IEC 62304 Cl.5.7 기반 시스템 테스트 계획서입니다.
Sprint마다 테스트 케이스를 추가/업데이트하세요.

작성 전 반드시 다음 문서를 참조하세요:
  - SW 요구사항 명세서(software-requirements-list.md): 모든 SRS ID를 테스트 케이스로 커버해야 함
  - FMEA(risk-table-fmea.md): 위험 통제 조치가 구현되었는지 검증하는 테스트 포함
  - 사이버보안 체크리스트(risk-management-cybersecurity-checklist.md): 보안 테스트 항목 반영

작성 지침:
1. 모든 SRS 요구사항(SRS-F-xxx, SRS-P-xxx 등)에 최소 1개의 테스트 케이스가 있어야 합니다
2. 테스트 ID 체계: TST-SYS-{N:3d} (예: TST-SYS-001)
3. 테스트 결과 컬럼은 실제 테스트 실행 후 채워주세요 (계획서는 Expected까지만)
4. 위험 통제 조치에 대한 테스트는 "위험 통제 검증?" 열을 Yes로 표시하세요
5. Pass/Fail 외에 Blocked(사전 조건 미충족), N/A(해당 없음)도 사용 가능합니다

테스트 카테고리:
  - Functional: SRS-F-xxx 기능 요구사항 검증
  - Performance: SRS-P-xxx 성능 요구사항 검증
  - Security: SRS-S-xxx 보안 요구사항 검증
  - Regression: 이전 버전에서 동작하던 기능이 유지되는지 확인
  - Boundary: 경계값 조건 검증 (허용 범위 초과/미만 입력)

테스트 환경 (필수 기재):
  - 테스트 환경은 실제 사용 환경과 유사해야 합니다 (IEC 62304 Cl.5.7.2)
  - 사용된 SOUP 버전을 명시하세요 (SOUP 리스트와 일치 확인)
-->

**문서 번호**: {DOC_ID}
**버전**: {VERSION} | **상태**: Draft (계획) / Final (프로토콜)
**Sprint**: {SPRINT_NUMBER} | **작성일**: {DATE}
**테스터**: {TESTER} | **검토자**: {REVIEWER}

---

## 표준 요건 매핑

| 표준 조항          | 제목                          | 해당 섹션          |
| ------------------ | ----------------------------- | ------------------ |
| IEC 62304 Cl.5.7.1 | 통합 시스템 테스트 절차 수립  | 전체               |
| IEC 62304 Cl.5.7.2 | 소프트웨어 시스템 테스트 수행 | 3. 테스트 케이스   |
| IEC 62304 Cl.5.7.4 | 테스트 결과와 요구사항 추적성 | 4. 추적성 매트릭스 |
| MDR Annex II 6.1   | 제품 검증                     | 전체               |

---

## 1. 테스트 환경 (Test Environment)

<!-- AI AGENT: 실제 테스트를 수행한 환경을 정확하게 기재하세요 -->

| 항목               | 사양                               |
| ------------------ | ---------------------------------- |
| OS / 환경          | {OS_VERSION}                       |
| 주요 SOUP 버전     | {SOUP_NAME} v{VERSION} (SOUP-{ID}) |
| 브라우저 / 런타임  | {BROWSER_OR_RUNTIME}               |
| 테스트 데이터 출처 | {TEST_DATA_SOURCE}                 |
| 테스트 실행 일시   | {TEST_DATE}                        |

---

## 2. 테스트 범위 (Test Scope)

| 포함                         | 제외                                 |
| ---------------------------- | ------------------------------------ |
| {IN_SCOPE_TEST}              | {OUT_OF_SCOPE_TEST}                  |
| SRS-F-xxx 전체 기능 요구사항 | 유닛 레벨 테스트 (별도 SDD에서 관리) |

---

## 3. 테스트 케이스 (Test Cases)

### 3.1 기능 테스트 (Functional Tests)

<!-- AI AGENT: 각 SRS-F-xxx 요구사항에 대한 테스트 케이스를 작성하세요
테스트 단계(Steps)는 재현 가능하도록 구체적으로 작성해야 합니다
예시:
  Steps: 1. {URL}에 접속한다 2. 사용자 ID {ID}와 비밀번호 {PW}를 입력한다 3. 로그인 버튼을 클릭한다
  Expected: 대시보드 페이지로 이동하고 사용자 이름이 표시된다 -->

| 테스트 ID   | SRS ID    | 테스트 카테고리 | 테스트 설명   | 사전 조건   | 테스트 단계                | 예상 결과    | 위험 통제 검증? | 실제 결과 | Pass? |
| ----------- | --------- | --------------- | ------------- | ----------- | -------------------------- | ------------ | --------------- | --------- | ----- |
| TST-SYS-001 | SRS-F-001 | Functional      | {TEST_DESC_1} | {PRECOND_1} | 1. {STEP_1}<br>2. {STEP_2} | {EXPECTED_1} | Yes / No        |           |       |
| TST-SYS-002 | SRS-F-002 | Functional      | {TEST_DESC_2} | {PRECOND_2} | 1. {STEP_1}<br>2. {STEP_2} | {EXPECTED_2} | No              |           |       |

### 3.2 성능 테스트 (Performance Tests)

| 테스트 ID     | SRS ID    | 테스트 카테고리 | 테스트 설명    | 허용 기준 | 측정 방법            | 실제 결과 | Pass? |
| ------------- | --------- | --------------- | -------------- | --------- | -------------------- | --------- | ----- |
| TST-SYS-P-001 | SRS-P-001 | Performance     | 응답 시간 측정 | <= {N}초  | {MEASUREMENT_METHOD} | {ACTUAL}  |       |

### 3.3 보안 테스트 (Security Tests)

<!-- AI AGENT: SRS-S-xxx 보안 요구사항에 대한 테스트를 작성하세요
다음 항목을 포함하는 것을 권장합니다:
- 인증 실패 케이스 (잘못된 자격증명, 세션 만료)
- 권한 없는 접근 시도
- SQL Injection / XSS 방어 확인
- TLS 통신 암호화 확인 -->

| 테스트 ID     | SRS ID    | 테스트 카테고리 | 테스트 설명          | 예상 결과                              | 위험 통제 검증? | 실제 결과 | Pass? |
| ------------- | --------- | --------------- | -------------------- | -------------------------------------- | --------------- | --------- | ----- |
| TST-SYS-S-001 | SRS-S-001 | Security        | {SECURITY_TEST_1}    | {EXPECTED}                             | Yes             |           |       |
| TST-SYS-S-002 | SRS-S-002 | Security        | TLS 통신 암호화 확인 | Wireshark 캡처 시 암호화된 패킷만 관측 | Yes             |           |       |

### 3.4 경계값 테스트 (Boundary Tests)

| 테스트 ID     | SRS ID    | 테스트 카테고리 | 테스트 조건    | 입력값       | 예상 결과         | 실제 결과 | Pass? |
| ------------- | --------- | --------------- | -------------- | ------------ | ----------------- | --------- | ----- |
| TST-SYS-B-001 | SRS-F-{N} | Boundary        | 최대값 입력    | {MAX_VALUE}  | {EXPECTED}        |           |       |
| TST-SYS-B-002 | SRS-F-{N} | Boundary        | 최소값 입력    | {MIN_VALUE}  | {EXPECTED}        |           |       |
| TST-SYS-B-003 | SRS-F-{N} | Boundary        | 범위 초과 입력 | {OVER_VALUE} | 오류 처리 및 거부 |           |       |

---

## 4. 추적성 매트릭스 (Traceability Matrix)

<!-- AI AGENT: 모든 SRS 요구사항이 테스트에 의해 커버되는지 확인하세요 -->

| SRS ID    | 요구사항 설명  | 테스트 ID     | 위험 ID   | 커버 여부 |
| --------- | -------------- | ------------- | --------- | --------- |
| SRS-F-001 | {REQ_DESC}     | TST-SYS-001   | -         | Yes       |
| SRS-S-001 | {SEC_REQ_DESC} | TST-SYS-S-001 | {RISK_ID} | Yes       |

---

## 5. 테스트 결과 요약 (Test Results Summary)

<!-- AI AGENT: 테스트 완료 후 아래 표를 채워주세요 -->

| 카테고리    | 전체 | Pass | Fail | Blocked | N/A |
| ----------- | ---- | ---- | ---- | ------- | --- |
| Functional  | {N}  |      |      |         |     |
| Performance | {N}  |      |      |         |     |
| Security    | {N}  |      |      |         |     |
| Boundary    | {N}  |      |      |         |     |
| **합계**    |      |      |      |         |     |

**결론**: Pass / Fail / Conditional Pass

**미해결 결함 목록**: (없음 또는 bug-fixes-documentation-list.md 참조)

---

## 6. 변경 이력

| 버전 | 날짜   | 작성자   | 변경 내용             |
| ---- | ------ | -------- | --------------------- |
| 0.1  | {DATE} | {AUTHOR} | 계획서 초안           |
| 1.0  | {DATE} | {TESTER} | 테스트 결과 입력 완료 |

---

> Template based on IEC 62304:2006/AMD1:2015 Clause 5.7, MDR 2017/745 Annex II 6.1
