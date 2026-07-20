# Configuration Management Plan

<!-- AI AGENT 작성 지침
이 문서는 IEC 62304 §8 (Configuration Management Process) 기반 형상관리 계획서입니다.
PA 단계에서 작성하는 핵심 산출물로, 본 문서가 형상관리의 단일 진실의 원천입니다.
SDMP(Software Development and Maintenance Plan)는 본 문서를 참조합니다.

작성 전 반드시 다음 문서를 참조하세요:
  - 소프트웨어 개발 및 유지보수 계획서(software-development-maintenance-plan.md): 개발 워크플로우, 도구 체인
  - 시스템 요구사항 명세서(system-requirements-spec.md): 타겟 환경, 구성 항목 후보
  - SOP Change Management (회사 QMS 자산; 시드 템플릿 global/qms/sop-change-management.md):
    회사 수준의 변경 평가·통제 절차. CMP는 본 기기의 형상관리를, SOP는 회사 전체의
    변경 통제 절차를 다룬다(상호 보완). 첫 기기 개발 시 회사 QMS asset이 아직 없으면
    상기 시드 템플릿으로 자사 SOP를 먼저 작성할 것.

작성 지침:
1. Section 2 (형상 식별): 형상 항목(CI) 후보를 식별하세요 — 소스 코드, 빌드 스크립트, SOUP, 문서, 환경 설정
2. Section 3 (버전 통제): 버전 네이밍 체계(시맨틱 버저닝)와 태그 정책을 정의하세요
3. Section 4 (변경 통제): Change Evaluation List 연계 절차를 기술하세요
4. Section 5 (형상 감사): 감사 주기·기준을 정의하세요
5. 본 문서는 PA 'Plan' 성격 — 구현 세부(도구 세부 설정 등)는 EA/운영 단계로 미룸

완성 체크리스트:
  [ ] 형상 항목(CI) 식별 기준 명시
  [ ] 버전 넘버링·태그 정책 정의
  [ ] 변경 통제 절차(SOP Change Management 연계) 기술
  [ ] 형상 감사 일정·기준 정의
  [ ] 형상 관리 담당자(Configuration Manager) 지정
-->

{PROJECT_NAME}의 소프트웨어 형상관리 계획서. 본 문서는 IEC 62304 §8에 따라 형상관리 프로세스를
정의하며, 모든 형상 관리 활동의 단일 진실의 원천이다. 작성자: {AUTHOR}, 티켓: {TICKET_ID}, 일자: {DATE}.

## Mapping of Standard Requirements to Document Sections

| Standard                | Clause                                                              | Document Section |
| ----------------------- | ------------------------------------------------------------------- | ---------------- |
| IEC 62304               | 5.1.9 Software Configuration Management Planning                    | 3                |
| IEC 62304               | 5.1.10 Supporting Items to be Controlled                            | 2                |
| IEC 62304               | 5.1.11 Software Configuration Item Control Before Verification      | 7                |
| IEC 62304               | 8.1 Configuration Identification                                    | 2                |
| IEC 62304               | 8.2 Change Control                                                  | 4                |
| IEC 62304               | 8.3 Configuration Status Accounting                                 | 5                |
| IEC 62304               | 8.4 Configuration Audit                                             | 6                |
| ISO 13485:2016          | 7.3.7 Design and Development Verification (configuration aspects)  | 6, 7             |
| ISO 13485:2016          | 7.5 Document Control (applied to configuration items)               | 3                |

## 1. Purpose and Scope

> 이 계획서의 목적과 적용 범위를 기술하세요. 어떤 소프트웨어 제품/버전에 적용되는지 명시.

{SCOPE_DESCRIPTION}

## 2. Configuration Identification

> 형상 항목(Configuration Item, CI)을 식별하는 기준을 정의하세요. 각 CI는 고유 식별자·버전을 갖는다.

형상 항목 후보:
* 소스 코드 (레포지토리 단위)
* 빌드 스크립트 및 환경 설정 (CI/CD 파이프라인 정의 포함)
* SOUP (third-party 의존성, lockfile)
* 소프트웨어 문서 (요구사항·설계·테스트 산출물)
* 빌드 산출물 (release artifact)

| CI Category    | Naming Convention | Tool           |
| -------------- | ----------------- | -------------- |
| {CI_CATEGORY}  | {CI_NAMING}       | {CI_TOOL}      |

## 3. Version Control

> 버전 네이밍 체계와 태그 정책을 정의하세요. 시맨틱 버저닝(MAJOR.MINOR.PATCH) 권장.

* 버전 체계: {VERSION_SCHEME} (예: Semantic Versioning 2.0.0)
* 태그 정책: {TAG_POLICY} (각 release 커밋에 tag 부여, 과거 버전 복원 가능해야 함)
* 버전 관리 도구: Git

## 4. Change Control

> 변경 통제 절차를 기술하세요. SOP Change Management와 연계.

변경 요청 → 영향 평가(Change Evaluation List) → 승인 → 구현 → 검증의 흐름을 따른다.
자세한 절차는 SOP Change Management를 참조한다. 본 절에서는 소프트웨어 형상 항목에
특화된 통제 기준만 명시한다.

* 변경 요청 기록: {CHANGE_REQUEST_LOCATION}
* 승인 권한자: {CHANGE_APPROVER}

## 5. Configuration Status Accounting

> 형상 상태 기록(status accounting) — 현재 각 CI의 버전·상태를 추적·보고하는 방법.

{STATUS_ACCOUNTING_METHOD}

## 6. Configuration Audit

> 형상 감사 일정·기준. 기능/물리 형상 감사(Functional/Physical Configuration Audit).

* 감사 주기: {AUDIT_FREQUENCY}
* 감사 기준: {AUDIT_CRITERIA}

## 7. Configuration Item Control Before Verification

> 검증 활동 시작 전, 검증 대상 형상 항목이 통제되어야 함. 검증 대상 CI 식별·고정 방법.

{PRE_VERIFICATION_CONTROL}

## 8. Roles

| Title                 | Name(s) |
| --------------------- | ------- |
| Configuration Manager |         |
| Release Manager       |         |
