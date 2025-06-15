> **Disclaimer:**  
> This project was completed as part of the **Google Advanced Data Analytics Professional Certificate on Coursera**. The dataset and business scenario are provided through the course for educational purposes.
> 
> **Author:** Tan Shi Wei  
> **Date:** 2025-06-04  
> **Project:** Waze User Churn Prediction
> 
> _📑 Tip: Use GitHub’s Outline tab to quickly navigate through the sections of this README._

# 📌 Context and Objective

<p align="center">
  <img src="https://github.com/user-attachments/assets/955e8943-b5e6-4aa4-a70c-fc4c311d5f45" alt="Waze Logo" width="200" height="200" />
</p>

This project focuses on predicting monthly user churn for Waze, a community-driven navigation app that partners with users, map editors, and organizations worldwide to improve the driving experience. It supports Waze’s broader effort to boost user growth and increase retention.

## Key Stakeholders

<div align="center">
  <table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; text-align: center;">
    <thead>
      <tr>
        <th>Name</th>
        <th>Role</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Harriet Hadzic</td>
        <td>Director of Data Analysis</td>
      </tr>
      <tr>
        <td>May Santner</td>
        <td>Data Analysis Manager</td>
      </tr>
      <tr>
        <td>Chidi Ga</td>
        <td>Senior Data Analyst</td>
      </tr>
      <tr>
        <td>Sylvester Esperanza</td>
        <td>Senior Project Manager</td>
      </tr>
      <tr>
        <td>Emrick Larson</td>
        <td>Finance & Administration Head</td>
      </tr>
      <tr>
        <td>Ursula Sayo</td>
        <td>Operations Manager</td>
      </tr>
    </tbody>
  </table>
</div>

> **Note:** All names, characters, and events in this project are fictional. No identification with actual persons (living or deceased) is intended or should be inferred. The data shared in this project has been altered for pedagogical purposes.

By analyzing user behavior data and building a predictive model, this project aims to:

* **Identify** which users are most likely to churn  
* **Uncover** when churn typically occurs  
* **Understand** potential reasons behind churn  

**The goal is to build a machine learning model that identifies users at risk of leaving, enabling Waze to engage them proactively with targeted retention strategies that enhance user satisfaction and drive business growth.**

# 🧭 Roadmap

This project followed the P.A.C.E framework of *Plan*, *Analyze*, *Construct* and *Execute* for a clear and structured analysis.

<details>
  <summary><em>Click to see detailed task-stage mapping</em></summary>

## Milestones and Deliverables

<div align="center">
  <table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; text-align: center;">
    <thead>
      <tr>
        <th>Milestone</th>
        <th>Tasks</th>
        <th>P.A.C.E</th>
        <th>Deliverables / Reports</th>
        <th>Stakeholder(s)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>1</strong></td>
        <td>Establish structure for project workflow</td>
        <td>Plan</td>
        <td>Global-level project document</td>
        <td>
          • May Santner
        </td>
      </tr>
      <tr>
        <td><strong>1a</strong></td>
        <td>Write a project proposal</td>
        <td>Plan</td>
        <td></td>
        <td>
          • Sylvester Esperanza
        </td>
      </tr>
      <tr>
        <td><strong>2</strong></td>
        <td>Compile summary information about the data</td>
        <td>Analyze</td>
        <td>Data files ready for EDA</td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>2a</strong></td>
        <td>Begin exploring the data</td>
        <td>Analyze</td>
        <td></td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>3</strong></td>
        <td>Data exploration and cleaning</td>
        <td>Plan and Analyze</td>
        <td>EDA report</td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>3a</strong></td>
        <td>Visualization building</td>
        <td>Analyze and Construct</td>
        <td>Tableau dashboard / visualizations</td>
        <td>
          • Sylvester Esperanza
        </td>
      </tr>
      <tr>
        <td><strong>4</strong></td>
        <td>Compute descriptive statistics</td>
        <td>Analyze</td>
        <td>Analysis of testing results between two important variables</td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>4a</strong></td>
        <td>Conduct hypothesis testing</td>
        <td>Analyze and Construct</td>
        <td></td>
        <td>
          • May Santner
        </td>
      </tr>
      <tr>
        <td><strong>5</strong></td>
        <td>Build a regression model</td>
        <td>Analyze and Construct</td>
        <td></td>
        <td>
          • May Santner
        </td>
      </tr>
      <tr>
        <td><strong>5a</strong></td>
        <td>Evaluate the model</td>
        <td>Execute</td>
        <td>Determine the success of the model</td>
        <td>
          • Harriet Hadzic
        </td>
      </tr>
      <tr>
        <td><strong>6</strong></td>
        <td>Build a machine learning model</td>
        <td>Construct</td>
        <td>Final model</td>
        <td>
          • Harriet Hadzic
        </td>
      </tr>
      <tr>
        <td><strong>6a</strong></td>
        <td>Communicate final insights with stakeholders</td>
        <td>Execute</td>
        <td>Final report presentation</td>
        <td>
          • Harriet Hadzic<br>
          • Emrick Larson<br>
          • Ursula Sayo
        </td>
      </tr>
    </tbody>
  </table>
</div>

---

## Estimated Timeline

- **Milestone 1**: 1–2 days  
- **Milestone 2**: 2–3 weeks  
- **Milestone 3**: 1 week  
- **Milestone 4**: 1 week  
- **Milestone 5**: 1–2 weeks  

</details>

# 📦 Import Libraries

```python
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
from matplotlib import pyplot as plt
```

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

# 📊 Exploratory Data Analysis

## **Visualizations**

```python
def boxplotter(col, figsize = (5, 2), fliersize = 1):
    plt.figure(figsize=figsize)
    sns.boxplot(x = df[col], fliersize = fliersize)
    plt.tight_layout()
    plt.show()
```

```python
def histogrammer(col, figsize = (8, 5), discrete = False, bins = 'auto'):
    plt.figure(figsize = figsize)
    sns.histplot(x = df[col], discrete = discrete, bins = bins)
    plt.tight_layout()
    plt.show()
```
### Individual Variable Analysis
**`sessions`**

_The number of occurrence of a user opening the app during the month_


```python
boxplotter('sessions')
``` 
<p align="center">
  <img src="https://github.com/user-attachments/assets/82adb330-7d42-42f5-a02a-e553d43166fc" alt="Image" />
</p>
    
```python
histogrammer('sessions')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/7ba087b3-043e-4bf9-91f8-b6b6f3b75567" alt="Image" />
</p>
    

**`drives`**

_An occurrence of driving at least 1 km during the month_


```python
boxplotter('drives')
``` 
<p align="center">
  <img src="https://github.com/user-attachments/assets/ff89a6da-d241-4a9c-94ab-905e01654863" alt="Image" />
</p>
    
```python
histogrammer('drives')
```    
<p align="center">
  <img src="https://github.com/user-attachments/assets/3a611215-275d-4557-93fc-b8eebc49e03f" alt="Image" />
</p>
    

**`total_sessions`**

_A model estimate of the total number of sessions since a user has onboarded_


```python
boxplotter('total_sessions')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/a032aba6-cfef-4729-b815-9b588cae8635" alt="Image" />
</p>
    
```python
histogrammer('total_sessions')
```    
<p align="center">
  <img src="https://github.com/user-attachments/assets/39884877-b2f1-46e7-8b5e-c11753b4059e" alt="Image" />
</p>
    

**`n_days_after_onboarding`**

_The number of days since a user signed up for the app_


```python
boxplotter('n_days_after_onboarding')
```  
<p align="center">
  <img src="https://github.com/user-attachments/assets/5abc988e-7167-4200-9aa3-1969a4c4a64c" alt="Image" />
</p>

```python
histogrammer('n_days_after_onboarding')
``` 
<p align="center">
  <img src="https://github.com/user-attachments/assets/668b65cf-c7a8-4109-85af-7255d6c28d94" alt="Image" />
</p>
    

**`driven_km_drives`**

_Total kilometers driven during the month_


```python
boxplotter('driven_km_drives')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/e8733f5a-a25e-48b0-95a9-318cef1bc847" alt="Image" />
</p>
    
```python
histogrammer('driven_km_drives')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/411d4721-42f0-4230-85af-765c06095ddb" alt="Image" />
</p>
    

**`duration_minutes_drives`**

_Total duration driven in minutes during the month_


```python
boxplotter('duration_minutes_drives')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/7136b3aa-f6b6-4f72-88c7-98d4ff5d94f2" alt="Image" />
</p>
  
```python
histogrammer('duration_minutes_drives')
``` 
<p align="center">
  <img src="https://github.com/user-attachments/assets/f59a364c-79fc-43c1-933e-a2f327a1290a" alt="Image" />
</p>
    

**`activity_days`**

_Number of days the user opens the app during the month_


```python
boxplotter('activity_days')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/62c3cf09-e6ca-460c-b6f5-7825d6435c54" alt="Image" />
</p>
    
```python
histogrammer('activity_days', discrete = True)
```    
<p align="center">
  <img src="https://github.com/user-attachments/assets/824b2af3-9209-4192-8c44-0dd8e632af15" alt="Image" />
</p>
    

**`driving_days`**

_Number of days the user drives (at least 1 km) during the month_


```python
boxplotter('driving_days')
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/60842c38-9641-4175-b3c9-f1b65c88222d" alt="Image" />
</p>
    
```python
histogrammer('driving_days', discrete = True)
```  
<p align="center">
  <img src="https://github.com/user-attachments/assets/5e64eb6e-27c0-4f1b-802a-89006bd46ed0" alt="Image" />
</p>
    
The above variables exhibited histograms that were either right-skewed or uniformly distributed.
Notable patterns and insights were particularly evident in the following variables:
- `total_sessions`: The median values in `sessions` and `total_sessions` were ~ 48 and ~160 respectively. This indicates that majority of users used the app in their last month.
- `activity_days` and `driving_days`: One would expect these two variables share a strong correlation. However, `activity_days` has a uniform distribution, while, `driving_days` has a right skewed one. These discrepancies are apparent at the start and end of the variables respective histograms, where users `activity_days` and `driving_days` do not tally.

**`device`**

_The type of device a user starts a session with_

```python
plt.figure(figsize = (3,3))
plt.pie(df['device'].value_counts(), labels = df['device'].value_counts().index, autopct='%1.1f%%')
plt.axis('equal');
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/45d1b695-33b0-435a-8403-44862cd84036" alt="Image" />
</p>
    
There are nearly twice as many iPhone users as Android users represented in this data.

**`label`**

_Binary target variable (“retained” vs “churned”) for if a user has churned anytime during the course of the month_

```python
plt.figure(figsize = (3,3))
plt.pie(df['label'].value_counts(), labels = df['label'].value_counts().index, autopct='%1.1f%%')
plt.axis('equal');
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/b3f17784-5a9f-4ab9-ab9e-5145cd3cb030" alt="Image" />
</p>
    
Less than 18% of the users churned.


### Relational & Grouped Analysis

**`driving_days` vs. `activity_days`**

```python
plt.figure(figsize = (8,5))
plt.hist(x = [df['driving_days'], df['activity_days']], bins = 'auto', label = ['driving days', 'activity days'])
plt.xlabel('counts')
plt.legend();
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/ff956dfc-71bd-46ef-bdf0-969dd34ac0d2" alt="Image" />
</p>
    
```python
plt.figure(figsize = (8,5))
sns.stripplot(x = df['driving_days'],
              y = df['activity_days']);
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/24ca6906-f637-4364-b6b5-c9af71f5d510" alt="Image" />
</p>
    
The differing maximum values and inconsistencies between `driving_days` and `activity_days` challenge the assumption that these variables are closely aligned. While every driving day is also an activity day, the reverse isn't always true, as users may open the app to check routes or traffic without actually driving. Clarifying this discrepancy with the data team would be important before proceeding with further analysis.

**Retention by device**

```python
plt.figure(figsize = (8,5))
sns.histplot(x = df['device'], hue = df['label'], multiple = 'dodge', stat = 'percent')
plt.legend(labels=['Retained', 'Churned']);
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/59ff7d20-af4e-48ea-aaa1-88300cd2a473" alt="Image" />
</p>
    
The proportion of churned users to retained users is consistent between device types.

**Retention by kilometers driven per driving day**
```python
df['km_per_driving_day'] = df['driven_km_drives'] / df['driving_days']
df['km_per_driving_day'].describe()
```
    
    count    1.499900e+04
    mean              inf
    std               NaN
    min      3.022063e+00
    25%      1.672804e+02
    50%      3.231459e+02
    75%      7.579257e+02
    max               inf
    Name: km_per_driving_day, dtype: float64

The infinity values are due to there being values of zero in the `driving_days` column, where Pandas imputes a value of infinity in the corresponding rows of the new column because division by zero is undefined.

```python
# Convert infinite values to zero
df.loc[df['km_per_driving_day'] == np.inf, 'km_per_driving_day'] = 0
df['km_per_driving_day'].describe()
```
    count    14999.000000
    mean       578.963113
    std       1030.094384
    min          0.000000
    25%        136.238895
    50%        272.889272
    75%        558.686918
    max      15420.234110
    Name: km_per_driving_day, dtype: float64

The maximum value is 15,420 kilometers _per drive day_,which is physically impossible. Therefore,  rows where the distance in this column is greater than 1,200 km would be excluded.

```python
plt.figure(figsize = (8,5))
sns.histplot(x = df[df['km_per_driving_day'] <= 1200]['km_per_driving_day'], hue = df['label'], multiple = 'fill')   
plt.ylabel('%');
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/409acdde-c9d5-4a13-a71f-7d3656119afa" alt="Image" />
</p>
    

**Churn rate per number of driving days**
```python
plt.figure(figsize = (8,5))
sns.histplot(x = df['driving_days'], hue = df['label'], bins = 'auto', discrete = True, multiple = 'fill')
plt.ylabel('%');
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/1652e069-1d7c-430f-9346-770a5bf77a37" alt="Image" />
</p>
    

- Churn is highest (40%) among users with no app usage last month.

- Users with more frequent use are less likely to churn.

- Churn from non-users may stem from past dissatisfaction or reduced need (e.g., better public transit).

- Heavy-user churn would indicate current dissatisfaction, which isn’t observed.

- `km_per_driving_day` positively correlates with churn—users driving more km per day tend to churn more.

- `driving_days` negatively correlates with churn—users driving on more days tend to churn less.

**Proportion of sessions that occurred in the last month**
```python
df['percent_sessions_in_last_month'] = df['sessions'] / df['total_sessions'] * 100
```
```python
plt.figure(figsize = (5,5))
sns.histplot(x = df['percent_sessions_in_last_month']);
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/12eb1463-f318-4be0-a592-33fcce0d4aa3" alt="Image" />
</p>
    
```python
print(float(df['percent_sessions_in_last_month'].median()))
print(float(df['n_days_after_onboarding'].median()))
```
    42.30970299276318
    1741.0
    
```python
plt.figure(figsize = (8,5))
sns.histplot(x = df[df['percent_sessions_in_last_month'] >= 40]['n_days_after_onboarding']);
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/afbb42cc-8fe9-419f-b775-72f47ec99fbf" alt="Image" />
</p>
    
- Half of users had ≥40% of sessions in the last month despite a median onboarding time of ~5 years.

- Days since onboarding for these users are uniformly distributed.

- This unusual spike in recent usage among long-term users warrants further investigation.

## Handling outliers

The boxplots for individual variables revealed several extreme values, highlighting the presence of outliers that could skew the analysis. To address this, values beyond the 95th percentile were capped to reduce their influence while preserving overall data integrity.

```python
def impute_outliers(column_name):
    min_val = df[column_name].min()
    max_val = df[column_name].max()
    percentile_95 = df[column_name].quantile(0.95)
    df.loc[df[column_name] > percentile_95, column_name] = percentile_95
```

```python
impute_outliers('sessions')
impute_outliers('drives')
impute_outliers('total_sessions')
impute_outliers('driven_km_drives')
impute_outliers('duration_minutes_drives')
```

```python
df.describe()
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
      <th>km_per_driving_day</th>
      <th>percent_sessions_in_last_month</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
      <td>14999.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>7499.000000</td>
      <td>76.568705</td>
      <td>64.058204</td>
      <td>184.031320</td>
      <td>1749.837789</td>
      <td>121.605974</td>
      <td>29.672512</td>
      <td>3939.632764</td>
      <td>1789.647426</td>
      <td>15.537102</td>
      <td>12.179879</td>
      <td>578.963113</td>
      <td>44.925534</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4329.982679</td>
      <td>67.297958</td>
      <td>55.306924</td>
      <td>118.600463</td>
      <td>1008.513876</td>
      <td>148.121544</td>
      <td>45.394651</td>
      <td>2216.041510</td>
      <td>1222.705167</td>
      <td>9.004655</td>
      <td>7.824036</td>
      <td>1030.094384</td>
      <td>28.691863</td>
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
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>3749.500000</td>
      <td>23.000000</td>
      <td>20.000000</td>
      <td>90.661156</td>
      <td>878.000000</td>
      <td>9.000000</td>
      <td>0.000000</td>
      <td>2212.600607</td>
      <td>835.996260</td>
      <td>8.000000</td>
      <td>5.000000</td>
      <td>136.238895</td>
      <td>19.622145</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>7499.000000</td>
      <td>56.000000</td>
      <td>48.000000</td>
      <td>159.568115</td>
      <td>1741.000000</td>
      <td>71.000000</td>
      <td>9.000000</td>
      <td>3493.858085</td>
      <td>1478.249859</td>
      <td>16.000000</td>
      <td>12.000000</td>
      <td>272.889272</td>
      <td>42.309703</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>11248.500000</td>
      <td>112.000000</td>
      <td>93.000000</td>
      <td>254.192341</td>
      <td>2623.500000</td>
      <td>178.000000</td>
      <td>43.000000</td>
      <td>5289.861262</td>
      <td>2464.362632</td>
      <td>23.000000</td>
      <td>19.000000</td>
      <td>558.686918</td>
      <td>68.721626</td>
    </tr>
    <tr>
      <th>max</th>
      <td>14998.000000</td>
      <td>243.000000</td>
      <td>201.000000</td>
      <td>454.363204</td>
      <td>3500.000000</td>
      <td>1236.000000</td>
      <td>415.000000</td>
      <td>8889.794236</td>
      <td>4668.899349</td>
      <td>31.000000</td>
      <td>30.000000</td>
      <td>15420.234110</td>
      <td>153.063707</td>
    </tr>
  </tbody>
</table>
</div>



# ⚖️ Statistical Hypothesis Testing

> While differences in averages are observed across groups, hypothesis testing is necessary to determine whether these differences are statistically significant or simply due to random variation in the sample data.

## Assumptions and Steps

Assumptions of a hypothesis test:
* Independence: Observations should be independent of each other.
* Random sampling: The data should be collected using a random sampling method to ensure representativeness.
* Normality: The sampling distribution of the test statistic should be approximately normally distributed. Thanks to the Central Limit Theorem, for sample sizes typically n ≥ 30, the sampling distribution tends to be approximately normal even if the underlying data is not.

Steps for conducting a hypothesis test:

1.   State the null hypothesis and the alternative hypothesis
2.   Choose a signficance level
3.   Find the p-value
4.   Reject or fail to reject the null hypothesis

> A 5% significance level (α = 0.05) is chosen for all hypothesis tests.
> 
> Since the dataset is a sample with unknown and potentially unequal population variances, `equal_var` is set to False in `stats.ttest_ind()` to relax the equal variance assumption.

## Hypothesis Testing: Comparison of Driving Activity Between iPhone and Android Users

### Descriptive Statistics

```python
df.groupby('device')['drives'].mean()
```
    device
    Android    66.231838
    iPhone     67.859078
    Name: drives, dtype: float64

$H_0$ : The average number of drives for iPhone users is equal to that for Android users. $\mu_{\text{iPhone}} = \mu_{\text{Android}}$

$H_A$ : The average number of drives for iPhone users is not equal to that for Android users. $\mu_{\text{iPhone}} \neq \mu_{\text{Android}}$

```python
iphone_drives = df[df['device'] == 'iPhone']['drives']
android_drives = df[df['device'] == 'Android']['drives']
```
```python
print(iphone_drives.shape)
print(android_drives.shape)
```
    (9672,)
    (5327,)
    
### Visualizations
```python
sns.histplot(iphone_drives, kde = True, color = 'blue');
```
<p align="center">
  <img src = "https://github.com/user-attachments/assets/0eae5910-e50d-4695-9718-661fb176fae1" alt="Image" />
</p>
  
```python
sns.histplot(android_drives, kde = True, color = 'blue');
```
<p align="center">
  <img src = "https://github.com/user-attachments/assets/7edc0d9e-5de5-40f6-ba38-3e8eb850ddee" alt="Image" />
</p>

### Hypothesis Testing

```python
# Perform the t-test
statistic, p_value, = stats.ttest_ind(a = iphone_drives, b = android_drives, equal_var = False)
print(p_value)
```
    0.143351972680206
  
The p-value for the hypothesis test is 0.143 (14.3%). Since 14.3% is greater than the preset significance level of 5%, we fail to reject the null hypothesis. Therefore, there is not enough evidence to conclude that the average number of drives differs between iPhone and Android users, and that any observed difference is likely due to random chance.

### Business Insights

* Device type likely does not influence driving behavior in terms of frequency.

* Marketing campaigns and resource allocation for user engagement can be designed and distributed universally across iPhone and Android users.

* Product features related to driving can be applied broadly across both platforms.

* Further analysis may be needed to explore other user behaviors or segments where device type matters.

## Hypothesis Testing: Impact of Driving Activity on User Retention

### Descriptive Statistics

```python
df.groupby('label')['drives'].mean()
```

    label
    churned     72.730678
    retained    66.075491
    Name: drives, dtype: float64

$H_0$ : The average number of drives for churned users is equal to that for retained users. $\mu_{\text{churned}} = \mu_{\text{retained}}$

$H_A$ : The average number of drives for churned users is not equal to that for retained users. $\mu_{\text{churned}} \neq \mu_{\text{retained}}$

```python
churned_drives = df[df['label'] == 'churned']['drives']
retained_drives = df[df['label'] == 'retained']['drives']
```

```python
print(churned_drives.shape)
print(retained_drives.shape)
```
    (2536,)
    (11763,)
    
### Visualizations

```python
sns.histplot(churned_drives, kde = True, color = 'blue');
```
<p align="center">
  <img src = "https://github.com/user-attachments/assets/63c21eac-1735-4355-8ca5-be94df383b7a" alt="Image" />
</p>
    
```python
sns.histplot(retained_drives, kde = True, color = 'blue');
```
<p align="center">
  <img src = "https://github.com/user-attachments/assets/0c5e2a1f-07eb-4c4f-bb28-c9815ae17123" alt="Image" />
</p>

### Hypothesis Testing

```python
# Perform the t-test
statistic, p_value, = stats.ttest_ind(a = churned_drives, b = retained_drives, equal_var = False)
print(p_value)
```
    1.804915245718726e-05
    
The p-value for the hypothesis test is 0.000018 or 0.0018%. Since 0.0018% is much smaller than the preset significance level of 5%, we reject the null hypothesis. Therefore, there is enough evidence to conclude that the average number of drives differs between churned and retained users, and that any observed difference is highly unlikely to be due to random chance.

### Business Insights

* Driving activity is a strong indicator of user retention.

* Retention strategies should focus on increasing driving activity.

* Target low-drive users with re-engagement campaigns.

## Hypothesis Testing: App Usage Activity Differences Between Churned and Retained Users

### Descriptive Statistics

```python
df.groupby('label')['activity_days'].mean()
```
    label
    churned      9.644716
    retained    16.816628
    Name: activity_days, dtype: float64

$H_0$ : There is no difference in the average number of app activity days between retained and churned users. $\mu_{\text{churned}} = \mu_{\text{retained}}$

$H_A$ : There is a significant difference in the average number of app activity days between retained and churned users. $\mu_{\text{churned}} \neq \mu_{\text{retained}}$

```python
churned_activity = df[df['label'] == 'churned']['activity_days']
retained_activity = df[df['label'] == 'retained']['activity_days']
```

```python
print(churned_activity.shape)
print(retained_activity.shape)
```
    (2536,)
    (11763,)
    
### Visualizations

```python
sns.histplot(churned_activity, kde = True, color = 'blue');
```
<p align="center">
  <img src = "https://github.com/user-attachments/assets/4ca3ede0-8dc4-4db8-bdda-c6f9d8e1c772" alt="Image" />
</p>

```python
sns.histplot(retained_activity, kde = True, color = 'blue');
```
<p align="center">
  <img src = "https://github.com/user-attachments/assets/67534cdb-293e-41b0-b2ca-f75a6ecaf2d5" alt="Image" />
</p>

### Hypothesis Testing

```python
# Perform the t-test
statistic, p_value = stats.ttest_ind(a = churned_activity, b = retained_activity, equal_var = False)
print(p_value)
```
    0.0
    
The p-value for the hypothesis test is approximately 0, indicating an extremely small probability that the observed difference occurred by random chance. Since this is far below the preset significance level of 5%, we reject the null hypothesis. Therefore, there is strong evidence to conclude that the average activity days differs significantly between churned and retained users.

### Business Insights

* App activity is strongly associated with user retention.

* Low activity days are a red flag for churn.

* Product and marketing teams should collaborate to keep users engaged.
