```
import pandas as pd
import pandas as pd
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
import pandas as pd
import seaborn as sns
sns.boxplot(data=dff)
```
