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
plt.figure(figsize=(8,8))
plt.title("Data with outliers")
tips.boxplot()
plt.show()
```
```
plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = tips[cols].quantile(0.25)
Q3 = tips[cols].quantile(0.75)
IQR = Q3 - Q1
df = tips[~((tips[cols] < (Q1 - 1.5 * IQR)) |(tips[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()
```
```
sns.barplot(x="day", y="total_bill", data=tips)
plt.title("Total Bill Amount by Day of Week")
plt.show()
```
```
sns.boxplot(x="smoker", y="tip", data=df)
plt.title("Tip Amount by Smoking Status")
plt.show()
```
```
df["tip_pct"] = df["tip"] / df["total_bill"]
sns.scatterplot(x="size", y="tip_pct", data=df)
plt.title("Tip Percentage by Dining Party Size")
plt.show()
```
```
sns.boxplot(x="sex", y="tip", data=df)
plt.title("Tip Amount by Gender")
plt.show()
```
```
sns.scatterplot(x="day", y="total_bill", data=df)
plt.title("Total Bill Amount by Day of Week")
plt.show()
```
```
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```
```
sns.barplot(x="size", y="total_bill", data=df)
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()
```
```
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
```
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()
```
```
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```


# OUPUT
# ![Screenshot 2023-05-29 105950](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/55e3e559-f090-41ac-bfc7-895a2e1942f1)
# ![Screenshot 2023-05-29 110035](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/f8e5435f-5492-4578-bf42-2196e6f33774)
# ![Screenshot 2023-05-29 110103](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/07687ec4-1402-4876-86a1-42f6692155da)
# ![Screenshot 2023-05-29 110135](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/2514e27b-796f-40e1-b3a6-cf314eac0230)
# ![Screenshot 2023-05-29 110201](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/5e777372-43a0-43dc-a13a-59d37468d3f8)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/0f0fdb23-dbbe-4c77-8d8c-389b6696feed)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/170011bd-1949-431c-bd62-66f2ef0ff65e)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/9e86449b-4415-4092-8920-829fb2ccffbd)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/47f6719a-7dd8-49e2-a85d-5ce8d184a0b3)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/9fa55399-8ad0-47c2-ba7d-9beab3ee2ecc)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/a85fce64-bc65-40e4-9800-820826ce70e6)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/88e61547-d4f6-4ecf-8871-a3887e9522c0)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/ec11db2a-3942-414a-9b16-4d599eeaa476)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/307307b5-86d8-487b-8f1f-55f502f2cbd6)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/11da5aa3-2cbc-4d56-8137-8562a7061751)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/84aeefff-962e-4f40-9844-32d63efc2593)
# ![image](https://github.com/Roselineb/Ex-08-Data-Visualization_1/assets/128909895/bb85635e-9cd5-4d19-a20b-6260aba01115)


# Result:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file
