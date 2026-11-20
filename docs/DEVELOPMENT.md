# Related implementations

The file collection has no inspected Git history establishing a complete chronology. Names such as "latest", "V2" and "production_ready" are not proof of release order or production readiness.

| Family | Objective | Bounds/initialization | Distinguishing behavior |
|---|---|---|---|
| Heat-loss efficiency | Negative predicted efficiency | 28-variable fixed box, midpoint | Calculated losses enter a 15-feature model |
| Fixed baseline | Negative model output | 14-variable fixed box, midpoint | Coal/steam upper bound plus operating inequalities |
| Multistart | Negative model output | Random starts, commonly 50 | Best successful result, then selected final checks |
| Hourly adaptive | Negative model output | 10th/90th percentiles and margin | 14 buffers; hourly update; clears data after acceptance |
| Minute/five-minute adaptive | Negative model output | Different percentiles, buffer capacities and cadences | Names and comments sometimes contradict actual intervals |
| Live-seed | Negative model output | Perturbations around current inputs | Broad fallback bounds and varied placeholder/integration methods |
| Direct SCC | Coal/steam ratio | API-summary-derived bounds | 30/50/200/300-start alternatives and different inequalities |
| Target distance | Absolute distance from target SCC | Expanded feasible-range calculations | Adjusts target; may write after validation warning |
| Constant SCC | No optimization in main cycle | Current state with replaced coal flow | Coal = target * current steam; distinguish from an optimized solution |

## Specific preserved defects

- B1 fixed baseline references `Specific_coal_cons` without a definition before optimization.
- Minute B3 constraint references `wind_box_dp_max`, absent from the manager's minimum dictionary.
- Target-distance final validation warns and continues instead of blocking all writes.
- Some scripts maximize a model while naming its prediction SCC; artifact target needs reconciliation.
- Some output mappings mix measured aggregates and optimized variables.
- Heat-loss equations use hard-coded coefficients and fixed loss terms; several candidate variables have no implemented influence.
- Learned bounds and ratios lack a full joint physical feasibility model.

## Suggested next engineering steps (not performed)

Select a canonical objective and model artifact, document units and independently fixed disturbances versus manipulated variables, reconcile ratio equations, make all validation paths fail closed, define feasible fallback behavior, validate data quality/timestamps, and evaluate on a time-separated historical period. Keep integration disabled until separately authorized and verified.
