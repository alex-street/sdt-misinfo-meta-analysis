# sdt-misinfo-meta-analysis
Code and tutorial for SDT meta analysis of misinformation interventions

## Formatting
### Long format
Format your individual studies so that they are in long format, with the following columns:
- `id`: the ID of the participant (i.e., study_pid)

### Re-format

- `pid`: the globally unique ID of the participant

### 

## Analysing Individual Studies
Formulas follow the syntax `response | aterms ~ pterms + (gterms | group)`, where `pterms` are fixed effects (assumed to be the same across observations), `gterms` are group-level effects (assumed to vary across grouping variables specified in `group`)

### Within Subject Comparison
```
study_formula <- bf(
  response ~ stimulus * time +                      # defines stimulus x time as the fixed effects
    (stimulus * time | pid)                         # partially pools the

brms (
)

```
### Between Subject Comparison

## Analysing Groups of Studies

> For all ordinal families, aterms may contain a term thres(number) to specify the number thresholds (e.g, thres(6)), which should be equal to the total number of response categories - 1. If not
given, the number of thresholds is calculated from the data. If different threshold vectors should be used for different subsets of the data, the gr argument can be used to provide the grouping variable 46 brmsformula (e.g, thres(6, gr = item), if item is the grouping variable). In this case, the number of thresholds can also be a variable in the data with different values per group.

```
formula <- bf(
  response | weight(n) | thres(gr = study)          # weights the 
    ~ stimulus * time +                             # defines stimulus x time as the fixed effects
    (stimulus * time | pid)                         # partially pools the

brms (
)

```
