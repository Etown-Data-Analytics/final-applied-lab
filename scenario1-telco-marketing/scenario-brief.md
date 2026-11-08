# Scenario: Telecom Customer Churn (Marketing)

This is real customer data from a telecom provider (phone, internet, and
streaming services). Leadership wants to know who is likely to cancel,
what plans and services correlate with sticking around, and whether
customers break into meaningful segments worth treating differently.

## Business questions (address at least 2 of these 3, not just one)

- Which customers are likely to churn, and what distinguishes them from
  customers who stay?
- Which contract types, services, or payment methods are associated with
  higher or lower churn?
- Can you group customers into meaningful segments and recommend a
  different retention action for each?

These are a starting point, not an exhaustive menu. If your team has a
sharper question grounded in this data, or wants to push further (extra
engineered features, more than one model compared, outside data brought
in), go for it — just make sure it's still answerable with what's here,
and run it by the instructor during scenario approval.

## Data

One file, `telco_churn.csv` (`telco_data.zip` on Canvas), one row per
customer, 7,043 customers.

| Column | Meaning |
|---|---|
| `customerID` | Unique customer identifier |
| `gender`, `SeniorCitizen`, `Partner`, `Dependents` | Customer demographics |
| `tenure` | Months the customer has been with the company |
| `PhoneService`, `MultipleLines` | Phone service details |
| `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies` | Which services the customer has |
| `Contract` | Month-to-month, one year, or two year |
| `PaperlessBilling`, `PaymentMethod` | Billing details |
| `MonthlyCharges`, `TotalCharges` | Dollar amounts |
| `Churn` | Yes/No, whether the customer left |

## Known data-quality quirks

This is real data, not cleaned for you. At minimum: `TotalCharges` looks
numeric but is stored as text, and a handful of rows have a blank value
in it (customers with 0 months of tenure, who haven't been charged yet).
Decide how you'll handle that column and state your rule.

## Where this connects to what you've learned

`Churn` is a classification target with a realistic (not 50/50) class
split, about 27% churn, so a majority-class baseline comparison matters
here too. Grouping customers by tenure/charges/services uses the same
clustering skills, applied fresh to this data.
