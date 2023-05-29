# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
tips = sns.load_dataset('tips')
tips
tips.describe()
tips.info()
tips.isnull().sum()
~tips.duplicated()
df1=tips[~tips.duplicated()]
df1
```
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, 
width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"}, 
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5 }, 
capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
```
avg_tip = tips.groupby('smoker')['tip'].mean()
p1= plt.bar(avg_tip.index, avg_tip, label='Tip', width=0.4)
plt.title('Average tip amount given by smokers and non-smokers')
plt.show()
```
```
tips["tip_per"] = tips["tip"] / tips["total_bill"]
sns.scatterplot(x="size", y="tip_per", data=tips)
plt.title("Tip Percentage by Dining Party Size")
plt.show()
```
```
states=tips.loc[:,["sex","tip"]]
states=states.groupby(by=["sex"]).sum().sort_values(by="tip")
sns.barplot(x=states.index,y="tip",data=states)
plt.xlabel=("Sex")
plt.ylabel=("Tips")
plt.show()
```
```
sns.histplot(data=tips, x="total_bill", hue="day", element="step", 
stat="density")
plt.title("Distribution of Total Bill Amounts by Day of the week")
plt.show()
```
```
sns.relplot(data=tips,x=tips["time"],y=tips["total_bill"],hue="time")
```
```
avg_total_bill = tips.groupby('size')['total_bill'].mean()
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
plt.title('Average Total bill amount given by Dining Party Size')
plt.show()
```
```
sns.relplot(data=tips,x="day",y="tip",hue="day")
```
```
s.barplot(x=tips['time'], y=tips['tip'])
plt.xlabel=("Service")
plt.ylabel=("Tips")
plt.show()
```
```
tips.corr()
sns.heatmap(tips.corr(),annot=True)
```
```
sns.scatterplot(x="total_bill", y="tip", data=tips)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```


# OUPUT
# ![Screenshot 2023-05-29 105950](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/55e3e559-f090-41ac-bfc7-895a2e1942f1)
# ![Screenshot 2023-05-29 110035](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/f8e5435f-5492-4578-bf42-2196e6f33774)
# ![Screenshot 2023-05-29 110103](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/07687ec4-1402-4876-86a1-42f6692155da)
# ![Screenshot 2023-05-29 110135](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/2514e27b-796f-40e1-b3a6-cf314eac0230)
# ![Screenshot 2023-05-29 110201](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/5e777372-43a0-43dc-a13a-59d37468d3f8)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/b5c3f31b-b7c7-4913-a865-61591794d9fe)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/d44a60e7-4ee6-451a-b66d-154f0c1e3ef1)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/a44b3084-58ab-4250-9ba9-77a44d7dc64f)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/9002f749-e257-421a-940d-09e16aaf00e0)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/3e31a7f9-1495-4920-8ab1-9ce71393d219)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/adeb2b7d-3f3d-4f9e-901f-d578431e6548)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/b0a28353-3bdb-4bba-9e8c-2c1286c3f2de)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/5d8f4b32-7be0-4df4-8173-92a81a340823)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/531b8f63-a270-48e5-b6e1-3139f2c9584d)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/d18598f3-ea2c-4809-b503-5358cb17f26e)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/39cde0a6-ef2d-47c5-a9de-ccc4f507c2bc)
# ![Screenshot 2023-05-29 110744](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/34adef17-a71a-4acf-ab28-449f2024e1b9)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/bcd17f90-d71c-4c1e-b711-bf270b857d75)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/aaccfa44-f622-4f33-b71a-39a0ffa3a1d2)

# Result:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file
