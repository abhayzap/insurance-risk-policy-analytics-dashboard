# Insurance Risk & Policy Analytics Dashboard

An interactive Power BI dashboard that analyzes customer demographics, risk profiles, claims, and communication preferences for an insurance business.

**Tools:** Power BI Desktop (Power Query, DAX), Excel
**Data:** [Insurance Claims and Policy Data (Kaggle)](https://www.kaggle.com/datasets/ravalsmit/insurance-claims-and-policy-data), a synthetic dataset

---

## Business Problem

Insurers need to understand who their customers are, which customers carry more risk, and how best to reach them. This dashboard answers three questions:

1. How do customer demographics relate to premiums and the insurance products they own?
2. How do credit score, risk level, and life events relate to claims?
3. How do customers prefer to be contacted (channel, time, language)?

## Dataset

Synthetic data split across five CSV files, modeled in Power BI:

| Table | Contents |
|---|---|
| Customer_data | Age, gender, marital status, occupation, education, income, location |
| Policy_data | Policy type, start/renewal date, premium, coverage, deductible, products owned |
| Claims_data | Claim history, previous claims |
| Risk_and_Segmentation | Credit score, risk label, driving record, life events |
| Preferences_data | Preferred channel, contact time, language |

## Approach

1. **Extract:** imported the CSV files into Power BI.
2. **Transform (Power Query):** cleaned headers, standardized formats, removed duplicates and nulls, and created calculated columns (Product Count, RiskColor, Age Group).
3. **Model:** built a star-style model around `Customer_ID` with one-to-many relationships and a `CreditGroupSort` table for ordering credit score bands.
4. **Visualize:** built three report pages with slicers and custom tooltips.

## Dashboard Pages

### 1. Customer Demographics & Premium Trends
![Demographics page](images/How%20Do%20Customer%20Demographics%20Influence%20Insurance%20Choices.png)

- Average premium is nearly flat across age groups (about 3,000 each).
- Entrepreneurs, managers, and salespeople have the highest average premiums; lawyers and doctors the lowest.
- Product mix by education level is fairly similar across groups.

### 2. Risk & Claims Insights
![Risk and claims page](images/Identify%20how%20customer%20risk%20levels%20impact%20insurance%20claims.png)

- Claim counts fall sharply in the 800+ credit score band.
- Marriage and job change are the most frequent life events across all risk levels.
- Risk label distribution by credit score band (see caveats below).

### 3. Communication Preferences
![Communication page](images/Screenshot%202026-10-04%20183931.png)

- Preferred channel by age group, preferred contact time, and language by gender.

## Key Insights

> Replace or confirm each with the exact numbers from your dashboard.

- Age has little effect on average premium; occupation shows more variation.
- Customers in the 800+ credit band file far fewer claims in absolute terms.
- Younger customers (18-35) lean toward email and text; older groups use mail and phone more.
- "Weekends" and "Morning" are the most preferred contact times; only about 13% choose "Anytime".

## Limitations

- The data is synthetic, so patterns may not reflect real insurance portfolios.
- Claim counts are absolute, not rates. Bands with fewer customers (such as 800+) will naturally show fewer claims.
- Predictive modeling and real-time data are out of scope for this version.

## Repository Structure

```
├── README.md
├── dashboard/     policy final.pbix
├── data/          source CSVs or a link to Kaggle
├── images/        dashboard screenshots
└── docs/          report and presentation (PDF)
```

## How to View

1. Download `dashboard/policy final.pbix`.
2. Open it in Power BI Desktop (Windows).
3. If prompted, point the data source to the CSV files in `data/`.

## Documentation

- [Design report (PDF)](docs/Policy%20Doc.pdf)
- [Presentation (PPTX)](docs/Insurance%20Risk%20%26%20Policy%20Analytics%20Dashboard.pptx)

## Future Work

- Add a claim prediction model.
- Show claim rate (claims per customer) by credit band and risk level.
- Add automated alerts for high-risk segments.

## Author

**Abhay Singh Thakur**
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/)
