# AutoAgenticDevAssets

AutoDevAgentTeam 시스템의 공통 Goose 레시피 및 컨텍스트 파일 저장소입니다.

## 디렉토리 구조

```
AutoAgenticDevAssets/
├── .goosehints                    # Goose 글로벌 컨텍스트 힌트
├── recipes/
│   ├── main/
│   │   ├── plan_flow.yaml         # !plan 명령 진입점
│   │   └── implement_flow.yaml    # !implement 명령 진입점
│   └── sub/
│       ├── sub_prd_generator.yaml
│       ├── sub_srs_analyzer.yaml
│       ├── sub_arch_designer.yaml
│       ├── sub_detail_designer.yaml
│       ├── sub_spec_kit_spec.yaml
│       ├── sub_spec_kit_plan.yaml
│       ├── sub_spec_kit_tasks.yaml
│       ├── sub_dev_env_setup.yaml
│       ├── sub_test_planner.yaml
│       └── sub_task_processor.yaml
└── templates/
    └── jira_report.md             # Jira 댓글용 보고서 템플릿
```

## 사용 방법

각 대상 프로젝트 레포에 이 레포를 submodule로 등록합니다:

```bash
git submodule add https://github.com/NeobiotechLabs/AutoAgenticDevAssets.git common-agent-assets
git submodule update --init --recursive
```

## 레시피 실행

```bash
# !plan 명령 시
goose run common-agent-assets/recipes/main/plan_flow.yaml

# !implement 명령 시
goose run common-agent-assets/recipes/main/implement_flow.yaml
```