# Ex-01_DS_Data_Cleansing
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Get the information about the data

## STEP 3
Remove the null values from the data

## STEP 4
Save the Clean data to the file

# CODE
# CODE FOR DATA SET 1:
~~~
import pandas as pd
df=pd.read_csv("Data_set.csv")
df.head(5)

df.info()

df.isnull()

df.isnull().sum()

df['show_name']=df['show_name'].fillna(df['aired_on'].mode()[0])
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['aired_on'].mode()[0])
df.head()

df['rating']df['rating'].fillna(df['rating'].mean())
df['current_overall _rank']=df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df.head()

df['watchers']=df['watchers'].fillna(df['watchers'].median())
df.head()

df.info()

df.isnull().sum()

~~~
### output 1:
### Data:
![image](https://user-images.githubusercontent.com/93427248/201912754-d2ef6e34-80e9-4ea6-a285-769f232d8146.png)

![image](https://user-images.githubusercontent.com/93427248/201912789-4d1aca82-8015-47d7-a02b-64ed5c843825.png)

![image](https://user-images.githubusercontent.com/93427248/201912826-820effc8-e69e-46c8-8b4b-9ece88c37e37.png)

![image](https://user-images.githubusercontent.com/93427248/201912881-50d59637-8a7c-4de9-80c7-cb4b952e4c5d.png)

### NON NULL BEFORE:
![image](https://user-images.githubusercontent.com/93427248/201912974-12d5c555-f809-4258-a04b-0288133fc947.png)MODE:
### MEAN:
![image](https://user-images.githubusercontent.com/93427248/201913159-ac110d1e-1e74-4362-a1ae-a8efbef79e82.png)
### MEDIAN:
![image](https://user-images.githubusercontent.com/93427248/201913240-659aed8d-de6a-4da2-9f14-eb0d985663fc.png)

![image](https://user-images.githubusercontent.com/93427248/201913298-3c552907-0276-4452-913f-d4e8923853ce.png)

### NON NULL AFTER:
![image](https://user-images.githubusercontent.com/93427248/201913361-9d636a9d-024a-4dfb-a017-4e606181c7eb.png)
##### CODE FOR DATA SET2:

~~~
import pandas as pd
import numpy as np
import seaborn as sns
d = pd.read_csv("/content/Loan_data.csv")
d
d.head()
d.describe()
d.tail()
d.isnull().sum()
d.shape
d.columns
d.duplicated

#Using mode method to fill the data in columns as Object(String)
#mode()[0] - Takes the most reccuring value and fills the empty cells
d['Gender'] = d['Gender'].fillna(d['Gender'].mode()[0])
d['Dependents'] = d['Dependents'].fillna(d['Dependents'].mode()[0])
d['Self_Employed'] = d['Self_Employed'].fillna(d['Self_Employed'].mode()[0])

#Using mean method to fill the data
d['LoanAmount'] = d['LoanAmount'].fillna(d['LoanAmount'].mean())
d['Loan_Amount_Term'] = d['Loan_Amount_Term'].fillna(d['Loan_Amount_Term'].mean())
d['Credit_History'] = d['Credit_History'].fillna(d['Credit_History'].mean())

sns.boxplot(y="LoanAmount",data=d)

#Checking the total no.of null values again
d.isnull().sum()

#Checking info of the dataset to check all the columns have entries
d.info()
~~~

### OUTPUT FOR DATASET 2:
### DATA:

![image](https://user-images.githubusercontent.com/93427248/201913458-63e1bebe-75e6-4003-bee5-065c783cb08b.png)
![image](https://user-images.githubusercontent.com/93427248/201913533-c43d0201-ec6e-4f77-a819-241fcc77d77a.png)
![image](https://user-images.githubusercontent.com/93427248/201913581-dbc07d35-482f-45a2-b6d5-3994a32425c8.png)
### NULL BEFORE:

![image](https://user-images.githubusercontent.com/93427248/201913617-ec2db793-37a8-427d-919e-7d33a20053f3.png)
### MODE:

![image](https://user-images.githubusercontent.com/93427248/201913640-76d6f3df-578e-4150-b7b9-a8b1f405c664.png)
### MEDIAN:
![image](https://user-images.githubusercontent.com/93427248/201913667-328cf047-1734-456c-b19a-9d05ded2e926.png)
![image](https://user-images.githubusercontent.com/93427248/201913689-6c62c8fd-09fc-4cf2-8e39-327333464c6e.png)
### NON NULL AFTER:
![image](https://user-images.githubusercontent.com/93427248/201913732-55241f23-6f85-403f-92e9-67c8b2678307.png)

### RESULT:
Thus the given data is read,cleansed and cleaned data is saved into the file.
