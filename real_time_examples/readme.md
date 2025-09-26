# DataGEMS Real-time Profiling Examples

This directory contains example instances of DataGEMS real-time profiling with extended Croissant profiles.

## Files

### `measurements_rt.json`
A minimal example of a **real-time profiling** dataset using the DataGEMS extended Croissant profile for streaming measurements.

**Schema:** [`dg-recordset-rt.schema.json`](../real_time_schemas/dg-recordset-rt.schema.json)

### What it shows (two-layer profile):

Timing & windowing: dg:time (eventTime, timezone) and dg:windowSpec
(e.g., sliding window: length 60m, slide 10m, optional lateness)

Layer 1 — Schema (stable): dg:schema with fields {name,type,unit?,key?,nullable?}, plus version/changedAt.

Layer 2 — Window summaries (refreshed every update): dg:rollingStats per variable
(median, MAD, {p5,p50,p95}, count/min/max/mean/var, missingRate; optional t-digest metadata).

Detection hooks (optional in minimal): dg:detectors and dg:outputs (Anomaly List, Risk Map).

The example is detection-first and avoids duplicating raw measurements; it only carries metadata needed to interpret current alerts.

## Key Real-time Profiling Features

Two-layer profile: Schema remains stable; summaries/models refresh each 10-minute update.

Detection-ready stats: Robust bands (median/MAD/P5–P95) and classic moments for temporal/spatial/short-horizon checks.

Backward compatible: Pure dg:* namespace extension; Croissant Generic/Distribution unchanged.

Optional add-ons (may appear in full examples):

dg:spatialContext (kNN/region)

dg:forecast (e.g., AR(1) params)

dg:observability (throughput, inter-arrival p95, lastRefresh)

dg:changefeed (audit/drift stream)
