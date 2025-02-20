# **Echo Classification: Leads vs. Sea Ice**  
## **Overview**
This repository contains the code and results for the **Week 4 Assignment** of the course, focusing on **unsupervised learning methods** for classifying SAR echoes into **leads (open water) and sea ice**.  

The project builds on the **Chapter1_Unsupervised_Learning_Methods_Michel.ipynb** notebook and includes:  
✅ **Implementation of clustering techniques (GMM) to classify echoes**  
✅ **Calculation of average echo shape and standard deviation for both classes**  
✅ **Comparison with ESA official classifications using a confusion matrix**  
✅ **Results visualization and performance metrics**  

---

## **Dataset and Notebook**
- **Source notebook: [Assignment_4_21115167.ipynb]** based on [`Chapter1_Unsupervised_Learning_Methods_Michel.ipynb`](https://drive.google.com/file/d/1HDSLjsWhLIDF-qbRj6sbGVd9t1LB7890/view?usp=drive_link)  
- **SAR Data:** Retrieved from NetCDF files containing **backscatter signals** and **waveform measurements**.  

---

## **Methodology**
### **1️⃣ Data Preprocessing**
- Extract SAR **latitude, longitude, waveform (echoes), and classification labels**.  
- Remove **NaN values** and **filter relevant classes (sea ice = 1, leads = 2)**.  
- Standardize the data using **`StandardScaler()`**.  

### **2️⃣ Unsupervised Learning for Classification**
- Apply **Gaussian Mixture Model (GMM)** clustering with **two components** (sea ice & leads).  
- Compute **average waveform** and **standard deviation** for each class.  
- Align echoes within each cluster using **cross-correlation**.

### **3️⃣ Validation Against ESA Data**
- Compare GMM predictions with ESA labels.  
- Compute **confusion matrix** and **classification report**.  

---

## **Results**
### **🔹 Average Waveform and Standard Deviation**
The plots of  (1) average echo shape and standard deviation (2) echos produced for these two classes  shows the **mean echo shape and variability** for sea ice and leads
![image](https://github.com/user-attachments/assets/77ef1b2e-fbb2-4be1-9e95-8f42dfc45e67)
![image](https://github.com/user-attachments/assets/429fcc06-743d-425b-9b4c-e6eb4e260efb)
![image](https://github.com/user-attachments/assets/961eb75d-0a61-47c5-9005-9c27c26def5b)
![image](https://github.com/user-attachments/assets/143444bf-bdaa-4efb-99e1-a87cc7517cce)


### **🔹 Confusion Matrix of my echo classification against the ESA official classification**
| Predicted | True Ice | True Lead |
|-----------|---------|----------|
| **Ice**   | 8856    | 22       |
| **Lead**  | 24      | 3293     |
