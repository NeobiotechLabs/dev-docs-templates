# dev-docs-templates

다목적 문서 템플릿 저장소. 규제 산출물(MDR)과 개발 산출물(dev)의 **출력 포맷(How)** 진실 원천.

> **3계층 아키텍처의 ① 계층** — `jira-mcp-server`(②)가 이 repo를 git submodule로 읽어 `doc_render`로 렌더하고, skill(③)이 절차를 지시한다.

---

## 디렉토리 구조

```
dev-docs-templates/
├── templates/
│   ├── mdr_docs/   # MDR 규제 산출물 (IEC 62304 PA/EA/ER + Annex II CA + QMS/보안 global) — openregulatory.com 기반
│   └── dev_docs/   # 개발 산출물 (plan / prd / spec / tasks) — feature(개발 Jira 티켓) 단위 산출물 분리
├── README.md
└── .gitignore
```

### `templates/mdr_docs/`

MDR 규제 문서 템플릿. 게이트(PA/EA/ER/CA) 및 전역(global · QMS · 보안)으로 구성. openregulatory.com 양식을 기반으로 하며 **저작권 notice가 각 템플릿 말단에 보존**됨(필수).

### `templates/dev_docs/`

개발 산출물 템플릿. 한 feature(개발 Jira 티켓)의 산출물을 단계별로 분리:

| 템플릿 | 용도 | 렌더 시 Jira 소스 |
|--------|------|-------------------|
| `prd_template.md` | 제품 요구사항 정의(PRD) | Epic/Feature 티켓, 사용자 스토리 |
| `spec_template.md` | 기능 명세(Spec) — 요구사항·인수시나리오 | Requirement 티켓 |
| `plan_template.md` | 구현 계획(Plan) — 접근·일정·리스크 | Task/서브태스크 |
| `tasks_template.md` | 태스크 분해(Tasks) — 체크리스트·의존성 | 서브태스크, Definition of Done |

워크플로우: **PRD → Spec → Plan → Tasks** (각 단계 산출물이 다음 단계의 입력).

---

## 템플릿 규약 (6-블록)

모든 템플릿은 다음 구조를 따른다. `doc_render`는 `{VAR}` 치환과 표 채우기로 산출물을 완성한다.

1. **작성 지침**(HTML 주석 `<!-- ... -->`) — 렌더 시 제거. 작성자/AI를 위한 안내.
2. **매핑 표**(선택) — 표준 조항(mdr_docs) 또는 Jira 키(dev_docs) ↔ 섹션.
3. **메타 `{VAR}`** — `DOC_ID`/`VERSION`/`AUTHOR`/`DATE`/`TICKET_ID` 등.
4. **본문 섹션** — 템플릿별 요구사항·계획·태스크 표.
5. **추적성** — Input from(상위 산출물) / Output to(하위 산출물).
6. **변경 이력** + 라이선스 notice.

---

## 사용 방법

### consumer 프로젝트에서 submodule로 연결

```bash
git submodule add git@github.com:NeobiotechLabs/dev-docs-templates.git dev-docs-templates
git submodule update --init --recursive
```

연결 후 `jira-mcp-server`의 `doc_render` 도구가 특정 commit pin을 가리켜 산출물 재현성을 확보한다(commit 변경 = 템플릿 버전 변경).

> 자세한 통합 설계는 `jira-mcp-server`의 `docs/mdr-template-integration-review.md` 참조.

### 템플릿 수정

- 템플릿은 이 repo에서 직접 수정 → commit. 산출물이 아닌 **포맷 자체**를 버전 관리.
- `{VAR}` 변수명은 `doc_render`의 렌더 파라미터와 일치해야 함.
- `mdr_docs/` 수정 시 openregulatory 라이선스 notice 보존 필수.

---

## 라이선스

- `templates/mdr_docs/` — openregulatory.com 양식 기반. 각 템플릿의 저작권 notice 준수.
- `templates/dev_docs/` — 사내 자체. © NeobiotechLabs.
