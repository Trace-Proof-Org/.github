# TraceProof

**TraceProof** is an autonomous agentic system for formal specification, model-code conformance verification, and deterministic bug reproduction in concurrent and distributed systems.

By bridging the gap between **formal methods (TLA+ / TLC)**, **runtime execution traces**, and **multi-agent AI systems**, TraceProof eliminates the prohibitive cost of hand-crafting formal specifications and delivers physically verified, reproducible bug diagnostics with zero false alarms.

---

## What It Does

TraceProof:

* **Mines Evidence-Backed Invariants**: Performs semantic AST analysis over source code, documentation, and repository history to extract protocol and code-level safety properties.
* **Synthesizes Formal Models**: Autonomously drafts checkable, modular **TLA+** specifications with an automated syntax self-repair gate.
* **Guarantees Model-Code Conformance**: Uses **Trace Validation** (`tla-mcp replay_scenario`) to prove that the formal specification faithfully admits real runtime execution paths before model checking begins.
* **Exhaustively Explores State Spaces**: Uses the **TLC Model Checker** to explore all possible concurrent thread interleavings and surface deep race conditions, deadlocks, and consistency violations.
* **Adversarially Audits Counterexamples**: Employs an independent **Adversarial Critic Agent** to red-team discovered counterexamples—auditing invariant soundness, model fidelity, and OS thread feasibility to filter out AI hallucinations.
* **Deterministically Reproduces Bugs**: Automatically compiles and executes synchronized Python test harnesses against the live codebase, forcing the exact failure schedule to catch physical errors (`AssertionError`) and file actionable issues.

---

## Multi-Agent Architecture

TraceProof is organized around **six specialized cooperating agents** sharing a unified verification knowledge base, with optional, selective human steering:

```
Source Code & Docs 
       │
       ▼
1. Repository Analysis Agent        ── Scopes dependencies, modules & change-impact
       │
       ▼
2. Invariant Mining Agent           ── Extracts evidence-backed safety invariants (AST & history)
       │
       ▼
3. Scenario & Model Planning Agent  ── Synthesizes TLA+ specs with optional engineer scenario guidance
       │
       ▼
4. Formal Verification Agent        ── Performs Trace Validation & TLC Model Checking via tla-mcp
       │
       ▼
5. Adversarial Agent (Critic)       ── Red-teams counterexamples to eliminate false alarms
       │
       ▼
6. Bug Confirmation Agent           ── Deterministically reproduces bugs on live runtime threads & files reports
```

1. **Repository Analysis Agent** — Maps project structure, call graphs, and historical change-impact to enable incremental, scoped verification.
2. **Invariant Mining Agent** — Discovers candidate invariants backed by code citations, commit evidence, and confidence metrics.
3. **Scenario & Model Planning Agent** — Scopes verification around critical concurrency paths, incorporating optional engineer steering (e.g., guided failure scenarios).
4. **Formal Verification Agent** — Drives the `tla-mcp` MCP server to perform trace validation (model-code conformance) and exhaustive TLC model checking.
5. **Adversarial Agent (Critic)** — Challenges candidate bugs as a skeptic, evaluating whether the counterexample is physically realizable or an artifact of model over-simplification.
6. **Bug Confirmation Agent** — Synthesizes deterministic replay harnesses (using barriers and controlled delays) to prove the bug on live runtime code and generate diagnostic reports.

---

## Technology Stack

* **Formal Methods**: TLA+, TLC Model Checker (via the `tla-rs` / `tla-mcp` Model Context Protocol server).
* **AI & Multi-Agent Coordination**: Claude (Anthropic), Gemini, Model Context Protocol (MCP).
* **Code Understanding**: Tree-sitter, Python AST static analyzers, GitHub REST/GraphQL APIs.
* **Runtime Verification & Testing**: Dynamic runtime tracing, `threading.Barrier` synchronization, Subprocess execution sandboxing.
* **Developer Interfaces**: Streamlit (Dashboard for scenario steering and verification analysis), Jira API & GitHub Issues (Automated ticket generation).

---

## Project Status

**Active Development / Proof of Concept Verified**

The core pipeline has been demonstrated end-to-end, discovering and deterministically reproducing complex concurrency anomalies (such as distributed leased lock lease expiration races) on live codebases.

---

### Team

**Deadliners**  
Faculty of Computers and Artificial Intelligence  
Cairo University  
Academic Year 2026–2027  

**Under the supervision of: Dr. Mohamed El-Ramly**
