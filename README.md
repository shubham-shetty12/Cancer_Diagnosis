# Cancer Diagnosis
### Machine learning Multi-Classification Problem
This was a challenging and impactful task of cancer diagnosis using machine learning and data analytics techniques. Cancer is a complex and heterogeneous disease, with multiple subtypes requiring different treatment approaches. By leveraging cutting-edge machine learning algorithms and feature engineering, I aimed to create a model that could distinguish between various cancer types with high precision and recall.

### Problem Statement :
Predict the probability of each data-point belonging to each of the nine classes based on data from patients.

### Real world/Business Objectives and Constraints :
- No low-latency requirement.
- Interpretability is important.
- Errors can be very costly.
- Probability of a data-point belonging to each class is needed.

### Performance Metric:
   - Log loss 
   - Confusion Matrix

### Data Overview:
We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that human experts/pathologists use to classify the genetic mutations.
Both these data files have a common column called ID.

**Data file's information:**
- training_variants (ID , Gene, Variations, Class)
- training_text (ID, Text).

We have data shape of (3321,4) in training_variants and (3321,2) in training_text, after peforming data preprocessing on 'Text' column we merged both files and final data has shape of (3321,5) using ID column. Splitted data into train and test with 80% and 20% and further split train into 80-20 for cross validation .
## EDA
 ### Distribution of data points among output classes in train, test and cv data
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/b1fad1c6-2ba9-4b37-8ded-e8180d814a01)
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/306cec39-aab4-4abc-9c86-c12ef93c3a44)
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/deccb436-4f50-4f12-8311-203552ce7a4b)

### Univariate Analysis on GENE features using PDF and CDF
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/b07d2c46-998a-471b-b9b8-2423969ed8ab)
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/e6b8c0d7-eaac-4b99-8221-dd2d47d93725)

### Univariate Analysis on VARIATION features using PDF and CDF
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/ea1bd63b-1617-4d01-8c67-3e8438dd20c0)
![image](https://github.com/shubham-shetty12/Cancer_Diagnosis/assets/137090796/6201c981-7a27-400e-a347-0a5d0437f121)

### Machine Learning Models:
- Trained a random model to check Worst case log loss and log loss obtained was 2.50
- Trained other models along with hyperparameter tuning using Random Search and Grid search method.
- Below Table displays models and their logloss scores.
  

|Model                                      |Log Loss|
| :------------                     |:---------------|
|Naive Bayes                                | 1.2714 |
|K-Nearest Neighbors                        | 1.0984 |
|Logistic Regression without class balance  | 1.0406 |
|Logistic Regression with class balance     | 1.0302 |
|Linear SVM                                 | 1.1046 |
|Random Forest                              | 1.1640 |
|Logistic Regression using ngrams           | 1.0042 |

**Conclusion:** 

Logistic Regression and Linear SVM performed better than other model with a log loss of ~1.03  after trying to use to n-grams =(1,2) and with Logistic Regression model we reduced log loss to ~1, it can futher be reduced using feature engineering techniques.
