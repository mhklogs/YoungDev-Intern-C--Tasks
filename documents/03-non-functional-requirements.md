# YoungDev-Intern-C--Tasks — Non-Functional Requirements

> **Important.** Performance, availability and security targets below are
> **placeholders**, not measurements. No load test, profiling run, or audit was
> performed. Every value marked `[TO BE MEASURED]` must be replaced with a real
> number before this document is used to make a performance or security claim.

## How to fill these in

1. Run a load test (k6, Artillery, or Locust) against a staging deployment.
2. Profile cold-start and hot-path latency with the framework's own tooling.
3. Record results in the table below alongside the date and commit SHA.

---

## NFR-1 Performance

| ID | Requirement | Target | Status |
| --- | --- | --- | --- |
| NFR-1.1 | Server response time, p95 | `[TO BE MEASURED]` | unmeasured |
| NFR-1.2 | Time to first byte, p95 | `[TO BE MEASURED]` | unmeasured |
| NFR-1.3 | Largest Contentful Paint, p75 | `[TO BE MEASURED]` | unmeasured |
| NFR-1.4 | Cumulative Layout Shift, p75 | `[TO BE MEASURED]` | unmeasured |
| NFR-1.5 | Cold start of a single instance | `[TO BE MEASURED]` | unmeasured |



## NFR-2 Scalability

| ID | Requirement | Target | Status |
| --- | --- | --- | --- |
| NFR-2.1 | Concurrent users supported | `[TO BE MEASURED]` | unmeasured |
| NFR-2.2 | Sustained request rate | `[TO BE MEASURED]` | unmeasured |
| NFR-2.3 | Data volume before degradation | `[TO BE MEASURED]` | unmeasured |

Hosting model: no Vercel configuration detected.
No container definitions detected.

## NFR-3 Availability and reliability

| ID | Requirement | Target | Status |
| --- | --- | --- | --- |
| NFR-3.1 | Uptime | `[TO BE MEASURED]` | unmeasured |
| NFR-3.2 | Recovery time objective | `[TO BE MEASURED]` | unmeasured |
| NFR-3.3 | Recovery point objective | `[TO BE MEASURED]` | unmeasured |
| NFR-3.4 | Database backup cadence | `[TO BE MEASURED]` | unverified |

## NFR-5 Security

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-5.1 | No secrets committed to the repository | verified — a `.gitignore` excluding `.env*` is present |
| NFR-5.2 | Secrets sourced from environment only | not applicable — no env reads detected |
| NFR-5.3 | Dependency vulnerability scan | `[TO BE RUN]` — `npm audit` / `pip-audit` |
| NFR-5.4 | Input validation on all user-supplied data | `[TO BE ASSESSED]` |
| NFR-5.5 | Rate limiting on public endpoints | `[TO BE ASSESSED]` |
| NFR-5.6 | HTTPS and HSTS | `[TO BE ASSESSED]` |
| NFR-5.7 | Personal data handling and retention | `[TO BE DOCUMENTED]` |

## NFR-6 Maintainability

| ID | Requirement | Status |
| --- | --- | --- |
| NFR-6.1 | Automated test coverage on core logic | **no test suite detected** |
| NFR-6.2 | Lint configuration present | [TO BE ASSESSED] |
| NFR-6.3 | Continuous integration on every push | **no CI workflow detected** |
| NFR-6.4 | Type checking enforced | [TO BE ASSESSED] |
