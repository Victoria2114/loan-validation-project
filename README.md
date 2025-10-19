# loan-validation-project
Loan Offers Validation & Business-Rules Analysis

This project analyzes two real-world datasets to identify system bugs and rule violations in a lending pipeline.

Datasets used:

offers.parquet: multiple loan offers per applicant; task: identify requests outside offered amounts.

business_rules_validation.parquet: approved loans with loan term, rate, credit score, state; task: check credit score bounds, state-specific rate caps, and monotonic interest rates.

Key findings:

All requested amounts in task 1 fell outside the offered option list → a critical UX/logic bug.

In task 2, 50+ credit-score violations, 9 state-rate violations and 12 monotonic-rate violations were detected (total 71 broken approvals).

Recommendation:

Validate requested amounts against available options before submission.

Enforce business-rules during approval, not after.

Built with Python & pandas.

