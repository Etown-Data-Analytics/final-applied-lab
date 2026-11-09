# Scenario: LendingClub Loans (Finance)

This is real loan data from LendingClub, a peer-to-peer lending company, scoped to loans issued in 2016 whose outcome is known (paid off, charged off, or defaulted). Leadership wants a better handle on who's likely to default, whether the interest rate borrowers get actually
lines up with their risk, and whether borrowers break into meaningful risk groups.

## Business questions (address at least 2 of these 3, not just one)

- What borrower characteristics predict default, and how good is a  model built on them compared to just guessing the majority outcome?
- Does the interest rate a borrower gets line up with their
  creditworthiness? What would you predict a fair rate to be from their characteristics?
- Can you group borrowers into meaningful risk tiers, and recommend a  different lending policy for each?

These are a starting point, not an exhaustive menu. If your team has a sharper question grounded in this data, or wants to push further (extra engineered features, more than one model compared, outside data brought in), go for it — just make sure it's still answerable with what's here,
and run it by the instructor for approval.

## Data

Source: [LendingClub loan data](https://www.kaggle.com/datasets/wordsforthewise/lending-club)
(via Kaggle; full dataset covers accepted loans 2007-2018, scoped here
to loans issued in 2016).

One file, `loans_2016.csv` (`lendingclub_data.zip` on Canvas), 293,105
loans issued in 2016 with a known final outcome.

| Column | Meaning |
|---|---|
| `id` | Unique loan identifier |
| `loan_amnt`, `term`, `installment` | Loan amount, term in months, monthly payment |
| `int_rate` | Interest rate (percent) |
| `grade`, `sub_grade` | LendingClub's own risk grade (A = safest, G = riskiest) |
| `emp_length`, `home_ownership`, `annual_inc` | Borrower employment/income info |
| `verification_status` | Whether income was verified |
| `issue_d` | Month/year the loan was issued |
| `loan_status` | Fully Paid, Charged Off, or Default, the raw outcome |
| `purpose` | What the loan was for |
| `addr_state` | Borrower's US state |
| `dti` | Debt-to-income ratio |
| `delinq_2yrs` | Delinquencies in the past 2 years |
| `earliest_cr_line` | Date of borrower's earliest credit line |
| `fico_range_low`/`high` | Borrower's FICO score range |
| `inq_last_6mths` | Credit inquiries in the last 6 months |
| `open_acc`, `total_acc` | Number of open/total credit accounts |
| `pub_rec` | Number of derogatory public records |
| `revol_bal`, `revol_util` | Revolving credit balance and utilization |

## Known data-quality quirks

This is real data, not cleaned for you. At minimum: `emp_length` has a substantial number of blank values, `dti` and `revol_util` have a smaller number of blanks, and `loan_status` is the raw text outcome, not a 0/1 flag, you'll need to derive your own default flag from it (Charged Off and Default both count as a default; decide how you treat each, and state your rule).