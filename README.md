## Final Applied Lab

The Final Applied Lab (FAL) is DAT300's team capstone: 25% of your grade. Your team picks one of four business scenarios, each built on a real organization's real data
(not a simulated dataset), works through the full pipeline you've practiced all semester (ingest, clean, explore, model or forecast), and delivers a written report and a presentation with a business recommendation.

Each session from here opens with a short concept intro (Databricks AutoML, then MLflow) before team work time. You don't need to know any of those tools yet; each gets introduced right before you'd use it. Forecasting is a reading assignment instead of an in-class presentation — see Canvas.

### Team formation

Teams are 2-3 students, self-organized. 
### The four scenarios

1. **Telecom Customer Churn (Marketing)**: real data from a telecom
   provider, 7,043 customers. Predict churn, find what drives it, and/or
   segment customers by plan/usage — pick at least two. See
   `scenario1-telco-marketing/scenario-brief.md`.
2. **Rossmann Store Sales (Operations)**: real daily sales from a German
   drugstore chain, 1,115 stores. Forecast demand, segment stores,
   and/or predict sales performance — pick at least two. See
   `scenario2-rossmann-operations/scenario-brief.md`.
3. **LendingClub Loans (Finance)**: real loan data from a peer-to-peer
   lender, 293,105 loans issued in 2016. Predict default, predict
   interest rate, and/or segment borrowers by risk — pick at least two.
   See `scenario3-lendingclub-finance/scenario-brief.md`.
4. **Hospital Readmissions (Healthcare)**: real de-identified clinical
   data from 130 US hospitals, 101,766 diabetic patient encounters.
   Predict 30-day readmission, find what drives it, and/or segment
   patients by risk — pick at least two. See
   `scenario4-hospital-healthcare/scenario-brief.md`.

Each scenario's data is here on this template repository.

After we decide on a team name and randomly assign scenarios, I will create a team repository from this template. At which point you will have access to everything. 

### Working as a team

Your team's code lives in a shared GitHub repository, not in separate individual notebooks. The instructor maintains one template repo in the class GitHub organization; your team's repo is created from that template and your team is added to it before team work time starts —
you don't need to create or configure anything yourself.

Each teammate still has their own individual Free Edition Databricks account; there's no shared Databricks workspace. To collaborate, each team member connects their own Databricks workspace to the team's GitHub repo using Databricks Git folders (Repos), clones it, and pushes/pulls through GitHub to stay in sync with teammates — the usual
pattern for a software team, just with everyone on separate Databricks accounts. 
Report and presentation slides are not part of the repo; submit those separately through Canvas.

### Deliverables

- **Written report** Your business question, what you did with the data, what you found, and your recommendation. Write it for someone who doesn't code, same audience as every lab's business-language write-up sections this semester.
- **Presentation** (8-10 minutes + 2-3 minutes of questions:) your findings and recommendation, presented to the class.

A fill-in template for both deliverables, with a pre-submission checklist, is in `fal-report-template.md`. Full grading breakdown in
`fal-rubric.md`.

### Key dates

| Date | What |
|---|---|
| Mon, Nov 9 (Session 11) | Form your team, pick + get your scenario approved, then start ingesting/cleaning your data |
| Mon, Nov 16 (Session 12) | Databricks AutoML/ML library intro, then work time |
| Mon, Nov 23 (Session 13) | MLflow intro, then work time |
| Mon, Nov 30 (Session 14) | Finish your work, submit your report, present to the class |
