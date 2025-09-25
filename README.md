# DataGEMS Real-time Profiling

A comprehensive real-time data profiling framework with extended Croissant profile support for streaming datasets.

## 🏗️ Project Architecture

```
dataset-profiler/
├── real_time_schemas/
│   ├── README.md
│   └── dg-recordset-rt.schema.json     # JSON Schema (validation)
└── real_time_examples/
    ├── README.md
    └── measurements_rt.json            # Example dataset (demonstration)
```

## 📋 Overview

This project provides **real-time profiling** capabilities for streaming datasets using an extended Croissant profile format. The framework enables:

- **Streaming window management** with configurable sliding windows
- **Live connectivity** through changefeed and query service integration
- **Real-time observability** with dynamic metrics and monitoring
- **Dynamic data quality** rules and governance

## 🔧 Core Components

### 📊 JSON Schema (`real_time_schemas/`)

The normative schema is available at **[real_time_schemas/dg-recordset-rt.schema.json](real_time_schemas/dg-recordset-rt.schema.json)**; see the [schemas documentation](real_time_schemas/README.md) for details and examples.

**Key Features:**
- **Schema ID**: `https://amy-77.github.io/datagem/real_time_schemas/dg-recordset-rt.schema.json`
- **Profile Version**: Supports versioned real-time profiling capabilities
- **Namespace**: Extends Croissant RecordSet with `dg:*` properties
- **Validation**: Comprehensive JSON Schema for real-time profiling metadata

### 📈 Example Datasets (`real_time_examples/`)

The extended Croissant profile output conforms to **[dg-recordset-rt.schema.json](real_time_schemas/dg-recordset-rt.schema.json)**.

**Sample Dataset:**
- **[measurements_rt.json](real_time_examples/measurements_rt.json)**: Real-time measurements with 15-minute sliding windows
- **Schema Compliance**: Validates against the normative schema
- **Live Features**: Demonstrates changefeed, query service, and rolling statistics

## 🚀 Real-time Profiling Features

### Streaming Data Management
- **Window Specification** (`dg:windowSpec`): Configurable sliding/tumbling windows
- **Window State Tracking** (`dg:windowState`): Live row counts and watermarks
- **Schema Evolution** (`dg:latestSchema`): Dynamic field definitions

### Live Connectivity & Plug-and-play
- **Change Data Capture** (`dg:changefeed`): Kafka-based streaming integration
- **Query Service** (`dg:queryService`): Arrow Flight real-time query interface

### Operational Observability
- **Rolling Statistics** (`dg:rollingStats`): Min/max, distinct counts, null fractions
- **Metrics & Monitoring** (`dg:metrics`, `dg:observability`): Performance tracking



## 📚 Documentation Structure

| Component | Description | Purpose |
|-----------|-------------|---------|
| **Schema** | [dg-recordset-rt.schema.json](real_time_schemas/dg-recordset-rt.schema.json) | Normative validation schema |
| **Examples** | [measurements_rt.json](real_time_examples/measurements_rt.json) | Reference implementation |


## 🔗 Standards Compliance

- **Base Standard**: [Croissant RecordSet](https://github.com/mlcommons/croissant) format
- **Extension Namespace**: `dg:*` properties for real-time capabilities
- **Schema Validation**: JSON Schema Draft 2020-12 compliant
- **Semantic Versioning**: Profile version tracking (`dg:profileVersion`)

## 🛠️ Usage

### Schema Validation
```bash
# Validate your real-time profile against the schema
jsonschema -i your_dataset.json real_time_schemas/dg-recordset-rt.schema.json
```

### Integration Example
```json
{
  "@type": "RecordSet",
  "@id": "rs:your_dataset_rt",
  "name": "Your Real-time Dataset",
  "dg:profileVersion": "1.0.0",
  "dg:windowSpec": {
    "type": "sliding",
    "size": "PT15M",
    "slide": "PT1M"
  }
}
```

## 📖 References

- **Schema Documentation**: See [§2.4](real_time_schemas/README.md) for detailed schema specifications
- **Example Usage**: See [§3.2](real_time_examples/README.md) for implementation examples
- **Extended Profile**: The "extended Croissant profile" output conforms to **[dg-recordset-rt.schema.json](real_time_schemas/dg-recordset-rt.schema.json)**

---
