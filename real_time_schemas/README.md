# DataGEMS Real-time Profiling Schemas

This directory contains JSON Schema definitions for DataGEMS real-time profiling with extended Croissant profiles.

## Files

### `dg-recordset-rt.schema.json`
JSON Schema for the DataGEMS extended Croissant RecordSet with **real-time profiling** capabilities.

**Canonical URL:** `https://github.com/amy-77/datagem/blob/main/real_time_schemas/dg-recordset-rt.schema.json`

## What it defines (two-layer profile inside RecordSet):

### Layer 1 — Schema (stable): fields/units/keys; pointer to eventTime; versioning on change.

### Layer 2 — Window Summaries & Tiny Models (refreshed every 10 min):
per-variable median/MAD, {p5,p50,p95}, count/min/max/mean/var, missingRate; optional
spatialContext (kNN/region) and short-horizon params (e.g., AR(1): phi/μ/σ_resid).

Timing & observability: dg:time, dg:windowSpec (model/length/slide/lateness), dg:observability.

Detection hooks: dg:detectors, dg:outputs (Anomaly List, Risk Map).

Change/audit: dg:changefeed.

Backward-compatible: Generic/Distribution unchanged; consumers that ignore dg:* still work.
