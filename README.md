[README.md](https://github.com/user-attachments/files/29777288/README.md)
# Steel Manufacturing RSS Dataset for Collaborative Manufacturing

This repository provides a steel manufacturing resource-service sequence (RSS) dataset for feature dependency tracing and key feature sequence (KFS) identification in collaborative manufacturing.

The dataset is organized according to a cross-organizational collaborative manufacturing workflow. It links upstream procurement resource-service features, manufacturing and alloy features, quality-inspection features, and downstream sales/market features. It is intended to support research on workflow-compliant feature dependency tracing, directed dependency graph construction, and KFS identification under collaborative manufacturing scenarios.


## Dataset File

| File | Sheet | Rows | Columns | Description |
| --- | --- | ---: | ---: | --- |
| `steel.xlsx` | `steel_data` | 5,657 | 28 | Steel manufacturing RSS dataset containing procurement, manufacturing, quality-inspection, and sales/market features. |

File checksum:

```text
SHA256: B4B15A7A944BADAECBC422868B7086DF1FAA9E3A49B64CA958CCE35E98352C73
```


## Dataset Context

In the associated study, a collaborative manufacturing task is treated as the ordered execution of workflows across different organizations. Resource services are arranged into a resource-service sequence (RSS), and each resource service is characterized by measurable feature values. The dependencies among these features form workflow-compliant upstream-downstream relationships.

Taking steel manufacturing as the application scenario, the dataset describes an RSS involving four major resource-service stages:

| RSS stage | Role in the collaborative workflow | Feature group |
| --- | --- | --- |
| Procurement | Upstream resource and supplier-related conditions | order quantity, cost, supplier stability, supplier premium, supplier risk |
| Manufacturing | Alloy composition and processing conditions | alloying elements and heat-treatment temperature |
| Quality inspection | Product quality and mechanical-performance indicators | strength, ductility, impact toughness, fracture toughness |
| Sales | Downstream commercial and market-response indicators | demand, competition, bulk discount, selling price target |

This structure allows researchers to evaluate whether upstream resource-service features influence downstream quality or market outcomes, and whether the resulting feature paths can be identified as key feature sequences.

## Variable Description

### Procurement Resource-Service Features

| Column | Description |
| --- | --- |
| `qty` | Signed quantity. |
| `cost` | Input cost. |
| `supplier_stability` | Supplier reliability/stability index. |
| `supplier_premium` | Supplier cost premium index. |
| `supplier_risk` | Supplier risk index. |

### Manufacturing Resource-Service Features

All alloy composition variables are reported as weight percentages.

| Column | Description |
| --- | --- |
| `C` | Carbon content, wt%. |
| `Mn` | Manganese content, wt%. |
| `Si` | Silicon content, wt%. |
| `Cr` | Chromium content, wt%. |
| `Ni` | Nickel content, wt%. |
| `Mo` | Molybdenum content, wt%. |
| `V` | Vanadium content, wt%. |
| `N` | Nitrogen content, wt%. |
| `Nb` | Niobium content, wt%. |
| `Co` | Cobalt content, wt%. |
| `W` | Tungsten content, wt%. |
| `Al` | Aluminum content, wt%. |
| `Ti` | Titanium content, wt%. |
| `temp` | heat-treatment temperature, in degrees Celsius. |

### Quality-Inspection Resource-Service Features

| Column | Description |
| --- | --- |
| `YS` | Yield strength, MPa. |
| `UTS` | Ultimate tensile strength, MPa. |
| `EL` | Elongation, %. |
| `Charpy` | Charpy impact energy, J. |
| `KIC` | Fracture toughness, MPa*m^0.5. |

### Sales and Market Features

| Column | Description |
| --- | --- |
| `demand` | Market demand index. |
| `competition` | Competition index. |
| `bulk_discount` | Bulk discount index. |
| `price` | Selling price target. |

## Basic Statistics

The published workbook contains 5,657 complete records and no missing values in the `steel_data` sheet. All 28 variables are numeric.

| Feature group | Number of columns | Columns |
| --- | ---: | --- |
| Procurement | 5 | `qty`, `cost`, `supplier_stability`, `supplier_premium`, `supplier_risk` |
| Manufacturing | 14 | `C`, `Mn`, `Si`, `Cr`, `Ni`, `Mo`, `V`, `N`, `Nb`, `Co`, `W`, `Al`, `Ti`, `temp` |
| Quality inspection | 5 | `YS`, `UTS`, `EL`, `Charpy`, `KIC` |
| Sales/market | 4 | `demand`, `competition`, `bulk_discount`, `price` |

## How to Load the Dataset

Python:

```python
import pandas as pd

df = pd.read_excel("steel.xlsx", sheet_name="steel_data")
print(df.shape)
```

R:

```r
library(readxl)

df <- read_excel("steel.xlsx", sheet = "steel_data")
dim(df)
```

## Suggested Use

This dataset can be used for:

- feature dependency tracing in collaborative manufacturing;
- key feature sequence identification;
- workflow-compliant upstream-downstream dependency analysis;
- directed dependency graph construction;
- evaluation of FFC-SHAP or related explainable machine-learning methods;
- comparison with feature selection, service-composition, or dependency-mining methods.

## Citation

If you use this dataset, please cite the associated paper and this repository.

```bibtex
@misc{steel_manufacturing_rss_dataset_2026,
  title  = {Steel Manufacturing RSS Dataset for Collaborative Manufacturing},
  author = {TODO: Add author names},
  year   = {2026},
  url    = {TODO: Add GitHub repository URL},
  note   = {Excel dataset, sheet steel_data}
}
```


## Notes
- The dataset is intended for research use in collaborative manufacturing and resource-service sequence analysis.
