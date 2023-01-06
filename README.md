# CS115-Report

## I. Datasets

### Source data

- The dataset was used in the report is [Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
- 
### Context 

- This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective of the dataset is to diagnostically predict whether or not a patient has diabetes, based on certain diagnostic measurements included in the dataset. Several constraints were placed on the selection of these instances from a larger database. In particular, all patients here are females at least 21 years old of Pima Indian heritage.

### Content

- The datasets consists of several medical predictor variables and one target variable, Outcome. Predictor variables includes the number of pregnancies the patient has had, their BMI, insulin level, age, and so on.

## II. Data Exploration

### Columns of dataset

> 1. Pregnancies
> 2. Glucose
> 3. BloodPressure
> 4. SkinThickness
> 5. Insulin
> 6. BMI
> 7. DiabetesPedigreeFunction
> 8. Age
> 9. Outcome

### Samples and Features

- There are 768 **sample** and 9 columns which can be divided into 8 ***features*** and 1 ***label output***.
- The output only has 2 class (1 or 0) but seem like the 0 class is approximately **twice** than 1 class (268-1 and 500-1).

### Features exploration

- The zero value of each feature. 

| Name of columns | number of 0 value |
|:----------------|------------------:|
| Pregnancies | 111 |
| Glucose | 5 |
| BloodPressures | 35 |
| SkinThickness | 227 |
| Insulin | 374 |
| BMI | 11 |
| DiabetesPedigreeFunction | 0 |
| Age | 0 |

- It can be ensure that Pregnancies can have 0 value (did not have pregnance before). But with 5 features named Glucose, BloodPressures, SkinThickness, Insulin and BMI can not be 0 because of medical in numberal. 
- Which means those 0 values are **missing data** and a suitable solution for this database is replacing all missing values of these 5 features by mean or median value of each feature.

## II. Feature engineer

### Balancing data

- As mentioned before, the label output has only 268 labels of 1 this number of 0 is 500 labels. This leads to imbalanced data and predictive model we build can be inclined to class 0.
- The solution here is ***over samples*** to the class 1 which mean increasing the number of class 1 samples up to 500 samples.
- Now we have 1000 samples which 500 samples of each class and the data now is balanced.

### Work with missing data

- There are of zero values of each features but we just concentrate on 5 features(Glucose, BloodPressures, SkinThickness, Insulin and BMI).
- The solution is to replace all missing value by mean or median value of each features, here is mean one used.
- The number of 0 value after replacing.

| Name of columns | number of 0 value |
|:----------------|------------------:|
| Pregnancies | 111 |
| Glucose | 0 |
| BloodPressures | 0 |
| SkinThickness | 0 |
| Insulin | 0 |
| BMI | 0 |
| DiabetesPedigreeFunction | 0 |
| Age | 0 |

### Scaling method

- There are two methods to scale the data is **Normalization** and **Standardization**.
- Here i use the Normalization methods to scale.

### Dimensionality reduction

- **Principal component analysis** (PCA) is a usefull and common solution to reduce the feature vector but still keep anough information to train the predictive model.
- With the number of features(8) it seem to be meaningless but in this report still showing the result of using pca.

### Adding more features

- This method is completely different from **Dimensionality reduction**.
- The result of using this method is showed in this report.
