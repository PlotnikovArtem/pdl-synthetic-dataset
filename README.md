# PDL synthetic dataset

Synthetic (fully made-up) data of a fictional microfinance lender issuing short-term PDL loans, Jan–Sep 2026.
No real people, companies or loans. Intended for pandas / analytics exercises.

| file | rows | one row = |
|---|---|---|
| `applications.csv` | 31 750 | loan application (`raw_bki` — credit bureau response, JSON string) |
| `loans.csv` | 17 978 | issued loan |
| `payments.csv` | 19 157 | payment on a loan (a loan may have several or none) |

```python
import pandas as pd
BASE = "https://raw.githubusercontent.com/PlotnikovArtem/pdl-synthetic-dataset/main/"
apps  = pd.read_csv(BASE + "applications.csv", parse_dates=["app_dt"])
loans = pd.read_csv(BASE + "loans.csv", parse_dates=["issue_dt", "due_dt"])
pays  = pd.read_csv(BASE + "payments.csv", parse_dates=["pay_dt"])
```
