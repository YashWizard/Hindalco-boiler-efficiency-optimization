# Mathematics as implemented

This is a transcription of historical code behavior, not a certified boiler calculation standard. Units and dimensional consistency must be checked before using these equations operationally.

## Heat losses

Let dT = Tfg - Tair and dh = SteamEnthalpy - FeedwEnthalpy.

```text
L1  = 100 * Mdfg * 0.24 * dT / GCV
L2  = TM * (584 + 0.45*dT) / GCV
L3  = 8.937 * H2 * (584 + 0.45*dT) / GCV
L4  = 100 * AF * AAS * 0.45 * dT / GCV
L5  = 0.02
L6  = 1.13
L7  = (ASH*15/100) * 10 * 8077 / (100*GCV)
L8  = (ASH*80/10000) * 0.23 * dT * 100 / GCV
L9  = (ASH*20/10000) * 0.23 * dT * 100 / GCV
L10 = 0.65
L11 = (0.8*MakeUpWater*300 + 0.2*MakeUpWater*150)*100
      / (SteamGen*dh/0.85)
L12 = RejectQuality*RejectGCV*100
      / (SteamGen*dh*1000/0.85)
Total = sum(L1 ... L12)
```

The labels are dry flue gas, moisture in fuel, hydrogen in fuel, moisture in air, partial combustion, unburnt ESP, unburnt bottom ash, sensible ESP, sensible bottom ash, radiation, blowdown and mill rejection respectively. `CO2` and `ESP_ASH` are candidate variables with no effect in this implementation. `self.C` is declared but not used in the fixed partial-combustion term.

The efficiency objective constructs a feature vector from some computed losses and some independent candidate inputs, then returns negative model prediction. Independent mill-rejection/blowdown/radiation feature values are not equated to their computed counterparts.

Explicit inequalities in that formulation are:

```text
Tfg - Tair >= 10
AAS / Mdfg >= 1.5
TM >= H2
```

## SCC formulations

SCC is explicitly calculated as coal_flow / steam_flow in the ratio optimizers. This ratio should be given physical units only after confirming the source flow units. Several print labels are inconsistent; a displayed label is not a unit-conversion specification.

The 14-feature model-maximization family uses coal index 9 and steam index 6. Direct-SCC alternatives use coal index 7 and steam index 4. Do not interchange the feature orders.

The constraint form passed to SLSQP is g(x) >= 0. Therefore `maximum_scc - coal/steam` implements an upper limit. The target-distance variant minimizes `abs(coal/steam - target_scc)`; the constant-target branch computes coal algebraically and does not solve an optimization problem in its main cycle.

## Numerical boundaries

Multistart is repeated local search, not a proof of global optimality. A successful solver status is not physical validation. A tree-based predictor may have flat regions under finite-difference perturbations, which requires numerical assessment before interpreting an optimizer result. No such assessment was executed during this packaging task.
