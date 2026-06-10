# Enhancing Urban Forestry Planning with an AI-Powered Tree Canopy DSS

This project builds a simple Decision Support System (DSS) for urban forestry planning in the Kitchener-Waterloo area. The goal is to help city planners understand tree canopy coverage, heat risk, maintenance needs, and possible equity concerns.

## Project Files

| File | Purpose |
| --- | --- |
| `Case_Study_Canopy.docx` | Written case study report |
| `Assignment_1.docx` / `Assignment_1.pdf` | Main written assignment report |
| `Assignment_1.ipynb` | Main Python notebook and program |
| `datasets/` | Source data files used in the analysis |
| `img/` | Charts and model output images |
| `Enhancing-Urban-Forestry-Planning-with-an-AI-Powered-Tree-Canopy-DSS.pptx` | Presentation slides |

## Data Sources

The project uses open data related to:

- Street tree inventory data from Waterloo
- Tree inventory data from Kitchener
- Tree canopy data from Kitchener
- 2021 census boundary files
- Environmentally Sensitive Policy Area (ESPA) data

## What The Notebook Does

The main program is `Assignment_1.ipynb`. It includes:

1. Merging Waterloo and Kitchener tree inventory data
2. Converting tree data into geospatial format
3. Joining tree data with census tract boundaries
4. Creating DSS metrics, such as:
   - total trees
   - large trees with `DBH > 45cm`
   - estimated canopy coverage
   - ESPA indicator
5. Creating visualizations for:
   - urban heat island risk
   - critical tree maintenance priority
   - canopy equity planning
6. Building a simple linear regression model to estimate annual maintenance cost

## Key Findings

### Urban Heat Island

The scatter plot shows a negative relationship between estimated canopy coverage and simulated summer temperature. Areas with lower canopy coverage usually have higher temperatures. This helps the DSS identify possible **High Priority Zones** for future tree planting.

### Budget Allocation

The bar chart shows the top 5 census areas with the most large trees (`DBH > 45cm`). For example, census zones like `0007.00` and `0003.00` have high numbers of large trees. These areas may need more maintenance attention before storm seasons.

### Canopy Equity

The equity dashboard shows how the DSS can compare canopy coverage, heat, and socio-economic conditions. Areas in the **Critical Need** quadrant have lower socio-economic index scores and lower canopy coverage. These areas can be considered first when planning future tree planting.

## Model Summary

The notebook builds a linear regression model:

```text
Annual Maintenance Cost = 60,650 + 1,197 * Critical Trees
```

The model output is:

- Intercept: about `$60,650 CAD`
- Cost per critical tree: about `$1,197 CAD`
- R-squared: about `0.9996`

This model is useful as a planning prototype. However, the maintenance cost is simulated, so the model should be tested with real municipal budget data before being used for real decisions.

## Important Notes

- `Canopy_Coverage_Pct` is an estimated value based on tree counts.
- `Surface_Temperature_C` is simulated from canopy coverage.
- `Socio_Economic_Index` is simulated for the dashboard.
- `DBH > 45cm` is used as a simple rule to identify large or aging trees. It does not prove that every tree is dangerous.
- The DSS results should be used as a planning example, not as final city policy.

## How To Run

1. Open `Assignment_1.ipynb`.
2. Make sure the `datasets/` folder is in the same project directory.
3. Run the notebook cells from top to bottom.
4. The output charts will be saved in the `img/` folder.

Required Python libraries include:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
geopandas
shapely
```

## Project Purpose

This project shows how AI and data analytics can support better urban forestry planning. It helps connect environmental data with business decisions, such as planting priority, maintenance budget planning, and long-term canopy management.
