# Trace Proof

**Trace Proof** is an agentic system for the maintenance phase of the Software Development Life Cycle (SDLC).

It aims to verify whether running production systems still behave according to their intended specifications by combining **formal methods**, **observability data**, and **AI agents**.

## What It Does

Trace Proof:

* Recovers formal specifications from available source code, documentation, and system logs.
* Uses **TLA+ / PlusCal** to model and validate system behavior.
* Maps abstract specification variables to concrete observability data.
* Checks observed behavior against the approved specification.
* Detects conformance violations and explains potential issues.
* Generates human-readable tickets for detected violations.

## Architecture

The system is built around several cooperating components:

* **Spec Assistant** — drafts formal specifications.
* **Linting & Validation** — checks specifications before approval.
* **Engineer Sign-off** — provides a human verification checkpoint.
* **Trace Mapper** — maps system observability data to specification variables.
* **Conformance Checker** — validates observed behavior against the specification.
* **Ticket Agent** — generates actionable tickets for violations.

## Technology

Planned technologies include:

* TLA+ / PlusCal
* TLC Model Checker
* LLM-based agents
* LangGraph
* OpenTelemetry
* Jira API

## Project Status

 **Under Development**

This Org contains the ongoing development of **Trace Proof**.

---

### Team

**Deadliners**
Faculty of Computers and Artificial Intelligence
Cairo University
Academic Year 2026–2027

**Under the supervision of Dr. Mohamed El-Ramly**
