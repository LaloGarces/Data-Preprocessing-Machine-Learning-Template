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
