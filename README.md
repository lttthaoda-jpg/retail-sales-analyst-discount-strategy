# retail-sales-analyst-discount-strategy
Analyzing retail sales data using R &amp; Probit Regression to evaluate discount strategies, identify loss-making orders, and determine safe discount thresholds for Central region.
Do discounts drive loss-making orders, and which discount levels are relatively safe?
Loss-making orders wipe out the equivalent of **34.95%** of the profit earned on profitable orders. In Central, orders discounted 30%+ are 28% of orders but cause 94% of losses.
- **Dataset:** Sample Superstore (simulated), 10,194 transactions (2023–2026)
- **Tools:** R (probit models, average marginal effects), Excel, AI tools (Claude AI)
- **Method:** probit regression (3 models), model validation, observed loss rate by exact discount level, break-even discount
## Repository structure
```
├── Retail_Sales_Analysis_Central_Discount.qmd   # all R code (Quarto)
├── Retail_Sales_Analysis_Central_Discount.md    # rendered, GitHub-friendly output
├── Retail_Sales_Analysis_Central_Discount.html  # rendered, self-contained HTML
├── Retail_Sales_Analysis_Slides_EN.pptx         # slide deck
└── data/
    └── sample_-_superstore.xls                  # sheet "Orders"
```
## How to reproduce
1. Put the Excel file in `data/` (sheet name must be `Orders`; edit `data_path` in the setup chunk if the file name differs).
2. Install packages once:

   ```r
   install.packages(c("readxl", "dplyr", "tidyr", "janitor", "scales", "knitr",
                      "mfx", "pscl", "lmtest", "car", "pROC", "ResourceSelection"))
   ```
3. Render:

   ```bash
   quarto render Retail_Sales_Analysis_Central_Discount.qmd
   ```
The last section of the output, **Reconciliation with the slides**, compares every reproduced number with the value on the slides (`OK` / `CHECK`).
## Read the full project walkthrough on Notion: 
https://large-gauge-ed0.notion.site/Retail-Sales-Analysis-Discount-Strategy-Loss-Risk-in-the-Central-Region-3f770e6c6a9680b8838cd54556d2e2fc 
## Limitations
The dataset is simulated and covers Central only, discount levels are few and tied to sub-categories, so results describe associations, not cause and effect. Pseudo R² (about 0.74) and AUC (about 0.97) are very high because profit is mechanically linked to price, cost and discount.
