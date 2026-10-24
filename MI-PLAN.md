# Mi plan de estudio — AI Engineering from Scratch

Plan personal sobre el curso. Lo mantiene Claude a pedido; los casilleros los tildás vos (o `/learn`,
que anota en `LEARNING.md`). Lecciones en inglés: el repo tiene 528 lecciones y ninguna traducida al
español. `/learn` las enseña en el idioma en que le hables.

## 1. Cómo está armado el curso (el mapa mental en tres frases)

1. **El catálogo** (`/catalog`, carpeta `phases/`) es el inventario completo: 528 lecciones en 20 fases
   apiladas, de álgebra lineal (fase 1) a agentes en producción (fase 17). Es un edificio de 20 pisos,
   no una lista para leer de punta a punta. Cada lección es una carpeta con `docs/en.md` (el texto),
   `code/` (lo que se corre) y `quiz.json` (el examen de salida).
2. **Los learning paths** (`/learning-paths`, carpeta `learning-paths/*.json`) son **recorridos
   curados** que cruzan el edificio tomando 8 a 17 lecciones puntuales de distintas fases. Hay cuatro
   troncales (fundamentos de software, construir y desplegar apps de IA, trabajar con agentes de
   código, criterio de producto), seis rutas de carrera (agentes, datos, evaluación, producto LLM,
   despliegue a cliente, developer relations) y dos focalizados (MCP y Agent Skills).
3. **Lo demás es periférico para vos**: 80 proyectos con corrector automático (`projects/`),
   certificaciones Claude/MCPA (`certifications/`), y los skills de tutor (`skills/`, ya instalados en
   esta sesión como `/learn`, `/course-guide`, `/check-understanding`).

La confusión viene de que el sitio muestra las tres capas con el mismo peso. La regla: **se elige UN
recorrido y se lo sigue en su orden**; el catálogo se usa solo como diccionario cuando algo no cierra.

## 2. Qué te sirve a vos (y qué no)

Supuestos (sin preguntar, corregilos si no aplican): sos PM, construís AcaQuant con Claude Code todos
los días, tenés un agente LangGraph y servidores MCP en producción, aprendés técnica a través de
Claude, y disponés de ~5 h por semana.

| Fase | Qué es | Para vos |
|---|---|---|
| 0 Setup · 1 Math · 2 ML · 3 Deep Learning | fundamentos matemáticos y de ML clásico | **Saltear.** No construís modelos. |
| 4 Visión · 5 NLP · 6 Audio · 7 Transformers · 8 GenAI · 9 RL · 10 LLMs from scratch · 12 Multimodal | cómo se entrena un modelo por dentro | **Saltear.** Consumís modelos por API. |
| **11 LLM Engineering** | prompts, structured outputs, RAG, evaluación, costo, guardrails | **Sí, en parte** (lo que el agente de AcaQuant ya hace). |
| **13 Tools & Protocols** | tool interface, schemas, **MCP**, Agent Skills | **Sí, en parte** (tenés `/mcp` y `/mcp-lab` en prod). |
| **14 Agent Engineering** | el loop del agente, LangGraph, fallas, inyección, evals, **trabajar con agentes de código**, **criterio de producto** | **El núcleo.** 54 lecciones; las 24 últimas son literalmente tu día a día. |
| 15 Autónomos · 16 Multi-agente · 18 Ética · 19 Capstones | sistemas autónomos y swarms | Después, si alguna vez hace falta. |
| 17 Infra & Producción | observabilidad, canary, SRE para IA | Solo 3 lecciones puntuales, dentro de un recorrido. |

## 3. El plan: cuatro etapas, ~38 h el núcleo

Orden pensado para que lo primero que estudiés sea lo que ya usás (y que cada lección te cambie algo
en AcaQuant esa misma semana). Cada ítem tiene el comando para la sesión de estudio: se corre en
este repo, Claude lee la lección local y la enseña interactiva. `Web` abre la misma lección en el sitio.

### Etapa 1 — Trabajar con agentes de código (recorrido «Agent-Assisted Engineering») · 15 h · ~3 semanas

Es la teoría de lo que ya hacés con Claude Code: `CLAUDE.md`, reglas, sub-agentes revisores, hooks de
push, handoff entre sesiones. Vas a reconocer tu propio repo en cada lección y a encontrar lo que te
falta.

| | min | Lección | Comando |
|---|---|---|---|
| [ ] | 45 | Why Capable Models Still Fail | `/learn phases/14-agent-engineering/31-agent-workbench-why-models-fail` |
| [ ] | 45 | The Minimal Agent Workbench | `/learn phases/14-agent-engineering/32-minimal-agent-workbench` |
| [ ] | 50 | Instructions as Executable Constraints (tu `CLAUDE.md`) | `/learn phases/14-agent-engineering/33-instructions-as-executable-constraints` |
| [ ] | 60 | Repo Memory and Durable State | `/learn phases/14-agent-engineering/34-repo-memory-and-state` |
| [ ] | 45 | Initialization Scripts for Agents | `/learn phases/14-agent-engineering/35-initialization-scripts` |
| [ ] | 50 | Scope Contracts and Task Boundaries | `/learn phases/14-agent-engineering/36-scope-contracts` |
| [ ] | 60 | Frame the Task Before the Agent Writes Code | `/learn phases/14-agent-engineering/43-frame-the-task-before-code` |
| [ ] | 65 | Build an Evidence-Backed Execution Plan (tu REGLA #2) | `/learn phases/14-agent-engineering/44-plan-from-evidence` |
| [ ] | 50 | Runtime Feedback Loops | `/learn phases/14-agent-engineering/37-runtime-feedback-loops` |
| [ ] | 55 | Verification Gates (tu `pre-deploy-check`) | `/learn phases/14-agent-engineering/38-verification-gates` |
| [ ] | 55 | Reviewer Agent: Separate Builder from Marker (tu `revisor`) | `/learn phases/14-agent-engineering/39-reviewer-agent` |
| [ ] | 70 | Delegate Agent Work with Isolation (tu regla `fable-orquesta`) | `/learn phases/14-agent-engineering/45-delegate-with-isolation` |
| [ ] | 50 | Multi-Session Handoff | `/learn phases/14-agent-engineering/40-multi-session-handoff` |
| [ ] | 60 | The Workbench on a Real Repo | `/learn phases/14-agent-engineering/41-workbench-for-real-repos` |
| [ ] | 65 | Turn Every Agent Correction into a System Improvement | `/learn phases/14-agent-engineering/46-turn-feedback-into-system` |
| [ ] | 75 | Capstone: Ship a Reusable Agent Workbench Pack | `/learn phases/14-agent-engineering/42-agent-workbench-capstone` |

Web: https://aiengineeringfromscratch.com/lesson?path=phases/14-agent-engineering/31-agent-workbench-why-models-fail&learningPath=using-coding-agents
Cierre de etapa: `/check-understanding 14` (8 preguntas, te dice qué repasar).

### Etapa 2 — Criterio de producto (recorrido «Product Judgment and Delivery») · 9 h · ~2 semanas

Es tu rol de PM aplicado a features con IA: outcome antes que output, el supuesto más riesgoso
primero, el corte más chico que cambia la decisión, métricas antes del resultado, prototipo vs piloto
vs producción. Corto y de alto retorno.

| | min | Lección | Comando |
|---|---|---|---|
| [ ] | 60 | Define the Outcome Before You Choose the Output | `/learn phases/14-agent-engineering/47-outcomes-before-output` |
| [ ] | 70 | Discover the Workflow People Actually Perform | `/learn phases/14-agent-engineering/48-discover-the-real-workflow` |
| [ ] | 65 | Map Assumptions and Resolve the Riskiest One First | `/learn phases/14-agent-engineering/49-map-assumptions-and-risk` |
| [ ] | 65 | Choose the Smallest Slice That Can Change the Decision | `/learn phases/14-agent-engineering/50-choose-the-smallest-testable-slice` |
| [ ] | 75 | Write Specifications That Preserve Judgment | `/learn phases/14-agent-engineering/51-write-specifications-that-preserve-judgment` |
| [ ] | 70 | Design Success Metrics Before the Result Exists | `/learn phases/14-agent-engineering/52-design-success-metrics` |
| [ ] | 70 | Choose Prototype, Pilot, or Production Deliberately | `/learn phases/14-agent-engineering/53-prototype-pilot-or-production` |
| [ ] | 75 | Build a Feedback Ratchet with Ownership and Retirement | `/learn phases/14-agent-engineering/54-build-the-feedback-ratchet` |

Web: https://aiengineeringfromscratch.com/lesson?path=phases/14-agent-engineering/47-outcomes-before-output&learningPath=shaping-the-build

### Etapa 3 — Cómo funciona tu agente por dentro (ruta «Agent Systems Engineering») · 14 h · ~3 semanas

La ruta de carrera que describe el AV AGENT: tool interface, schemas, MCP básico, el loop
observar-pensar-actuar, contexto y memoria, **LangGraph con checkpoints**, patrones de orquestación,
modos de falla, inyección de prompt, desarrollo guiado por evals, runtimes (cola/evento/cron) y
observabilidad. Al terminar vas a poder leer `agente/grafo/` y discutir diseño con fundamento.

| | min | Lección | Comando |
|---|---|---|---|
| [ ] | 45 | The Tool Interface — Why Agents Need Structured I/O | `/learn phases/13-tools-and-protocols/01-the-tool-interface` |
| [ ] | 45 | Tool Schema Design | `/learn phases/13-tools-and-protocols/05-tool-schema-design` |
| [ ] | 55 | MCP Fundamentals: Stateless Requests and JSON-RPC | `/learn phases/13-tools-and-protocols/06-mcp-fundamentals` |
| [ ] | 60 | The Agent Loop: Observe, Think, Act | `/learn phases/14-agent-engineering/01-the-agent-loop` |
| [ ] | 60 | Tool Use and Function Calling | `/learn phases/14-agent-engineering/06-tool-use-and-function-calling` |
| [ ] | 90 | Context Engineering: Windows, Budgets, Memory, and Retrieval | `/learn phases/11-llm-engineering/05-context-engineering` |
| [ ] | 75 | Agent Memory — Virtual Context and Memory Paging | `/learn phases/14-agent-engineering/07-memory-virtual-context-memgpt` |
| [ ] | 75 | Stateful Graph Orchestration (LangGraph, checkpoints) | `/learn phases/14-agent-engineering/13-langgraph-stateful-graphs` |
| [ ] | 60 | Orchestration Patterns: Supervisor, Swarm, Hierarchical | `/learn phases/14-agent-engineering/28-orchestration-patterns` |
| [ ] | 60 | Failure Modes: Why Agents Break | `/learn phases/14-agent-engineering/26-failure-modes-agentic` |
| [ ] | 75 | Prompt Injection and the PVE Defense | `/learn phases/14-agent-engineering/27-prompt-injection-defense` |
| [ ] | 60 | Eval-Driven Agent Development (tu carpeta `evals/`) | `/learn phases/14-agent-engineering/30-eval-driven-agent-development` |
| [ ] | 60 | Production Runtimes: Queue, Event, Cron (tu `agente-worker` y crontab) | `/learn phases/14-agent-engineering/29-production-runtimes` |
| [ ] | 45 | Agent Observability: Langfuse, Phoenix, Opik | `/learn phases/14-agent-engineering/24-agent-observability-platforms` |

Web: https://aiengineeringfromscratch.com/learning-paths.html#career-route-agentic-ai-engineer
Cierre de etapa: `/check-understanding 13` y `/check-understanding 14`.

### Etapa 4 — Según lo que te pida AcaQuant (elegir UNA, no las dos)

**4a. MCP en serio** (recorrido «Model Context Protocol», 17 lecciones, 23 h; tutor propio
`/learn-mcp`, lleva su propio `MCP-LEARNING.md`). Solo si vas a abrir `/mcp` a terceros o a
cobrarlo: la mitad del recorrido es autorización OAuth, gateways, registries y conformance. Para el
uso interno actual, con las 3 lecciones de MCP de la etapa 3 alcanza. Las que más te tocan si lo
hacés: `07-building-an-mcp-server`, `09-mcp-transports`, `15-mcp-security-tool-poisoning`,
`16-mcp-security-oauth-2-1`, `28-mcp-tool-contracts-and-content`.

**4b. Apps de IA en producción** (recorrido «Building and Deploying AI Applications», 12 lecciones,
13 h). Lo que le falta al Quant y al briefing: structured outputs, RAG y evaluación con casos
versionados, caching y costo, guardrails, observabilidad, canary. Si el próximo trimestre es «hacer
el research con IA confiable», es esta.

## 4. La rutina de una lección (60 a 90 minutos, una por sesión)

1. **Abrir** este repo en Claude Code y correr el comando de la fila. `/learn` hace repaso de la
   anterior, enseña por secciones, te hace escribir y correr, y cierra con el quiz.
2. **Correr el código de la lección** desde la raíz del repo (`python3 phases/.../code/x.py`): el
   output es la evidencia. Nunca saltear este paso: leer sin correr es la forma de creer que se entendió.
3. **Una frase propia** al terminar: «esto en AcaQuant es ___». Si no podés completarla, la lección no
   cerró; se vuelve a la sección que faltó.
4. **Un cambio concreto** en AcaQuant por semana, salido de lo estudiado (una regla, un test, un eval,
   un hook). Es la única métrica que importa; las lecciones tildadas no.
5. Tildar el casillero acá y commitear.

Herramientas de apoyo:
- Trabado en un tema o un bug: `/course-guide <tema>` apunta a la lección exacta.
- Glosario de términos: `glossary/terms.md`.
- Una sola vez, para que `/learn` tenga dónde anotar: `/start-learning` y decirle «empezame en la
  fase 14» (saltea el quiz de ubicación; crea `LEARNING.md`, que no reemplaza este plan).

## 5. Qué NO hacer

- No leer el catálogo entero ni «empezar por la fase 0 para estar seguro»: son 306 h y el 80 % no te
  sirve.
- No hacer dos recorridos a la vez ni mezclar `/learn`, `/learn-mcp` y `/claude-certification`: cada
  uno lleva su archivo de estado y se pisan en la cabeza, no en el disco.
- No arrancar un proyecto de `projects/` antes de terminar la etapa 1. Si querés uno después, el que
  más se parece a tu trabajo es `projects/research-report-agent` (con `/build-project`).
- No tildar sin haber corrido el código.

## 6. Progreso

| Semana | Etapa | Lecciones hechas | Cambio aplicado en AcaQuant |
|---|---|---|---|
| | | | |
