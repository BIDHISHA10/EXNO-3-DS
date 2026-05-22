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
## Name:Gogineni Bidhisha
## Reg No:212223040048
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
```
<img width="377" height="458" alt="image" src="https://github.com/user-attachments/assets/df0ca054-1e85-4e17-9393-98430409d665" />

```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
bidhisha=OrdinalEncoder(categories=[pm])
bidhisha.fit_transform(df[["ord_2"]])
```
<img width="185" height="240" alt="image" src="https://github.com/user-attachments/assets/237288a5-adb2-4c42-bef2-b5604c21a018" />

```
df['bo2']=bidhisha.fit_transform(df[["ord_2"]])
print(df)
```

<img width="437" height="266" alt="image" src="https://github.com/user-attachments/assets/5266fd74-fd9a-4e52-be18-267bd0612a25" />

```
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
```

<img width="422" height="467" alt="image" src="https://github.com/user-attachments/assets/19091893-0617-4695-9dad-80d35c38b492" />

```
from sklearn.preprocessing import OneHotEncoder
ohe = OneHotEncoder(sparse_output=False)
df2 = df.copy()
enc = pd.DataFrame(ohe.fit_transform(df2[["nom_0"]]))
df2 = pd.concat([df2, enc], axis=1)
df2
```
<img width="543" height="461" alt="image" src="https://github.com/user-attachments/assets/393654a9-6691-4b44-a2ac-811cc2c276e9" />

```
 pd.get_dummies(df2,columns=["nom_0"])
```

<img width="833" height="470" alt="image" src="https://github.com/user-attachments/assets/52eb0766-67e9-4ff3-b19f-281a230526b8" />

```
pip install category_encoders

```
<img width="983" height="461" alt="image" src="https://github.com/user-attachments/assets/9ba6c6e1-92cd-4681-a415-06cc39ee07bc" />

```
from category_encoders import BinaryEncoder
df=pd.read_csv("data.csv")
df
```
<img width="612" height="447" alt="image" src="https://github.com/user-attachments/assets/ab625219-6a7d-49b9-b9f9-662eb33da7cd" />

```
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
df
```
<img width="605" height="485" alt="image" src="https://github.com/user-attachments/assets/5601f4a3-a7d9-4c0e-9b5a-6a9a3c35fd49" />

```
dfb=pd.concat([df,nd],axis=1)
dfb
```

<img width="872" height="478" alt="image" src="https://github.com/user-attachments/assets/b20e2bd3-9b53-4367-8152-60440e1ae93a" />


```
from category_encoders import TargetEncoder
 te=TargetEncoder()
 CC=df.copy()
 new=te.fit_transform(X=CC["City"],y=CC["Target"])
 CC=pd.concat([CC,new],axis=1)
 CC
```
<img width="700" height="455" alt="image" src="https://github.com/user-attachments/assets/7c1ceb18-30ab-4c27-86cd-bb31de86166f" />

# RESULT:

Thus the given data, Feature Encoding, Transformation process and save the data to a file was performed successfully.
       
