# Evaluation provenance

The following values were read from saved notebook outputs, not calculated during repository preparation.

| Original source | Cell (zero-based) | Target label | Train RMSE / MAE / R2 | Test RMSE / MAE / R2 |
|---|---:|---|---|---|
| Boiler_1 Model (2)-checkpoint.ipynb | 44 | Boiler efficiency | 0.1154 / 0.0887 / 0.9126 | 0.1160 / 0.0892 / 0.9114 |
| Boiler_1 Model (2)-checkpoint.ipynb | 67 | SCC | 0.0063 / 0.0048 / 0.9348 | 0.0065 / 0.0049 / 0.9324 |

The archive notebook contains the same reported values. Do not count those as a second independent evaluation. Root notebook cell numbers differ (selected-model training appears in cells 47 and 70). All public notebooks have outputs cleared, so this document preserves only aggregate evaluation evidence.

The code uses an 80/20 random split with split seed 42. It does not establish an independent future-period test, cross-plant test or prospective deployment evaluation. Process target units, source-data identity, leakage risks and artifact lineage remain unresolved. R-squared is not classification accuracy. No fuel-saving percentage or operational benefit is inferred from these metrics.

Saved exceptions also exist in source notebooks, including MLflow access errors and syntax errors. The availability of some saved model metrics does not prove that every subsequent optimization or integration cell ran successfully.
