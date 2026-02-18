### 📌 Overview
This project implements a parameterized non-linear transformation on the NO₂ feature from the *India Air Quality Dataset* and learns the parameters of a Gaussian probability density function (PDF) from the transformed data.

Dataset Source:  
https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

---

## 🎯 Objective

1. Transform NO₂ values using a roll-number-based non-linear function:
   
   z = x + aᵣ sin(bᵣ x)

2. Learn parameters of the probability density function:

   p̂(z) = c e^(−λ (z − μ)²)

3. Estimate parameters:
   - μ (mean)
   - λ (lambda)
   - c (normalization constant)

---

## 🔢 Roll Number Used

**102303196**

### Computed Parameters

- r mod 7 = 1  
- r mod 5 = 1  

Therefore:

- aᵣ = 0.05 × (r mod 7) = 0.05  
- bᵣ = 0.3 × (r mod 5 + 1) = 0.6  

Final Transformation:

z = x + 0.05 sin(0.6x)

---

## 🧠 Methodology

### Step 1: Data Extraction
- Download dataset using `kagglehub`
- Extract `no2` column
- Remove missing values

### Step 2: Non-Linear Transformation
Apply:

z = x + aᵣ sin(bᵣ x)

### Step 3: Parameter Estimation (Gaussian MLE)

For Gaussian distribution:

μ = mean(z)  
σ² = variance(z)  
λ = 1 / (2σ²)  
c = √(λ / π)

---

## 📊 Final Estimated Parameters

- μ ≈ 26.12  
- λ ≈ 0.00146  
- c ≈ 0.02156  

---

## 📈 Visualization
The histogram of transformed data is plotted along with the learned Gaussian PDF to verify fitting quality.

---

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- KaggleHub

---

## ▶️ How to Run

1. Open Google Colab or Jupyter Notebook.
2. Install kagglehub:
   pip install kagglehub
3. Run the notebook.
4. The dataset downloads automatically.
5. Final parameters will be printed in the output.

---

## 📂 Project Structure

Assignment-1/
│
├── notebook.ipynb
├── README.md
└── requirements.txt

---

## 📌 Key Learning Outcomes

- Non-linear feature transformation
- Parameter estimation using Maximum Likelihood
- Gaussian probability density modeling
- Data visualization and statistical analysis

---

## 👤 Author

Roll No: 102303196  
Course Assignment Submission  

