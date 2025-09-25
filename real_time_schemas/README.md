# DataGEMS Real-time Profiling Schemas

This directory contains JSON Schema definitions for DataGEMS real-time profiling with extended Croissant profiles.

## Files

### `dg-recordset-rt.schema.json`
JSON Schema for the DataGEMS extended Croissant RecordSet with **real-time profiling** capabilities.

**Canonical URL:** `https://github.com/amy-77/datagem/blob/main/real_time_schemas/dg-recordset-rt.schema.json`

This schema defines the structure for **real-time profiling** features:
- **Streaming window management** (`dg:windowSpec`, `dg:windowState`, `dg:rollingStats`)
- **Live connectivity & plug-and-play** (`dg:changefeed`, `dg:queryService`)
- **Real-time observability** (`dg:metrics`, `dg:observability`)
- **Dynamic data quality** (`dg:qualityRules`, `dg:privacy`, `dg:access`)

## Usage

You can validate your extended Croissant profiles against this schema using any JSON Schema validator:

```bash
# Using ajv-cli
npx ajv-cli validate -s schemas/dg-recordset-rt.schema.json -d examples/measurements_rt.json

# Using python jsonschema
python -c "
import json
from jsonschema import validate

with open('schemas/dg-recordset-rt.schema.json') as f:
    schema = json.load(f)
    
with open('examples/measurements_rt.json') as f:
    instance = json.load(f)
    
validate(instance, schema)
print('✓ Valid')
"
```

## Examples

See the `../examples/` directory for example instances that conform to this schema.
