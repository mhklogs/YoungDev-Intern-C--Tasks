# YoungDev-Intern-C--Tasks — SDLC Lifecycle

> The lifecycle below describes how this build is produced and maintained, and maps
> each software-engineering artifact in `documents/` to its lifecycle phase.

## 1. Methodology

**Iterative, artifact-driven development** with lightweight Milestone gates. The
lifecycle combines an explicit Analysis / Design / Implement / Test / Release /
Operate structure (traceable in this documentation set) with the reality that
portfolio builds ship iteratively. No heavyweight process is imposed — phases are
lightweight, and quality gates are automation wherever the stack supports it.

For this repo the lifecycle is grounded in what the code actually is:

> YoungDev — a C++ internship coursework archive.

## 2. Phases

| Phase | Activities | Artifacts in this repo |
| --- | --- | --- |
| **1. Discovery** | Problem framing, stakeholder/user intent, market sanity-check | `documents/01-market-analysis.md` |
| **2. Requirements** | Functional + non-functional requirements from the implemented scope | `documents/02-functional-requirements.md` · `documents/03-non-functional-requirements.md` |
| **3. Design** | Context + level-0 data flow; architecture and integration decisions | `documents/04-data-flow-diagram.md` · `documents/06-architecture.md` |
| **4. Implement** | Source changes against the design; incrementally committed to git | Source tree + commit history |
| **5. Verify** | Compile/lint/tests (where present); manual smoke test of user-facing flows | Test config in repo; `05-use-cases.md` as the walkthrough script |
| **6. Release & operate** | Build, sign (where applicable), deploy or publish; monitor + maintain | Release artifacts / deployment config |
| **7. Improve** | Feedback loop: re-run Discovery with new evidence, update requirements | Next lifecycle iteration |

## 3. Requirements traceability

Requirement identifiers in `02-functional-requirements.md` and `03-non-functional-requirements.md`
map directly to implemented use cases in `05-use-cases.md`. A change that touches a behavior
should update the corresponding FR/NFR and the DFD in the same commit — documentation and
code are kept in lockstep rather than generated separately.

## 4. Quality gates

- **Static:** build and lint pass on the committed source; release builds are verified
  (signed artifacts checked with `apksigner` for Android, `npm run build`/typecheck for web).
- **Functional:** user-facing flows follow `05-use-cases.md`; smoke-testing covers the
  primary journey end to end.
- **Non-functional targets:** NFRs marked `[TO BE MEASURED]` in `03-non-functional-requirements.md`
  are not yet instrumented — they are goals, not achieved guarantees.

## 5. Release policy

- **Commit discipline.** Every change is a single, reviewable commit with a message
  describing the behavior, not the diff.
- **Tagging.** Releases are tagged in git and, for deliverables, the built artifact
  (signed APK / deployed URL) is recorded in the README.
- **Health.** A broken build blocks the next feature commit. Security findings are
  treated as release blockers, not backlog items.

## 6. Contributing / reproducing

1. Use the documented stack in `06-architecture.md` to reproduce the build.
2. Follow the phase order: update requirements and design before implementation.
3. Run the verification gate for the platform before opening a change.
4. Document any material misstatement you find and fix it in the same change.

## 7. Risks to the lifecycle

| Risk | Mitigation |
| --- | --- |
| Requirements drift vs. implemented code | Traceability check in every change |
| Unmeasured NFRs treated as done | `[TO BE MEASURED]` stays visible until instrumented |
| Repo/branch divergence in multi-repo work | Single canonical repo per product; renames over deletes |
