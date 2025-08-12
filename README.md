# 📊 Faragir Sanat Mehrbin — Customer Satisfaction Analysis (SPSS)

## 📚 Table of Contents
- 🔖 [Project Overview](#-project-overview)
- ✅ [Step 1. Descriptive Statistics](#-step-1-descriptive-statistics)
- 🧪 [Step 2. Reliability Test (Cronbach’s Alpha)](#-step-2-reliability-test-cronbachs-alpha)
- 🔗 [Step 3. Correlation Analysis](#-step-3-correlation-analysis)
- 📈 [Step 4. Regression Analysis](#-step-4-regression-analysis)
- 🚀 [Recommendations to Lift Satisfaction](#-recommendations-to-lift-satisfaction)
  
## 🔖 Project Overview
This repo outlines a focused **customer satisfaction study** using **SPSS**. The aim is to map how key experience drivers—**Delivery, Product Quality, Price Fairness, Support, Ease of Ordering**—relate to **Overall Satisfaction**, and package the work for decision-makers.

**Inputs.** Likert (1–5) survey covering the factors above .  
**Methods (SPSS).** Descriptives → Reliability (Cronbach’s α) → Correlations → Linear Regression.  
**Outputs.** Clean, GitHub-ready tables & visuals; simple explanations; an action framework (impact × effort). 

## ✅ Step 1. Descriptive Statistics

### 🔍 What this step does
Summarises each factor’s **central tendency (Mean)** and **dispersion (Std. Dev.)**.  
**Scale:** 1 = Very dissatisfied · 3 = Neutral · 5 = Very satisfied

### 📊 Results (SPSS)
| Factor                | N   | Mean | Std. Dev. |
|----------------------|-----|------|-----------|
| Overall Satisfaction | 549 | 3.58 | 1.051     |
| Delivery             | 549 | 3.49 | 0.941     |
| Product Quality      | 549 | 3.72 | 0.712     |
| Price Fairness       | 549 | 3.43 | 0.631     |
| Support Satisfaction | 549 | 3.59 | 0.635     |
| Ease of Ordering     | 549 | 3.82 | 0.524     |
| **Valid N (listwise)** | **549** |      |           |

> 📝 **Reading guide:**  
> Higher **Mean** = better perceived experience.  
> **Std. Dev. ≤ ~1.0** ⇒ customers broadly agree; **>1.2** ⇒ views are polarised.

### 💡 Interpretation (business)
- **Strong baselines:** Ease of Ordering (3.82), Product Quality (3.72).  
- **Improvement candidates:** Price Fairness (3.43), Delivery (3.49).  
- **Consistency:** All SDs ≤ ~1.05 → perceptions are stable; improvements should shift the overall average.
### 🔑 Key Takeaway (simple)
People say **ordering is easy** and **quality is good**. They are **less happy with price fairness and delivery**.  
Focus next on **clearer pricing** and **on-time delivery**.

## 🧪 Step 2. Reliability Test (Cronbach’s Alpha)

**Purpose.** Check whether the five driver items (Delivery, Product Quality, Price Fairness, Support, Ease of Ordering) behave consistently as a scale. *Overall Satisfaction is excluded*—it’s the outcome.

### 📊 Result (SPSS)
| Metric            | Value |
|-------------------|-------|
| Cronbach’s Alpha  | **0.868** |
| N of Items        | **5** |

### 💡 Interpretation (reporting)
An alpha of **0.868** indicates **good internal consistency**: these drivers are measuring the same underlying experience without being redundant. This means the scale is **stable and reliable**, and each item still contributes useful, distinct information.

### 🧭 What this enables
We can **safely use** these items together in the next steps—examining relationships with Overall Satisfaction (correlations) and estimating **unique driver impact** (regression)—while keeping Overall Satisfaction as the dependent variable.

---
## 🔗 Step 3. Correlation Analysis

**Purpose.** Identify which experience factors move with **Overall Satisfaction** before controlling for overlap.

### 📊 Correlation Matrix (Pearson r)
|                          | Overall Satisfaction | Delivery | Product Quality | Price Fairness | Support Satisfaction | Ease Of Ordering |
|--------------------------|----------------------|----------|------------------|----------------|----------------------|------------------|
| **Overall Satisfaction** | 1.000                | .699**   | .632**           | .677**         | .629**               | .619**           |
| **Delivery**             | .699**               | 1.000    | .610**           | .655**         | .629**               | .575**           |
| **Product Quality**      | .632**               | .610**   | 1.000            | .579**         | .598**               | .549**           |
| **Price Fairness**       | .677**               | .655**   | .579**           | 1.000          | .607**               | .531**           |
| **Support Satisfaction** | .629**               | .629**   | .598**           | .607**         | 1.000                | .579**           |
| **Ease Of Ordering**     | .619**               | .575**   | .549**           | .531**         | .579**               | 1.000            |

**Notes:** ** indicates p < .01 (2-tailed). N = 549 for all pairs.

### 💡 Interpretation (reporting)
All five drivers are **strong, positive** companions of Overall Satisfaction. The tight cluster of high correlations shows a **coherent customer experience**, with **Delivery** and **Price Fairness** showing the strongest raw links. Because drivers also correlate with each other, we proceed to regression to isolate **unique impact**.

### 🔑 Key takeaway
Each driver is meaningfully tied to satisfaction; **Delivery** and **Price Fairness** stand out prior to controls.

## 📈 Step 4. Regression Analysis

**Purpose.** Estimate each driver’s **unique** contribution to **Overall Satisfaction** while controlling for overlap among drivers.

### 📊 Model Summary
| Model | R     | R Square | Adjusted R Square | Std. Error of Estimate |
|------:|:-----:|:--------:|:-----------------:|:----------------------:|
| 1     | 0.798 | 0.636    | 0.633             | 0.637                  |

### 🧪 ANOVA
| Source      | Sum of Squares | df  | Mean Square | F       | Sig.  |
|-------------|----------------|-----|-------------|---------|-------|
| Regression  | 385.256        | 5   | 77.051      | 189.983 | .000  |
| Residual    | 220.223        | 543 | 0.406       |         |       |
| Total       | 605.479        | 548 |             |         |       |

### 🔩 Coefficients (DV = Overall Satisfaction)
| Term                  | B       | Std. Error | Beta   | t      | Sig.  |
|-----------------------|---------|------------|--------|--------|-------|
| (Constant)            | -1.803  | 0.218      | —      | -8.268 | .000  |
| Delivery              | 0.295   | 0.044      | 0.264  | 6.738  | .000  |
| Product Quality       | 0.238   | 0.054      | 0.161  | 4.442  | .000  |
| Price Fairness        | 0.407   | 0.062      | 0.244  | 6.536  | .000  |
| Support Satisfaction  | 0.185   | 0.063      | 0.112  | 2.958  | .003  |
| Ease Of Ordering      | 0.370   | 0.070      | 0.184  | 5.314  | .000  |

### 🧾 Reporting Note
The model explains **63.6%** of variance in satisfaction (**R² = 0.636**, **F(5,543) = 189.98**, **p < .001**). All predictors are statistically significant. By standardized effects (**Beta**), **Delivery** shows the largest unique association, followed by **Price Fairness**, **Ease**, **Product Quality**, and **Support**.

### 🔑 Key takeaway
Satisfaction is well-explained by the five drivers; **Delivery** and **Price Fairness** provide the strongest **unique** lift when other factors are held constant.


## 🚀 Recommendations to Lift Satisfaction

### 🎯 Main Focus: **Fair Prices**
**Why:** lowest mean **3.43**, strong link to satisfaction (**r = .677**), solid unique impact (**β = .244**, **B = .407/pt**).  
**Do next:** Show the **full price early** (include shipping/tax), offer **bundle/volume discounts**, and **explain the value** (warranty, calibration, reviews).  
**Check weekly:** “Price fairness” rating in the survey, and how many people **quit at the payment page**.

### 📦 Next: **Reliable Delivery**
**Why:** second lowest mean **3.49**, strongest driver (**r = .699**, **β = .264**).  
**Do next:** Show the **delivery day before paying**, give a **tracking link**, and **message customers if there’s a delay**.  
**Check:** % of orders that **arrive on the promised day**, average **days late**, and **damaged items**.

