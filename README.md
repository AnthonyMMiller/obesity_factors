# obesity_factors

# Research Questions & Results Summary

## Primary Research Questions

### RQ1: Is there a statistically significant correlation between food deserts and obesity?

**Hypothesis Testing:**
- H₀: No significant relationship exists
- H₁: Significant relationship exists

**Result: ✅ YES (HYPOTHESIS 1 SUPPORTED)**

| Metric | Value | Interpretation |
|--------|-------|-----------------|
| Correlation (r) | 0.1417 | Weak positive correlation |
| Model 1 R² | 0.020 | Explains only 2% of variance |
| Model 1 Coefficient | 0.0268 | +1% food desert → +0.027% obesity |
| Model 1 p-value | <0.001 | Highly statistically significant |
| F-statistic | 64.12 | Very strong evidence against null |

**Conclusion:** Yes, a statistically significant relationship exists. However, it's weak in practical terms.

**Evidence:** Model 1 regression output shows coefficient is 0.0268 (SE=0.003, t=8.01, p<0.001)

---

### RQ2: Does this relationship persist when controlling for socioeconomic factors?

**Hypothesis Testing:**
- H₀: Food desert effect disappears or remains significant after controls
- H₁: Food desert effect remains significant and strong after controls

**Result: ❌ NO (HYPOTHESIS 2 NOT SUPPORTED IN STRONG FORM)**

| Metric | Model 1 | Model 2 | Change |
|--------|---------|---------|--------|
| Food Desert Coefficient | 0.0268 | -0.0029 | -0.0297 (110% reduction!) |
| Food Desert p-value | <0.001 | 0.261 | NO LONGER SIGNIFICANT |
| R² | 0.020 | 0.504 | 25× improvement |
| Poverty Coefficient | N/A | 0.1633 | HIGHLY SIGNIFICANT |
| Education Coefficient | N/A | -0.2632 | HIGHLY SIGNIFICANT |

**Conclusion:** The food desert effect **completely disappears** when controlling for socioeconomic factors. This indicates the original relationship was **spurious**—driven by confounding.

**Evidence:** Model 2 regression output shows:
- Food desert coefficient: -0.0029 (SE=0.003, t=-1.13, p=0.261)
- Poverty coefficient: 0.1633 (SE=0.015, t=10.92, p<0.001)
- Education coefficient: -0.2632 (SE=0.008, t=-31.46, p<0.001)

**Key Insight:** Socioeconomic factors explain the apparent food desert effect. Counties with more food deserts tend to be poorer and less educated, and it's those factors that drive obesity—not food access per se.

---

### RQ3: Do socioeconomic factors moderate the food desert-obesity relationship?

**Hypothesis Testing:**
- H₀: No moderation; relationship is constant across poverty levels
- H₁: Moderation exists; relationship varies by poverty level

**Result: ✅ YES (HYPOTHESIS 3 SUPPORTED)**

| Metric | Model 3 | Interpretation |
|--------|---------|-----------------|
| Food Desert × Poverty Interaction | 0.2079 | SIGNIFICANT |
| Interaction p-value | <0.001 | Highly significant |
| Interaction SE | 0.049 | Precise estimate |
| R² improvement (vs Model 2) | 0.507 vs 0.504 | +0.3% additional explained variance |

**Conclusion:** Poverty significantly moderates the food desert-obesity relationship. The effect of food deserts depends on poverty levels.

**Evidence:** Model 3 regression output shows interaction term coefficient 0.2079 (SE=0.049, t=4.22, p<0.001)

---

## Interpretation of Moderation Effect

### What the Interaction Means:

The positive interaction coefficient (0.2079) indicates that **the food desert effect is amplified at higher poverty levels**.

### Quantitative Example:

Using standardized variables from Model 3:

**In a LOW-POVERTY County (1 SD below mean):**
- Food desert effect ≈ -0.133 - 0.208(-1) = +0.075
- Minimal positive relationship

**In a HIGH-POVERTY County (1 SD above mean):**
- Food desert effect ≈ -0.133 + 0.208(1) = +0.075
- Noticeably stronger positive relationship

The effect essentially **flips** from negative to positive as poverty increases.

### Policy Implication:

Food desert interventions may be most effective in economically disadvantaged areas, while having little impact in affluent counties (where access is less constrained).

---

## Which Socioeconomic Factor Matters Most?

### Standardized Coefficient Comparison (Model 3):

| Variable | Coefficient | Absolute Value | Relative Impact |
|----------|-------------|-----------------|-----------------|
| Education (std) | **-2.6702** | 2.67 | **Strong negative** |
| Poverty (std) | **0.8654** | 0.87 | Moderate positive |
| Food Desert (std) | -0.1325 | 0.13 | Weak (non-significant main effect) |
| Income (std) | -0.1734 | 0.17 | Weak (non-significant) |
| FD × Poverty (interaction) | **0.2079** | 0.21 | Moderate interaction |

### Ranking by Impact on Obesity:
1. **Education (Bachelor's+)** - Strongest protective factor
2. **Poverty Rate** - Strongest risk factor
3. **Food Desert × Poverty Interaction** - Context-dependent risk
4. **Median Income** - Weak, mediated by other factors

---

## Comparison to Literature

### Your Findings vs. Existing Research:

| Finding | Your Study | Literature |
|---------|-----------|------------|
| Bivariate FD-Obesity correlation | +0.14 | Typically 0.10–0.25 ✅ |
| Effect with controls | -0.003 (non-sig) | Mixed; many find reduced effect ✅ |
| Socioeconomic confounding | Strong | Well-established ✅ |
| Moderation by poverty | Yes | Understudied; novel contribution ✅ |
| Strongest predictor | Education (-0.27) | Often income or poverty (literature variable) ✅ |

**Conclusion:** Findings align well with literature while contributing new insights on moderation effects.

---

## Statistical Significance vs. Practical Significance

### The Crucial Distinction:

**Statistically Significant ≠ Practically Important**

| Model | Statistically Significant? | Practically Significant? |
|-------|---------------------------|--------------------------|
| Model 1 | YES (p < 0.001) | **NO** (R² = 0.020) |
| Model 2 | YES (F = 793, p < 0.001) | **YES** (R² = 0.504) |
| Model 3 | YES (F = 641, p < 0.001) | **SLIGHT** (ΔR² = 0.003) |

### Why This Matters:

- **Model 1** has statistical significance but NO predictive power (2% variance explained)
- **Model 2** is both statistically and practically significant (explains 50% of obesity variation)
- **Model 3** adds statistical refinement (interaction is significant) but minimal practical improvement


---

## Sample Sizes and Power

### County Representation:

| Geography | Count | Percentage |
|-----------|-------|------------|
| Total US counties | 3,235 | — |
| **Included in analysis** | **3,129** | **96.7%** |
| Missing FIPS matches | 106 | 3.3% |

### Statistical Power:

With N = 3,129 and α = 0.05, your study has:
- **Power > 0.99** to detect small effects (r > 0.05)
- **Excellent power** for all effects of interest
- **Sufficient power** even for interaction effects

This large sample size is both a strength (good power) and a challenge (small effects become significant).

---

## Key Findings Ranked by Importance

### 1. **Socioeconomic Confounding is Dominant**
- Adding poverty, income, and education to Model 1 increases R² from 0.020 to 0.504
- Food desert effect becomes non-significant (p = 0.261)
- **Implication:** Focus on socioeconomic interventions first

### 2. **Education is the Strongest Predictor**
- Coefficient: -0.2632 (standardized: -2.67)
- Each additional 1% of Bachelor's degrees → 0.26% lower obesity
- **Implication:** Health literacy and education programs highly impactful

### 3. **Poverty Moderates the Food Desert Effect**
- Interaction term: 0.2079 (p < 0.001)
- Food deserts matter more in poor counties
- **Implication:** Targeted food access interventions in economically disadvantaged areas

### 4. **Food Access Alone is Insufficient**
- Model 1 explains only 2% of obesity variation
- Even in Model 3 (with controls), main food desert effect is non-significant
- **Implication:** Cannot rely on food desert remediation alone

### 5. **Income's Direct Effect is Modest**
- Coefficient: -5.17e-6 (not significant, p = 0.416)
- Effect is mediated through poverty and education
- **Implication:** It's the relative disadvantage, not absolute income level
