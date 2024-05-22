```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
df=pd.read_csv('titanic_dataset.csv')
df
df.head()
df.tail()
df.info()
df.isnull().sum()
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
dff=pd.DataFrame(age)
dff
q1=dff.quantile(0.25)
q2=dff.quantile(0.5)
q3=dff.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
dff=dff[((dff>=low)&(dff<=high))]
dff
sns.boxplot(data=dff)
data={'weight':[12,15,18,21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57,60,63,66,69,202,72, 75, 78, 81, 84, 232, 87, 90, 93,96,99,258]}
ds=pd.DataFrame(data)
ds
```
