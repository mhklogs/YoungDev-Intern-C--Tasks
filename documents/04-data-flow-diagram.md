
# YoungDev-Intern-C--Tasks — Data Flow Diagram

> Generated from static analysis on 2026-09-28. The diagram shows processes and
> stores that were **positively detected**. Dashed nodes are inferred from a
> dependency and were not traced through the code — verify before relying on them.

## Context diagram (level 0)

```mermaid
flowchart LR
    U["External user<br/>(browser / client)"] -->|"requests"| S["YoungDev-Intern-C--Tasks"]
    S -->|"responses"| U
    S -->|"outbound calls"| X["Third-party services"]
```

## Level-0 decomposition

```mermaid
flowchart TD
    U["External user"] --> P1

    subgraph APP ["YoungDev-Intern-C--Tasks"]
        P1["Presentation layer<br/>0 route module(s), 0 component(s)"]
        P2["Application / API layer<br/>0 handler(s)"]
        P3["Domain logic<br/>business rules"]
        P1 --> P2 --> P3
    end

    P2 --> D1[("Data store 1")]
    P3 --> D2[("Data store 2")]
    P2 -.->|"reads"| EXT["External: none detected"]
```

## Data stores

| Store | Evidence | Status |
| --- | --- | --- |

| *(none detected)* | no database client found in manifests | n/a |

## External integrations

| Integration | Direction | Evidence |
| --- | --- | --- |

| *(none detected)* | — | no outbound client library found |

## Data classification

| Data class | Present | Notes |
| --- | --- | --- |
| Public content | unclear | served pages |
| User account data | not detected | no auth library detected — confirm whether accounts exist |
| Personal / sensitive data | `[TO BE CLASSIFIED]` | cannot be determined statically |
| Credentials / secrets | yes, by design | environment variables only, never in source |
| Payment data | not detected | |
