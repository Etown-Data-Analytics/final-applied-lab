# DAT300 Final Applied Lab Grading Rubric

Total: 100 points (25% of course grade). Team grade; every member of a team receives the same grade unless a team flags an uneven contribution to the instructor.

| Component | Item | Pts |
|---|---|---:|
| Data work | Ingestion and cleaning: raw data read correctly, each data-quality issue in the scenario brief identified and handled with a stated, defensible rule | 15 |
| Data work | Exploratory analysis: relevant distributions/relationships examined before modeling, not skipped | 10 |
| Modeling | At least 2 of the scenario brief's business-question types are addressed (e.g., a predictive model and a segmentation, or a forecast and a driver analysis); each technique fits its question and is correctly applied with a train/test split or equivalent validation where relevant | 20 |
| Modeling | Results evaluated against a meaningful baseline (e.g., majority-class accuracy, a naive forecast), not reported in isolation | 10 |
| Business translation | Findings translated into plain business language, not left as raw model output | 10 |
| Business translation | Recommendation is specific and actionable, tied directly to the findings | 10 |
| Report | Written report is clear, organized, and readable by someone who doesn't code; 4-6 pages | 10 |
| Presentation | Presentation is clear, fits the 8-10 minute window, and the team answers questions well | 15 |

## What "good" looks like, by component

- **Ingestion and cleaning**: every issue named in the scenario brief (duplicates, blanks, the specific quirk unique to that scenario) is addressed, with the team's chosen rule stated rather than silently applied. More importantly, document all cleaning done to the data.

- **Modeling**: the technique matches the question, and the team covers at least 2 of the 3 business-question types in their scenario brief (not just one). A team  predicting a yes/no outcome should be doing classification, not clustering; a team asking "what will next quarter look like" should be forecasting or at least looking at a time series, not just a static snapshot. Teams are not required to use every technique from the semester, but should use the right one for each question they pursue and not force a technique that doesn't fit.
- **Baseline comparison**: a result only means something next to a reasonable alternative. "74% accuracy" means nothing on its own; "74% accuracy against a 71% majority-class baseline" is definitely and improvement.
- **Business translation**: a coefficient, a cluster centroid, or a forecasted number is not a recommendation by itself. "Customers in this segment are 3x more likely to cancel" is a finding; "target this segment with a retention offer before their renewal date" is the recommendation that finding supports.

## Common issues to watch for

- A model's accuracy reported without a baseline to compare it to.
- A report or presentation that stops at "here's what the model found" without a recommendation.
- An uneven team contribution
