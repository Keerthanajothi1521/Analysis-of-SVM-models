# Analysis-of-SVM-models
Overview:
This work explores the performance of Support Vector Machine (SVM) models with different kernels for a binary classification task. The goal is to predict a target variable based on a dataset containing both numerical and categorical features.

Key Highlights
Data Preprocessing: Numerical features were standardized, while categorical variables were one-hot encoded to ensure compatibility with the SVM model. 
The dataset was split into training and testing sets for reliable evaluation.
Model Evaluation: Three SVM kernels—Linear, Polynomial, and Radial Basis Function (RBF)—were trained and compared. Each model's performance was assessed
using standard classification metrics.
Best Performing Model: The RBF kernel demonstrated the most balanced performance, with strong generalization and minimal overfitting, making it the optimal
choice for this task.
Future Work: Further tuning and additional algorithms could be explored to enhance predictive performance.

Dataset:
Filename: ClassificationDataset.csv
Target Variable: Binary classification (Recurred: Yes/No)

Data Preprocessing:
To prepare the data for SVM modeling, the following steps were applied:
1. Handling Numerical Features
Standardization: Numerical features (e.g., Age) were scaled using StandardScaler to ensure consistent model performance.
2. Handling Categorical Features
One-Hot Encoding: Categorical variables (e.g., Gender, Smoking) were converted into a binary format using OneHotEncoder.
3. Train-Test Split
Split Ratio: 70% training, 30% testing
Random State: Fixed for reproducibility

Model Training & Evaluation:
Three SVM kernel functions were tested:
The project evaluated three SVM kernel functions—Linear, Polynomial (Poly), and Radial Basis Function (RBF)—for binary classification of the "Recurred" target variable (with classes "Yes" and "No"). The Linear kernel, best suited for linearly separable data, showed strong overall accuracy but exhibited a slightly larger gap between training and test performance. The Polynomial kernel effectively captured non-linear relationships, achieving the highest training accuracy of all kernels, though with a marginally higher train-test gap that suggested mild overfitting tendencies. Most impressively, the RBF kernel demonstrated superior performance with the highest test accuracy (96.52% for "No" and 91% recall for "Yes") and the smallest generalization gap (just 0.12%), indicating excellent bias-variance tradeoff. All models maintained robust performance metrics for both classes, with the RBF kernel particularly excelling—achieving 97% precision for "Yes" and 99% recall for "No". The "No" class consistently showed stronger metrics across all kernels, while the "Yes" class maintained high but slightly lower performance, with the RBF model delivering 94% F1-score for "Yes" versus 98% for "No". This comprehensive analysis confirms the RBF kernel's optimal balance of accuracy and generalizability while highlighting consistent, high-quality classification performance for both outcome categories.

Results:
Comparative Kernel Performance
Our evaluation of three SVM kernels revealed distinct strengths in classifying the binary "Recurred" outcome (Yes/No):
1. Linear Kernel:
Demonstrated reliable performance with 96.52% test accuracy
Maintained strong precision for both classes (97% for "Yes", 96% for "No")
Showed slightly higher variance (1.24% train-test gap) compared to RBF
2. Polynomial Kernel:
Achieved peak training accuracy (99.25%), indicating excellent learning capability
Delivered 97.39% test accuracy with good class balance
Exhibited the largest train-test gap (1.86%), suggesting mild overfitting tendencies
3. RBF Kernel (Optimal Performer):
Best test accuracy (96.52%) with near-perfect generalization (only 0.12% train-test gap)
Exceptional recall for negative cases (99% for "No")
Maintained strong positive case identification (91% recall for "Yes")
Achieved the most balanced F1-scores (94% for "Yes", 98% for "No")

Key Findings
1. The RBF kernel demonstrated superior generalization with the smallest performance gap between training (96.64%) and testing (96.52%)
2. All models showed excellent negative class detection, with recall for "No" cases exceeding 96% across all kernels
3. The Polynomial kernel, while achieving the highest training accuracy, showed signs of overfitting with the largest performance drop during testing
4. Class imbalance considerations: The models performed slightly better on "No" cases, suggesting potential benefits from:
-Targeted feature engineering for "Yes" cases
-Class weighting adjustments
-Additional data collection for recurrent cases

Practical Implications:
Healthcare: Predicting patient readmission risks ("Recurred=Yes/No") to optimize care plans.
Finance: Identifying high-risk loan applicants or fraudulent transactions.
Marketing: Classifying customer responses (e.g., "Will they subscribe? Yes/No") for targeted campaigns.

Repository Structure:
SVM_Classification_Analysis/  
├── data/  
│   └── ClassificationDataset.csv  
├── notebooks/  
│   ├──Preprocessing.ipynb
│   ├──split data.ipynb
│   └──evaluation.ipynb
├── results/  
│   ├──linear kernel.png
│   ├──poly kernel.png
│   └──RBF kernel.png
├── Visualisations/
│   ├──SVM accuracy
│   ├──RBF kernel-class wise performance
├──Presentation.pptx
└── README.md  





