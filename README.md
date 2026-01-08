# Linear Regression & GLMs — FAANG-Level Hands-On

**Goal:** Build strong, interview-ready intuition for linear regression, regularization, and GLM thinking (loss functions, link functions, assumptions).

**Outcome:** Students can implement linear regression from scratch (closed-form + GD), reason about bias/variance + regularization, and connect GLMs to real ML problems.

---

# How to Start

1. **Fork** this repository.  
2. Open `linreg_student_lab.ipynb` in **Google Colab**.  
3. Complete all **TODO** sections.  
4. **Restart runtime → Run All** cells.  
5. Push changes and submit a **Pull Request**.  

⚠️ **Do NOT edit notebooks directly on GitHub.**

---

## Lab Rules (FAANG Style)

- ✅ Track shapes (`X (n,d)`, `w (d,)`, `y (n,)`)
- ✅ Compare closed-form vs gradient descent
- ✅ Always include a baseline + error analysis
- ✅ Avoid data leakage in feature creation (time-split thinking)
- ❌ No scikit-learn for the core tasks

---

# Out of Scope

- Full production training pipelines
- Deep statistical proofs

---

# Notebook Rules

- Do **NOT** rename the notebook  
- Do **NOT** delete TODOs  
- Do **NOT** hardcode outputs  
- Notebook must run **top-to-bottom**  

---

# Dataset

- Synthetic regression data (controlled noise + collinearity)

## Why?

- Removes dataset distractions
- Lets us stress-test conditioning and regularization

---

## Section 1 — Ordinary Least Squares (OLS)

### Task 1.1: Closed-form solution using `solve`

- Implement `w_hat = (X^T X)^{-1} X^T y` using `np.linalg.solve`

**Checkpoint Questions:**

- Why prefer `solve` over explicit inverse?
- When is `X^T X` singular or ill-conditioned?

---

### Task 1.2: Evaluate fit + residuals

- Compute MSE
- Plot/inspect residual distribution

**Interview Angle:**

- What does a non-random residual pattern imply?

---

## Section 2 — Gradient Descent for Linear Regression

### Task 2.1: Implement MSE loss + gradient

**FAANG Gotcha:**

- Missing constants (2/n)
- Shape bugs in gradients

---

### Task 2.2: Train with GD + compare to closed-form

**Checkpoint Questions:**

- What controls convergence speed?
- How does feature scaling affect GD?

---

## Section 3 — Regularization (Ridge)

### Task 3.1: Ridge closed-form

- `w = (X^T X + λI)^{-1} X^T y`

**Interview Angle:**

- Why does ridge help with collinearity?

---

### Task 3.2: Bias/variance demonstration

- Compare train vs test error under different λ

---

## Section 4 — GLM Intuition

### Task 4.1: Map problems to (distribution, link)

- Linear regression: Gaussian + identity link
- Logistic regression: Bernoulli + logit link
- Poisson regression: count + log link

**Checkpoint Questions:**

- What changes: loss or model form?

---

## Submission Expectations

Students must submit:

- Completed notebook
- Short answers to checkpoint questions
- A brief comparison: closed-form vs GD vs ridge

---

## FAANG Interview Evaluation Rubric

| Skill                          | Evaluated |
|--------------------------------|-----------|
| Correctness                    | ✅        |
| Optimization intuition         | ✅        |
| Regularization intuition       | ✅        |
| Error analysis                 | ✅        |
| Explanation clarity            | ✅        |

---

## Stretch Problems (Optional)

- Add L1 regularization via coordinate descent (bonus)
- Implement polynomial features + ridge
- Show instability under collinearity without ridge
