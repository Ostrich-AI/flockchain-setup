# Component architecture

```mermaid
flowchart TD
  C[Channel and operating system] --> V[Versioned installer]
  V --> R[Review provenance and instructions]
  R --> H[Selected local host]
  H --> N[Installed node software]
```

Conceptual source-oriented view, not a verified deployment diagram. Consult the README code map and configuration catalogue for concrete entrypoints. Provider connections depend on the selected feature and environment.
