# Software Development and Maintenance Plan

<!-- AI AGENT 작성 지침
이 문서는 IEC 62304 Cl.5.1 기반 SW 개발 및 유지보수 계획서입니다. PA 단계 핵심 산출물입니다.

작성 전 반드시 다음 문서를 참조하세요:
  - 시스템 요구사항 명세서(system-requirements-spec.md): 팀 구성, 타겟 환경 확인
  - 사용 목적 정의서(intended-use.md): 제품명, SW 안전 등급 확인

작성 지침:
1. Section 2.2 (SW 안전 등급): IEC 62304 Cl.4.3 기준으로 Class A/B/C를 결정하고 근거를 기술하세요
2. Section 3 (Design Phases): 우리 Gate 프로세스에 맞게 PA/EA/ER/CA로 업데이트하세요
   - PA: 기획 및 계획 -> 개발 시작 전 승인
   - EA: 요구사항 및 설계 -> 코딩 시작 전 승인
   - ER: 구현 및 검증 -> Sprint 반복 (Sprint No, 완료 일자 기입)
   - CA: 최종 릴리스 -> 검증 완료 후 승인
3. Section 5 (Configuration Management): 형상관리 상세 정책·절차는 Configuration Management Plan
   을 참조. 이 섹션은 개발 워크플로우 수준의 개요(Git 브랜치 전략이 CMP 기준을 따른다는 정도)만 기술.
4. 보안(Security): 본 SDP에 보안 챕터를 두지 않음. 보안 계획·정책·위협 모델링은
   Security Management Plan (IEC 81001-5-1) 참조.
5. Section 2.1 팀 구성에 실제 인원을 기재하고 역할을 구체화하세요

완성 체크리스트:
  [ ] 제품명 및 SW 안전 등급 명시
  [ ] Design Phases에 PA/EA/ER/CA Gate 반영
  [ ] Section 5 형상관리는 Configuration Management Plan 참조 확인
  [ ] Security Management Plan (IEC 81001-5-1) 참조 확인
  [ ] 담당자 역할(R&R) 기재
-->


This document summarizes development and maintenance activities.

## Mapping of Standard Requirements to Document Sections

| ISO 13485:2016 Section                | Document Section |
| ------------------------------------- | ---------------- |
| 7.3.2 Design and Development Planning | 1, 2, 3, 7       |

| Classes | IEC 62304:2006 Section                                                     | Document Section |
| ------- | -------------------------------------------------------------------------- | ---------------- |
| A, B, C | 4.4.2 Risk Management Activities                                           | 1                |
| A, B, C | 5.1.1 a) (Processes)                                                       | 1                |
| A, B, C | 5.1.1 b) (Deliverables)                                                    | 1                |
| A, B, C | 5.1.1 c) (Traceability)                                                    | 1                |
| A, B, C | 5.1.1 d) (Configuration and Change Management)                             | 1, 5             |
| A, B, C | 5.1.1 e) (Problem Resolution)                                              | 1                |
| A, B, C | 5.1.2 Keep Software Development Plan Updated                               | 1                |
| A, B, C | 5.1.3 Software Development Plan Reference to System Design and Development | 2                |
| C       | 5.1.4 Software Development Standards, Methods and Tools Planning           |                  |
| B, C    | 5.1.5 Software Integration and Integration Test Planning                   | 3, 8             |
| A, B, C | 5.1.6 Software Verification Planning                                       | 7                |
| A, B, C | 5.1.7 Software Risk Management Planning                                    | 1                |
| A, B, C | 5.1.8 Documentation Planning                                               | 6                |
| A, B, C | 5.1.9 Software Configuration Management Planning                           | 5                |
| B, C    | 5.1.10 Supporting Items to be Controlled                                   | 5                |
| B, C    | 5.1.11 Software Configuration Item Control Before Verification             | 5                |
| B, C    | 5.1.12 Identification and Avoidance of Common Software Defects             | 4                |
| A, B, C | 6.1 Software Maintenance Plan.                                             | 10               |

## 1 Relevant Processes and Documents

Please see the relevant processes for the following activities:

 * Risk management activities incl. SOUP risks: SOP Integrated Software Development
 * Problem resolution: SOP Problem Resolution
 * Software development incl. deliverables, traceability, regular update of software development plan: SOP
   Integrated Software Development
 * Change management: SOP Change Management
 * SOUP List
 * Usability engineering activities: SOP Integrated Software Development

## 2. Required Resources

### 2.1 Team

| Role                | Count | Responsibilities                            |
| ------------------- | ----- | ------------------------------------------- |
| Head of Development | 1     | Prioritizing tasks and technical oversight  |
| Frontend Developer  | 2     | Implementing Frontend Software Requirements |
| Backend Developer   | 1     | Implementing Backend Software Requirements  |

### 2.2 Software

#### IEC 62304 Software Safety Classification

The software safety classification for \[enter device name\] has been established as class \[XXXX\] per IEC 62304:2006/AMD1:2015 based on the decision-making process outlined in table 3 and in paragraph 4.3 of the norm. A malfunction of, or latent design flaw in the software device may lead to situations with unacceptable risks \[for example: false-positive and false-negative diagnosis, resulting in unnecessary interventions or missed necessary interventions\]. This excludes software safety class A. Serious injuries or death, however, can be ruled out because \[XXXX\]. Considering these risk control measures external to the software system, safety class C can be ruled out, resulting in class B.

#### Measuring Function

The \[enter device name\] does not include a measuring function, as described in EU Regulation 2017/45 and relevant regulatory guidance documents. The definition of MEDDEV 2.1-5 for measuring functions does not apply because \[XXX\].

#### Combination With Other Products

To achieve its intended purpose, the \[enter device name\] is intended to be used in combination with \[for example: MRI/CT scanners that produce imaging data\]. Specifications for compatible equipment are described in the List of Software Requirements as well as in the Instructions for Use. Relevant verification and validation tests will be added to the documentation.

#### Product Lifetime

The software's lifetime is established to be \[for example: three years\]. This is what is expected to be the maximum time until the implementation of a significant change, by which the manufacturer is able to react to the relevant changes to the software device environment, such as SOUP changes, cybersecurity innovations, or the evolving technological or medical state of the art.

#### Programming Languages

> List the languages you’ll be using, including compiler and language versions.

| Name   | Version |
| ------ | ------- |
| Python | 3.8     |

#### Development Software

> List software used to support development, e.g., IDEs.

| Name    | Version  |
| ------- | -------- |
| PyCharm | 2020.1.4 |

### 2.3 System Requirement / Target Runtime

> List your target runtime(s).

| Name    | Version |
| ------- | ------- |
| CPython | 3.8     |

> Specify system requirements, e.g., the minimum specifications of the server / compute instance you'll be
> running your software on

*Minimum system requirements:*

 * *Server-grade dual-core CPU, e.g., Intel Xeon E3-1230 v5 or higher*
 * *4 GB of RAM*
 * *1 GBit/s up- and downlink*
 * *20GB SSD storage*

## 3 Design Phases

> The 13485 requires you to specify "Design Phases". Here are some suggestions which you could use.

| Title          | Estimated Completion Date | Description | Review method                   |
| -------------- | ------------------------- | ----------- | ------------------------------- |
| Specification  |                           |             | Software Requirements Checklist |
| Implementation |                           |             | Code Reviews                    |
| Testing        |                           |             | System Test                     |
| Validation     |                           |             | Usability Evaluation            |
| Release        |                           |             | Release Checklist               |

## 4 Avoiding Common Software Defects Based on Selected Programming Technology

> Discuss how your selected programming technology may introduce risks and how you plan to avoid them. With
> modern, dynamically-typed languages, an obvious risk is that you encounter runtime exceptions. So you could
> argue that your test coverage is great and compensates for that. You could also link to your risk analysis
> here if you analyse those risks further.

## 5 Configuration Management and Version Control

> Describe which version control software you're using (probably git, like all human beings on this planet
> right now, except enterprise developers). Also describe your branching model, i.e., how your developers
> create branches during development, how you name them and how you merge them (pull requests? merge commits?
> squash before?). Your code review will be described in the next section.
>
> Importantly, describe which things (code, build files, etc.) are put in version control. Describe how you
> name versions and how you tag them. Your goal should be that you can retrieve an old version and build
> it. Why? Something with a newer version may go wrong (harm patients) and you may need to roll back.

형상관리(식별·변경 통제·상태 기록·감사)의 상세 정책과 절차는 **Configuration Management Plan**
을 따른다. 본 섹션에서는 개발 워크플로우 수준의 개요만 기술한다.

* Git을 버전 관리 도구로 사용. 모든 소스 코드·빌드 파일은 버전 관리 대상.
* 개발자는 `master`에서 분기한 피처 브랜치에서 작업. 구현 완료 시 `master`로 머지 커밋 생성.
* 각 release는 고유 식별 가능하도록 tag 부여(SemVer 2.0.0). 버전 체계·태그 정책·변경 통제 절차의
  상세는 Configuration Management Plan §3·§4를 참조.

## 6 Documentation Activities

> Describe your policy on what should be documented while you develop software. Maybe you want to require
> your developers to document all methods which are private. Maybe you want to keep an up-to-date software
> architecture diagram in the repository, etc. Make sure to mention how traceability between Software Requirements and Tests is maintained.

## 7 Implementation Verification Activities

> Describe verification activities, e.g. code review.

*For each pull request, a code review is performed by a team member who was not the main author of the code
under review. The code review is only marked as "approved" if the code complies with the code review
criteria. This is:*

 * *Code fulfils the software requirements*
 * *Adherence to [PEP8 Style Guide](https://www.python.org/dev/peps/pep-0008/)*

## 8 Software System Test Activities

> Describe software system test activities. This could be continuous integration which is triggered by opening
> a pull request (e.g. Travis CI, Circle CI). Describe what is tested and how that automated system works.

*Integration tests are included in software system tests.*

## 9 Validation Activities

Validation is carried out as formative and summative usability evaluation as described in the software development process. A usability evaluation file (plan, protocol and report) will be prepared.

## 10 Maintenance Activities

> Describe how often you check SOUP issue trackers and how you document them.

*SOUP issue trackers are checked at least once every 6 months. The verification date is updated in the SOUP
list accordingly.*

---

Template Copyright [openregulatory.com](https://openregulatory.com). See [template
license](https://openregulatory.com/template-license).

Please don't remove this notice even if you've modified contents of this template.
