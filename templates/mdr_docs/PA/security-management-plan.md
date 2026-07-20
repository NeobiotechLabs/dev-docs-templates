# Security Management Plan

<!-- AI AGENT 작성 지침
이 문서는 IEC 81001-5-1:2021 (Health software — Part 5-1: Security activities
in the software lifecycle) 및 AAMI TIR57 기반 보안 관리 계획서입니다.
PA 단계 핵심 산출물로, 본 문서가 보안의 단일 진실의 원천입니다.

작성 전 반드시 다음 문서를 참조하세요:
  - 소프트웨어 개발 및 유지보수 계획서(software-development-maintenance-plan.md): 개발 프로세스
  - 위험 관리 계획서(risk-management-plan.md): 위해 정의, 위험 수용 기준
  - 시스템 요구사항 명세서(system-requirements-spec.md): 시스템 경계, 자산

작성 지침:
1. Section 1 (보안 정책): Security by Design 원칙과 조직 보안 정책을 명시
2. Section 3 (위협 모델링): 접근법(STRIDE 등)만 명시 — 구체적 위협 목록은 EA 산출물
3. Section 5 (보안 V&V): 어떤 검증을 수행할지(SAST/SCA/침투테스트)만 명시 — 도구·절차 세부는 EA
4. 본 문서는 PA 'Plan' 성격 — 구현 세부(SBOM 도구명·CVD runbook 등)는 EA/운영 단계로 미룸

완성 체크리스트:
  [ ] 보안 정책(Security by Design) 명시
  [ ] 자산·위협 모델링 접근법 정의
  [ ] 보안 요구사항 도출 기준(CIA) 정의
  [ ] 보안 V&V 접근법(SAST/SCA/펜테스트) 명시
  [ ] 취약점 관리·CVE 모니터링 주기 정의
  [ ] 보안 담당자(Security Manager) 지정
-->

{PROJECT_NAME}의 보안 관리 계획서. 본 문서는 IEC 81001-5-1:2021에 따라 소프트웨어 보안
활동을 정의하며, 보안의 단일 진실의 원천이다. 작성자: {AUTHOR}, 티켓: {TICKET_ID}, 일자: {DATE}.

## Mapping of Standard Requirements to Document Sections

| Standard                | Clause                                                                          | Document Section |
| ----------------------- | ------------------------------------------------------------------------------- | ---------------- |
| IEC 81001-5-1:2021      | 5.1.1 Cybersecurity risk management plan                                        | all              |
| IEC 81001-5-1:2021      | 5.2 Threat modelling                                                            | 3                |
| IEC 81001-5-1:2021      | 5.3 Specification of security requirements                                       | 4                |
| IEC 81001-5-1:2021      | 5.4 Implementation of security controls (planning)                              | 4                |
| IEC 81001-5-1:2021      | 5.5 Cybersecurity risk control verification (approach)                          | 5                |
| IEC 81001-5-1:2021      | 7 Cybersecurity activities in the operation phase (approach)                    | 6, 7             |
| AAMI TIR57              | Security Risk Management Process                                                | 3, 4             |

## 1. Purpose, Scope and Security Policy

> 목적·적용 범위·Security by Design 원칙·조직 보안 정책을 기술.

* Security by Design 원칙: 최소 권한, 방어 심도, 보안 기본값(deny-by-default)
* {SECURITY_POLICY}

## 2. Security Organization and Roles

| Title             | Name(s) |
| ----------------- | ------- |
| Security Manager  |         |
| Incident Response |         |

## 3. Threat Modelling Approach (IEC 81001-5-1 §5.2)

> 위협 모델링 **접근법**만 명시. 구체적 위협 식별·평가는 EA 산출물로 이관.

* 방법론: {THREAT_METHODOLOGY} (예: STRIDE — Spoofing/Tampering/Repudiation/Info Disclosure/DoS/Elevation of Privilege)
* 자산 식별 범위: {ASSET_SCOPE}

## 4. Security Requirements (IEC 81001-5-1 §5.3-5.4, AAMI TIR57)

> 보안 요구사항 도출 기준. CIA(기밀성·무결성·가용성) 관점.

도출 기준:
* 인증(Authentication): {AUTH_CRITERIA}
* 권한 부여(Authorization): {AUTHZ_CRITERIA}
* 암호화(Encryption): {CRYPTO_CRITERIA}
* 로깅·감사(Logging): {LOGGING_CRITERIA}

## 5. Security V&V Approach (IEC 81001-5-1 §5.5)

> 보안 검증 **접근법** — 무엇을 수행할지만 명시. 도구·절차 세부는 EA.

* 정적 분석(SAST): {SAST_APPROACH}
* 소프트웨어 구성 분석(SCA) / 취약점 스캔: {SCA_APPROACH}
* 침투 테스트: {PENTEST_APPROACH}

## 6. Vulnerability Management (IEC 81001-5-1 §7)

> 취약점 관리·CVE 모니터링 주기 — 계획 수준.

* CVE 모니터링 주기: {CVE_MONITORING_FREQUENCY}
* 취약점 등록·조치: {VULN_TRACKING}

## 7. Cybersecurity Incident Response / CVD (IEC 81001-5-1 §7)

> 보안 사고 대응·Coordinated Vulnerability Disclosure 접근법 — 계획 수준.

* 사고 대응 절차: {INCIDENT_RESPONSE}
* CVD 정책: {CVD_POLICY}

## 8. SBOM Management

> Software Bill of Materials 관리 방침.

* SBOM 형식: {SBOM_FORMAT} (예: SPDX, CycloneDX)
* 생성·갱신 시점: {SBOM_GENERATION}
