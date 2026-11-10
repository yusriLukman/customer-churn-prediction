# E-Commerce Customer Churn Prediction

## Project brief

**Business question:** Which customers are most likely to churn, and which of
them should a retention team contact first when the budget is limited?

**Intended users:** A CRM / retention team at an e-commerce company.

**Primary metrics:**
- Model comparison: PR-AUC (about [X]% of customers churn, so accuracy is misleading).
- Decision quality: expected net value at the chosen threshold, based on explicit
  cost assumptions.

**Trade-off:** Catching more churners (higher recall) means contacting more loyal
customers by mistake (lower precision). The threshold is chosen from cost
assumptions, not from a default value.

**Evaluation plan (fixed before modeling):** a 20% stratified hold-out set is
locked and used once at the end. Model selection uses repeated stratified
cross-validation on the training set only.

**Known limitations (to be updated):** [snapshot data / no timestamps / customer
ID available or not], and the dataset's origin is not fully documented.
