## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
Import Required Libraries and Reading the Dataset:
```
import numpy as np
import pandas as pd
from scipy.stats import boxcox
from sklearn.preprocessing import LabelEncoder,StandardScaler,PowerTransformer
df=pd.read_csv("Data_to_Transform.csv")
print("The Dataset is readed successfully")
print("The Original Dataset:")
print(df.head())
print("The Original Dataset:")
print(df.head())
numeric_column=df.select_dtypes(include=np.number).columns[0]
positive_data=df[df[numeric_column]>0].copy()
```
Log Transformation
```
positive_data["Log Transformation"]=np.log(positive_data[numeric_column])
```
Reciprocal Transformation
```
positive_data["Reciprocal"]=1/positive_data[numeric_column]
```
Square Root Transformation
```
positive_data["Square Root"]=np.sqrt(positive_data[numeric_column])
```
Boxcox method
```
positive_data["Box_cox"],lambda_value=boxcox(positive_data[numeric_column])
```
Yeojohnson method
```
pt=PowerTransformer(method='yeo-johnson')
df['Yeo-Johnson_Transformation']=pt.fit_transform(df[[numeric_column]])
```
# Output:
<img width="989" height="407" alt="image" src="https://github.com/user-attachments/assets/bb9b0d94-aa05-4cf6-899d-6558d8ed4c8b" />

# RESULT:
Thus,The Feature Encoding and Transformation performed successfully

       
