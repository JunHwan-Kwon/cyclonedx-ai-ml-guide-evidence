# Input/output quantization

[BOM example](efficientnet-lite0.json) · [Results](results.json) · [Sources](SOURCE_MANIFEST.json)

| Source | Commit |
| --- | --- |
| Guide | `e0925d8940aa1a0a3fca442469d86265dd93e38c` |
| Specification | `5a816a371871e75f4dd0d51f27e8af599a255e4e` |
| Property taxonomy #175 | `f5f956dd7fd0c312f05520ce7aecc3746d099645` |
| Artifact observations | `ac79fad51b622fc84281d668b6e68138e5e72e10` |

| Artifact | SHA-256 |
| --- | --- |
| EfficientNet-Lite0 TFLite | `bc2ffe19c1118de0c0c2a9088992da5589722656e0fba81421385300a4a34b16` |

| Direction | Tensor | Dtype | Shape | Scale | Zero point |
| --- | --- | --- | --- | ---: | ---: |
| input | `images` | UINT8 | `[1, 224, 224, 3]` | 0.012566016986966133 | 131 |
| output | `Softmax` | UINT8 | `[1, 1000]` | 0.00390625 | 0 |

| Validator | Schema | Documents | Valid | Errors |
| --- | --- | ---: | ---: | ---: |
| python-jsonschema 4.26.0 | modular | 1 | 1 | 0 |
| python-jsonschema 4.26.0 | bundled | 1 | 1 | 0 |
| Ajv 8.20.0 | modular | 1 | 1 | 0 |
| Ajv 8.20.0 | bundled | 1 | 1 | 0 |

| Artifact-record comparison | Parameters checked | Differences |
| --- | ---: | ---: |
| Name, dtype and shape → BOM | 2 | 0 |
| Bit width, scheme and granularity → BOM | 2 | 0 |
| Scale and zero point → result table | 2 | 0 |

| Quantity | Location |
| --- | --- |
| Native quantization classification | BOM: `modelProperties.inputs/outputs[*].quantization` |
| Observed scale and zero point | Result table and `results.json` |

| Definition | Recorded rule | Source |
| --- | --- | --- |
| Native `symmetric` | Zero point fixed at zero | [Schema](https://github.com/CycloneDX/specification/blob/5a816a371871e75f4dd0d51f27e8af599a255e4e/schema/2.0/modules/cyclonedx-ai-ml-2.0.schema.json) |
| Proposed `affine_symmetric` | Zero point depends on integer representation; 0 for zero-centered signed INT8. Companion `scale` required. | [Taxonomy #175](https://github.com/CycloneDX/cyclonedx-property-taxonomy/blob/f5f956dd7fd0c312f05520ce7aecc3746d099645/cdx/ai-ml.md#L184) |
| Proposed taxonomy `scheme` | Required when another quantization property is used | [Taxonomy #175](https://github.com/CycloneDX/cyclonedx-property-taxonomy/blob/f5f956dd7fd0c312f05520ce7aecc3746d099645/cdx/ai-ml.md#L155) |
| Parameter extension properties | `properties` is a sibling of `quantization` | [Schema](https://github.com/CycloneDX/specification/blob/5a816a371871e75f4dd0d51f27e8af599a255e4e/schema/2.0/modules/cyclonedx-ai-ml-2.0.schema.json) |
