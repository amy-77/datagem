# DataGEMS Real-time Profiling Examples

This directory contains example instances of DataGEMS real-time profiling with extended Croissant profiles.

## Files

### `measurements_rt.json`
A minimal example of a **real-time profiling** dataset using the DataGEMS extended Croissant profile for streaming measurements.

**Schema:** [`dg-recordset-rt.schema.json`](../real_time_schemas/dg-recordset-rt.schema.json)

This example demonstrates **real-time profiling** features:
- **Streaming window configuration** (`dg:windowSpec`): 15-minute sliding window with 1-minute slides
- **Live window state tracking** (`dg:windowState`): Current row count and watermark
- **Dynamic schema evolution** (`dg:latestSchema`): Latest field definitions
- **Real-time rolling statistics** (`dg:rollingStats`): Min/max, approximate distinct counts, null fractions
- **Live change data capture** (`dg:changefeed`): Kafka-based CDC configuration
- **Interactive query interface** (`dg:queryService`): Arrow Flight query endpoint

## Key Real-time Profiling Features

1. **Streaming Data Windowing**: Shows how real-time streaming data is windowed and tracked
2. **Live Connectivity & Plug-and-play**: Real-time access via changefeed and query service
3. **Dynamic Operational Metadata**: Live window state, real-time statistics, and schema evolution
4. **Standards Compliance**: Extends Croissant RecordSet with `dg:*` namespace for real-time profiling

## Usage in Documentation

These examples can be referenced in technical documentation using:

- **Schema Link**: `https://github.com/datagems-eosc/dataset-profiler/blob/main/schemas/dg-recordset-rt.schema.json`
- **Example Link**: `https://github.com/datagems-eosc/dataset-profiler/blob/main/examples/measurements_rt.json`
