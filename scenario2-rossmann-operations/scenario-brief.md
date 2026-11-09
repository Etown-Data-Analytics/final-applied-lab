# Scenario: Rossmann Store Sales (Operations)

This is real daily sales data from Rossmann, a German drugstore chain
with over 1,100 stores. Management wants help understanding sales
patterns and planning ahead: which stores are trending up or down, how
promotions and holidays affect sales, and what to expect next.

## Business questions (address at least 2 of these 3)

- How do sales vary by day of week, promotions, and holidays? What would
  you forecast for a store (or group of stores) going forward?
- What distinguishes high-performing stores from low-performing ones?
- Can you group stores into meaningful segments and recommend a
  different strategy for each?

These are a starting point, not an exhaustive menu. If your team has a
sharper question grounded in this data, or wants to push further (extra
engineered features, more than one model compared, outside data brought
in), go for it — just make sure it's still answerable with what's here,
and run it by the instructor.

## Data

Source: [Rossmann Store Sales](https://www.kaggle.com/c/rossmann-store-sales)
(Kaggle competition data, Rossmann drugstore chain).

Two files (`rossmann_data.zip` on Canvas): `train.csv` (over 1,000,000
rows, one row per store per day, Jan 2013 - Jul 2015) and `store.csv`
(one row per store, 1,115 stores) with store-level attributes.

**`train.csv`**
| Column | Meaning |
|---|---|
| `Store` | Store ID, joins to `store.csv` |
| `DayOfWeek` | 1 (Monday) through 7 (Sunday) |
| `Date` | The sales date |
| `Sales` | That day's sales in Euros (the usual target) |
| `Customers` | Number of customers that day |
| `Open` | 1 if the store was open, 0 if closed |
| `Promo` | 1 if the store was running a promotion that day |
| `StateHoliday` | A letter code if that day was a state holiday, else "0" |
| `SchoolHoliday` | 1 if schools were closed that day |

**`store.csv`**
| Column | Meaning |
|---|---|
| `Store` | Store ID |
| `StoreType`, `Assortment` | Store format and product assortment category |
| `CompetitionDistance` | Distance in meters to the nearest competitor |
| `CompetitionOpenSinceMonth`/`Year` | When the nearest competitor opened |
| `Promo2`, `Promo2SinceWeek`/`Year`, `PromoInterval` | A recurring promotion program some stores participate in |

## Known data-quality quirks

This is real data, not cleaned for you. At minimum: rows where `Open` is
0 have `Sales` of 0 by definition, not a missing-data problem, decide
whether to exclude them from your analysis. There are also a small
number of rows where `Open` is 1 but `Sales` is 0, a genuine anomaly
worth deciding how to handle. `store.csv` has real missing values in the
competition and Promo2 columns (not every store has a known competitor
or participates in Promo2).