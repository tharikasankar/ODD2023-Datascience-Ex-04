# ODD2023-Datascience-Ex-04
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1:
Import the built libraries required to perform EDA and outlier removal.

# STEP 2:
Read the given csv file

# STEP 3:
Convert the file into a dataframe and get information of the data.

# STEP 4:
Return the objects containing counts of unique values using (value_counts()).

# STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8:
Save the final data set into the file.

# PROGRAM:
Name : THARIKA S
Register Number : 212222230159
# SuperStore.csv file:
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)
# diabetes.csv file:
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes.csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
# OUTPUT:
# SUPERSTORE:
# DATA FRAME OF SUPERSTORE
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/5f840753-5779-4d0a-bcfd-242efad0c8fd)
# Data information
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/70907bdc-d99c-40d4-9081-2df201adb017)
# Data describing
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/b0d15999-5bc7-4bd4-b04d-457fc29503c1)
# Sum of null values
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/4f601a9a-8913-48be-b857-88d0fdb43cd0)
# After removing null values
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/382386c5-5d0c-4bf9-be4d-13fe630649ae)
# Scatter plot
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/085a4bd1-c8f6-4230-86b8-fd49411b3f54)
# Bar plot
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/e432a9db-b0c7-47eb-898e-26b6012111a5)
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/d5081d63-d3e3-468b-b560-6f2d242adaca)
# Box plot
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/accd0bc9-eb87-4ee2-950b-6be7848c9488)
# Dist plot
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/4b6514b4-57f5-4c4d-98d3-09539964dea6)
# Correlation coefficient interpretation
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/dadc017e-d292-4961-930c-5ed46560b375)
# Heat map
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-04/assets/119475507/4513074a-8231-437d-8a87-aca1453172b9)

# DIABETES
# DATA FRAME FOR DIABETES

