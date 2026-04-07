# Intended Use

<!-- AI AGENT 작성 지침
이 문서는 MDR Annex II 1.1, ISO 14971 Cl.5.2, IEC 62366-1 Cl.5.1 기반 사용 목적 정의서입니다.
PA 단계의 첫 번째 핵심 문서로, 모든 이후 문서의 근거가 됩니다.

작성 지침:
1. "Intended Use": 의료 기기의 核心 기능을 명확하고 간결하게 기술하세요
   - 무엇을 하는가? (진단/치료/모니터링)
   - 어떤 방식으로? (AI 분석, 데이터 수집 등)
   - 어떤 결과를 제공하는가? (점수, 권고사항, 시각화 등)
   예시: "This software is intended to assist clinicians in detecting {CONDITION} by analyzing {INPUT_DATA} and providing a risk score."

2. "Intended Medical Indication": 대상 질환/상태를 구체적으로 기술하고
   "제외 기준(Exclusion Criteria)"을 반드시 포함하세요

3. "Patient Population": 나이, 체중, 동반 질환 등 구체적 특성을 기술하세요

4. "User Profile": 의료 종사자인지 일반 사용자인지 명확히 구분하세요
   - 필요한 교육/자격 요건
   - 기술 숙련도 수준

5. "Use Environment": 병원 환경인지 재택 환경인지 구분하고
   소음, 조명, 시간 압박 등 환경적 특성을 기술하세요

6. "Operating Principle": 입력 -> 처리 -> 출력 흐름을 명확히 기술하세요
   AI/ML 모델을 사용하는 경우 반드시 "보조 진단 도구"임을 명시하세요

완성 체크리스트:
  [ ] 제품명 및 버전 기재
  [ ] Medical Indication에 제외 기준(Contraindications) 포함
  [ ] 의도된 사용자와 환자 집단 구분 명확
  [ ] MDR 등급 결정을 위한 충분한 정보 제공
  [ ] IFU(instructions-for-use.md)와 내용 일치 확인
-->


## Mapping of Requirements to Document Sections

| MDR Class | MDR Section                   | Document Section |
| --------- | ----------------------------- | ---------------- |
| (All)     | Annex II, 1.1 a) - d), h), i) | (All)            |

| ISO 14971:2019 Section | Document Section |
| ---------------------- | ---------------- |
| 5.2                    | (All)            |

| IEC 62366-1:2015 Section | Document Section |
| ------------------------ | ---------------- |
| 5.1                      | (All)            |

## Product

 * Name: *\<product name\>*
 * Version: *\<product version\>*
 * Basic UDI-DI: *\<insert UDI-DI, if/when available\>*

## Intended Use

> Describe the core medical functionality of your device and how it treats, diagnoses or alleviates a disease.
> Keep it high-level so that this description is true for as long as possible even when the device is updated.

## Intended Medical Indication

> Describe the condition(s) and/or disease(s) to be screened, monitored, treated, diagnosed, or prevented by
> your software. Importantly, also list exclusion criteria: Maybe patients with a certain diagnosis should not
> be using your device.

## Contraindications

> List anything that you want to explicitly exclude from your intended use.

## Patient Population

> Describe the patient population your software is intended to be used on. Note that this may overlap with the
> user profile (section below), but not necessarily. Your software could be used by physicians to diagnose
> diseases in patients, so in that case, they don't overlap. Some ideas for characteristics to describe: Age
> group, weight range, health, condition(s).

## User Profile

> Describe the typical user of the software. Some ideas could be: Qualifications, prior training (for your
> software), technical proficiency, time spent using the software.

## Use Environment Including Software/Hardware

> Describe the typical use environment. What sort of devices is this running on? Does the software only run on
> one device or multiple devices? Is it loud and chaotic like in an emergency ward? How's the lighting?
>
> Also, add other software or hardware which is required by your device. Most commonly, apps require users to
> have a smartphone with a compatible operating system (iOS / Android).

## Operating Principle

> It's kind of a stretch to describe the "operating principle" of software. I guess this makes more sense for
> hardware devices. In any case, I'd just generally state what sort of input goes in and what output comes
> out, e.g. you could be processing images and returning diagnoses.

The device is stand-alone software. It receives input from the user and outputs information.

## Part of the Body / Type of Tissue Interacted With

The device is stand-alone software. It receives input from the user and outputs information. It doesn't come
in contact with tissue or bodily fluids.

## Variants / Accessories

> Describe variants and/or accessories of/to this device, if applicable. For typical stand-alone software of
> startups, this shouldn't be applicable.

---

Template Copyright [openregulatory.com](https://openregulatory.com). See [template
license](https://openregulatory.com/template-license).

Please don't remove this notice even if you've modified contents of this template.
