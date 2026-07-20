# Краткое описание проекта: SALSA

## 1. Суть проекта и ценностное предложение
- **Имя продукта:** SALSA (Scaled Agentic Lean Secure Agile)
- **Видение продукта:** Open-source реализация ядра SAFe Agentic Operating System (SAFe AOS). Расширение Framework-as-Code для SAFe 6.0, которое трансформирует методологию из статической документации в активную, AI-native операционную систему, используя Git (Markdown + Mermaid.js) как единый источник истины.
- **Целевая аудитория:**
  - Руководство компаний (C-level), руководство портфеля
  - Lean Portfolio Management (LPM), Epic Owner
  - Release Train Engineers (RTE), Product Management, System Architects
  - Agile-команды, SPC, DevSecOps, SRE, AppSec инженеры
- **Ключевой метрик успеха:** Радикальное сокращение Time-to-Market на 60–80%, устранение задержек передачи, автоматическая готовность бэклога, встроенное качество, снижение накладных расходов.

### Scope MVP
- Open Source ядро: meta-agent prompts, библиотека skill'ов по ролям, templates визуализации Mermaid.js для Portfolio & Solution Intent.
- End-to-end приватная демонстрация: один гипотетический Epic, проходящий от Lean Business Case через AI-Native SDLC к автоматизированному релизу.

### Явно не входит в scope
- Не замена SAFe; это набор инструментов для SPC, который дополняет методологию.
- Полный enterprise UI/dashboard слой — это амбиция, а не часть MVP.

## 2. Политика языка и документирования
- **System prompts агентов, правила, workflows, skills:** только английский.
- **Документация проекта, архитектура, спеки:** только английский.
- **Комментарии в коде, логи, сообщения об ошибках:** только английский.
- **Git commit messages:** английский, Conventional Commits.
- **Entries в бэклоге / task tracker:** допускается русский и английский.
- **Черновики переходного этапа / интервью notes:** русский разрешён только в `.backlog/` и `docs/domain/*Interview*.md`.

## 3. Глобальные ограничения технического стека
- **Текущая фаза:** только Markdown анализ и архитектура.
- **Backend:** TBD — будет решено перед фазой имплементации.
- **Frontend:** TBD — будет решено перед фазой имплементации.
- **Database:** TBD — будет решено перед фазой имплементации.
- **Message broker / event streaming:** TBD — будет решено перед фазой имплементации.
- **Monorepo / multi-repo:** сохранить текущую структуру monorepo.

## 4. Высокоуровневые границы домена (DDD контексты)
1. **Portfolio Management** — стратегические темы, горизонты инвестиций, Lean Business Case, WSJF, workflow Epic Owner.
2. **Lean Portfolio Orchestration** — мониторинг LPM, guardrails бюджета, выравнивание соответствия требованиям.
3. **ART / Program Coordination** — PI Planning, Program Board (Mermaid.js), зависимости, workflow RTE.
4. **Solution Intent & Architecture** — Solution Architect, системные спецификации, соответствие архитектуре.
5. **AI-Native Team SDLC** — анализ, архитектура, имплементация, QA, развёртывание.
6. **Meta-Agent Governance** — генерация правил/workflows/skills, аудит соответствия, валидация PR.
7. **Quality & Security gating** — встроенное качество, AppSec сканы, threat modeling, enforcement политик.
8. **Backlog Bus** — кросс-агентная передача задач через `.backlog/`.
9. **Mermaid Visualization Library** — AI-readable/generatable диаграммы для уровней Portfolio, Solution, Program, Team.

## 5. Спецификации операционной среды
- **Локальный dev sandbox engine:** TBD.
- **Целевая облачная инфраструктура:** TBD.
- **AI runtime стратегия:** модель-агностична и deployment-агностична. Участники могут использовать свой собственный локальный AI runtime (напр., VS Code + OpenCode + OpenRouter/Kimi). Корпорация, развертывающая агентскую рабочую силу, будет использовать свой собственный защищённый контур.
