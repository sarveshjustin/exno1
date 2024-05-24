# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: 
Read the given Data

STEP 2: 
Get the information about the data

STEP 3: 
Remove the null values from the data

STEP 4: 
Save the Clean data to the file

STEP 5: 
Remove outliers using IQR

STEP 6: 
Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/23007232/exno1/assets/139115574/f9dbdc04-4be5-4b20-a96a-45a7ceacc3eb)

```
print(df.head(7))
```
![image](https://github.com/23007232/exno1/assets/139115574/52aa8716-92e3-4c73-807e-d5098b4199b0)

```
print(df.tail(2))
```
![image](https://github.com/23007232/exno1/assets/139115574/a3473664-cab9-428f-a6e8-dc268f3530c0)

```
df.info()
```
![image](https://github.com/23007232/exno1/assets/139115574/5633fb67-da73-49d9-b382-a57e130da727)

```
print(df.describe())
```
![image](https://github.com/23007232/exno1/assets/139115574/3dd0d199-d6b3-4f1d-be24-7636cbb305f5)

```
df.isnull().sum()
```
![image](https://github.com/23007232/exno1/assets/139115574/10ed0633-fd3c-4d2b-b7d6-84074af42c42)

```
df.nunique()
```
![image](https://github.com/23007232/exno1/assets/139115574/31fef60e-095c-439d-822d-83d37497582b)

```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/23007232/exno1/assets/139115574/5b0e4d17-ba80-4bad-a757-a8dd4a157e2c)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/23007232/exno1/assets/139115574/9583ad8b-0e21-465a-81f6-eb80bdaa8fb9)

```
min=df.M4.min()
min
```
![image](https://github.com/23007232/exno1/assets/139115574/4f939806-c897-4023-bd84-f2fc0228a6ec)

```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/23007232/exno1/assets/139115574/0fe9d119-9955-46e4-aa4d-f015ee42a054)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/23007232/exno1/assets/139115574/aeed1407-9538-49ab-b58c-21b0387b1b2b)

```
sns.boxplot(data=af)
```
![image](https://github.com/23007232/exno1/assets/139115574/597c7373-f0d1-4411-90a2-a5f2d2b70cb7)

```
sns.scatterplot(data=af)
```
![image](https://github.com/23007232/exno1/assets/139115574/d07ba8ce-9076-4445-9ce5-aba5775d31d5)

```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/23007232/exno1/assets/139115574/cc603175-d6dd-4617-a7b1-01a4b32c3e6c)

```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/23007232/exno1/assets/139115574/4371683c-6703-49f3-8600-7300de751ead)

```
af.dropna()
```
![image](https://github.com/23007232/exno1/assets/139115574/324e76de-b5be-4fdd-b844-adedf74d4165)

```
sns.boxplot(data=af)
```
![image](https://github.com/23007232/exno1/assets/139115574/300a90fc-ae5c-4f56-ac2a-e1814a63b2ca)

```
sns.scatterplot(data=af)
```
![image](https://github.com/23007232/exno1/assets/139115574/fb95343a-d5a0-489d-8d56-703bb7ef17c8)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/23007232/exno1/assets/139115574/9feeed07-4198-4d88-a6e9-ddc512dfa307)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/23007232/exno1/assets/139115574/cca90aec-3133-4847-bf6c-5af724cf4792)

# Result
Thus the given program executed successfully.
