<p align="center">
  <img width="800" alt="traceproof-logo-removebg-preview" src="https://github.com/user-attachments/assets/3ee49a37-3ef1-4f36-bc6b-17f974bcb1a2" />
  <h3 align="center">The AI-Assisted Formal Verification Framework</h3>
</p>

---

**TraceProof** is an agentic framework we are building to explore **automated formal specification (TLA+)**, **model-code verification**, and **bug reproduction** in concurrent software systems, targeting issues such as **race conditions, deadlocks, and atomicity violations**. We are initially targeting **C++** concurrent code.

Writing formal specifications by hand requires significant time and expertise, while asking LLMs to generate specifications directly from large codebases often leads to context overload and inaccurate models. **Our goal with TraceProof** is to combine **formal methods** and **multi-agent workflows** to make formal verification more practical and accessible for real-world concurrent code.

## Project Goals

TraceProof aims to:

* **Analyze & Slice Concurrent Codebases**: Use static analysis to map concurrent components, shared state, and synchronization boundaries, then extract focused code slices for specific verification scenarios.
* **Mine Evidence-Backed Invariants**: Extract candidate safety properties from source code, documentation, design specs, and repository history, rather than relying on code alone.
* **Synthesize Focused TLA+ Models**: Draft modular, checkable **TLA+** specifications linked back to the original source lines.
* **Verify Models**: Use the **TLC Model Checker** to explore concurrent thread interleavings and find invariant violations. We are also exploring the **TLA+ Proof System (TLAPS)** to help localize violations to specific actions.
* **Critique & Filter Candidate Bugs**: Use an **Adversarial Critic Agent** to review counterexamples, check whether the model faithfully represents the code, and reduce false alarms.
* **Assist in Bug Reproduction**: Map counterexample traces back to source code to help build multi-threaded tests that reproduce the issue.

## Technology Stack

* **Formal Methods:** TLA+, TLC Model Checker (exploring TLAPS)
* **Code Analysis:** Tree-sitter static analysis, program slicing, Git history analysis
* **AI & Agents:** Pydantic AI, Claude, Gemini, Model Context Protocol (MCP)

## Project Status

**Work in Progress**

We have built early prototypes for C++ concurrency analysis and code slicing, and are currently developing **Repository & Evidence Analysis** (Stage 1) and **Invariant Mining, Slicing & TLA+ Generation** (Stage 2).

## Team, Supervision & Mentorship

**Team**  
Youssef Hassan · Ahmed Sayed · Fares Ahmed · Andrew Wafae · Adham Hamdy

**Academic Supervision**  
Dr. Mohamed El-Ramly · Dr. Desoky Abdelqawy

**Technical Support & Mentorship**  
MongoDB

**Institution**  
Faculty of Computers and Artificial Intelligence, Cairo University  
*Academic Year 2026-2027*
