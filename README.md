# Ex02-Outlier
You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

CODE and OUTPUT:
```
import pandas as pd
import seaborn as sns
from scipy import stats
import numpy as np
```
```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/9ce6fcf4-506e-413b-9134-88436850657d)
