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

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/b87cb9ea-2971-44e5-b7f1-f4d8125e34a7)
```
df=sns.load_dataset('tips')
df
```
![image](https://github.com/user-attachments/assets/5b223496-cc1c-484c-9957-73d34c221847)
```
sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
```
![image](https://github.com/user-attachments/assets/3d36ae95-d427-4aab-9c8b-f98b947585bb)
```
avg_tb=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()
print(avg_tb)
print(avg_tip)
```
![image](https://github.com/user-attachments/assets/89d3134a-146a-46df-8927-052b126a9f98)
```
p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/56098040-6509-4e5d-bbba-a27b8d1fd651)
```
sns.barplot(x='day',y='total_bill',hue='sex',data=df,palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Average Total Bill by Day and Sex')
```
![image](https://github.com/user-attachments/assets/b843154f-d3c5-41ad-a45f-38bc59144dbd)
```
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=df)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs Tip Amount')
```
![image](https://github.com/user-attachments/assets/c3beafc4-16c7-4358-bb70-01d881a67837)
```
import pandas as pd
df=pd.read_csv('/content/titanic_dataset (1).csv')
df
```
![image](https://github.com/user-attachments/assets/ff779f1d-d331-48d6-91f2-aa78d7e658ba)
```
sns.histplot(data=df,x='Pclass',hue='Survived',kde=True)
```
![image](https://github.com/user-attachments/assets/8f1603f0-5c19-478e-9d91-93ee6e272e68)
```
df=sns.load_dataset('tips')
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
```
![image](https://github.com/user-attachments/assets/3c2169ba-5722-4309-807e-f896bbaeefd0)
```
sns.boxplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.8,boxprops={"facecolor":"yellow","edgecolor":"purple"},whiskerprops={"color":"blue","linestyle":"-","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.2})
```
![image](https://github.com/user-attachments/assets/4671fa75-98c8-44da-b040-920a73239cd3)
```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,palette="Set3",inner="quartile")
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Violin Plot of Total Bill by Day and Smoker Status')
```
![image](https://github.com/user-attachments/assets/9ffc59b2-5071-4154-b7cf-67b05d4552e4)
```
sns.set(style="whitegrid")
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='total_bill',hue='sex',data=tip)
```
![image](https://github.com/user-attachments/assets/52ac9b1b-9100-4c1d-8bc3-dad81f80095d)
```
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![image](https://github.com/user-attachments/assets/f9bef13b-3b0d-4fa9-8d48-d9dc18d61a96)
```
sns.kdeplot(data=tip,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/840b0e38-1e57-447a-8513-2619069d0c7b)
```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/fd5cde48-aac3-4528-bbd0-701ad2f2d479)
```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/455e317e-c579-4765-89c5-3d6f0434d53a)
```
import matplotlib.pyplot as plt
import numpy as np
df=sns.load_dataset('tips')
numeric_cols=df.select_dtypes(include=[np.number]).columns
corr=df[numeric_cols].corr()
hm=sns.heatmap(corr,annot=True,cmap='YlGnBu',linewidths=0.5)
```
![image](https://github.com/user-attachments/assets/4b424d25-91e5-4003-bf25-9c965a1b452d)

# Result:
 Thus the data visualization code executed successfully.
