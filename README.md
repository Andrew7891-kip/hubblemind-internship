# hubblemind-internship
Estimation of Obesity Levels Based on Eating Habits and Physical Condition
1. Introduction
This project aims to predict obesity levels based on dietary and physical activity attributes using Python. The data was collected from individuals in Mexico, Peru, and Colombia and includes 2111 records with 17 attributes. The target variable NObeyesdad classifies individuals into seven obesity categories, ranging from "Insufficient Weight" to "Obesity Type III."

The objectives of this project include:

Cleaning and preprocessing the dataset.
Conducting exploratory data analysis (EDA).
Building machine learning models to predict obesity levels.
Extracting insights for public health interventions.
2. Data Preprocessing
2.1 Importing and Inspecting Data
The dataset contains 17 attributes, including continuous, binary, and categorical variables.
Initial inspection showed no missing values, and the data types were consistent with variable descriptions.
2.2 Encoding
Binary variables: Gender, family_history_with_overweight, FAVC, SMOKE, and SCC were label-encoded.
Categorical variables: Variables such as CAEC, CALC, and MTRANS were one-hot encoded to ensure compatibility with machine learning models.
Target variable: The NObeyesdad variable was label-encoded for classification.
2.3 Outlier Detection and Handling
Continuous variables like Age, Height, and Weight were visualized using boxplots.
Outliers were identified and capped at 1.5 times the interquartile range (IQR) to prevent their undue influence on model performance.
2.4 Normalization
Continuous variables (Age, Height, Weight, etc.) were scaled using the MinMaxScaler to standardize their values to a range of 0-1, ensuring uniformity in feature scaling.
3. Exploratory Data Analysis (EDA)
3.1 Summary Statistics
Continuous variables were summarized:
Age: Mean = 29.1 years, Min = 14 years, Max = 61 years.
Height: Mean = 1.64 meters, Min = 1.4 meters, Max = 2.05 meters.
Weight: Mean = 72.5 kg, Min = 39 kg, Max = 173 kg.
3.2 Distribution Analysis
Age: Right-skewed distribution with most individuals aged 20-40.
Height: Approximately normal distribution.
Weight: Slight right skew due to individuals with extreme obesity.
3.3 Relationship Exploration
Boxplots revealed:
Higher obesity levels were associated with increased weight.
Physical activity frequency (FAF) decreased as obesity levels increased.
Individuals with a family history of overweight tended to have higher obesity levels.
3.4 Correlation Analysis
Heatmap of continuous variables showed:
Strong positive correlation between Weight and Height.
Moderate negative correlation between physical activity frequency (FAF) and obesity levels.
4. Machine Learning Models
4.1 Train-Test Split
Data was split into 80% training and 20% testing sets to evaluate model performance.
4.2 Models Implemented
Logistic Regression:
A linear model for multi-class classification.
Parameters: Default settings with max_iter=1000.
Random Forest Classifier:
An ensemble learning method capturing non-linear relationships.
Parameters: Default settings with 100 estimators.
4.3 Results
Logistic Regression:
Accuracy: 78%
Weighted F1-Score: 0.76
Challenges: Misclassification in borderline categories like Overweight Levels I and II.
Random Forest:
Accuracy: 88%
Weighted F1-Score: 0.87
Outperformed Logistic Regression due to its ability to model complex patterns in the data.
5. Advanced Visualizations
5.1 Pair Plot
Pairwise scatterplots showed distinct groupings for higher obesity categories, highlighting relationships among Age, Weight, Height, and obesity levels.
5.2 Feature Importance
Random Forest identified the following top predictors:
Weight: The most significant predictor.
Family history of overweight: A strong contributor.
Physical activity frequency (FAF): Negatively correlated with obesity.
Number of main meals consumed daily (NCP): Positively associated with obesity.
5.3 Confusion Matrix
Random Forest confusion matrix:
High classification accuracy for extreme obesity levels (e.g., Obesity Type III).
Minor misclassification between Normal Weight and Overweight Level I.
6. Key Insights
Physical Activity: Lower physical activity frequency strongly correlates with higher obesity levels.
Family History: Individuals with a family history of overweight are more prone to obesity.
Dietary Habits: High-calorie food consumption (FAVC) and the number of daily main meals (NCP) are significant contributors to obesity.
Age and Obesity: Obesity levels increase with age until middle adulthood.
7. Conclusion
This study successfully utilized machine learning models to classify obesity levels based on dietary and physical activity attributes. The Random Forest model demonstrated superior performance, achieving 88% accuracy and a weighted F1-score of 0.87. These findings provide valuable insights for designing interventions targeting modifiable risk factors such as diet and exercise.

8. Recommendations
Physical Activity Programs: Promote active lifestyles through community initiatives.
Nutritional Education: Educate individuals on healthy eating habits and the dangers of high-calorie diets.
Further Research: Incorporate additional features (e.g., genetic markers) to improve obesity predictions.
9. Deliverables
Cleaned Dataset: final_cleaned_data.csv
Code: Python scripts for data preprocessing, EDA, and machine learning.
Visualizations: Histograms, KDE plots, boxplots, feature importance, and confusion matrix heatmap.
Report: This detailed document summarizing the project.
