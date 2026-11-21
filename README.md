# The Macroeconomic Impact of the 2026 Gulf Crisis
### Evidence from Turkey, Poland and South Africa | Panel Data Econometrics

## Research question
Did the 2026 Gulf Crisis, and the oil price shock that came with it, increase inflationary pressure in emerging net-importing economies?

## Data
- **Countries:** Turkey, Poland, South Africa (balanced panel)
- **Period:** monthly, January 2023 to mid-2026
- **Variables:**
  - CPI (consumer price index), used as the inflation measure
  - IPI (industrial production index)
  - Policy interest rate
  - VIX index, as a proxy for global financial uncertainty
  - Brent crude oil price
  - Post-crisis dummy (1 during the crisis period, 0 otherwise)

## Methodology
- Dependent variable: log of CPI
- Explanatory variables: policy interest rate, VIX, post-crisis dummy
- Estimators compared: **Pooled OLS, Fixed Effects (FE), Random Effects (RE)**
- Model selection:
  - **Hausman test** (FE vs RE)
  - **Breusch-Pagan LM test** (pooled vs panel models)
- Robust standard errors to account for heteroskedasticity and autocorrelation
- Tools: R [add the packages you used, e.g. plm, ggplot2]

## Results

| Variable | Pooled OLS | Fixed Effects | Random Effects |
|---|---|---|---|
| Interest rate | 0.0484 (p < 0.001) | 0.0183 (p < 0.001) | 0.0196 (p < 0.001) |
| VIX | 0.0117 (p = 0.148) | 0.0071 (p = 0.131) | 0.0073 (p = 0.144) |
| Post-crisis dummy | 0.1882 (p = 0.039) | 0.1893 (p = 0.076) | 0.1893 (p = 0.079) |

**Model selection**

| Test | Statistic | p-value | Conclusion |
|---|---|---|---|
| Hausman | 5.822 | 0.1206 | Random Effects preferred |
| Breusch-Pagan | 196.82 | < 0.001 | Pooled OLS rejected |

## Key findings
- **Random Effects is the preferred model.** The Hausman test does not reject it, and the Breusch-Pagan test rejects pooled OLS, so country-specific effects matter.
- **Interest rates are positively and strongly associated with inflation (p < 0.001) in all three models.** This most likely reflects central banks tightening in response to rising prices, not interest rates causing inflation.
- **The post-crisis dummy is positive in all three models** (about 0.19 log points). It is significant at the 5% level in pooled OLS and at the 10% level in FE and RE, so the evidence of a crisis effect is suggestive rather than strong.
- **VIX is not significant in any model**, so global uncertainty shows no direct effect on inflation in this sample.
- **Countries differ a lot.** Turkey has by far the highest and fastest-rising CPI, Poland is stable, and South Africa shows a sharp decline in industrial production.

## Figures
Brent crude rose sharply in early 2026 after the crisis began, while CPI and industrial production followed very different paths across the three countries. See the figures in `tables_and_graphs_.pdf`.

## Limitations
- Only 3 countries and a short time window, which limits statistical power.
- The post-crisis dummy captures any change after the crisis began, not only the oil shock.
- The model explains the CPI level and does not control for country-specific trends, which matter especially for Turkey.

## Files
- `advanced_econometrics_report_.pdf`: full report (introduction, methodology, results, discussion, conclusion)
- `tables_and_graphs_.pdf`: descriptive statistics, estimation tables, model selection tests and figures
- [add your R script here, e.g. `analysis.R`]

## Team
Group project for Advanced Econometrics at Tunis Business School.
Ranim Khaskhoussi, Fedi Feki, Majd Kahri, Rissen Guermazi
Instructor: Dr. Naceur Khraief
