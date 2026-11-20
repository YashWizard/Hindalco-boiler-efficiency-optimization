# Source guide

This guide describes historical source, not a validated deployable service. Original line numbers refer to the source files before anonymization; use the linked copies for public review. Boiler/client identifiers may have been replaced with consistent aliases.

## minute_boiler3.py.txt

**Original:** `1minute.py`  
**Public copy:** [reference/adaptive/minute_boiler3.py.txt](../reference/adaptive/minute_boiler3.py.txt)

Minute-update 5th/95th-percentile adaptive variant.

**Limitations:** Constraint references missing wind_box_dp_max key. Final constraint validation does not certify plant safety.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 17–158
- `Utkal_Boiler_B3` — original lines 160–676
- `__init__` — original lines 25–66
- `add_real_time_data` — original lines 68–72
- `calculate_adaptive_bounds_and_constraints` — original lines 74–108
- `should_update_bounds` — original lines 110–112
- `update_bounds_and_constraints_if_needed` — original lines 114–139
- `validate_bounds_compatibility` — original lines 141–158
- `__init__` — original lines 168–226
- `load_model` — original lines 228–231
- `update_constraints` — original lines 233–249
- `objective` — original lines 251–254
- `air_to_fuel_ratio` — original lines 256–259
- `scc_constraint` — original lines 261–263
- `validate_solution` — original lines 265–267
- `multi_start_optimization` — original lines 269–308
- `initialize_tags` — original lines 310–384
- `safe_avg` — original lines 386–392
- `_get_batch_url` — original lines 394–397
- `_batch_fetch` — original lines 399–439
- `read_tag_value` — original lines 441–473
- `write_predictions_to_pi` — original lines 475–493
- `run` — original lines 495–540
- `run_loop` — original lines 542–676

## constant_target.py.txt

**Original:** `AHH_SCC_AGAIN.py`  
**Public copy:** [reference/direct_scc/constant_target.py.txt](../reference/direct_scc/constant_target.py.txt)

Sets constant SCC and computes required coal as target times measured steam.

**Limitations:** Main cycle does not optimize. A loaded model or optimizer-shaped class does not make this an ML optimization result.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `load_tag_map_csv_from_minio` — original lines 21–29
- `SCCOptimizer` — original lines 31–359
- `main` — original lines 361–369
- `__init__` — original lines 32–120
- `load_model` — original lines 122–124
- `safe_avg` — original lines 126–130
- `_get_batch_url` — original lines 132–134
- `_batch_fetch` — original lines 136–168
- `read_tag_value` — original lines 170–196
- `_extract_numeric_value` — original lines 198–205
- `scc_objective` — original lines 207–208
- `collect_current_data` — original lines 210–244
- `write_predictions_to_pi` — original lines 246–264
- `run_optimization_cycle` — original lines 266–342
- `run_real_time_loop` — original lines 344–359

## live_seed_notes.py.txt

**Original:** `analyz this.txt`  
**Public copy:** [reference/adaptive/live_seed_notes.py.txt](../reference/adaptive/live_seed_notes.py.txt)

Python implementation stored as text; 180-sample buffer and one-minute update.

**Limitations:** Sample capacity is not proof of a three-minute time window.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 16–104
- `Utkal_Boiler_B2` — original lines 106–300
- `__init__` — original lines 18–28
- `add_real_time_data` — original lines 30–33
- `calculate_adaptive_bounds_and_constraints` — original lines 35–65
- `should_update_bounds` — original lines 67–68
- `update_bounds_and_constraints_if_needed` — original lines 70–84
- `validate_bounds_compatibility` — original lines 86–104
- `__init__` — original lines 110–145
- `load_model` — original lines 147–149
- `update_constraints` — original lines 151–161
- `objective` — original lines 163–165
- `air_to_fuel_ratio` — original lines 167–169
- `scc_constraint` — original lines 171–172
- `validate_solution` — original lines 174–175
- `multi_start_optimization` — original lines 177–203
- `initialize_tags` — original lines 205–209
- `safe_avg` — original lines 211–213
- `read_tag_value` — original lines 215–231
- `write_predictions_to_pi` — original lines 233–246
- `run_loop` — original lines 253–300

## boiler1.py.txt

**Original:** `B1_scc_deployment.py`  
**Public copy:** [reference/fixed_bounds/boiler1.py.txt](../reference/fixed_bounds/boiler1.py.txt)

Fourteen-feature model maximization under coal/steam ratio and operational constraints.

**Limitations:** Undefined Specific_coal_cons before optimization. Mixed measured and optimized outputs. Ten-second sleep despite one-minute message.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B1` — original lines 16–445
- `__init__` — original lines 17–108
- `objective` — original lines 110–113
- `air_to_fuel_ratio` — original lines 115–118
- `scc_constraint` — original lines 120–124
- `load_model` — original lines 126–128
- `initialize_tags` — original lines 130–183
- `safe_avg` — original lines 186–191
- `_get_batch_url` — original lines 193–195
- `_batch_fetch` — original lines 197–236
- `read_tag_value` — original lines 238–274
- `write_predictions_to_pi` — original lines 277–299
- `run_loop` — original lines 302–445

## boiler2_read_mapping.txt

**Original:** `b2_read_api_tags.txt`  
**Public copy:** [reference/configuration/boiler2_read_mapping.txt](../reference/configuration/boiler2_read_mapping.txt)

Read-endpoint configuration material.

**Limitations:** Anonymized mapping; not executable Python.

**Static status:** Original syntax issue at line 7: invalid decimal literal. Preserved.

**Functions/classes:**


## boiler3_read_mapping.txt

**Original:** `b3_read_tag_api.txt`  
**Public copy:** [reference/configuration/boiler3_read_mapping.txt](../reference/configuration/boiler3_read_mapping.txt)

Read-endpoint configuration material.

**Limitations:** Same original size as boiler2 map but different content.

**Static status:** Original syntax issue at line 13: invalid decimal literal. Preserved.

**Functions/classes:**


## boiler3_named.py.txt

**Original:** `B3_scc_deployment.py`  
**Public copy:** [reference/fixed_bounds/boiler3_named.py.txt](../reference/fixed_bounds/boiler3_named.py.txt)

Related fixed-bound model/ratio optimizer and PI integration.

**Limitations:** Filename and class boiler designation differ; do not infer configuration correctness or chronology from names.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B2` — original lines 16–448
- `__init__` — original lines 17–94
- `objective` — original lines 96–99
- `air_to_fuel_ratio` — original lines 101–104
- `scc_constraint` — original lines 108–112
- `load_model` — original lines 114–116
- `initialize_tags` — original lines 118–177
- `safe_avg` — original lines 180–185
- `_get_batch_url` — original lines 187–189
- `_batch_fetch` — original lines 191–230
- `read_tag_value` — original lines 232–268
- `write_predictions_to_pi` — original lines 270–292
- `run_loop` — original lines 295–448

## boiler3_write_mapping.txt

**Original:** `b3_write_tag_api.txt`  
**Public copy:** [reference/configuration/boiler3_write_mapping.txt](../reference/configuration/boiler3_write_mapping.txt)

Output-endpoint configuration material.

**Limitations:** Anonymized mapping; no authority to operate equipment implied.

**Static status:** Original syntax issue at line 10: invalid decimal literal. Preserved.

**Functions/classes:**


## heat_loss_experiment.py.txt

**Original:** `BE_EXP_1.py`  
**Public copy:** [reference/efficiency/heat_loss_experiment.py.txt](../reference/efficiency/heat_loss_experiment.py.txt)

Related loss-equation and efficiency-model experiment.

**Limitations:** Syntax issue at original line 257; preserve as historical source, not a runnable deployment.

**Static status:** Original syntax issue at line 257: unindent does not match any outer indentation level. Preserved.

**Functions/classes:**

- `Utkal_Boiler_B1` — original line 14
- `__init__` — original line 17
- `load_model` — original line 105
- `initialize_tags` — original line 109
- `safe_avg` — original line 164
- `_get_batch_url` — original line 171
- `_batch_fetch` — original line 175
- `read_tag_value` — original line 216
- `read_tag_value` — original line 254
- `write_predictions_to_pi` — original line 281
- `calculate_losses` — original line 305
- `objective` — original line 351
- `run_loop` — original line 378

## boiler2_write_mapping.txt

**Original:** `boiler2_write_api.txt`  
**Public copy:** [reference/configuration/boiler2_write_mapping.txt](../reference/configuration/boiler2_write_mapping.txt)

Output-endpoint configuration material.

**Limitations:** Anonymized mapping.

**Static status:** Original syntax issue at line 8: invalid decimal literal. Preserved.

**Functions/classes:**


## boiler1_heat_loss.py.txt

**Original:** `Boiler_1_Deployment_Script (1).py`  
**Public copy:** [reference/efficiency/boiler1_heat_loss.py.txt](../reference/efficiency/boiler1_heat_loss.py.txt)

Twelve labeled loss terms, 28-variable SLSQP efficiency-model maximization, PI integration.

**Limitations:** Several losses are constants. Calculated and independent loss features are not reconciled. Units and physical calibration require review.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B1` — original lines 16–554
- `__init__` — original lines 17–114
- `load_model` — original lines 116–118
- `initialize_tags` — original lines 120–158
- `safe_avg` — original lines 160–165
- `_get_batch_url` — original lines 167–169
- `_batch_fetch` — original lines 171–210
- `read_tag_value` — original lines 212–248
- `write_predictions_to_pi` — original lines 277–299
- `calculate_losses` — original lines 301–345
- `objective` — original lines 347–372
- `run_loop` — original lines 375–554

## five_minute_boiler2.py.txt

**Original:** `Boiler_2.1minute.py`  
**Public copy:** [reference/adaptive/five_minute_boiler2.py.txt](../reference/adaptive/five_minute_boiler2.py.txt)

Five-minute adaptive updates with 10th/90th percentiles and 30-start default search.

**Limitations:** Actual update interval is five minutes despite filename. Thirty-second loop sleep; buffer length is not duration.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 17–166
- `Utkal_Boiler_B2` — original lines 168–657
- `__init__` — original lines 25–67
- `add_real_time_data` — original lines 69–73
- `calculate_adaptive_bounds_and_constraints` — original lines 75–115
- `should_update_bounds` — original lines 117–119
- `update_bounds_and_constraints_if_needed` — original lines 121–146
- `validate_bounds_compatibility` — original lines 148–166
- `__init__` — original lines 173–225
- `load_model` — original lines 227–230
- `update_constraints` — original lines 232–248
- `objective` — original lines 250–253
- `air_to_fuel_ratio` — original lines 255–258
- `scc_constraint` — original lines 260–262
- `validate_solution` — original lines 264–266
- `multi_start_optimization` — original lines 268–306
- `initialize_tags` — original lines 308–367
- `safe_avg` — original lines 369–375
- `_get_batch_url` — original lines 377–380
- `_batch_fetch` — original lines 382–422
- `read_tag_value` — original lines 424–458
- `write_predictions_to_pi` — original lines 460–482
- `run` — original lines 484–526
- `run_loop` — original lines 528–657

## minute_boiler2.py.txt

**Original:** `boiler_2_imin.py`  
**Public copy:** [reference/adaptive/minute_boiler2.py.txt](../reference/adaptive/minute_boiler2.py.txt)

One-minute adaptive boiler2 variant with multistart optimization.

**Limitations:** Ten-second sleep plus processing time differs from buffer comments assuming one sample per second.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 17–169
- `Utkal_Boiler_B2` — original lines 171–641
- `__init__` — original lines 25–68
- `add_real_time_data` — original lines 70–74
- `calculate_adaptive_bounds_and_constraints` — original lines 76–114
- `should_update_bounds` — original lines 116–118
- `update_bounds_and_constraints_if_needed` — original lines 120–145
- `validate_bounds_compatibility` — original lines 147–169
- `__init__` — original lines 176–228
- `load_model` — original lines 230–232
- `update_constraints` — original lines 234–248
- `objective` — original lines 250–252
- `air_to_fuel_ratio` — original lines 254–256
- `scc_constraint` — original lines 258–259
- `validate_solution` — original lines 261–262
- `multi_start_optimization` — original lines 264–293
- `initialize_tags` — original lines 295–354
- `safe_avg` — original lines 356–361
- `_get_batch_url` — original lines 363–365
- `_batch_fetch` — original lines 367–406
- `read_tag_value` — original lines 408–444
- `write_predictions_to_pi` — original lines 446–468
- `run` — original lines 470–511
- `run_loop` — original lines 513–641

## live_seed_experiment_a.py.txt

**Original:** `cryemojitryemojihappyemoji.py`  
**Public copy:** [reference/adaptive/live_seed_experiment_a.py.txt](../reference/adaptive/live_seed_experiment_a.py.txt)

Related 14-parameter adaptive search implementation.

**Limitations:** Informal filename does not indicate a separate project; retained as a distinct historical variant.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 15–101
- `Utkal_Boiler_B2` — original lines 103–317
- `__init__` — original lines 16–26
- `add_real_time_data` — original lines 28–31
- `calculate_adaptive_bounds_and_constraints` — original lines 33–62
- `should_update_bounds` — original lines 64–65
- `update_bounds_and_constraints_if_needed` — original lines 67–81
- `validate_bounds_compatibility` — original lines 83–101
- `__init__` — original lines 107–142
- `load_model` — original lines 144–146
- `update_constraints` — original lines 148–158
- `objective` — original lines 160–162
- `air_to_fuel_ratio` — original lines 164–166
- `scc_constraint` — original lines 168–169
- `validate_solution` — original lines 171–172
- `multi_start_optimization` — original lines 174–200
- `initialize_tags` — original lines 202–232
- `safe_avg` — original lines 234–236
- `read_tag_value` — original lines 238–252
- `write_predictions_to_pi` — original lines 254–267
- `run_loop` — original lines 269–317

## live_seed_variant.py.txt

**Original:** `latest0-Copy1.1.py`  
**Public copy:** [reference/adaptive/live_seed_variant.py.txt](../reference/adaptive/live_seed_variant.py.txt)

Related live-input-seeded optimizer with different integration content.

**Limitations:** Distinct from root latest0.1.py; its similarly named checkpoint is a copy of latest0.1.py.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 16–104
- `Utkal_Boiler_B2` — original lines 106–351
- `__init__` — original lines 18–28
- `add_real_time_data` — original lines 30–33
- `calculate_adaptive_bounds_and_constraints` — original lines 35–65
- `should_update_bounds` — original lines 67–68
- `update_bounds_and_constraints_if_needed` — original lines 70–84
- `validate_bounds_compatibility` — original lines 86–104
- `__init__` — original lines 110–145
- `load_model` — original lines 147–149
- `update_constraints` — original lines 151–161
- `objective` — original lines 163–165
- `air_to_fuel_ratio` — original lines 167–169
- `scc_constraint` — original lines 171–172
- `validate_solution` — original lines 174–175
- `multi_start_optimization` — original lines 177–203
- `initialize_tags` — original lines 205–264
- `safe_avg` — original lines 265–267
- `read_tag_value` — original lines 269–285
- `write_predictions_to_pi` — original lines 288–301
- `run_loop` — original lines 303–351

## live_seed_prototype.py.txt

**Original:** `latest0.1.py`  
**Public copy:** [reference/adaptive/live_seed_prototype.py.txt](../reference/adaptive/live_seed_prototype.py.txt)

Adaptive ranges and candidate starts perturbed around current input values.

**Limitations:** Experimental integration and fallbacks need review; no claim of operational reliability.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 16–104
- `Utkal_Boiler_B2` — original lines 106–296
- `__init__` — original lines 18–28
- `add_real_time_data` — original lines 30–33
- `calculate_adaptive_bounds_and_constraints` — original lines 35–65
- `should_update_bounds` — original lines 67–68
- `update_bounds_and_constraints_if_needed` — original lines 70–84
- `validate_bounds_compatibility` — original lines 86–104
- `__init__` — original lines 110–145
- `load_model` — original lines 147–149
- `update_constraints` — original lines 151–161
- `objective` — original lines 163–165
- `air_to_fuel_ratio` — original lines 167–169
- `scc_constraint` — original lines 171–172
- `validate_solution` — original lines 174–175
- `multi_start_optimization` — original lines 177–203
- `initialize_tags` — original lines 205–209
- `safe_avg` — original lines 211–213
- `read_tag_value` — original lines 215–231
- `write_predictions_to_pi` — original lines 233–246
- `run_loop` — original lines 248–296

## expanded_monitor.py.txt

**Original:** `live_daataa.py`  
**Public copy:** [reference/monitoring/expanded_monitor.py.txt](../reference/monitoring/expanded_monitor.py.txt)

Expanded measurement monitor and plotting.

**Limitations:** Three-second polling. Not the ITC Streamlit replay dashboard.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `fetch_tag_value` — original lines 103–120
- `update_plot` — original lines 122–180
- `print_data_status` — original lines 182–206

## basic_monitor.py.txt

**Original:** `live_data.py`  
**Public copy:** [reference/monitoring/basic_monitor.py.txt](../reference/monitoring/basic_monitor.py.txt)

PI measurement fetching and rolling plots.

**Limitations:** Thirty-second polling; external measurements/configuration withheld.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `fetch_tag_value` — original lines 35–54
- `update_plot` — original lines 56–90
- `print_data_status` — original lines 92–108

## live_work_prototype.py.txt

**Original:** `Live_Work.py`  
**Public copy:** [reference/adaptive/live_work_prototype.py.txt](../reference/adaptive/live_work_prototype.py.txt)

Percentile ranges, near-current search starts and fallback to input values.

**Limitations:** Contains integration placeholders and broad bounds when history is insufficient.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 16–114
- `Utkal_Boiler_B2` — original lines 116–280
- `__init__` — original lines 21–32
- `add_real_time_data` — original lines 34–37
- `calculate_adaptive_bounds_and_constraints` — original lines 39–74
- `should_update_bounds` — original lines 76–77
- `update_bounds_and_constraints_if_needed` — original lines 79–93
- `validate_bounds_compatibility` — original lines 95–114
- `__init__` — original lines 120–155
- `load_model` — original lines 157–159
- `update_constraints` — original lines 161–171
- `objective` — original lines 173–175
- `air_to_fuel_ratio` — original lines 177–179
- `scc_constraint` — original lines 181–182
- `validate_solution` — original lines 184–185
- `multi_start_optimization` — original lines 187–213
- `initialize_tags` — original lines 215–218
- `safe_avg` — original lines 220–222
- `read_tag_value` — original lines 224–226
- `write_predictions_to_pi` — original lines 228–230
- `run_loop` — original lines 232–280

## measurement_summaries.py.txt

**Original:** `min_max_printing.py`  
**Public copy:** [reference/direct_scc/measurement_summaries.py.txt](../reference/direct_scc/measurement_summaries.py.txt)

Model optimizer with measurement mean/max summaries and diagnostic printing.

**Limitations:** Syntax issue at original line 481. Not a runnable release.

**Static status:** Original syntax issue at line 481: inconsistent use of tabs and spaces in indentation. Preserved.

**Functions/classes:**

- `Utkal_Boiler_B1` — original line 14
- `__init__` — original line 17
- `load_model` — original line 110
- `objective` — original line 115
- `air_to_fuel_ratio` — original line 119
- `scc_constraint` — original line 122
- `validate_solution` — original line 125
- `multi_start_optimization` — original line 128
- `initialize_tags` — original line 153
- `safe_avg` — original line 233
- `_get_batch_url` — original line 241
- `_batch_fetch` — original line 245
- `read_tag_value` — original line 286
- `get_tag_mean_max` — original line 354
- `write_predictions_to_pi` — original line 391
- `run` — original line 415
- `run_loop` — original line 462

## live_seed_experiment_b.py.txt

**Original:** `RoryFinalGiveIt.py`  
**Public copy:** [reference/adaptive/live_seed_experiment_b.py.txt](../reference/adaptive/live_seed_experiment_b.py.txt)

Related adaptive constraints, multistart search and integration.

**Limitations:** Shared core logic with other live-seed variants; chronology not established.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 15–101
- `Utkal_Boiler_B2` — original lines 103–320
- `__init__` — original lines 16–26
- `add_real_time_data` — original lines 28–31
- `calculate_adaptive_bounds_and_constraints` — original lines 33–62
- `should_update_bounds` — original lines 64–65
- `update_bounds_and_constraints_if_needed` — original lines 67–81
- `validate_bounds_compatibility` — original lines 83–101
- `__init__` — original lines 107–142
- `load_model` — original lines 144–146
- `update_constraints` — original lines 148–158
- `objective` — original lines 160–162
- `air_to_fuel_ratio` — original lines 164–166
- `scc_constraint` — original lines 168–169
- `validate_solution` — original lines 171–172
- `multi_start_optimization` — original lines 174–200
- `initialize_tags` — original lines 202–233
- `safe_avg` — original lines 235–237
- `read_tag_value` — original lines 239–253
- `write_predictions_to_pi` — original lines 255–268
- `run_loop` — original lines 270–320

## target_distance.py.txt

**Original:** `SCC_FIX_1.py`  
**Public copy:** [reference/direct_scc/target_distance.py.txt](../reference/direct_scc/target_distance.py.txt)

Minimizes distance from target SCC; expanded bounds, diagnostics and fallback.

**Limitations:** Final failed-validation warning can continue to writing. Target and fallback values are not validated operating recommendations.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `load_tag_map_csv_from_minio` — original lines 21–29
- `SCCOptimizer` — original lines 31–533
- `main` — original lines 535–542
- `__init__` — original lines 32–120
- `load_model` — original lines 122–124
- `safe_avg` — original lines 126–130
- `_get_batch_url` — original lines 132–134
- `_batch_fetch` — original lines 136–168
- `read_tag_value` — original lines 170–196
- `_extract_numeric_value` — original lines 198–205
- `get_tag_mean_max` — original lines 207–238
- `build_initial_bounds` — original lines 240–282
- `scc_objective` — original lines 284–285
- `target_scc_objective` — original lines 287–289
- `get_constraints_scc_focused` — original lines 291–304
- `validate_solution` — original lines 306–314
- `debug_optimization_run` — original lines 316–321
- `multi_start_optimization` — original lines 323–371
- `collect_current_data` — original lines 373–407
- `write_predictions_to_pi` — original lines 409–427
- `run_optimization_cycle` — original lines 429–518
- `run_real_time_loop` — original lines 520–533

## focused.py.txt

**Original:** `scc_focused.py.txt`  
**Public copy:** [reference/direct_scc/focused.py.txt](../reference/direct_scc/focused.py.txt)

Direct SCC minimization using API-derived bounds and repeated starts.

**Limitations:** SCC objective and feasibility checks differ from model-maximization family.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `SCCOptimizer` — original lines 17–517
- `main` — original lines 520–529
- `__init__` — original lines 18–83
- `load_model` — original lines 85–87
- `initialize_tags` — original lines 89–141
- `safe_avg` — original lines 143–148
- `_get_batch_url` — original lines 150–153
- `_batch_fetch` — original lines 155–191
- `read_tag_value` — original lines 193–204
- `get_tag_mean_max` — original lines 206–242
- `build_initial_bounds` — original lines 244–274
- `scc_objective` — original lines 276–278
- `get_constraints_scc_focused` — original lines 280–285
- `validate_solution` — original lines 287–293
- `multi_start_optimization` — original lines 295–333
- `collect_current_data` — original lines 335–376
- `write_predictions_to_pi` — original lines 378–400
- `run_optimization_cycle` — original lines 402–480
- `run_real_time_loop` — original lines 482–517

## csv_mapping.py.txt

**Original:** `scs_focuses.py`  
**Public copy:** [reference/direct_scc/csv_mapping.py.txt](../reference/direct_scc/csv_mapping.py.txt)

CSV-configured ratio optimizer with current-value delta constraints and 300 starts.

**Limitations:** Final custom validation checks SCC rather than every physical relation.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `load_tag_map_csv` — original lines 17–19
- `SCCOptimizer` — original lines 21–396
- `main` — original lines 398–405
- `__init__` — original lines 22–82
- `load_model` — original lines 84–86
- `safe_avg` — original lines 88–92
- `_get_batch_url` — original lines 94–96
- `_batch_fetch` — original lines 98–130
- `read_tag_value` — original lines 132–141
- `get_tag_mean_max` — original lines 143–171
- `build_initial_bounds` — original lines 173–195
- `scc_objective` — original lines 197–198
- `get_constraints_scc_focused` — original lines 200–220
- `validate_solution` — original lines 222–227
- `multi_start_optimization` — original lines 229–258
- `collect_current_data` — original lines 260–291
- `write_predictions_to_pi` — original lines 293–311
- `run_optimization_cycle` — original lines 313–371
- `run_real_time_loop` — original lines 373–396

## input_comparison.py.txt

**Original:** `tags _ updated.txt`  
**Public copy:** [reference/diagnostics/input_comparison.py.txt](../reference/diagnostics/input_comparison.py.txt)

Two-round API measurement comparison and model-input testing.

**Limitations:** Diagnostic source only; private configuration anonymized.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `fetch_pi_values` — original lines 50–92
- `compare_values` — original lines 94–138
- `run_model_prediction_test` — original lines 140–211

## mapping_notes.txt

**Original:** `tags_url.txt`  
**Public copy:** [reference/configuration/mapping_notes.txt](../reference/configuration/mapping_notes.txt)

Additional API/tag configuration material.

**Limitations:** Anonymized identifiers and endpoints; exact operational provenance unresolved.

**Static status:** Original syntax issue at line 15: invalid decimal literal. Preserved.

**Functions/classes:**


## tag_mapping_function.py.txt

**Original:** `tag_urls.txt`  
**Public copy:** [reference/configuration/tag_mapping_function.py.txt](../reference/configuration/tag_mapping_function.py.txt)

Measurement mapping function stored in a text file.

**Limitations:** All plant identifiers and endpoint values replaced; not a usable plant configuration.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `initialize_tags` — original lines 1–68

## csv_mapping_variant.py.txt

**Original:** `test_pls.txt`  
**Public copy:** [reference/direct_scc/csv_mapping_variant.py.txt](../reference/direct_scc/csv_mapping_variant.py.txt)

Closely related CSV-configured SCC optimizer stored as text.

**Limitations:** Most function bodies match csv_mapping; constraint differences retained.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `load_tag_map_csv` — original lines 17–19
- `SCCOptimizer` — original lines 21–393
- `main` — original lines 395–402
- `__init__` — original lines 22–82
- `load_model` — original lines 84–86
- `safe_avg` — original lines 88–92
- `_get_batch_url` — original lines 94–96
- `_batch_fetch` — original lines 98–130
- `read_tag_value` — original lines 132–141
- `get_tag_mean_max` — original lines 143–171
- `build_initial_bounds` — original lines 173–195
- `scc_objective` — original lines 197–198
- `get_constraints_scc_focused` — original lines 200–218
- `validate_solution` — original lines 220–225
- `multi_start_optimization` — original lines 227–255
- `collect_current_data` — original lines 257–288
- `write_predictions_to_pi` — original lines 290–308
- `run_optimization_cycle` — original lines 310–368
- `run_real_time_loop` — original lines 370–393

## boiler2.py.txt

**Original:** `V2_B2_scc_deployment-Copy1.py`  
**Public copy:** [reference/multistart/boiler2.py.txt](../reference/multistart/boiler2.py.txt)

Repeated SLSQP starts under fixed bounds with final inequality checks.

**Limitations:** Model-target interpretation and deployed artifact identity remain unverified.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B2` — original lines 16–475
- `__init__` — original lines 17–81
- `load_model` — original lines 83–85
- `objective` — original lines 87–89
- `air_to_fuel_ratio` — original lines 91–92
- `scc_constraint` — original lines 94–95
- `validate_solution` — original lines 97–98
- `multi_start_optimization` — original lines 100–123
- `initialize_tags` — original lines 126–193
- `safe_avg` — original lines 196–201
- `_get_batch_url` — original lines 203–205
- `_batch_fetch` — original lines 207–246
- `read_tag_value` — original lines 248–284
- `write_predictions_to_pi` — original lines 286–308
- `run` — original lines 311–349
- `run_loop` — original lines 351–475

## boiler3.py.txt

**Original:** `V2_B3_scc_deployment.py`  
**Public copy:** [reference/multistart/boiler3.py.txt](../reference/multistart/boiler3.py.txt)

Related multistart optimizer and boiler-specific API mappings.

**Limitations:** Mappings are anonymized; not a verified operational release.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B3` — original lines 16–513
- `__init__` — original lines 17–81
- `load_model` — original lines 83–85
- `objective` — original lines 87–89
- `air_to_fuel_ratio` — original lines 91–92
- `scc_constraint` — original lines 94–95
- `validate_solution` — original lines 97–98
- `multi_start_optimization` — original lines 100–123
- `initialize_tags` — original lines 126–185
- `safe_avg` — original lines 188–193
- `_get_batch_url` — original lines 195–197
- `_batch_fetch` — original lines 199–238
- `read_tag_value` — original lines 240–276
- `write_predictions_to_pi` — original lines 278–300
- `run` — original lines 303–356
- `run_loop` — original lines 358–513

## hourly_boiler3.py.txt

**Original:** `V2_B3_scc_deployment_UPT1.py`  
**Public copy:** [reference/adaptive/hourly_boiler3.py.txt](../reference/adaptive/hourly_boiler3.py.txt)

Hourly 10th/90th-percentile bounds, 15-percent range margin, 14 buffers, 50-start SLSQP.

**Limitations:** Buffers count samples, are cleared after updates, and are not a strict timestamp rolling hour. Three random feasibility probes are not a proof.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 17–201
- `Utkal_Boiler_B3` — original lines 203–848
- `__init__` — original lines 27–71
- `add_real_time_data` — original lines 73–83
- `calculate_adaptive_bounds_and_constraints` — original lines 85–131
- `should_update_bounds` — original lines 133–140
- `update_bounds_and_constraints_if_needed` — original lines 142–171
- `validate_bounds_compatibility` — original lines 173–201
- `__init__` — original lines 211–266
- `load_model` — original lines 268–276
- `update_constraints` — original lines 278–304
- `objective` — original lines 306–317
- `air_to_fuel_ratio` — original lines 319–330
- `scc_constraint` — original lines 332–342
- `validate_solution` — original lines 344–354
- `multi_start_optimization` — original lines 356–407
- `initialize_tags` — original lines 409–496
- `safe_avg` — original lines 498–512
- `_get_batch_url` — original lines 514–525
- `_batch_fetch` — original lines 527–577
- `read_tag_value` — original lines 579–622
- `write_predictions_to_pi` — original lines 624–647
- `run` — original lines 649–699
- `run_loop` — original lines 701–848

## narrow_target_range.py.txt

**Original:** `WORK_242.py`  
**Public copy:** [reference/direct_scc/narrow_target_range.py.txt](../reference/direct_scc/narrow_target_range.py.txt)

Direct ratio optimization with a narrow SCC interval and 200 starts.

**Limitations:** Ratios can improve mathematically without a validated process-response relationship.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `SCCOptimizer` — original lines 17–525
- `main` — original lines 528–537
- `__init__` — original lines 18–83
- `load_model` — original lines 85–87
- `initialize_tags` — original lines 89–141
- `safe_avg` — original lines 143–148
- `_get_batch_url` — original lines 150–153
- `_batch_fetch` — original lines 155–191
- `read_tag_value` — original lines 193–204
- `get_tag_mean_max` — original lines 206–242
- `build_initial_bounds` — original lines 244–274
- `scc_objective` — original lines 276–278
- `get_constraints_scc_focused` — original lines 283–293
- `validate_solution` — original lines 295–301
- `multi_start_optimization` — original lines 303–341
- `collect_current_data` — original lines 343–384
- `write_predictions_to_pi` — original lines 386–408
- `run_optimization_cycle` — original lines 410–488
- `run_real_time_loop` — original lines 490–525

## checkpoint_minute_boiler3.py.txt

**Original:** `.ipynb_checkpoints/1minute-checkpoint.py`  
**Public copy:** [reference/adaptive/variants/checkpoint_minute_boiler3.py.txt](../reference/adaptive/variants/checkpoint_minute_boiler3.py.txt)

Minute-update 5th/95th-percentile adaptive variant.

**Limitations:** Constraint references missing wind_box_dp_max key. Final constraint validation does not certify plant safety.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 17–158
- `Utkal_Boiler_B3` — original lines 160–676
- `__init__` — original lines 25–66
- `add_real_time_data` — original lines 68–72
- `calculate_adaptive_bounds_and_constraints` — original lines 74–108
- `should_update_bounds` — original lines 110–112
- `update_bounds_and_constraints_if_needed` — original lines 114–139
- `validate_bounds_compatibility` — original lines 141–158
- `__init__` — original lines 168–226
- `load_model` — original lines 228–231
- `update_constraints` — original lines 233–249
- `objective` — original lines 251–254
- `air_to_fuel_ratio` — original lines 256–259
- `scc_constraint` — original lines 261–263
- `validate_solution` — original lines 265–267
- `multi_start_optimization` — original lines 269–308
- `initialize_tags` — original lines 310–384
- `safe_avg` — original lines 386–392
- `_get_batch_url` — original lines 394–397
- `_batch_fetch` — original lines 399–439
- `read_tag_value` — original lines 441–473
- `write_predictions_to_pi` — original lines 475–493
- `run` — original lines 495–540
- `run_loop` — original lines 542–676

## checkpoint_boiler3_named.py.txt

**Original:** `.ipynb_checkpoints/B3_scc_deployment-checkpoint.py`  
**Public copy:** [reference/fixed_bounds/variants/checkpoint_boiler3_named.py.txt](../reference/fixed_bounds/variants/checkpoint_boiler3_named.py.txt)

Related fixed-bound model/ratio optimizer and PI integration.

**Limitations:** Filename and class boiler designation differ; do not infer configuration correctness or chronology from names.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B2` — original lines 16–448
- `__init__` — original lines 17–94
- `objective` — original lines 96–99
- `air_to_fuel_ratio` — original lines 101–104
- `scc_constraint` — original lines 108–112
- `load_model` — original lines 114–116
- `initialize_tags` — original lines 118–177
- `safe_avg` — original lines 180–185
- `_get_batch_url` — original lines 187–189
- `_batch_fetch` — original lines 191–230
- `read_tag_value` — original lines 232–268
- `write_predictions_to_pi` — original lines 270–292
- `run_loop` — original lines 295–448

## checkpoint_live_work_prototype.py.txt

**Original:** `.ipynb_checkpoints/Live_Work-checkpoint.py`  
**Public copy:** [reference/adaptive/variants/checkpoint_live_work_prototype.py.txt](../reference/adaptive/variants/checkpoint_live_work_prototype.py.txt)

Percentile ranges, near-current search starts and fallback to input values.

**Limitations:** Contains integration placeholders and broad bounds when history is insufficient.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `AdaptiveBoundsAndConstraintsManager` — original lines 16–114
- `Utkal_Boiler_B2` — original lines 116–280
- `__init__` — original lines 21–32
- `add_real_time_data` — original lines 34–37
- `calculate_adaptive_bounds_and_constraints` — original lines 39–74
- `should_update_bounds` — original lines 76–77
- `update_bounds_and_constraints_if_needed` — original lines 79–93
- `validate_bounds_compatibility` — original lines 95–114
- `__init__` — original lines 120–155
- `load_model` — original lines 157–159
- `update_constraints` — original lines 161–171
- `objective` — original lines 173–175
- `air_to_fuel_ratio` — original lines 177–179
- `scc_constraint` — original lines 181–182
- `validate_solution` — original lines 184–185
- `multi_start_optimization` — original lines 187–213
- `initialize_tags` — original lines 215–218
- `safe_avg` — original lines 220–222
- `read_tag_value` — original lines 224–226
- `write_predictions_to_pi` — original lines 228–230
- `run_loop` — original lines 232–280

## checkpoint_boiler3.py.txt

**Original:** `.ipynb_checkpoints/V2_B3_scc_deployment-checkpoint.py`  
**Public copy:** [reference/multistart/variants/checkpoint_boiler3.py.txt](../reference/multistart/variants/checkpoint_boiler3.py.txt)

Related multistart optimizer and boiler-specific API mappings.

**Limitations:** Mappings are anonymized; not a verified operational release.

**Static status:** Parses (static check only; not executed).

**Functions/classes:**

- `Utkal_Boiler_B3` — original lines 16–498
- `__init__` — original lines 17–81
- `load_model` — original lines 83–85
- `objective` — original lines 87–89
- `air_to_fuel_ratio` — original lines 91–92
- `scc_constraint` — original lines 94–95
- `validate_solution` — original lines 97–98
- `multi_start_optimization` — original lines 100–123
- `initialize_tags` — original lines 126–185
- `safe_avg` — original lines 188–193
- `_get_batch_url` — original lines 195–197
- `_batch_fetch` — original lines 199–238
- `read_tag_value` — original lines 240–276
- `write_predictions_to_pi` — original lines 278–300
- `run` — original lines 303–341
- `run_loop` — original lines 343–498
