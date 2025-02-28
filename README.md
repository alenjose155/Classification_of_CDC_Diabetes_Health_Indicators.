# Classification_of_CDC_Diabetes_Health_Indicators

## Overview  
Diabetes is a widespread chronic disease affecting millions of Americans each year, imposing a substantial financial burden on the economy. It impairs the body's ability to regulate blood glucose levels, leading to various health complications such as heart disease, vision loss, limb amputation, and kidney disease.

Though there is no cure for diabetes, **early detection and intervention** play a crucial role in managing the disease. This project aims to develop a **predictive model** for diabetes risk using **machine learning techniques**, helping healthcare providers and public health officials identify at-risk individuals.

## Dataset  
The dataset used in this project is sourced from **Kaggle** and originates from the **Behavioral Risk Factor Surveillance System (BRFSS)**, an annual telephone survey conducted by the **CDC since 1984**. The survey collects data on health-related risk behaviors, chronic health conditions, and preventative service usage.

This dataset contains **three CSV files**, among which we used:  
- **diabetes_012_health_indicators_BRFSS2015.csv**  
  - **253,680 responses**  
  - **21 features** representing various health indicators  
  - **Target variable (`Diabetes_012`) with three classes**:  
    - **0** → No diabetes (or only during pregnancy)  
    - **1** → Prediabetes  
    - **2** → Diabetes  

This dataset is **imbalanced**, requiring advanced techniques like **SMOTE** for better model performance.

## Methodology  

### Data Preprocessing & Feature Selection  
- **SMOTE (Synthetic Minority Over-sampling Technique)** was applied to balance the dataset and improve minority class representation.  
- **Information Gain (IG)** was used as the feature selection criterion, selecting the **top 15 features** that contribute the most to the prediction model.  

### Modeling & Evaluation  
- **Machine Learning Algorithm**: **CatBoost** was chosen for its strong performance on categorical data.  
- **Hyperparameter Tuning**: The model was optimized using **200 iterations** and a **learning rate of 0.01**.  
- **Performance Metrics**:  
  - **Accuracy**: 84%  
  - **Macro-Average Metrics**: Improved after applying SMOTE, ensuring fair classification across all classes.  

### Model Explainability  
- **SHAP (SHapley Additive Explanations)** was used to interpret model predictions:  
  - The **SHAP waterfall plot** illustrated how features influenced specific instances.  
  - The **SHAP summary bar chart** highlighted **GenHlth, HighChol, and BMI** as the most influential features.   

## Results & Conclusion  
- **CatBoost with SMOTE** was the best-performing model, balancing **accuracy, fairness, and computational efficiency**.  
- The **top 15 features selected using IG** led to a **lighter and more efficient model** while maintaining strong predictive performance.  
- **SHAP and** improved model interpretability, making predictions more transparent.  

## Future Scope  
1. **Advanced Machine Learning Models**  
   - Exploring **Cost-Sensitive Learning, Balanced Random Forest, or Deep Learning** techniques to improve minority class predictions.  
2. **Enhanced Feature Selection**  
   - Using **Recursive Feature Elimination (RFE)** and **Wrapper Methods** to refine the feature selection process.  
3. **Class-Wise Explainability**  
   - Leveraging **LIME to analyze misclassified instances**, enhancing the interpretability of minority class predictions.  
4. **Domain-Specific Feature Engineering**  
   - Incorporating additional **domain knowledge-based features** to improve prediction accuracy.  

## Acknowledgements  
This dataset was not created by me. It is sourced from Kaggle, based on the **BRFSS 2015 dataset**, originally provided by the **CDC**. 
