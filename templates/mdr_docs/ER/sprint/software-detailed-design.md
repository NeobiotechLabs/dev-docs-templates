# Software Detailed Design (SDD): {PRODUCT_NAME}

**문서 번호**: {DOC_ID}  
**버전**: 1.0 | **상태**: Draft  
**작성일**: {DATE} | **작성자**: {AUTHOR}  
**검토자**: {REVIEWER} | **승인자**: {APPROVER}

---

## 표준 요건 매핑 (Standard Requirements Mapping)

> IEC 62304 Class B/C에서 상세 설계서(SDD)가 필수 산출물임 (Cl.5.4)
> Class A는 생략 가능하나 인터페이스 정의는 권장

| IEC 62304 조항 | 제목                              | 해당 섹션          | Class |
| -------------- | --------------------------------- | ------------------ | ----- |
| Cl. 5.4.1      | 소프트웨어 유닛 구현 및 검증 계획 | 1. 설계 개요       | B, C  |
| Cl. 5.4.2      | 소프트웨어 유닛 검증              | 5. 유닛 검증 계획  | B, C  |
| Cl. 5.4.3      | 소프트웨어 유닛 추가 상세 설계    | 3. 상세 설계       | C     |
| Cl. 5.3.2      | 소프트웨어 아키텍처 인터페이스    | 4. 인터페이스 설계 | B, C  |
| Cl. 5.5.2      | 소프트웨어 유닛 구현 검증         | 5. 유닛 검증 계획  | B, C  |

---

## 1. 설계 개요 (Design Overview)

### 1.1 목적 및 범위

이 문서는 {PRODUCT_NAME}의 SW 상세 설계를 기술한다.
SW 아키텍처 설명서(SAD)에서 정의된 각 SW 아이템(Item)을 유닛(Unit) 수준까지 세분화하여 구현에 필요한 알고리즘, 데이터 구조, 인터페이스를 정의한다.

- **대상 SW 항목**: {SW_ITEM_LIST}
- **IEC 62304 SW 안전 등급**: Class {IEC62304_CLASS}
- **참조 문서**:
  - SW 아키텍처 설명서 (SAD): {SAD_DOC_ID}
  - SW 요구사항 명세서 (SRS): {SRS_DOC_ID}
  - 위험 관리 계획서 (RMP): {RMP_DOC_ID}

---

## 2. SW 아이템 구조 (SW Item Structure)

> IEC 62304 Cl.5.3.1 (SW 아키텍처 정의) 참조 - 상위 SAD에서 정의된 구조를 이 섹션에서 유닛 수준으로 분해

### 2.1 아이템 분해 구조 (Decomposition)

```
{PRODUCT_NAME}
  |-- {ITEM_1_NAME}          # SW 아이템 1
  |     |-- {UNIT_1_1_NAME}  # SW 유닛 1.1
  |     |-- {UNIT_1_2_NAME}  # SW 유닛 1.2
  |-- {ITEM_2_NAME}          # SW 아이템 2
        |-- {UNIT_2_1_NAME}  # SW 유닛 2.1
```

### 2.2 아이템/유닛 목록

| 유닛 ID  | 유닛 명       | 상위 아이템 | 안전 등급     | 설명          |
| -------- | ------------- | ----------- | ------------- | ------------- |
| UNIT-001 | {UNIT_1_NAME} | {ITEM_1}    | Class {CLASS} | {UNIT_1_DESC} |
| UNIT-002 | {UNIT_2_NAME} | {ITEM_1}    | Class {CLASS} | {UNIT_2_DESC} |

---

## 3. 유닛 상세 설계 (Unit Detailed Design)

> IEC 62304 Cl.5.4.3 (Class C 필수): 알고리즘, 데이터 구조, 처리 조건 상세 기술

### 3.1 {UNIT_1_NAME} (UNIT-001)

#### 3.1.1 목적 (Purpose)

{UNIT_1_PURPOSE}

#### 3.1.2 알고리즘 / 처리 로직 (Algorithm / Processing Logic)

> Class C에서 구현 수준의 로직을 기술해야 함. Class B는 인터페이스 수준까지.

```
{ALGORITHM_DESCRIPTION}
예시:
1. 입력 데이터 수신 및 유효성 검사
2. 전처리 (정규화, 포맷 변환)
3. 핵심 연산 실행
4. 결과 후처리 및 출력
5. 오류 조건 처리 및 반환
```

#### 3.1.3 데이터 구조 (Data Structures)

| 항목      | 타입     | 범위 / 허용값 | 초기값      | 설명     |
| --------- | -------- | ------------- | ----------- | -------- |
| {FIELD_1} | {TYPE_1} | {RANGE_1}     | {DEFAULT_1} | {DESC_1} |
| {FIELD_2} | {TYPE_2} | {RANGE_2}     | {DEFAULT_2} | {DESC_2} |

#### 3.1.4 오류 처리 (Error Handling)

| 오류 조건           | 처리 방법    | 반환 코드 | 로그 여부 |
| ------------------- | ------------ | --------- | --------- |
| {ERROR_CONDITION_1} | {HANDLING_1} | {CODE_1}  | Yes / No  |
| {ERROR_CONDITION_2} | {HANDLING_2} | {CODE_2}  | Yes / No  |

#### 3.1.5 요구사항 추적 (Requirements Traceability)

| SRS 요구사항 ID | 설명         |
| --------------- | ------------ |
| {SRS_ID_1}      | {REQ_DESC_1} |

---

### 3.2 {UNIT_2_NAME} (UNIT-002)

> 위 3.1 양식을 반복하여 각 유닛을 기술

---

## 4. 인터페이스 설계 (Interface Design)

> IEC 62304 Cl.5.3.2 (아키텍처 인터페이스), Cl.5.4.3 (상세 인터페이스)

### 4.1 유닛 간 인터페이스 (Unit-to-Unit Interfaces)

| ID      | 송신 유닛     | 수신 유닛       | 데이터/신호 | 형식     | 설명          |
| ------- | ------------- | --------------- | ----------- | -------- | ------------- |
| ICD-001 | {SENDER_UNIT} | {RECEIVER_UNIT} | {DATA_NAME} | {FORMAT} | {DESCRIPTION} |

### 4.2 외부 시스템 인터페이스 (External Interfaces)

| ID      | 인터페이스 대상   | 프로토콜 / 방식 | 데이터 형식 | 설명          |
| ------- | ----------------- | --------------- | ----------- | ------------- |
| EXT-001 | {EXTERNAL_SYSTEM} | {PROTOCOL}      | {FORMAT}    | {DESCRIPTION} |

### 4.3 SOUP 연동 인터페이스 (SOUP Interfaces)

> IEC 62304 Cl.5.3.5 (SOUP 격리 전략)

| SOUP 명       | 버전      | 인터페이스 방식  | 격리 전략            |
| ------------- | --------- | ---------------- | -------------------- |
| {SOUP_1_NAME} | {VERSION} | {INTERFACE_TYPE} | {ISOLATION_STRATEGY} |

---

## 5. 유닛 검증 계획 (Unit Verification Plan)

> IEC 62304 Cl.5.4.2, Cl.5.5.2 (유닛 검증 방법 및 기준)

### 5.1 검증 방법

| 방법           | 설명                   | 적용 대상 유닛     |
| -------------- | ---------------------- | ------------------ |
| 코드 리뷰      | 정적 분석 및 피어 리뷰 | 전체               |
| 유닛 테스트    | 자동화 단위 테스트     | UNIT-001, UNIT-002 |
| 정적 분석 도구 | 코딩 표준 준수 검사    | 전체               |

### 5.2 합격 기준 (Acceptance Criteria)

| 유닛 ID  | 기준 항목                 | 합격 기준값                      |
| -------- | ------------------------- | -------------------------------- |
| UNIT-001 | 코드 커버리지 (Branch)    | >= 80% (Class C: >= 100%)        |
| UNIT-001 | 정적 분석 경고            | 0건 (Justification 포함 시 허용) |
| UNIT-002 | 코드 커버리지 (Statement) | >= 80%                           |

---

## 6. 위험 관련 설계 고려사항 (Risk-Related Design Considerations)

> ISO 14971 Cl.6 (위험 통제 조치), IEC 62304 Cl.7.1 (SW 위험 분석)

| 위험 ID     | 위험 설명     | 통제 조치           | 구현 유닛 |
| ----------- | ------------- | ------------------- | --------- |
| {RISK_ID_1} | {RISK_DESC_1} | {CONTROL_MEASURE_1} | UNIT-001  |

---

## 7. 추적성 매트릭스 (Traceability)

> IEC 62304 Cl.5.1.1(c), Cl.5.7.4

| SRS 요구사항 ID | 유닛 ID  | 유닛 테스트 ID | 위험 ID     |
| --------------- | -------- | -------------- | ----------- |
| {SRS_ID_1}      | UNIT-001 | {TEST_ID_1}    | {RISK_ID_1} |
| {SRS_ID_2}      | UNIT-002 | {TEST_ID_2}    | -           |

---

## 8. 변경 이력 (Revision History)

| 버전 | 날짜   | 작성자   | 변경 내용 |
| ---- | ------ | -------- | --------- |
| 0.1  | {DATE} | {AUTHOR} | 초안 작성 |

---

> Template based on IEC 62304:2006/AMD1:2015 Clause 5.4, ISO 14971:2019
