# Editable diagram sources

Conceptual diagrams of the publicly described system. The README uses SVG versions for predictable rendering. Keep these sources and the SVGs aligned.

## Platform architecture

```mermaid
flowchart TB
  T[Hourly telemetry] --> P[Python / PySpark ingestion and transformations]
  A[Airflow scheduling, retries and checkpoints] -.-> P
  A -.-> D[Diagnostic workflows: forecasting, anomalies and RCA]
  P --> E[Elasticsearch: history, aggregations and analytical outputs]
  P --> D
  D --> E
  E --> F[FastAPI protected APIs and integration]
  M[MongoDB: users, rules and metadata] --> F
  F --> U[Flutter: monitoring, investigation and assistant access]
```

Solid arrows show main connections; dashed arrows show orchestration. This groups subsystems rather than documenting deployment topology.

## Data stages

```mermaid
flowchart LR
  T[Hourly telemetry] --> R[Raw] --> C[Cleaned] --> S[Serving]
  A[Airflow: retries and checkpoints] -.-> C
  A -.-> R
```

Python / PySpark processing prepares telemetry for application queries and diagnostic workflows. Storage implementations are omitted from this stage-level view.
