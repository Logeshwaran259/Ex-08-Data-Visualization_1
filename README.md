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
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

# OUPUT
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/dce95149-65ca-40d6-9705-76e80a843a93)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/73a162cf-5c1a-47ed-8495-9425c1e79a99)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/4f59d7f7-40bc-49b3-91d4-5c276849b2eb)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/0a27dc64-802d-4111-b104-76d65aefc9c5)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/6ae224b7-1dd9-4b55-80fd-d9e4a6ac16ca)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/950569b4-30e0-4008-a98a-4b62c7ebf0c7)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/6664e23a-17a7-47c7-b3e9-94d9544d883d)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/7fffbd78-926e-4b4a-9bf5-174aaa27e464)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/8a08e048-8fe6-4e8c-8e3e-3ea7410eb85f)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/011ab83e-5a97-4141-badc-08d6a03f0239)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/c7c8a0e9-6017-47e0-9dfc-27f8b61e063d)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/4d3423aa-00eb-4e3a-a4e4-545eed1f300f)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/dfdd857a-4bda-4ca9-ab30-7326141fa8ad)
![image](https://github.com/ATHDY005/Ex-08-Data-Visualization_1/assets/84709944/a3dbeeca-b041-4018-ac13-2be813cfe11f)

# RESULT
Hence Data Visualization on a complex dataset was performed and the data was saved to a file.
