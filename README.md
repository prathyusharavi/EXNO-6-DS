# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

## Developed by: Y Prathyusha
## Reg.No:212223240187
# Coding and Output:
```p
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x, y=y)
```
![image](https://github.com/user-attachments/assets/47b7f58c-52a7-4ef3-8adc-e8453aa16e49)
```p
df=sns.load_dataset('tips')
df
```
![image](https://github.com/user-attachments/assets/3c12799c-e4b4-4a75-8240-df0646879218)
```p
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")
```
![image](https://github.com/user-attachments/assets/f7425dce-b745-458a-b7b3-4897a98a1f8f)
```p
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title('Multi-Line Plot')
plt.xlabel('X Label')
plt.ylabel('Y Label')

```
![image](https://github.com/user-attachments/assets/2e77258a-d251-4e72-9e38-c418d243fdd6)
```p
import seaborn as sns
import matplotlib.pyplot as plt
tips =sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip= tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2=plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/adb91034-ee5d-40c2-bd7e-ef41bf237917)
```p
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip =tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom = avg_total_bill, label='Tip', width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()

```
![image](https://github.com/user-attachments/assets/1e363116-5c86-42e8-b099-abaa113f1c4f)
```p
years= range (2000, 2012)
apples= [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges= [0.962, 0.941 , 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896]
plt.bar(years, apples)
plt.bar(years,oranges, bottom=apples)

```
![image](https://github.com/user-attachments/assets/e580e7ab-3f7d-45e4-a6e3-6537e7e3869d)
```p
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/9073ea76-6c96-4d89-82cc-5eae91566fdc)

```p
import pandas as pd
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/95c1cede-2a73-47fa-9e96-d7cfa21f830a)
```p
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/2fb328ad-48dc-41a0-963c-6c05495800a3)
```p
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/24d7df47-967b-443b-99e5-4aab869df137)
```p
import seaborn as sns
tips = sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex',data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/ef7aaeee-5f02-4743-b8b6-2ba6c12e1099)
```p
import seaborn as sns
import numpy as np
import pandas as pd
np.random.seed (1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name = "Numerical Variable")
num_var
```
![image](https://github.com/user-attachments/assets/10cb90c4-55ae-4c75-91ce-2fe0b277e017)
```p
sns.histplot(data= num_var, kde=True)
```
![image](https://github.com/user-attachments/assets/5b53d7b2-27b6-4427-bb53-d9ae6e0bee65)
```p
sns.histplot(data=df,x="Pclass",hue="Survived",kde=True)
```
![image](https://github.com/user-attachments/assets/65109203-c8d3-46ec-9183-bcc589f19f39)
```p
import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed (0)
marks = np.random.normal(loc=70, scale=10, size=100)
marks
```
![image](https://github.com/user-attachments/assets/1dfb5630-8ea0-44e4-82c6-3875092f94e7)
```p
sns.histplot(data=marks, bins=10, kde =True, stat='count', cumulative=False, multiple='stack', element='bars', palette ='Seti', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Marks')
```
![image](https://github.com/user-attachments/assets/84a7bcb2-cf81-48f3-ac05-6429024e0240)
```p
import seaborn as sns
import pandas as pd
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/9c63e865-1ae2-4ad8-99d8-744a71b81d6d)
```p
sns.boxplot(x="day", y="total_bill", hue="smoker", data= tips, linewidth=2, width=0.6,boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"}, whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/d5cc5379-4e4f-4fcf-b223-0b344a7dd631)
```p
sns.boxplot(x='Pclass', y='Age', data=df, palette='rainbow')
plt.title("Age by Passenger Class, Titanic")
```
![image](https://github.com/user-attachments/assets/553535ad-8bd7-4c5f-9850-0b5429676084)


```p
sns.violinplot(x="day", y="total_bill", hue="smoker", data= tips, linewidth=2, width=0.6
               , palette="Set3",inner='quartile')
plt.xlabel("Day of the week")
plt.ylabel('Total Bill')
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/cd470536-f403-40fe-a107-0322c15d6b74)
```p
import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data = tip)
```
![image](https://github.com/user-attachments/assets/e5e39cc3-c54f-4cbb-bf1e-4c3083e8784a)
```p
import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![image](https://github.com/user-attachments/assets/d013c527-7e3c-422e-bf22-3bb212ca6908)
```p
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip', y='day', data=tip)
```
![image](https://github.com/user-attachments/assets/174c1688-93a4-45b6-a5db-51a89615c9b9)
```p
sns.kdeplot(data=tips,x='total_bill', hue='time', multiple ='fill',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/dc226870-4ded-4618-bb29-6a920453d28c)
```p
sns.kdeplot(data=tips,x='total_bill', hue='time', multiple='layer', linewidth=3, palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/34f04a4d-c03c-478b-a2ab-b52e5f8028f3)
```p
sns.kdeplot(data=tips,x='total_bill', hue='time', multiple='stack', linewidth=3, palette='Set2', alpha=0.8)
```
![image](https://github.com/user-attachments/assets/fe53dcbc-10fc-4fb4-9e51-bfeae24eb6d7)
```p
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
mart=mart[['Gender','Payment','Unit price','Quantity','Total','gross income']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/1b7d0e5b-e584-4e21-aeac-ff4b6f8a20a1)
```p
sns.kdeplot(data=mart,x='Total')
```
![image](https://github.com/user-attachments/assets/22a76097-fef1-4610-8a29-189cc4a955a9)
```p
sns.kdeplot(data=mart,x='Unit price')
```
![image](https://github.com/user-attachments/assets/e6395f8c-4dc7-4c43-b25a-f2cb2d0004a7)
```p
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/93c978aa-ea4b-482b-a06d-995a2fcf012e)
```p
sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack')
```
![image](https://github.com/user-attachments/assets/8c843195-2cdb-4370-a12f-9e9c3c5f6564)
```p
sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack',linewidth=5,palette='Dark2',alpha=0.5)
```
![image](https://github.com/user-attachments/assets/7e611989-7dcd-4e3f-8741-0a7b374e9a91)
```p
sns.kdeplot(data=mart,x='Unit price',y='gross income')
```
![image](https://github.com/user-attachments/assets/1c3342dd-9c3e-4808-89f1-d5c81cc8227f)
```p
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)
```
![image](https://github.com/user-attachments/assets/5bae8c1c-6a34-4e1b-8a78-f1abb19de8d7)
```p
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/aeacb30b-8134-4dea-b009-2853e0e5cb09)
```p
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/b31a6bf7-c733-4965-9c6d-1628986d486b)
```p
tips=sns.load_dataset('tips')
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr
sns.heatmap(corr, annot=True, cmap="plasma", linewidths=0.5)
```
![image](https://github.com/user-attachments/assets/c90cdcdd-f399-4e08-bd58-4af13eabcae3)



# Result:
Successfully completed Data Visualization using seaborn python library for the given datas.


