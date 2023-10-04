# Ex02-Outlier
# AIM
to examine price_per_sqft column in given bhp.csv which contains property prices in the city of banglore, India. 

 ALGORITHM
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
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/08493d40-76a2-40de-9890-6b75e159ec1f)
```
df = pd.read_csv("bhp.csv")
q1 = df['price_per_sqft'].quantile(0.25)
q2 = df['price_per_sqft'].quantile(0.5)
q3 = df['price_per_sqft'].quantile(0.75)
iqr = q3-q1
iqr
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/9ce6fcf4-506e-413b-9134-88436850657d)
```
low = q1-1.5*iqr
low
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/3accfff8-0352-40d9-8576-e6da12884288)
```
high = q3+1.5*iqr
high
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/ddb7c485-9faf-447a-9b37-7e97bd982844)

```
df = df[((df['price_per_sqft']>=low) & (df['price_per_sqft']<=high))]
df
```


![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/4d513b1e-7ba5-43b5-937b-bee5813e0fff)

```
z = np.abs(stats.zscore(df['price_per_sqft']))
z
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/01b4c79a-1270-4839-b64c-f940f86b8a54)

```
df1 = df[z<3]
df1
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/3a80a513-ddd0-4d70-a539-3b6430f6ac69)

```
from google.colab import files
uploaded = files.upload()
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/1aec4bee-49b1-433b-b707-fed7e991836d)

```
df = pd.read_csv("height_weight.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/efd3990e-6e3c-4339-9812-09c9d75a3999)

```
low = q1 - 1.5*iqr
low
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/8380a1d2-34f1-4fad-89ba-9785b640f8e6)

```
high = q3+1.5*iqr
high
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/27340fa8-c185-4ab4-97f0-f45b9900eaec)

```
df = df[((df['height'] >=low) & (df['height']<= high))]
df
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/7fdf83ca-689e-48e3-915b-74eb24f1b807)

```
z = np.abs(stats.zscore(df['height']))
z
```


![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/d76dcbd0-92e2-4cd6-a0a6-8e968de2a26b)

```
df1 = df[z<3]
df1
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/c4ce43d3-f476-4200-a03a-cd06c9e05935)

```
df = pd.read_csv("height_weight.csv")
q1 = df['weight'].quantile(0.25)
q2 = df['weight'].quantile(0.5)
q3 = df['weight'].quantile(0.75)
iqr = q3-q1
iqr
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/fda5d620-7def-44b9-a134-de03cdce2451)

```
low = q1 - 1.5*iqr
low
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/c3acd65b-f2e2-4a8f-b879-9e0a1c87651a)

```
high = q3 + 1.5*iqr
high
```


![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/68bf17ea-1383-4dfe-8a7e-dccd1141dcad)

```
df1 = df[((df['weight'] >=low) & (df['weight']<= high))]
df1
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/056046bc-7362-489c-867e-67b51059f1d5)

```
z = np.abs(stats.zscore(df1['weight']))
z
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/42e1ea6b-c548-4580-939d-c84d3be22051)

```
df2 = df1[z<3]
df2
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/b257591f-98c9-42c8-bf84-767ea3986e22)

```
from google.colab import files
uploaded = files.upload()
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/36cc32f1-d5e2-4e01-b34d-46914f25cd88)

```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/487fe257-a52a-4b55-ba0e-0ebb254b29d7)

```
low = q1 - 1.5*iqr
low
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/443c981e-c233-49ab-a069-3081173db537)



```
high = q3 + 1.5*iqr
high
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/6ee353b3-9529-45c2-ac6a-a6dee0c1bbea)



```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/5052ea9a-24ee-4ae9-8916-5d84dae20f27)


```
z = np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/0f26df67-1358-411b-9625-4df4b5cc7939)


```
df1 = df[z<3]
df1
```

![image](https://github.com/madhi43/ODD2023---Datascience---Ex-02/assets/103943383/2a8a4804-ae04-465f-8985-1a25cf5503ab)


# RESULT 
 Thus the  price_per_sqft column is examined in the given bhp.csv which contains property prices in the city of banglore, India and the outliers are removed.

