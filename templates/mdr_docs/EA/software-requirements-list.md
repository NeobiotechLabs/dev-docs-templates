# Software Requirements List (SRS): {PRODUCT_NAME}

<!-- AI AGENT 작성 지침
이 문서는 IEC 62304 Cl.5.2 기반 SW 요구사항 명세서입니다.
A/B/C 전체 등급에서 필수 산출물입니다.

작성 전 반드시 다음 문서를 참조하세요:
  - 시스템 요구사항 명세서(system-requirements-spec.md): 시스템 요구사항 및 SRS로 분해할 항목 확인
  - 사용 목적 정의서(intended-use.md): 의도된 사용자, 사용 환경 확인
  - FMEA(risk-table-fmea.md): 위험 통제 조치(Risk Control Measure)가 SRS에 반영되었는지 확인

작성 지침:
1. 모든 요구사항에 고유 ID를 부여하세요 (예: SRS-F-001, SRS-S-001)
2. IEC 62304 카테고리를 정확히 분류하세요:
   - Functional (기능 요구사항)
   - Performance (성능 요구사항)
   - User Interface (사용자 인터페이스)
   - Security (보안 요구사항)
   - Interface (외부 인터페이스)
   - Regulatory (규제 준수 요구사항)
3. 보안 요구사항(IEC 81001-5-1)은 Security 카테고리로 반드시 포함하세요
4. 위험 통제 조치(Risk Control Measure)를 요구사항으로 추가할 때는
   Risk Control Measure 열을 Yes로 표시하고 FMEA의 Risk ID를 연결하세요
5. 각 요구사항은 독립적으로 검증 가능해야 합니다 (Verifiable)

예시 요구사항 ID 체계:
  SRS-F-001: 기능 요구사항 #001
  SRS-P-001: 성능 요구사항 #001
  SRS-UI-001: 사용자 인터페이스 요구사항 #001
  SRS-S-001: 보안 요구사항 #001
  SRS-I-001: 인터페이스 요구사항 #001
  SRS-R-001: 규제 요구사항 #001
-->

**문서 번호**: {DOC_ID}
**버전**: {VERSION} | **상태**: Draft
**작성일**: {DATE} | **작성자**: {AUTHOR}
**검토자**: {REVIEWER} | **승인자**: {APPROVER}

---

## 표준 요건 매핑 (Standard Requirements Mapping)

| 표준 조항            | 제목                        | 해당 섹션        | Class   |
| -------------------- | --------------------------- | ---------------- | ------- |
| IEC 62304 Cl.5.2.1   | SW 요구사항 정의            | 1~3              | A, B, C |
| IEC 62304 Cl.5.2.2   | SW 요구사항 내용            | 1~3              | A, B, C |
| IEC 62304 Cl.5.2.3   | SW 요구사항 검토            | 전체             | A, B, C |
| IEC 62366-1 Cl.5.2   | 사용 오류 관련 UI 특성 식별 | 2. UI 요구사항   | -       |
| IEC 62366-1 Cl.5.6   | 사용자 인터페이스 사양      | 2. UI 요구사항   | -       |
| IEC 81001-5-1 Cl.5.2 | 보안 요구사항               | 3. 보안 요구사항 | -       |
| MDR Annex I 17.2     | IT 보안 고려                | 3. 보안 요구사항 | -       |
| ISO 13485 Cl.7.2.1   | 고객 관련 프로세스          | 전체             | -       |

---

## 1. 기능 및 성능 요구사항 (Functional & Performance Requirements)

<!-- AI AGENT: 시스템 요구사항 명세서의 SYS-F-xxx 항목을 SW 수준으로 분해하여 작성하세요
각 요구사항은 "SW는 [조건]에서 [동작]을 [기준]으로 수행해야 한다" 형식으로 작성하면 좋습니다

예시:
- SRS-F-001: 사용자가 로그인 후 대시보드를 요청할 경우, 시스템은 3초 이내에 결과를 반환해야 한다.
- SRS-P-001: 시스템은 동시 사용자 100명 이상을 처리할 수 있어야 한다. -->

| ID        | SW 시스템   | 카테고리    | 요구사항 설명                     | 위험 통제 조치? | 관련 Risk ID | 검증 방법        |
| --------- | ----------- | ----------- | --------------------------------- | --------------- | ------------ | ---------------- |
| SRS-F-001 | {SW_SYSTEM} | Functional  | {REQ_DESC}                        | Yes / No        | {RISK_ID}    | System Test      |
| SRS-P-001 | {SW_SYSTEM} | Performance | 시스템은 {N}초 이내 응답해야 한다 | No              | -            | Performance Test |

---

## 2. 사용자 인터페이스 요구사항 (User Interface Requirements)

<!-- AI AGENT: IEC 62366-1 관점에서 사용 오류(Use Error)를 방지하는 UI 요구사항을 작성하세요
다음 항목을 고려하세요:
- 위험 관련 정보의 가시성 (색상, 크기, 위치)
- 사용자 확인(Confirmation) 절차가 필요한 위험 동작
- 오류 메시지의 명확성

예시:
- SRS-UI-001: 위험 등급 HIGH 결과는 빨간색 배경과 경고 아이콘으로 표시해야 한다.
- SRS-UI-002: 데이터 삭제 동작 전 사용자 확인(Confirmation Dialog)을 표시해야 한다. -->

| ID         | SW 시스템   | 카테고리       | 요구사항 설명 | 위험 통제 조치? | 관련 Risk ID | 검증 방법      |
| ---------- | ----------- | -------------- | ------------- | --------------- | ------------ | -------------- |
| SRS-UI-001 | {SW_SYSTEM} | User Interface | {UI_REQ_DESC} | Yes / No        | {RISK_ID}    | Usability Test |

---

## 3. 보안 요구사항 (Security Requirements)

<!-- AI AGENT: MDR Annex I 17.2 및 IEC 81001-5-1 기준으로 사이버보안 요구사항을 작성하세요
다음 항목을 필수로 포함하세요:
- 인증 및 접근 제어
- 데이터 암호화 (전송/저장)
- 감사 로그
- 취약점 패치 정책

예시:
- SRS-S-001: 시스템은 모든 사용자 세션에 JWT 기반 인증을 적용해야 한다 (exp: 1시간).
- SRS-S-002: 모든 API 통신은 TLS 1.2 이상을 사용해야 한다.
- SRS-S-003: 로그인 실패 5회 이상 시 계정을 30분간 잠금 처리해야 한다. -->

| ID        | SW 시스템   | 카테고리 | 요구사항 설명                                      | 위험 통제 조치? | 관련 Risk ID | 검증 방법     |
| --------- | ----------- | -------- | -------------------------------------------------- | --------------- | ------------ | ------------- |
| SRS-S-001 | All         | Security | 모든 사용자 인증은 {AUTH_METHOD}을 사용해야 한다   | Yes             | {RISK_ID}    | Security Test |
| SRS-S-002 | All         | Security | 모든 API 통신은 TLS 1.2 이상을 사용해야 한다       | Yes             | {RISK_ID}    | Security Test |
| SRS-S-003 | {SW_SYSTEM} | Security | 환자 데이터는 AES-256으로 암호화하여 저장해야 한다 | Yes             | {RISK_ID}    | Security Test |

---

## 4. 인터페이스 요구사항 (Interface Requirements)

<!-- AI AGENT: 시스템 요구사항 명세서의 SYS-I-xxx 항목을 SW 수준으로 구체화하세요
외부 시스템(EHR, PACS, DICOM 서버 등)과의 연동 사양을 포함하세요 -->

| ID        | SW 시스템 | 카테고리  | 요구사항 설명                                           | 위험 통제 조치? | 관련 Risk ID | 검증 방법        |
| --------- | --------- | --------- | ------------------------------------------------------- | --------------- | ------------ | ---------------- |
| SRS-I-001 | Backend   | Interface | 시스템은 {EXTERNAL_SYSTEM}과 {PROTOCOL}로 연동해야 한다 | No              | -            | Integration Test |

---

## 5. 규제 준수 요구사항 (Regulatory Compliance Requirements)

<!-- AI AGENT: MDR 및 적용 표준에서 요구하는 SW 준수 사항을 명시하세요 -->

| ID        | SW 시스템 | 카테고리   | 요구사항 설명                                            | 근거 표준 | 검증 방법       |
| --------- | --------- | ---------- | -------------------------------------------------------- | --------- | --------------- |
| SRS-R-001 | All       | Regulatory | SW는 IEC 62304:2006/AMD1:2015를 준수하여 개발되어야 한다 | IEC 62304 | Document Review |
| SRS-R-002 | All       | Regulatory | SW는 ISO 14971:2019에 따른 위험 관리를 수행해야 한다     | ISO 14971 | Document Review |

---

## 6. 추적성 (Traceability)

이 문서의 요구사항은 다음 문서와 연결된다:

| 연결 방향         | 연결 문서                                                 |
| ----------------- | --------------------------------------------------------- |
| 입력 (Input from) | 시스템 요구사항 명세서 (system-requirements-spec.md)      |
| 입력 (Input from) | FMEA 위험 통제 조치 (risk-table-fmea.md)                  |
| 출력 (Input for)  | SW 아키텍처 설계서 (software-architecture-description.md) |
| 출력 (Input for)  | 시스템 테스트 계획서 (software-system-test-plan.md)       |

---

## 7. 변경 이력 (Revision History)

| 버전 | 날짜   | 작성자   | 변경 내용 |
| ---- | ------ | -------- | --------- |
| 0.1  | {DATE} | {AUTHOR} | 초안 작성 |

---

> Template based on IEC 62304:2006/AMD1:2015 Clausee 5.2, IEC 81001-5-1, MDR 2017/745 Annex I
