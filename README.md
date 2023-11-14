# Ex-09-Data-Visualization-
## DATE:
## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


## CODE
```
DEVELOPED BY:HARINI V
REGISTER NO: 212222230044
```
### Data preprocessing:
```python
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)
```
```
df.isnull().sum()
```
### Handling Outliers:
```
plt.figure(figsize=(5,5))
plt.title("Data with Outliers")
df.boxplot()
plt.show()
```
### Removing Outliers:
```
plt.figure(figsize=(5,5))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR =Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) | (df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()
```
### Which day of the week has the highest total bill amount?
```
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()
```
### What is the average tip amount given by smokers and non smokers:
```
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")
```
### How does the tip percentage vary based on the size of the dining party hall?
```
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
### Which gender tends to leave higher tips:
```
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")
```
### Is there any relationship between the total bill amount and the day of the week?
```
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")
```
### How does the distribution of total bill amounts vary across the different time periods?
```
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()
```
### Which dining party size group tends to have average highest total bill amount?
```
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()
```
### What is the distribution of tip amounts for each day of the week?
```
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
### How does the tip amount vary based on the type of services?
```
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()
```
### Is there any coorelation between the total bill amount and tip amount?
```
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```
## OUTPUT:
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/e1f9f22b-ef72-4ac1-80e6-5deacc9da1fa)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/e17d64f7-cce2-414b-a6a7-f1905db28481)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/8ff7c080-2fbd-4367-be77-165d856d427d)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/992a134d-95c0-41ba-b653-d3c90ec8e84b)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/fdf08fe4-be98-4bcf-b929-8cb24ad4a3aa)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/78e4c8d1-de9b-49f8-9e32-84de8b973408)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/f44d6c22-9a8e-48e7-a849-281a8dc80f85)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/302aa291-bfd8-460a-87d1-55b415070203)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/0bed1b4b-ea17-4080-beff-cd1dc7baa7ab)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/b9d0fc59-ba37-406a-ac33-a41721e5a0ee)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/c3ba49c7-735d-4048-96c7-75b6be69a09c)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/597b7301-9aea-4dcd-9d44-7cb070023a21)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/80ab2ab6-ddb0-430c-8bc6-9e6a93b169ca)
```
```
![image](https://github.com/harini1006/ODD2023-Datascience-Ex-09/assets/113497405/38becb38-2471-405e-b23a-aad4b22a10ae)
```

 ## RESULT:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.

