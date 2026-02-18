# Learn Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

## 📌 OBJECTIVE

This project performs nonlinear transformation and probabilistic modeling of Nitrogen Dioxide (NO₂) concentrations using real-world air quality data.

The objective of this project is to:
- Apply a roll-number-based nonlinear transformation to NO₂ values
- Model the transformed data using a Gaussian Probability Density Function (PDF)
- Estimate parameters using Maximum Likelihood Estimation (MLE)

---

## 📂 Dataset

- **Dataset Name:** India Air Quality Data  
- **Source:** Kaggle
- **Link:** https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data
- **Feature Used:** NO2  

### ⚙️ Methodology

- Extracted the NO₂ column
- Removed missing values (NaN entries)
- Converted data to numerical format

---

## 🔄 Step 1: Nonlinear Data Transformation

Each NO₂ value `x` is transformed using the formula:

\[
z = x + a_r \sin(b_r x)
\]

Where:

\[
a_r = 0.05 (r \bmod 7)
\]

\[
b_r = 0.3 (r \bmod 5 + 1)
\]

- `r` = University Roll Number  
- `mod` = Remainder operator  

The transformed dataset is denoted as `z`.

---

##  Step 2: Gaussian Modeling

The transformed data `z` is modeled using:

\[
\hat{p}(z) = c \cdot e^{-\lambda (z - \mu)^2}
\]

This represents the exponential form of a Gaussian distribution.

###  Relation to Standard Gaussian

Standard Gaussian form:

\[
p(z) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(z-\mu)^2}{2\sigma^2}}
\]

By comparison:

\[
\lambda = \frac{1}{2\sigma^2}
\]

\[
c = \frac{1}{\sqrt{2\pi\sigma^2}}
\]

---

##  Parameter Estimation (Maximum Likelihood Estimation)

The parameters are estimated as:

- **μ (mean)** = mean of transformed data `z`
- **σ² (variance)** = variance of transformed data `z`
- **λ** = 1 / (2σ²)
- **c** = 1 / √(2πσ²)

###  Why MLE?

For Gaussian distributions:
- Sample mean is the MLE of μ
- Sample variance is the MLE of σ²

These are sufficient statistics for normal distribution.

---

## 📊 Model Validation

- Histogram of transformed data plotted
- Learned Gaussian PDF overlaid
- Visual inspection confirms model fit



## 📌 Final Results

Estimated Parameters:

μ = 22.09969685486927
λ = 0.003161233404904664
c = 0.03172147293735902

