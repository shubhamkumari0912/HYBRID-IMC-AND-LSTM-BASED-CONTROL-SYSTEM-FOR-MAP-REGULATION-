# Hybrid IMC + LSTM-Based Drug Dosage & MAP Control System

## Project Overview
This project presents a hybrid intelligent system for personalized blood pressure control by combining Internal Model Control (IMC) with a Long Short-Term Memory (LSTM) based deep learning model. The system focuses on regulating Mean Arterial Pressure (MAP) by recommending the most suitable drug type and dosage for each patient. IMC uses a mathematically modeled approach (FOPDT) to estimate dosage, while the LSTM model learns temporal patterns from patient data to enhance prediction accuracy. A command-line interface (CLI) allows users to input patient details and receive real-time, personalized recommendations. The hybrid model achieved 95% classification accuracy and demonstrated effective MAP regulation through simulation, offering a promising step toward smarter, AI-assisted healthcare solutions.

This project implements a **hybrid intelligent control system** to recommend personalized **drug type and dosage** for blood pressure (MAP) regulation using:

-  **IMC (Internal Model Control)** for equation-based dosage estimation  
-  **LSTM/ANN model** for drug classification and adaptive dosage prediction  
-  **CLI Interface** for real-time patient interaction

---

##  Key Features

- **IMC Controller:** Uses FOPDT parameters (gain `k`, time constant `τ`, delay `θ`) to compute drug dosage
- **LSTM Model:** Predicts drug type + dosage using patient history and time-series MAP data
- **Patient Static Data Handling:** Includes age, gender, weight, MAP, comorbidities
- **Performance:**  
  - Drug classification accuracy: **95%**  
  - Dosage RMSE: Low error  
-  **Simulation:** Validates MAP stabilization before and after drug application

---

##  Methodology

1. **Data Preprocessing**
   - Clean, scale, and structure data
   - Compute MAP using:  
     \[
     	ext{MAP} = rac{	ext{SBP} + 2 	imes 	ext{DBP}}{3}
     \]

2. **IMC Path (Equation-Based)**
   - Estimate FOPDT model from MAP response  
   - Use IMC control law to suggest dosage

3. **ANN + LSTM Path (AI-Based)**
   - Train on historical MAP + patient data  
   - Dual output:
     - Drug Type (classification)
     - Dosage (regression)

4. **CLI Output**
   - Users enter patient data  
   - System outputs drug name, dosage, urgency level

---

