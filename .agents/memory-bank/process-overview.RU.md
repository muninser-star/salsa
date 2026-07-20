# Fast-ASDLC: Процесс разработки ПО и обзор AI Runtime

## 1. Локальная среда исполнения AI
- **Стратегия развёртывания:** модель-агностична и tool-агностична. Local-LLM first / в защищённом корпоративном контуре, когда задействованы стратегические данные.
- **Платформа inference engine:** зависит от участника. Текущий пример: OpenRouter API через OpenCode extension в VS Code.
- **Основная модель рассуждений / оркестрации:** зависит от участника. Текущий пример: Kimi через OpenRouter.
- **Основная модель генерации кода:** зависит от участника. Текущий пример: Kimi через OpenRouter.
- **Ограничение:** на этом этапе не требуется единый runtime. Manifests рабочей силы должны оставаться портативными между OpenCode, Cursor, Cline и будущими инструментами.

## 2. Локальная человеко-агентная интеграция и маппинг ролей
- **Основная IDE среда проекта:** VS Code + OpenCode extension.
- **CLI workspace tooling:** native Zsh/Bash.

### 2.1 Матрица роль → инструмент

| SDLC роль агента | Target IDE / Interface | Agentic tool / Wrapper | Ограничение рабочего пространства |
| :--- | :--- | :--- | :--- |
| **Meta-Agent** | VS Code | OpenCode | `/.agents/`, root dotfiles, `.backlog/` |
| **Analyst Agent** | VS Code | OpenCode | `/.backlog/`, `/docs/domain/` |
| **Architect Agent** | VS Code | OpenCode | `/docs/` (domain, specs, architecture) |
| **Programmer Agent** | VS Code | OpenCode | `/src/`, `/tests/`, `/infra/` |
| **QA Automation Agent** | VS Code | OpenCode | `/tests/`, `/docs/specs/` (READ only) |

## 3. Целевые targets инфраструктурного манифеста
- **CI/CD orchestration tool:** TBD.
- **Infrastructure-as-Code engine:** TBD.
- **Application security tooling:** TBD.

## 4. Роль Meta-Agent (Process Architect)
- **Назначение роли:** проектирует, инициализирует и непрерывно настраивает локальную AI-native agentic SDLC инфраструктуру.
- **Обязанности:** конфигурирует identities агентов (`rules/`), operational sequences (`workflows/`), и capabilities (`skills/`). Интегрирует environments инструментов.
- **Deliverables:** операционные конфигурации для downstream project agents на основе ограничений `project-brief.md`.

## 5. Роли Agentic Workforce
- **Analyst Agent:** переводит человеческие намерения в Use Cases, UI mocks, и Ubiquitous Language mappings в `/docs/domain/`.
- **Architect Agent:** строит C4 Model views (Mermaid.js), enforcement Threat Modeling, и производит strict, low-level execution task files в `/docs/specs/`.
- **Programmer Agent:** имплементирует production логику, unit tests, и infrastructure automation containers (`infra/`) sequentially.
- **QA Automation Agent:** оркестрирует integration/load validation setups путём развёртывания System Under Test (SUT) и tracking bugs.

## 6. Git-центричный lifecycle и quality gates
- **Изоляция:** каждая backlog задача запускает dedicated feature-branch.
- **Backlog "Bus":** tracking файл в `.backlog/` действует как context handoff bus. Каждый агент добавляет ссылки на свои вновь созданные артефакты.
- **State Transition:** архитектурные активы внутри feature branch представляют состояние TO-BE. При успешном human review и merge в `main`, они переходят в definitive AS-IS системное состояние.
- **Human-in-the-Loop:** явные human validation checkpoints блокируют каждый inter-agent role transition.

## 7. Последовательность выполнения SDLC фаз

### Текущая фаза: Phase 0 / Phase 1
- **Phase 0 (Infrastructure Setup):** Meta-Agent читает `project-brief.md` и `process-overview.md`, затем инициализирует/обновляет agent workforce manifests и tool configurations.
- **Phase 1 (Analysis & Design):** только Markdown.
  - Analyst Agent строит requirements и Use Cases с formal Acceptance Criteria внутри `/docs/domain/usecases/` и обновляет `/docs/domain/glossary.md`. [HITL Gate]
  - Architect Agent получает на вход эти use cases для конструирования C4 models (Mermaid.js), Threat Models, и low-level specifications (имена файлов/классов/методов) внутри `/docs/specs/`.
  - QA Agent выполняет static contract analysis сгенерированной архитектуры относительно analytical use cases перед любой разработкой кода. [HITL Gate]

### Отложенные фазы
- **Phase 2 (Implementation):** отложена до заполнения Section 3 в `project-brief.md` человеком.
- **Phase 3 (Environment Deployment):** отложена до решения о tech stack.
- **Phase 4 (Validation):** отложена до trigger implementation.
- **Phase 5 (Delivery):** финальный human review и merge в `main`.

## 8. Универсальные стандарты

### Политика языка
- **System prompts агентов, правила, workflows, skills:** строго английский.
- **Документация проекта и артефакты:** английский, кроме backlog/interview черновиков как определено в `project-brief.md`.

### Основания Quality Engineering
- **Contract-First Constraint:** генерация кода запрещена без approved upstream specification file.
- **Test Coverage Gates:** 100% unit test coverage требуется для чистого Domain layer; minimum 90% для Application и Infrastructure layers (применимо когда начинается имплементация).
- **Context Preservation:** агенты должны активно summarize task history внутри `.agents/memory-bank/active-context.md`.
