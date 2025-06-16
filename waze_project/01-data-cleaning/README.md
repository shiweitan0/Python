# 🧹 Data Cleaning

```python
# Load dataset into dataframe
df = pd.read_csv('../data/waze_dataset.csv')
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th>Column Name</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>label</td>
      <td>obj</td>
      <td>Binary target variable (“retained” vs “churned”) for if a user has churned anytime during the course of the month</td>
    </tr>
    <tr>
      <td>sessions</td>
      <td>int</td>
      <td>The number of occurrences of a user opening the app during the month</td>
    </tr>
    <tr>
      <td>drives</td>
      <td>int</td>
      <td>An occurrence of driving at least 1 km during the month</td>
    </tr>
    <tr>
      <td>device</td>
      <td>obj</td>
      <td>The type of device a user starts a session with</td>
    </tr>
    <tr>
      <td>total_sessions</td>
      <td>float</td>
      <td>A model estimate of the total number of sessions since a user has onboarded</td>
    </tr>
    <tr>
      <td>n_days_after_onboarding</td>
      <td>int</td>
      <td>The number of days since a user signed up for the app</td>
    </tr>
    <tr>
      <td>total_navigations_fav1</td>
      <td>int</td>
      <td>Total navigations since onboarding to the user’s favorite place 1</td>
    </tr>
    <tr>
      <td>total_navigations_fav2</td>
      <td>int</td>
      <td>Total navigations since onboarding to the user’s favorite place 2</td>
    </tr>
    <tr>
      <td>driven_km_drives</td>
      <td>float</td>
      <td>Total kilometers driven during the month</td>
    </tr>
    <tr>
      <td>duration_minutes_drives</td>
      <td>float</td>
      <td>Total duration driven in minutes during the month</td>
    </tr>
    <tr>
      <td>activity_days</td>
      <td>int</td>
      <td>Number of days the user opens the app during the month</td>
    </tr>
    <tr>
      <td>driving_days</td>
      <td>int</td>
      <td>Number of days the user drives (at least 1 km) during the month</td>
    </tr>
  </tbody>
</table>
</div>


```python
df.head()
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>label</th>
      <th>sessions</th>
      <th>drives</th>
      <th>total_sessions</th>
      <th>n_days_after_onboarding</th>
      <th>total_navigations_fav1</th>
      <th>total_navigations_fav2</th>
      <th>driven_km_drives</th>
      <th>duration_minutes_drives</th>
      <th>activity_days</th>
      <th>driving_days</th>
      <th>device</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>retained</td>
      <td>283</td>
      <td>226</td>
      <td>296.748273</td>
      <td>2276</td>
      <td>208</td>
      <td>0</td>
      <td>2628.845068</td>
      <td>1985.775061</td>
      <td>28</td>
      <td>19</td>
      <td>Android</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>retained</td>
      <td>133</td>
      <td>107</td>
      <td>326.896596</td>
      <td>1225</td>
      <td>19</td>
      <td>64</td>
      <td>13715.920550</td>
      <td>3160.472914</td>
      <td>13</td>
      <td>11</td>
      <td>iPhone</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>retained</td>
      <td>114</td>
      <td>95</td>
      <td>135.522926</td>
      <td>2651</td>
      <td>0</td>
      <td>0</td>
      <td>3059.148818</td>
      <td>1610.735904</td>
      <td>14</td>
      <td>8</td>
      <td>Android</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>retained</td>
      <td>49</td>
      <td>40</td>
      <td>67.589221</td>
      <td>15</td>
      <td>322</td>
      <td>7</td>
      <td>913.591123</td>
      <td>587.196542</td>
      <td>7</td>
      <td>3</td>
      <td>iPhone</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>retained</td>
      <td>84</td>
      <td>68</td>
      <td>168.247020</td>
      <td>1562</td>
      <td>166</td>
      <td>5</td>
      <td>3950.202008</td>
      <td>1219.555924</td>
      <td>27</td>
      <td>18</td>
      <td>Android</td>
    </tr>
  </tbody>
</table>
</div>

```python
df.info()
```
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 14999 entries, 0 to 14998
    Data columns (total 13 columns):
     #   Column                   Non-Null Count  Dtype  
    ---  ------                   --------------  -----  
     0   ID                       14999 non-null  int64  
     1   label                    14299 non-null  object 
     2   sessions                 14999 non-null  int64  
     3   drives                   14999 non-null  int64  
     4   total_sessions           14999 non-null  float64
     5   n_days_after_onboarding  14999 non-null  int64  
     6   total_navigations_fav1   14999 non-null  int64  
     7   total_navigations_fav2   14999 non-null  int64  
     8   driven_km_drives         14999 non-null  float64
     9   duration_minutes_drives  14999 non-null  float64
     10  activity_days            14999 non-null  int64  
     11  driving_days             14999 non-null  int64  
     12  device                   14999 non-null  object 
    dtypes: float64(3), int64(8), object(2)
    memory usage: 1.5+ MB
    

* From the `df.head()` output, there appears to be no missing values among the variables.

* From the `df.info()` output, the data types for all the variables are predominantly of int64, except for `label` and `device` which is of the object type, `total_sessions`, `driven_km_drives` and `duration_minutes_drives` are of float64.
  
* From the 'Non-Null Count' output from df.info(), of the 14,999 entries, the `label` column only has 14,299 non-null entries, therefore, it has 700 null values.

## Null values and summary statistics

```python
# Display summary stats of rows with null values
df[df['label'].isnull()].describe()
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>sessions</th>
      <th>drives</th>
      <th>total_sessions</th>
      <th>n_days_after_onboarding</th>
      <th>total_navigations_fav1</th>
      <th>total_navigations_fav2</th>
      <th>driven_km_drives</th>
      <th>duration_minutes_drives</th>
      <th>activity_days</th>
      <th>driving_days</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
      <td>700.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>7405.584286</td>
      <td>80.837143</td>
      <td>67.798571</td>
      <td>198.483348</td>
      <td>1709.295714</td>
      <td>118.717143</td>
      <td>30.371429</td>
      <td>3935.967029</td>
      <td>1795.123358</td>
      <td>15.382857</td>
      <td>12.125714</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4306.900234</td>
      <td>79.987440</td>
      <td>65.271926</td>
      <td>140.561715</td>
      <td>1005.306562</td>
      <td>156.308140</td>
      <td>46.306984</td>
      <td>2443.107121</td>
      <td>1419.242246</td>
      <td>8.772714</td>
      <td>7.626373</td>
    </tr>
    <tr>
      <th>min</th>
      <td>77.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>5.582648</td>
      <td>16.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>290.119811</td>
      <td>66.588493</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>3744.500000</td>
      <td>23.000000</td>
      <td>20.000000</td>
      <td>94.056340</td>
      <td>869.000000</td>
      <td>4.000000</td>
      <td>0.000000</td>
      <td>2119.344818</td>
      <td>779.009271</td>
      <td>8.000000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>7443.000000</td>
      <td>56.000000</td>
      <td>47.500000</td>
      <td>177.255925</td>
      <td>1650.500000</td>
      <td>62.500000</td>
      <td>10.000000</td>
      <td>3421.156721</td>
      <td>1414.966279</td>
      <td>15.000000</td>
      <td>12.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>11007.000000</td>
      <td>112.250000</td>
      <td>94.000000</td>
      <td>266.058022</td>
      <td>2508.750000</td>
      <td>169.250000</td>
      <td>43.000000</td>
      <td>5166.097373</td>
      <td>2443.955404</td>
      <td>23.000000</td>
      <td>18.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>14993.000000</td>
      <td>556.000000</td>
      <td>445.000000</td>
      <td>1076.879741</td>
      <td>3498.000000</td>
      <td>1096.000000</td>
      <td>352.000000</td>
      <td>15135.391280</td>
      <td>9746.253023</td>
      <td>31.000000</td>
      <td>30.000000</td>
    </tr>
  </tbody>
</table>
</div>

```python
# Display summary stats of rows without null values
df[df['label'].notnull()].describe()
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>sessions</th>
      <th>drives</th>
      <th>total_sessions</th>
      <th>n_days_after_onboarding</th>
      <th>total_navigations_fav1</th>
      <th>total_navigations_fav2</th>
      <th>driven_km_drives</th>
      <th>duration_minutes_drives</th>
      <th>activity_days</th>
      <th>driving_days</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
      <td>14299.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>7503.573117</td>
      <td>80.623820</td>
      <td>67.255822</td>
      <td>189.547409</td>
      <td>1751.822505</td>
      <td>121.747395</td>
      <td>29.638296</td>
      <td>4044.401535</td>
      <td>1864.199794</td>
      <td>15.544653</td>
      <td>12.182530</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4331.207621</td>
      <td>80.736502</td>
      <td>65.947295</td>
      <td>136.189764</td>
      <td>1008.663834</td>
      <td>147.713428</td>
      <td>45.350890</td>
      <td>2504.977970</td>
      <td>1448.005047</td>
      <td>9.016088</td>
      <td>7.833835</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.220211</td>
      <td>4.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>60.441250</td>
      <td>18.282082</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>3749.500000</td>
      <td>23.000000</td>
      <td>20.000000</td>
      <td>90.457733</td>
      <td>878.500000</td>
      <td>10.000000</td>
      <td>0.000000</td>
      <td>2217.319909</td>
      <td>840.181344</td>
      <td>8.000000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>7504.000000</td>
      <td>56.000000</td>
      <td>48.000000</td>
      <td>158.718571</td>
      <td>1749.000000</td>
      <td>71.000000</td>
      <td>9.000000</td>
      <td>3496.545617</td>
      <td>1479.394387</td>
      <td>16.000000</td>
      <td>12.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>11257.500000</td>
      <td>111.000000</td>
      <td>93.000000</td>
      <td>253.540450</td>
      <td>2627.500000</td>
      <td>178.000000</td>
      <td>43.000000</td>
      <td>5299.972162</td>
      <td>2466.928876</td>
      <td>23.000000</td>
      <td>19.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>14998.000000</td>
      <td>743.000000</td>
      <td>596.000000</td>
      <td>1216.154633</td>
      <td>3500.000000</td>
      <td>1236.000000</td>
      <td>415.000000</td>
      <td>21183.401890</td>
      <td>15851.727160</td>
      <td>31.000000</td>
      <td>30.000000</td>
    </tr>
  </tbody>
</table>
</div>

- The means of the two populations are comparable.  
- However, their **minimum** and **maximum** values differ significantly.  
- This is evident in the following variables:  
  - **`driven_km_drives`** with a difference of ~6000  
  - **`duration_minutes_drives`** with a difference of ~6000  

## Null values - device counts

```python
# Get count of null values by device
df[df['label'].isnull()]['device'].value_counts()
```
```plaintext
device
iPhone     447
Android    253
Name: count, dtype: int64
```
Out of the **700 null values**, there are **447 iPhone** and **253 Android** users that have null values.

```python
# Calculate % of iPhone nulls and Android nulls
df[df['label'].isnull()]['device'].value_counts(normalize = True)
```
    device
    iPhone     0.638571
    Android    0.361429
    Name: proportion, dtype: float64

```python
# Calculate % of iPhone users and Android users in full dataset
df['device'].value_counts(normalize = True)
```
    device
    iPhone     0.644843
    Android    0.355157
    Name: proportion, dtype: float64

The proportion of missing values by device aligns with their overall distribution in the dataset, suggesting the missingness is likely random.


```python
# Calculate counts of churned vs. retained
df['label'].value_counts(normalize = True)
```
    label
    retained    0.822645
    churned     0.177355
    Name: proportion, dtype: float64

The data has **82% retained** and **18% churned** users.

```python
# Calculate median values of all columns for churned and retained users
retained_medians = df[df['label'] == 'retained'].median(numeric_only = True)
churned_medians = df[df['label'] == 'churned'].median(numeric_only = True)
comparison_df = pd.concat([retained_medians, churned_medians], axis = 1)
comparison_df.columns = ['Retained Median', 'Churned Median']
print(comparison_df)
```

                             Retained Median  Churned Median
    ID                           7509.000000     7477.500000
    sessions                       56.000000       59.000000
    drives                         47.000000       50.000000
    total_sessions                157.586756      164.339042
    n_days_after_onboarding      1843.000000     1321.000000
    total_navigations_fav1         68.000000       84.500000
    total_navigations_fav2          9.000000       11.000000
    driven_km_drives             3464.684614     3652.655666
    duration_minutes_drives      1458.046141     1607.183785
    activity_days                  17.000000        8.000000
    driving_days                   14.000000        6.000000
    
* Users who churned averaged ~3 more drives in the last month than retained users, but retained users used the app on over twice as many days as churned users in the same time period.

* The median churned user drove ~200 more kilometers and 2.5 more hours during the last month than the median retained user.

```python
# Calculate the median, and isolate for km per drive
df['km_per_drive'] = df['driven_km_drives'] / df['drives']
df.groupby(by = 'label').median(numeric_only = True)['km_per_drive']
```
    label
    churned     74.109416
    retained    75.014702
    Name: km_per_drive, dtype: float64

```python
# Calculate the median, and isolate for km per driving day
df['km_per_driving_day'] = df['driven_km_drives'] / df['driving_days']
df.groupby(by = 'label').median(numeric_only = True)['km_per_driving_day']
```
    label
    churned     697.541999
    retained    289.549333
    Name: km_per_driving_day, dtype: float64

```python
# Calculate the median, and isolate for drives per driving day
df['drives_per_driving_day'] = df['drives'] / df['driving_days']
df.groupby(by = 'label').median(numeric_only = True)['drives_per_driving_day']
```
    label
    churned     10.0000
    retained     4.0625
    Name: drives_per_driving_day, dtype: float64

* Churned users take more drives per driving day (e.g., 10 drives/day vs 4 for retained).

* Each drive is about the same length for both groups (~74–75 km).

* Because churned users drive more times per day, their total kilometers per driving day is much higher.
 

```python
# For each label, calculate the number of Android users and iPhone users
df.groupby(by = 'label')['device'].value_counts(normalize = True)
```
    label     device 
    churned   iPhone     0.648659
              Android    0.351341
    retained  iPhone     0.644393
              Android    0.355607
    Name: proportion, dtype: float64

## Data overview

* The dataset contains 82% retained and 18% churned users, indicating a significant class imbalance.

* Device distribution is 64% iPhone and 36% Android, with comparable churn rates across both.

* Median values were used for comparisons due to their robustness to outliers.

* The `label` column has 700 missing values.

* Interestingly, churned users drove nearly 240% more kilometers per driving day than retained users, prompting further investigation.

