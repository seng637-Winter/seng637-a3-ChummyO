## Range.Intersect

![man_flow_1](Data_flow_graph_Range_class.png)

#### Def-Use sets per statement
| | |
|:--:|:--:|
| defs: | def(1) = {b0, b1} |
| uses: | use(2) = {b0, this.lower} |
| | use(3) = {b1, this.lower} |
| | use(4) = {b0, b1, this.lower} |
| du-pairs: | for b0: (1, 2), (1, 4) |
| | for b1: (1, 3), (1, 4) |

#### Table 5. DU-Pair per variable
| Variable | Def at node (n) | DCU (v, n) | DPU (v, n) |
|:--:|:--:|:--:|:--:|
| b0 | 1 | {} | {(2, 3), (2, 4)} |
| b1 | 1 | {} | {} |

Total
CU = 0
PU = 2

#### Table 6. DU-Pair Coverage
| | |
|:--:|:--:|
| Test Case | DU-pairs covered |
| intersectsWithBLBAndLB | dpu {(2, 3), (3, END)} |
| intersectsWithBLBAndALB | dpu {(2, 3), (3, END)} |
| intersectsWithBLBAndAUB | dpu {(2, 3), (3, END)} |
| intersectsWithLBAndALB | dpu {(2, 3), (3, END)} |
| intersectsWithLBAndUB | dpu {(2, 3), (3, END)} |
| intersectsWithNormalAndNormal | dpu {(2, 4), (4, END)} |
| intersectsWithBUBAndUB | dpu {(2, 4), (4, END)} |
| intersectsWithBUBAndAUB | dpu {(2, 4), (4, END)} |
| intersectsWithUBAndAUB | dpu {(2, 4), (4, END)} |
| intersectsWithInputAUBAndMAX | dpu {(2, 4), (4, END)} |
| intersectsWithInputBLBAndMIN | dpu {(2, 3), (3, END)} |
| intersectsWithInputNaNAnd1 | dpu {(2, 4), (4, END)} |

Total
CU<sub>c</sub> = 0
PU<sub>c</sub> = 4
