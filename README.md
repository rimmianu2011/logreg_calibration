# Logistic Regression & Calibration — FAANG-Level Hands-On

**Goal:** Treat probabilistic outputs as first-class: calibration, class imbalance, thresholding, and metric tradeoffs.

**Outcome:** Students can implement logistic regression predictions, compute calibration diagnostics (reliability curve, ECE), and reason about imbalanced evaluation (PR vs ROC) like a FAANG ML engineer.

---

# How to Start

1. **Fork** this repository.  
2. Open `calibration_student_lab.ipynb` in **Google Colab**.  
3. Complete all **TODO** sections.  
4. **Restart runtime → Run All** cells.  
5. Push changes and submit a **Pull Request**.  

⚠️ **Do NOT edit notebooks directly on GitHub.**

---

## Lab Rules (FAANG Style)

- ✅ Always separate ranking quality (ROC-AUC) from probability quality (calibration)
- ✅ For imbalanced problems, always look at PR-AUC and threshold metrics
- ✅ Use reliability diagrams and ECE as calibration signals
- ✅ Discuss business cost tradeoffs for thresholds

---

# Out of Scope

- scikit-learn calibration utilities (we implement core metrics ourselves)

---

# Notebook Rules

- Do **NOT** rename the notebook  
- Do **NOT** delete TODOs  
- Do **NOT** hardcode outputs  
- Notebook must run **top-to-bottom**  

---

# Dataset

- Synthetic imbalanced binary classification + probability-shift scenarios

## Why?

- Lets us control imbalance and miscalibration
- Mirrors real-world deployment failures

---

## Section 1 — Metrics Refresher (ROC/PR)

### Task 1.1: Implement confusion-matrix metrics

- precision, recall, F1

**Checkpoint Questions:**

- Why can accuracy be misleading under imbalance?

---

### Task 1.2: ROC-AUC vs PR-AUC intuition

**Interview Angle:**

- When is PR-AUC the right metric?

---

## Section 2 — Calibration

### Task 2.1: Reliability curve + ECE

**FAANG Gotcha:**

- A good ROC-AUC model can be poorly calibrated.

---

### Task 2.2: Temperature scaling (simple)

- Fit a single scalar temperature T on a validation split

**Checkpoint Questions:**

- Why does temperature scaling preserve ranking but change calibration?

---

## Section 3 — Thresholding & Costs

### Task 3.1: Choose threshold for a cost function

**Interview Angle:**

- Translate model outputs to business decisions.

---

## Submission Expectations

- Completed notebook
- Short written answers to checkpoint questions
- A short recommendation: metric + threshold for the scenario

---

## FAANG Interview Evaluation Rubric

| Skill                     | Evaluated |
|---------------------------|-----------|
| Metric selection          | ✅        |
| Calibration intuition     | ✅        |
| Threshold reasoning       | ✅        |
| Code correctness          | ✅        |
| Explanation clarity       | ✅        |

---

## Stretch Problems (Optional)

- Implement Brier score
- Compare isotonic vs temperature scaling (conceptually)
- Build slice-based calibration analysis
