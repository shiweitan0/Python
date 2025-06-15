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

