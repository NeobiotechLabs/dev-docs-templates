# System Requirements Specification (SRS): {PRODUCT_NAME}

**문서 번호**: {DOC_ID}  
**버전**: 1.0 | **상태**: Draft  
**작성일**: {DATE} | **작성자**: {AUTHOR}  
**검토자**: {REVIEWER} | **승인자**: {APPROVER}

---

## 표준 요건 매핑 (Standard Requirements Mapping)

| 표준 조항                | 제목                              | 해당 섹션          |
| ------------------------ | --------------------------------- | ------------------ |
| IEC 62304:2006 Cl. 5.1.3 | SW 개발 계획에서 시스템 설계 참조 | 1. 제품 개요       |
| IEC 62304:2006 Cl. 5.2.1 | SW 요구사항 정의                  | 4. SW 요구사항     |
| MDR Annex II, 3.(a)      | 설계 및 제조 정보                 | 3. 시스템 요구사항 |
| MDR Annex I, Cl. 10      | 화학적/물리적/전기적 특성         | 5. 성능 요구사항   |
| ISO 14971:2019 Cl. 5.2   | 의도된 사용 이해                  | 1. 제품 개요       |

---

## 1. 제품 개요 (Product Overview)

### 1.1 사용 목적 (Intended Use)

> IEC 62304 Cl.5.1.3, ISO 14971 Cl.5.2, MDR Annex II 1.1(c) 참조
> 사용 목적 정의서(intended-use.md)와 일치해야 함

{INTENDED_USE_SUMMARY}

- **의료 목적**: {MEDICAL_PURPOSE}
- **대상 환자**: {TARGET_PATIENT_POPULATION}
- **의도된 사용자**: {INTENDED_USER}
- **사용 환경**: {USE_ENVIRONMENT}
- **MDR 등급**: {MDR_CLASS} | **IEC 62304 SW 안전 등급**: Class {IEC62304_CLASS}

### 1.2 제품 설명 (Product Description)

{PRODUCT_DESCRIPTION}

### 1.3 범위 (Scope)

| 항목                    | 내용           |
| ----------------------- | -------------- |
| **포함 (In Scope)**     | {IN_SCOPE}     |
| **제외 (Out of Scope)** | {OUT_OF_SCOPE} |

---

## 2. 이해관계자 요구사항 (Stakeholder Requirements)

> MDR Annex II 3.(a), ISO 13485 7.2.1, IEC 62304 Cl.5.1.3

| ID      | 사용자 그룹    | 요구사항 설명                                     | 안전 관련 여부 |
| ------- | -------------- | ------------------------------------------------- | -------------- |
| STK-001 | {USER_GROUP_1} | {STAKEHOLDER_REQ_1}                               | Yes / No       |
| STK-002 | {USER_GROUP_2} | {STAKEHOLDER_REQ_2}                               | Yes / No       |
| STK-003 | 규제 당국      | 제품은 MDR 2017/745 및 적용 표준을 준수해야 한다. | Yes            |

---

## 3. 시스템 요구사항 (System Requirements)

> IEC 62304 Cl.5.1.3, MDR Annex II 3.(a)

### 3.1 기능 요구사항 (Functional Requirements)

| ID        | 요구사항 설명      | 출처 (Trace to) | 우선순위  |
| --------- | ------------------ | --------------- | --------- |
| SYS-F-001 | {FUNCTIONAL_REQ_1} | STK-001         | Must Have |
| SYS-F-002 | {FUNCTIONAL_REQ_2} | STK-002         | Must Have |

### 3.2 성능 요구사항 (Performance Requirements)

> MDR Annex I, Cl. 10 (화학적/물리적/전기적 특성)

| ID        | 요구사항 설명       | 허용 기준 (Acceptance Criteria) | 측정 방법          |
| --------- | ------------------- | ------------------------------- | ------------------ |
| SYS-P-001 | {PERFORMANCE_REQ_1} | {ACCEPTANCE_CRITERIA_1}         | {MEASURE_METHOD_1} |

### 3.3 인터페이스 요구사항 (Interface Requirements)

| ID        | 인터페이스 유형   | 설명                        |
| --------- | ----------------- | --------------------------- |
| SYS-I-001 | HW/OS             | {HW_OS_REQUIREMENT}         |
| SYS-I-002 | 외부 시스템       | {EXTERNAL_SYSTEM_INTERFACE} |
| SYS-I-003 | 사용자 인터페이스 | {UI_REQUIREMENT}            |

### 3.4 환경 요구사항 (Environmental Requirements)

| 항목               | 사양                    |
| ------------------ | ----------------------- |
| 운영 환경          | {OPERATING_ENVIRONMENT} |
| 대상 OS / 런타임   | {TARGET_OS_RUNTIME}     |
| 최소 하드웨어 사양 | {MIN_HW_SPEC}           |

---

## 4. 안전 및 보안 요구사항 (Safety & Security Requirements)

> MDR Annex I Chapter I (GSPR), IEC 81001-5-1, ISO 14971

### 4.1 안전 요구사항 (Safety Requirements)

| ID        | 요구사항 설명  | 연관 위험 (Risk ID) |
| --------- | -------------- | ------------------- |
| SYS-S-001 | {SAFETY_REQ_1} | {RISK_ID_1}         |

### 4.2 사이버보안 요구사항 (Cybersecurity Requirements)

> MDR Annex I, 17.2 (IT 보안 고려), IEC 81001-5-1

| ID          | 요구사항 설명                           |
| ----------- | --------------------------------------- |
| SYS-SEC-001 | 인증 및 접근 제어: {AUTH_REQUIREMENT}   |
| SYS-SEC-002 | 데이터 암호화: {ENCRYPTION_REQUIREMENT} |
| SYS-SEC-003 | 감사 로그: {AUDIT_LOG_REQUIREMENT}      |

---

## 5. 규제 요구사항 (Regulatory Requirements)

> MDR Annex II 4. (규제 및 표준 준수 정보)

| 규제/표준       | 버전           | 적용 여부 | 비고              |
| --------------- | -------------- | --------- | ----------------- |
| EU MDR 2017/745 | -              | O         | 기본 적용         |
| IEC 62304       | 2006/AMD1:2015 | O         | SW 수명주기       |
| ISO 14971       | 2019           | O         | 위험 관리         |
| IEC 62366-1     | 2015           | O         | 사용성 엔지니어링 |
| IEC 81001-5-1   | 2021           | O         | 사이버보안        |
| ISO 13485       | 2016           | O         | QMS               |

---

## 6. 제약사항 및 가정 (Constraints & Assumptions)

### 6.1 제약사항

| ID      | 설명           |
| ------- | -------------- |
| CON-001 | {CONSTRAINT_1} |

### 6.2 가정

| ID      | 설명           |
| ------- | -------------- |
| ASS-001 | {ASSUMPTION_1} |

---

## 7. 요구사항 우선순위 (MoSCoW)

| 분류                        | 요구사항 ID 목록     |
| --------------------------- | -------------------- |
| Must Have                   | SYS-F-001, SYS-S-001 |
| Should Have                 | {SHOULD_HAVE_LIST}   |
| Could Have                  | {COULD_HAVE_LIST}    |
| Won't Have (이번 버전 제외) | {WONT_HAVE_LIST}     |

---

## 8. 추적성 요약 (Traceability Summary)

> IEC 62304 Cl.5.1.1(c) (추적성 계획)

이 문서의 요구사항은 다음 문서와 연결된다:

- **입력 (Input from)**: 사용 목적 정의서 (intended-use.md)
- **출력 (Input for)**: SW 요구사항 명세서 (software-requirements-list.md), 위험 관리 계획서 (risk-management-plan.md), SW 개발 계획서 (software-development-maintenance-plan.md)

---

## 9. 변경 이력 (Revision History)

| 버전 | 날짜   | 작성자   | 변경 내용 |
| ---- | ------ | -------- | --------- |
| 0.1  | {DATE} | {AUTHOR} | 초안 작성 |

---

> Template based on IEC 62304:2006/AMD1:2015, ISO 14971:2019, MDR 2017/745 Annex II
