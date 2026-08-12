# # Mining the Unbanked

## Mining Financial Inclusion: Who Gets Left Out of Banking in East Africa?

23,524 adults surveyed across **Kenya, Rwanda, Tanzania and Uganda**
(FinScope surveys via the Zindi *Financial Inclusion in Africa* challenge).
Only **14.1%** have a bank account **Kenya leads at 25.1%**. The project
mines who is included, who is excluded, and predicts it per household.

## How to run (tested end to end)

```bash
pip install -r requirements.txt
```

## Layout
```
data/raw/        financial_inclusion_train.csv  (23,524 x 13, zero missing)
data/processed/  clean mart, SQLite star-schema warehouse, rules, segments, results
notebooks/DSA2040_full_project.ipynb   THE WHOLE PROJECT IN ONE NOTEBOOK:
   Part 1  audit + features + star schema + OLAP mining of the cube
   Part 2  exploration + chi-square / Cramér's V tests
   Part 3  association-rule mining (Apriori vs FP-Growth) + k-means segments
   Part 4  8 ML classifiers, honest accuracy discussion, drivers
   Part 5  the interactive dashboard + live household scorer (widgets)
dashboard/dashboard.html   standalone interactive dashboard (white/pink/coral/gold)
reports/term_paper.docx    the write-up (~2,700 words incl. references)
```

## Headline findings

| Finding | Number |
|---|---|
| Banked: Kenya / Rwanda / Tanzania / Uganda | 25.1% / 11.5% / 9.2% / 8.6% |
| The education staircase | 4.1% (no formal) → 51.1% (tertiary) |
| The phone effect | 18.4% banked with a phone vs 1.7% without |
| Strongest inclusion rule | govt job + phone → 77.7% banked (lift 5.5) |
| Starkest exclusion cell | 675 young phone-less Tanzanians — 0 banked |
| Segments | 4 archetypes, banked rates 1.6% → 53.6% |
| Best model | Random Forest, hold-out ROC-AUC 0.874 (CV 0.856 ± 0.007) |
| Live scorer contrast | Nairobi professional 90% vs off-grid widow 1% |

Source: Zindi, *Financial Inclusion in Africa* (FinScope surveys 2016-2018).
