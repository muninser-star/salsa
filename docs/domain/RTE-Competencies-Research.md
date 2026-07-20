# RTE (Release Train Engineer) — Исследование компетенций

> **Для задачи:** WBS-002.1 — RTE Agent — Role Identity  
> **Автор:** Denis Opalinskiy  
> **Дата:** 20.07.2026  
> **Контекст:** SALSA Project (Agentic SAFe 6.0 Implementation)

---

## 1. Определение RTE в SAFe 6.0

**Release Train Engineer** — роль на уровне Agile Release Train (ART), отвечающая за:
- Фасилитацию Program Increment (PI) Planning
- Координацию потока ценности через систему команд
- Выявление и разрешение зависимостей между командами
- Мониторинг метрик исполнения (Velocity, CFD, Lead Time)
- Поддержку Lean-Agile принципов и практик

**В контексте SALSA (AI-Native):**
- RTE Agent автоматизирует рутину фасилитации
- Строит Program Board в Mermaid.js
- Генерирует PI Planning артефакты
- Отслеживает зависимости между командами через Git

---

## 2. Ядро компетенций RTE

### 2.1 **SAFe Framework Expertise**
| Компетенция | Уровень | Описание |
|---|---|---|
| SAFe Program Level | 9/10 | Глубокое понимание ART, PI Planning, Relentless Improvement |
| Lean-Agile Values & Principles | 9/10 | Alignment, Working Software, Customer Focus |
| PI Planning Facilitation | 9/10 | Virtual/Hybrid PI Planning, conflicts resolution, dependencies |
| Agile Metrics & Flow | 8/10 | Velocity trends, Cumulative Flow, Lead Time, Throughput |
| Scaled Scrum Master practices | 7/10 | SAFe SM mindset at scale, team synchronization |

### 2.2 **Program Coordination & Orchestration**
| Компетенция | Уровень | Описание |
|---|---|---|
| Dependency Management | 9/10 | Cross-team risk mapping, ARF (Agile Release Framework) |
| Program Board Management | 8/10 | Status tracking, risk lanes, feature mapping |
| PI Execution Monitoring | 8/10 | Burndown analysis, team health checks, velocity tracking |
| Cross-functional Communication | 8/10 | Executive stakeholders, Product Management, Teams |
| Risk & Issue Management | 7/10 | Escalation paths, mitigation strategies |

### 2.3 **AI-Native SDLC Context (SALSA Specific)**
| Компетенция | Уровень | Описание |
|---|---|---|
| Mermaid.js Diagrams | 7/10 | Program Board templates, flow diagrams, C4 models read |
| Git-centric Workflows | 8/10 | PR-driven decisions, branch strategy, history tracing |
| AI Agent Orchestration | 6/10 | Understanding of meta-agent system, role interfaces |
| Markdown Documentation | 7/10 | Artifacts as code, version control for processes |
| Technical Literacy | 6/10 | SDLC phases, deployment pipelines (basic), CI/CD concepts |

### 2.4 **Soft Skills & Leadership**
| Компетенция | Уровень | Описание |
|---|---|---|
| Facilitation & Influence | 9/10 | Without direct authority, consensus building |
| Conflict Resolution | 8/10 | Dependency disputes, capacity conflicts, priority negotiation |
| Coaching & Mentoring | 7/10 | Scrum Masters, Product Managers, Architects |
| Data-Driven Decision Making | 8/10 | Metrics interpretation, trend analysis, forecasting |
| Emotional Intelligence | 7/10 | Team pulse, morale, psychological safety |

### 2.5 **Specific Technical Knowledge (RTE in SALSA)**
| Компетенция | Уровень | Описание |
|---|---|---|
| OKR/KPI Alignment | 8/10 | Linking team objectives to business outcomes |
| Story Pointing & Capacity Planning | 8/10 | Estimation rigor, load balancing, PI capacity calc |
| Value Stream Mapping | 7/10 | End-to-end flow visualization, bottleneck identification |
| Velocity Forecasting | 7/10 | Trend analysis, PI prediction, buffer planning |
| Governance & Compliance | 6/10 | Risk management frameworks, audit trails |

---

## 3. Компетенции по ролям взаимодействия

### Взаимодействие с **Epic Owner**
- Понимание Lean Business Case (LBC) структуры
- Влияние на Solution Intent и Program Vision
- Сценарное планирование (PI vs. Investment Horizon)

### Взаимодействие с **Product Management**
- Backlog prioritization (WSJF, ICE/RICE)
- Feature-to-team allocation
- Acceptance criteria alignment

### Взаимодействие с **System Architect**
- Non-functional requirements (NFR) mapping
- System dependencies understanding
- Architecture compliance checks

### Взаимодействие с **Scrum Masters / Team Leads**
- Team velocity trends
- Impediment escalation
- Capacity forecasting

### Взаимодействие с **DevSecOps / SRE**
- Deployment readiness (Definition of Done)
- Release risk assessment
- Rollback & incident response coordination

---

## 4. Компетенции по фазам PI

### **Phase 1: Pre-PI Planning (неделя 1)**
- Agenda development
- Stakeholder alignment
- Dependency list preparation (from previous PI)
- Team readiness assessment

**Требуемые компетенции:**
- Facilitation (8/10)
- SAFe Program Level (9/10)
- Stakeholder Management (7/10)

### **Phase 2: PI Planning Event (дни 1-2)**
- Kickoff & context setting
- Business context presentation
- Team breakout facilitation
- Conflict resolution (dependencies, capacity)
- Program Board construction

**Требуемые компетенции:**
- Facilitation (9/10)
- Conflict Resolution (8/10)
- PI Planning Expertise (9/10)
- Program Board Management (8/10)
- Communication (8/10)

### **Phase 3: PI Execution (недели 2-13)**
- Weekly standups (at ART level)
- Risk & issue tracking
- Dependency monitoring
- Progress communication
- Velocity trend analysis

**Требуемые компетенции:**
- Agile Metrics (8/10)
- Risk Management (7/10)
- Communication (8/10)
- Data-Driven Decisions (8/10)

### **Phase 4: PI Review & Retrospective (день 14)**
- Demo organization
- Stakeholder feedback collection
- Metrics review (velocity, CFD, lead time)
- Retrospective facilitation
- Improvement stories creation

**Требуемые компетенции:**
- Facilitation (8/10)
- Data Analysis (8/10)
- Coaching (7/10)
- Metrics (8/10)

---

## 5. Компетенции для AI-Native RTE Agent (SALSA)

### **Декодирование системных требований**
- Чтение `.agents/rules/rte.md` (constraints, boundaries)
- Понимание guardrails для RTE Agent

### **Генерация PI Planning артефактов**
- Markdown-based Program Board
- Dependency matrix в Mermaid.js
- Risk lanes visualization
- Feature allocation table

### **Метрики & аналитика**
- Velocity calculation (story points → hours)
- Burndown prediction
- Lead time trends
- Throughput analysis

### **Интеграция с другими агентами**
- Handoff от LPM Agent (Investment Themes)
- Handoff к Analyst Agent (Story generation)
- Input to Architecture Agent (dependencies, NFRs)

### **Human-in-the-Loop Protocol**
- Flagging decisions that need human approval
- Escalation criteria definition
- Conflict presentation format

---

## 6. Модель компетенций (матрица 10x10)

```
Компетенция               | Уровень | Примечание
--------------------------|---------|------------------
1. SAFe Framework         | 9/10    | Must-have; foundation
2. PI Planning            | 9/10    | Must-have; core workflow
3. Facilitation           | 9/10    | Must-have; coordination
4. Dependency Management  | 9/10    | Must-have; risk mitigation
5. Program Board Mgmt     | 8/10    | Critical; artifact ownership
6. Metrics & Analytics    | 8/10    | Critical; data-driven insights
7. Conflict Resolution    | 8/10    | Critical; team sync
8. Communication          | 8/10    | Critical; stakeholder management
9. Mermaid.js (SALSA)     | 7/10    | Important; AI-native context
10. Git-centric Workflows | 8/10    | Important; artifact storage
11. Technical Literacy    | 6/10    | Nice-to-have; SDLC basics
12. OKR Alignment         | 8/10    | Important; business context
```

---

## 7. Взаимодействия с другими ролями (Dependency Map)

```
                    ┌─── Epic Owner Agent
                    │         ↓
            ┌───────┴── RTE Agent ──────┬─────────┐
            │                            │         │
            ↓                            ↓         ↓
      LPM Agent                    Product Mgmt    System Architect
      (Strategic Themes)            (Backlog)      (Solution Intent)
            │                            │         │
            └────────────┬───────────────┴─────────┘
                         ↓
                    Scrum Masters (Teams)
                         │
                         ├─── Analyst Agent
                         ├─── Architect Agent
                         ├─── Programmer Agent
                         └─── QA Agent
```

---

## 8. Риски дефицита компетенций

| Дефицит | Риск | Пример последствия |
|---------|------|-------------------|
| SAFe Knowledge < 7/10 | Неправильная интерпретация принципов | PI Planning игнорирует Lean values |
| Facilitation < 8/10 | Низкое качество координации | Зависимости остаются нерешенными |
| Metrics < 7/10 | Слепота на трендах | Velocity collapse not detected |
| Conflict Resolution < 7/10 | Эскалация вместо решения | Задержки в разрешении конфликтов |
| Mermaid (для SALSA) < 6/10 | Некачественные диаграммы | Program Board нечитаем для агентов |

---

## 9. Путь развития компетенций

### **Новичок (0-3 месяца)**
- SAFe Program Level: 5 → 7
- PI Planning: 4 → 6
- Facilitation: 4 → 6

### **Практик (3-12 месяцев)**
- SAFe Program Level: 7 → 8
- PI Planning: 6 → 8
- Facilitation: 6 → 8
- Dependency Management: 5 → 7

### **Эксперт (1-3 года)**
- SAFe Program Level: 8 → 9
- Все core компетенции: 7-9/10
- Может менторить других

---

## 10. Оценка Denis Opalinskiy против Profile

| Компетенция | Требуемый уровень | Твой текущий | Gap | Примечание |
|---|---|---|---|---|
| SAFe Framework | 9/10 | 8/10 | −1 | Strong SAFe background (Rambler) |
| PI Planning | 9/10 | 8/10 | −1 | Experienced RTE at Rambler |
| Facilitation | 9/10 | 8/10 | −1 | Proven track record (conflict resolution) |
| Metrics & Analytics | 8/10 | 9/10 | +1 | OKR/KPI expertise is advantage |
| Mermaid.js (SALSA) | 7/10 | 4/10 | −3 | Learning required (new tech) |
| Git-centric Workflows | 8/10 | 6/10 | −2 | Some Git exposure, needs deepening |
| AI Agent Orchestration | 6/10 | 5/10 | −1 | Meta-agent context learning needed |

**Общая оценка:** 7/10 (Ready for role with targeted Mermaid & meta-agent ramp-up)

---

## 11. Вывод & Рекомендации

### **Для WBS-002.1 (RTE Agent — Role Identity)**

**Что делать:**
1. Документировать guardrails для RTE Agent (constraints, boundaries)
2. Определить interface к другим агентам (input/output contracts)
3. Выбрать subset компетенций для MVP (e.g., PI Planning + Program Board, hold on Metrics v1)
4. Создать system prompt на основе этого исследования

**Критические компетенции для MVP:**
- ✅ SAFe Program Level (9/10)
- ✅ PI Planning (9/10)
- ✅ Facilitation (9/10)
- ✅ Dependency Management (8/10)
- 🔄 Program Board Management (8/10) — требует Mermaid integration
- 📌 Metrics (defer to Phase 2)

### **Для WBS-002.2 (RTE Agent — Workflow)**

Следует за Role Identity, после human approval на компетенции.

---

## References & Sources

- **SAFe 6.0 official:** Scaled Agile Framework documentation (SAFe RTE role specification)
- **Rambler case:** Denis' Agile Coach experience at Rambler (30-50 person cross-functional teams, RTE coordination)
- **SALSA context:** `.agents/rules/rte.md` (TBD — to be written during WBS-002.1)
- **Previous research:** `.backlog/wbs-002-salsa.md`, `assignment-002.md`
