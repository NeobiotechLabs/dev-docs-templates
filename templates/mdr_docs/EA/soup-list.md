# SOUP List (Software of Unknown Provenance)

<!-- AI AGENT 작성 지침
이 문서는 IEC 62304 Cl.8.1.2 기반 SOUP 목록입니다. EA 단계에서 초안 작성 후 매 Sprint 업데이트합니다.

작성 전 반드시 다음 문서를 참조하세요:
  - SW 아키텍처 설계서(software-architecture-description.md): SOUP 격리 전략 확인
  - 프로젝트 requirements.txt / package.json: 실제 사용 라이브러리 목록 확인

작성 지침:
1. SOUP ID 체계: SOUP-{N:3d} (예: SOUP-001)
2. 프로젝트에서 실제 사용하는 모든 서드파티 라이브러리/프레임워크를 포함하세요
   (직접 의존성 + 주요 간접 의존성)
3. 위험 등급 판단 기준:
   - Low: 고장 시 환자 위해 없음 (로깅, UI 유틸리티 등)
   - Medium: 고장 시 가역적 위해 가능 (데이터 처리 라이브러리 등)
   - High: 고장 시 비가역적 위해 가능 (인증, 암호화, 진단 알고리즘 라이브러리 등)
4. CVE 취약점은 최소 6개월마다 검토하고 "Last verified at" 날짜를 업데이트하세요
   (SOP Integrated Software Development 참조)
5. IEC 81001-5-1 관점: 보안 관련 SOUP(인증, 암호화 등)는 Known Anomalies를 반드시 확인하세요

SOUP 추가 체크리스트 (신규 추가 시):
  [ ] 버전 고정 (pinned version) 여부 확인
  [ ] CVE 데이터베이스 조회 (https://nvd.nist.gov)
  [ ] 라이선스 호환성 확인
  [ ] SBOM(Software Bill of Materials) 업데이트
  [ ] SAD의 SOUP 격리 전략 섹션에 반영
-->


> The 62304 requires you to document your SOUP, which is short for Software of Unknown Provenance. In human
> language, those are the third-party libraries you're using in your code, typically in your
> `requirements.txt` or `Gemfile`.

| Classes | IEC 62304:2006 Section                          | Document Section |
| ------- | ----------------------------------------------- | ---------------- |
| B, C    | 5.3.3 (Functional and Performance Requirements) | 2                |
| B, C    | 5.3.4 (Hardware and Software Requirements)      | 2                |
| B, C    | 7.1.2 (Hazardous Situations)                    | 2                |
| B, C    | 7.1.3 (SOUP Anomaly Lists)                      | 2                |
| A, B, C | 8.1.2 (Identify SOUP)                           | 2                |

## 1 Risk Level Definitions

> The 62304 requires you to assess risks associated with SOUP. The simplest way to do this is to classify each
> SOUP as a certain risk level. Unless you're developing software which shoots radiation at patients, it's
> likely that your SOUP risk levels remain "low" or "medium".

| Risk Level | Definition                                                 |
| ---------- | ---------------------------------------------------------- |
| Low        | Malfunction in SOUP can't lead to patient harm.            |
| Medium     | Malfunction in SOUP can lead to reversible patient harm.   |
| High       | Malfunction in SOUP can lead to irreversible patient harm. |

## 2 SOUP List

> This is the actual SOUP list. For each third-party library you use, add an entry in the table below. The
> idea is to only have one "global" SOUP list for your medical device even though the code may actually live
> in multiple repositories. That's what the "software system" column is for; you could also mention your (git)
> repository there.

> When specifying requirements, the 62304 requires you to mention functional, performance, hard- and software
> requirements. However, you may not have to re-state certain requirements if they apply to all SOUP,
> e.g., "runs on Linux". So prefer to keep the requirements simple, in a way in which you would communicate them
> to colleagues on your development team when answering the question "why did we import this library?".

> As with all templates: It's more about the content (i.e., the columns you see below) than the tool (filling
> this out in Google sheets / markdown / wherever). Nobody says that you have to maintain this as a Google
> sheet. If you can find a way to integrate this in your workflow in a better way, e.g., in a markdown file in
> your git repository, go for it! Just keep in mind that you need to be able to export it to send it to
> auditors.

| ID  | Software System | Package Name | Programming Language | Version | Website                                          | Last verified at | Risk Level | Requirements               | Verification Reasoning                                                      |
| --- | --------------- | ------------ | -------------------- | ------- | ------------------------------------------------ | ---------------- | ---------- | -------------------------- | --------------------------------------------------------------------------- |
| 1   | Mobile App      | react-native | JavaScript           | 0.61    | [Link](https://facebook.github.io/react-native/) | 23.10.2020       | Low        | * Runs JS on Android / iOS | Commonly used, maintained by a large organisation, sufficient test coverage |

---

Template Copyright [openregulatory.com](https://openregulatory.com). See [template
license](https://openregulatory.com/template-license).

Please don't remove this notice even if you've modified contents of this template.
