# Infrastructure Monitoring and Analytics Platform

Documentation-only case study for a mobile-first internal monitoring and diagnostics platform built for operational infrastructure teams.

> Proprietary code and internal data are not included. This repository summarizes architecture, ownership, system design, and sanitized implementation details.

## Summary

I owned and delivered an internal software product that unified infrastructure telemetry, KPI dashboards, alarm workflows, forecasting, anomaly detection, root-cause analysis, and AI-assisted investigation into one operator-facing system.

The work is best understood as a software systems and operational analytics platform, not as a telecom-only dashboard. The transferable engineering value is in backend services, data pipelines, analytics serving, monitoring workflows, and productized diagnostic tooling.

## Confirmed Scale

- 1,500+ distributed infrastructure endpoints
- 60+ operational KPIs
- Millions of records processed per day
- 50+ internal users
- More than 96% measured pipeline success rate in one variant
- More than 70% reduction in manual troubleshooting effort
- More than 40% MTTR reduction

## Architecture

```mermaid
flowchart LR
  A["Infrastructure telemetry"] --> B["PySpark ingestion and cleaning"]
  B --> C["Airflow orchestration"]
  C --> D["Elasticsearch serving layer"]
  C --> E["MongoDB application layer"]
  D --> F["FastAPI backend and API gateway"]
  E --> F
  F --> G["Flutter mobile client"]
  F --> H["Forecasting, anomaly, RCA, and assistant workflows"]
```

## Core Subsystems

- Mobile-first Flutter client for operational users
- FastAPI backend and API gateway
- MongoDB application layer
- Elasticsearch analytics and serving layer
- PySpark processing jobs
- Airflow orchestration, scheduling, checkpointing, and recovery
- KPI dashboards, site/cell views, alarms, and investigation flows
- Forecasting and anomaly detection outputs connected to operator workflows
- Root-cause analysis summaries and ranked probable causes

## Engineering Ownership

I owned the platform end to end:

- ingestion pipeline design
- Spark/Airflow processing
- Elasticsearch indexing and query patterns
- backend API design
- dashboard and mobile workflow integration
- forecasting and anomaly workflow integration
- RCA and assistant workflow integration
- delivery of the final internal product

## Recruiter Signal

This project demonstrates production-oriented software systems work across backend services, data pipelines, mobile product delivery, operational analytics, and reliability-focused internal tooling.

## Tech Stack

Flutter, FastAPI, Python, PySpark, Airflow, Elasticsearch, MongoDB, time-series processing, anomaly detection, forecasting, RCA workflows.
