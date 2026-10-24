# Power BI DAX — RFM Scoring and KPIs

These formulas were transcribed from the surviving Power BI Desktop project. They are included as **technical examples from the archived report**, not as a reusable model or a predictive churn algorithm.

## Recency (R)

```dax
R_score =
VAR R = [R_days]
RETURN
SWITCH(TRUE(), R <= 30, 5, R <= 90, 4, R <= 180, 3, R <= 365, 2, 1)
```

Higher scores indicate a more recent purchase: at most 30 days = 5; 31–90 = 4; 91–180 = 3; 181–365 = 2; over 365 = 1.

## Frequency (F)

```dax
F_score =
VAR F = [F_count]
RETURN
SWITCH(TRUE(), F >= 10, 5, F >= 5, 4, F >= 3, 3, F >= 2, 2, 1)
```

A customer with 10+ purchases scores 5; 5–9 scores 4; 3–4 scores 3; 2 scores 2; 0–1 scores 1.

## Monetary value (M)

```dax
M_score =
VAR M = [M_total]
RETURN
SWITCH(TRUE(), M >= 5000, 5, M >= 2000, 4, M >= 800, 3, M >= 300, 2, 1)
```

Thresholds (project currency: CNY): at least 5,000 = 5; 2,000–4,999.99 = 4; 800–1,999.99 = 3; 300–799.99 = 2; less than 300 = 1.

## Average sales per customer

```dax
客均消费 = DIVIDE([总销售额], [总客户数], 0)
```

`DIVIDE` provides a fallback of zero when division cannot be performed.

## Interpretation and limitations

- RFM is **rule-based behavioral segmentation**, not a trained churn prediction model.
- The meaning and calculation of `[M_total]` and the reference date for `[R_days]` need to be checked in their upstream definitions before making stronger claims.
- The scores use fixed business thresholds rather than quantiles.
- Missing-value behavior and segment assignments should be validated before operational use.
- The original PBIX and customer-level data are not published.
