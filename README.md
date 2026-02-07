#EX.NO:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import numpy as np
import pandas as pd
data=pd.read_csv("Data_set.csv")
data
```

<img width="1565" height="570" alt="Screenshot 2026-02-07 235250" src="https://github.com/user-attachments/assets/7a7a097c-e801-4bc6-8bc4-43bc0e3180ef" />

```
data.head(4)
```
<img width="1533" height="246" alt="image" src="https://github.com/user-attachments/assets/bcb6c926-38d2-4c70-b4e9-5a930cefb6c2" />

```
data.tail(7)
```
<img width="1552" height="365" alt="image" src="https://github.com/user-attachments/assets/2e97100c-e451-4d2c-9c27-9634bd5548ac" />

```
data.isnull()
```
<img width="1307" height="568" alt="image" src="https://github.com/user-attachments/assets/ec52eee3-0a7b-4790-b711-5d817c8f1972" />

```
data.notnull()
```
<img width="1357" height="589" alt="image" src="https://github.com/user-attachments/assets/9d31fddf-56c6-4cf5-ae8a-a87b93ac10c8" />

```
data.isnull().sum()
```

<img width="1328" height="301" alt="image" src="https://github.com/user-attachments/assets/51e8202c-4339-4ff5-9172-2aa5e61b0248" />


```
data.dropna(axis=1)
```
<img width="1436" height="588" alt="image" src="https://github.com/user-attachments/assets/d925716d-a43d-4503-b8f3-f07dec2b776e" />

```
data.dropna(axis=0)
```
<img width="1606" height="738" alt="image" src="https://github.com/user-attachments/assets/729fca13-24f0-47c0-96c7-d8fba2adb1fc" />

```
data.fillna(0)
```
<img width="1588" height="586" alt="image" src="https://github.com/user-attachments/assets/54bdb41c-b260-4b3a-88fd-ffda1655a22b" />

```
data.fillna(method="ffill")
```
<img width="1575" height="594" alt="image" src="https://github.com/user-attachments/assets/bb8f704f-f389-4f4d-aa43-7b29a39c7b03" />

```
data.bfill()
```
<img width="1589" height="575" alt="image" src="https://github.com/user-attachments/assets/d88d939e-826d-4f03-8c73-e84865a7379a" />

```
data.fillna({'rating':0,'country':'South Korea'})
```
<img width="1588" height="595" alt="image" src="https://github.com/user-attachments/assets/cf67883a-d10f-4f16-8c34-b8b7ec3563aa" />

```
ir=pd.read_csv("Data_set.csv")
ir
```
<img width="1583" height="585" alt="image" src="https://github.com/user-attachments/assets/f90c68f9-08ef-4ae7-974f-6f93b0879b00" />

```
ir.head()
```
<img width="1557" height="297" alt="image" src="https://github.com/user-attachments/assets/e7cd97a8-c234-4451-a529-c7cb5d7b39f7" />

```
ir.tail()
```
<img width="1594" height="281" alt="image" src="https://github.com/user-attachments/assets/787d971f-1059-40f3-b6da-263ac8b52e6d" />

```
ir.info()
```
<img width="1451" height="467" alt="image" src="https://github.com/user-attachments/assets/b2de0821-2051-414d-9875-e9e2f887f596" />

```
ir.describe()
```
<img width="1447" height="414" alt="image" src="https://github.com/user-attachments/assets/5896cb57-91f7-44c5-b3d2-f7113a8d8178" />

```
ir.isnull().sum()
```
<img width="1526" height="313" alt="image" src="https://github.com/user-attachments/assets/13dc3548-6708-4752-9a12-c0ec1c46e648" />

```
ir.isnull().any()
```
<img width="1407" height="292" alt="image" src="https://github.com/user-attachments/assets/ebc4b8b6-a55b-4185-9f02-75f45720f386" />

```
ir.notnull()
```
<img width="1361" height="584" alt="image" src="https://github.com/user-attachments/assets/056811cb-4166-4dcf-9cb4-5c128c66401d" />

```
ir.dropna()
```
<img width="1587" height="717" alt="image" src="https://github.com/user-attachments/assets/af067a59-9771-4266-843f-4b1e6aad67a8" />

```
ir.dropna(axis=1)
```
<img width="1367" height="580" alt="image" src="https://github.com/user-attachments/assets/b9c7cf08-f2c8-4a82-9dba-68b124c1c531" />

```
ir.fillna(8)
```
<img width="1591" height="592" alt="image" src="https://github.com/user-attachments/assets/0cd3b574-2bcd-4c03-9eea-da9d9ec49bda" />

```
ir.fillna(method='ffill')
```
<img width="1604" height="583" alt="image" src="https://github.com/user-attachments/assets/92f58a86-7394-4bee-8b7d-e9c1c406686a" />

```
ir.fillna(method='bfill')
```
<img width="1578" height="580" alt="image" src="https://github.com/user-attachments/assets/b0dec2dc-d787-4c6f-a45d-972ee545d346" />

```
import seaborn as sns
sns.boxplot(x='num_episodes',data=ir)
```
<img width="1397" height="735" alt="image" src="https://github.com/user-attachments/assets/fcb1e268-7dab-4ee5-9f95-d49eb417a294" />

```
Q1=ir.num_episodes.quantile(0.25)
Q3=ir.num_episodes.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="1564" height="68" alt="image" src="https://github.com/user-attachments/assets/831c0547-ff26-44ba-9565-e4db648bc015" />

```
ran=ir[((ir.num_episodes<(Q1-1.5*IQR))|(ir.num_episodes>(Q3+1.5*IQR)))]
ran['num_episodes']
```
<img width="1448" height="373" alt="image" src="https://github.com/user-attachments/assets/cfac0aa9-d7ab-4109-a1df-a72920fa95f8" />

```
sns.boxplot(x='num_episodes',data=ran)
```
<img width="1030" height="734" alt="image" src="https://github.com/user-attachments/assets/73b395a3-c993-4f75-ad41-e5190d2f94f0" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['lifetime_popularity_rank']))
z
```
<img width="1555" height="348" alt="image" src="https://github.com/user-attachments/assets/e3b33b78-3857-46f8-84b3-1ad7f6cdcecf" />

```
ir1=ir[z<3]
ir1
```

<img width="1574" height="578" alt="image" src="https://github.com/user-attachments/assets/c4f54446-5fef-4532-b13b-438ce1fe1a9e" />



# Result
          
Thus the given data successfully performed data cleaning and saved the cleaned data to a file
