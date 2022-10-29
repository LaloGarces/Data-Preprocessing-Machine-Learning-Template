# Data Preprocessing Machine Learning Template

## This is a Colab Template to be used as Data Preprocessing step before apply any ML Model. Within the Notebook, you will find the explanation and details of the “Why” of these steps presented on this template.

### In this template, we present this 6 essential preprocessing steps: 

 - Importing libraries
 - Importing the dataset
 - Deal with missing data
 - Encode categorical data
 - Split the dataset into Training and Test
 - Feature Scaling
 
### 1.- Importing libraries

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import sklearn as sk

```

 
### 2.- Importing dataset

```
from google.colab import drive
drive.mount("/content/gdrive")
from google.colab import files
uploaded = files.upload()

```

```
dataset = pd.read_csv("dataset.csv")
```

### 3.- Deal with missing data

```
from sklearn.impute import SimpleImputer
imputer = SimpleImputer(missing_values=np.nan, strategy='mean')
imputer.fit(x[:, :])
x[:, :] = imputer.transform(x[:, :])
```

### 4.- Encoding Categorical Data

```
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder
ct = ColumnTransformer(transformers=[('encoder', OneHotEncoder(), [])], remainder='passthrough')
x = np.array(ct.fit_transform(x))
```

### 5.- Split the data into Training and Test Set

```
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size = 0.2, random_state = 1)
```


### 6.- Feature Scaling

```
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
x_train[:,:] = sc.fit_transform(x_train[:, :])
x_test[:, :] = sc.fit_transform(x_test[:, :])
```
