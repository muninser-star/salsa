# Fast-ASDLC: Software Development Process & AI Runtime Overview

## 1. Local AI Execution Environment
- **Deployment strategy:** Model-agnostic and tool-agnostic. Local-LLM first / within protected corporate contour where strategic data is involved.
- **Inference engine platform:** Participant-specific. Current example: OpenRouter API via the OpenCode extension in VS Code.
- **Primary reasoning / orchestration model:** Participant-specific. Current example: Kimi via OpenRouter.
- **Primary code generation model:** Participant-specific. Current example: Kimi via OpenRouter.
- **Constraint:** No single runtime is mandated at this stage. The workforce manifests must remain portable across OpenCode, Cursor, Cline, and future tooling.

## 2. Local Human-Agent Interface Setup & Role Mapping
- **Primary IDE environment for the project:** VS Code + OpenCode extension.
- **CLI workspace tooling:** Native Zsh/Bash.

### 2.1 Role-to-Tool Matrix

| SDLC Role Agent | Target IDE / Interface | Agentic Tool / Wrapper | Workspace Restriction |
| :--- | :--- | :--- | :--- |
| **Meta-Agent** | VS Code | OpenCode | `/.agents/`, root dotfiles, `.backlog/` |
| **Analyst Agent** | VS Code | OpenCode | `/.backlog/`, `/docs/domain/` |
| **Architect Agent** | VS Code | OpenCode | `/docs/` (domain, specs, architecture) |
| **Programmer Agent** | VS Code | OpenCode | `/src/`, `/tests/`, `/infra/` |
| **QA Automation Agent** | VS Code | OpenCode | `/tests/`, `/docs/specs/` (READ) |
| **RTE Agent** | VS Code | OpenCode | `.backlog/pi-*/`, `.backlog/dependencies/`, `/docs/architecture/adr/program-board-*.md` |
| **Risk Manager Agent** | VS Code | OpenCode | `.backlog/risk-audit/` (write), `.backlog/`, `/docs/architecture/adr/`, `.members/` (read) |

## 3. Target Infrastructure Manifest Targets
- **CI/CD orchestration tool:** TBD.
- **Infrastructure-as-Code engine:** TBD.
- **Application security tooling:** TBD.

## 4. The Meta-Agent (Process Architect) Role
- **Role Purpose:** Designs, initializes, and continuously fine-tunes the local AI-native agentic SDLC infrastructure.
- **Responsibilities:** Configures agent identities (`rules/`), operational sequences (`workflows/`), and capabilities (`skills/`). Integrates tool environments.
- **Deliverables:** Operational configurations for downstream project agents based on `project-brief.md` constraints.

## 5. Agentic Workforce Roles
- **Analyst Agent:** Translates human intentions into Use Cases, UI mocks, and Ubiquitous Language mappings inside `/docs/domain/`.
- **Architect Agent:** Builds C4 Model views (Mermaid.js), enforces Threat Modeling, and produces strict, low-level execution task files inside `/docs/specs/`.
- **Programmer Agent:** Implements production logic, unit tests, and infrastructure automation containers (`infra/`) sequentially.
- **QA Automation Agent:** Orchestrates integration/load validation setups by deploying the System Under Test (SUT) and tracking bugs.

## 6. Git-Centric Lifecycle & Quality Gates
- **Isolation:** Every backlog task triggers a dedicated feature-branch.
- **The Backlog "Bus":** The tracking file in `.backlog/` acts as the context handoff bus. Each agent appends links to their newly created artifacts.
- **State Transition:** Architectural assets inside a feature branch represent the *TO-BE* state. Upon successful human review and merge to `main`, they transition to the definitive *AS-IS* system state.
- **Human-in-the-Loop:** Explicit human validation checkpoints block every inter-agent role transition.

## 7. SDLC Phase Execution Sequence

### Current Phase: Phase 0 / Phase 1
- **Phase 0 (Infrastructure Setup):** Meta-Agent reads `project-brief.md` and `process-overview.md`, then initializes/updates the agent workforce manifests and tool configurations.
- **Phase 1 (Analysis & Design):** Markdown only.
  - Analyst Agent builds requirements and Use Cases with formal Acceptance Criteria inside `/docs/domain/usecases/` and updates `/docs/domain/glossary.md`. [HITL Gate]
  - Architect Agent inputs these use cases to construct C4 models (Mermaid.js), Threat Models, and low-level specifications (file/class/method names) inside `/docs/specs/`.
  - QA Agent performs static contract analysis of the generated architecture against the analytical use cases before any code is written. [HITL Gate]

### Deferred Phases
- **Phase 2 (Implementation):** Deferred until `project-brief.md` Section 3 is populated by human decision.
- **Phase 3 (Environment Deployment):** Deferred until tech stack is decided.
- **Phase 4 (Validation):** Deferred until implementation triggers it.
- **Phase 5 (Delivery):** Final human review and merge to `main`.

## 8. Universal Standards

### Language Policy
- **Agent system prompts, rules, workflows, skills:** Strictly English.
- **Project documentation & artifacts:** English, except backlog/interview drafts as defined in `project-brief.md`.

### Quality Engineering Foundations
- **Contract-First Constraint:** Code generation is prohibited without an approved upstream specification file.
- **Test Coverage Gates:** 100% unit test coverage required for pure Domain layer; minimum 90% for Application and Infrastructure layers (applicable once implementation begins).
- **Context Preservation:** Agents must actively summarize task history inside `.agents/memory-bank/active-context.md`.
