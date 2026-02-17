# 📊 Roll-Number-Parameterized Probability Density Function Model

## 👤 Student Information
**Name:** Arun Mahajan  
**Roll Number:** 102303346  

---

## 📌 Project Overview

This project implements a **Roll-Number-Parameterized Non-Linear Transformation Model** to learn the parameters of a Gaussian-type Probability Density Function (PDF).

The transformation is based on the student's university roll number, making the model unique and personalized.

The dataset used is the **India Air Quality Dataset**, with **NO₂ concentration** as the selected feature.

---

## 📂 Dataset

- Source: Kaggle – India Air Quality Data  
- Feature Used: `NO2`
- File Required: `data.csv`

Make sure the dataset file is placed in the same directory as the notebook before execution.

---

## 🔄 Step 1: Non-Linear Transformation

Each value of NO₂ (x) is transformed using:

\[
z = x + a_r \sin(b_r x)
\]

Where:

\[
a_r = 0.05 \times (r \bmod 7)
\]
\[
b_r = 0.3 \times (r \bmod 5 + 1)
\]

For Roll Number **102303346**:

- \( a_r = 0.30 \)
- \( b_r = 0.60 \)

Final Transformation:

\[
z = x + 0.30 \sin(0.60x)
\]

---

## 📈 Step 2: Learning the PDF Parameters

The probability density function is modeled as:

\[
\hat{p}(z) = c \cdot e^{-\lambda (z - \mu)^2}
\]

Parameters are estimated using **Maximum Likelihood Estimation (MLE)**:

- \( \mu = \text{mean}(z) \)
- \( \sigma^2 = \text{variance}(z) \)
- \( \lambda = \frac{1}{2\sigma^2} \)
- \( c = \frac{1}{\sqrt{2\pi\sigma^2}} \)

---

## 📊 Output

The notebook:

✔ Computes transformation parameters  
✔ Applies roll-based non-linear transformation  
✔ Estimates Gaussian parameters  
✔ Plots histogram with fitted PDF  
✔ Produces final learned probability model  

---

## 🛠 Technologies Used

- Python 3
- NumPy
- Pandas
- Matplotlib
- Google Colab

---

## 🚀 How to Run

1. Clone the repository
2. Place `data.csv` in the project folder
3. Open the notebook in Google Colab
4. Run all cells
