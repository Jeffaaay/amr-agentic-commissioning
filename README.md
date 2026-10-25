# amr-agentic-commissioning

Paper 2: Agentic Commissioning. Public research workspace; initialized 2026-10-23, baseline published 2026-10-24. No experiment or hardware validation is claimed.

- [Frozen research plan](docs/RESEARCH_PLAN.md)
- [Implementation milestones](docs/MILESTONES.md)
- [Decisions and IP boundaries](docs/DECISIONS.md)
- [Audit status](docs/AUDIT_STATUS.md)
- [Experiment log](docs/EXPERIMENT_LOG.md)

## Baseline source code

Start with [code/](code/README.md): current AMR PCB application source, offline C regressions, source hashes and update instructions. Includes the PD15 telemetry implementation. This is a source/test baseline; paper experiments and hardware acceptance remain pending.

## Structure

- `specifications/`
- `platforms/`
- `braking_tests/`
- `physics_oracle/`
- `sweeps/`
- `experiments/`
- `tests/`

## Execution boundary

Only allowlisted experimental policies may be edited by candidate-generating agents. Evaluators, hidden scenarios, baseline fixtures and safety constraints must be isolated. No live robot credentials, motion or flashing permissions. No safety-limit weakening.

The shared harness lives only in Jeffaaay/amr-faultbench. Exact dependency pins will be recorded before use. Oct 23–24 audit; Oct 25 schema freeze; Oct 26–Nov 1 isolated implementation and separately authorized measurements.

- [Research execution report](docs/RESEARCH_REPORT.md)
- [Prioritized GitHub backlog](docs/ISSUES.md)

Shared harness reference is locked to `d53f635fef1c5c6f021a041062089e1bcd5df7b9` in dependencies.lock.json and experiments/manifest.template.json. It currently contains scaffolding and a draft trace contract, not a runnable experiment harness. Check out exactly that commit; do not copy core. Before running an experiment, fill every provenance/approval field and record this repository's own commit.

- [中文执行顺序与当前边界](docs/EXECUTION_ROADMAP.md)
- [功能基准登记](docs/BASELINE_REGISTER.md)

- [现场测量准备单](braking_tests/FIELD_HANDOFF.md)
- [600 kg 载荷模板](platforms/payload_600kg.yaml) · [1000 kg 载荷模板](platforms/payload_1000kg.yaml)
- [物理约束输入与拒绝条件](docs/PHYSICS_ORACLE_CONTRACT.md)
