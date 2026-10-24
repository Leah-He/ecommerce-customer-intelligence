# Power BI — Technical Showcase

Selected evidence from an archived multi-platform e-commerce analytics project developed during an internship in China. The original reports and diagrams use Chinese-language labels.

## Reporting samples

### Customer segmentation
![Customer value reporting](02_customer_segmentation_report.png)

Segment summary, customer value distribution, and drill-down navigation. The customer-level table has been excluded from this public excerpt.

### Product analytics
![Product analytics](03_product_analytics_report.png)

Category filtering, ABC classification, and sales and order trends.

### Retention risk monitoring
![Retention risk analytics](04_retention_risk_report.png)

Aggregated indicators of at-risk customer groups, repeat purchasing and recall priorities.

## Data relationships

![Power BI model relationships](01_data_relationships.png)

The archived Power BI model includes six active relationships connecting customer, order, product, family and risk-analysis tables. Five are many-to-one and one is many-to-many. The many-to-many relationship should be reviewed for ambiguous filters or double-counting risks; this is **not claimed to be a perfect star schema**.

## Implementation notes

- [DAX measures and RFM scoring](dax_measures.md) — observed Recency, Frequency and Monetary scoring logic and a revenue-per-customer KPI.
- [Selected Power Query M transformations](power_query.md) — identifier fallback, product composite keys, and type standardization.

## Availability and confidentiality

Only selected visual excerpts and technical documentation are included. Underlying datasets, client records, and the original PBIX are not included. Some source files and development dependencies are no longer available. Screenshots reflect historical report states, not a live deployment or independent verification of outcomes. The excerpts contain aggregated commercial information; publication remains subject to the original owner's permission.
