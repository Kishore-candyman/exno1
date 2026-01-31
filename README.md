# Exno:1
Data Cleaning Process

## NAME: KISHORE M
## REG. NO." 212224040161

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

# Coding and Output:

```
import pandas as pd
df = pd.read_csv("SAMPLEIDS.csv")
df
```
<img width="938" height="710" alt="image" src="https://github.com/user-attachments/assets/62c620b9-86e9-4565-ad3a-ef131b340905" />

```
df.head()
```
<img width="866" height="210" alt="image" src="https://github.com/user-attachments/assets/1ee2903b-4529-4fec-b8cc-4c8e07d86bb1" />

```
df.tail()
```
<img width="897" height="205" alt="image" src="https://github.com/user-attachments/assets/86ee1f65-6559-473b-ab6f-0f403d5c4e1b" />

```
df.info()
```
<img width="453" height="351" alt="image" src="https://github.com/user-attachments/assets/f1ab4f99-df90-46c9-a722-cf454768f885" />

```
df.describe()
```
<img width="832" height="294" alt="image" src="https://github.com/user-attachments/assets/0a059250-baf7-47b5-9e52-040275af8339" />

```
df.isnull().sum()
```
<img width="268" height="458" alt="image" src="https://github.com/user-attachments/assets/2b88d35d-a821-425c-a1a2-d5e613e1440b" />

```
df.isnull().any()
```
<img width="298" height="457" alt="image" src="https://github.com/user-attachments/assets/bf3192b3-5893-4889-a9bd-fc9de1b4db7a" />

```
df.dropna()
```
<img width="908" height="460" alt="image" src="https://github.com/user-attachments/assets/7364d944-21e7-4954-be73-d5dd0e3a63e3" />

```
df.fillna(0)
```
<img width="873" height="708" alt="image" src="https://github.com/user-attachments/assets/5c85fc68-c995-4e5a-b806-64d881c28a1f" />

```
df.dillna(method="ffill")
```
<img width="1374" height="740" alt="image" src="https://github.com/user-attachments/assets/a6e43735-d423-44e2-b4eb-d0e93c0a2c16" />

```
df.fillna({'GENDER':'MALE','NAME':'SRI'})
```
<img width="866" height="704" alt="image" src="https://github.com/user-attachments/assets/919e9d33-be4c-4598-97ea-421b184dbee4" />

```
ir = pd.read_csv("iris.csv")
ir
```
<img width="655" height="427" alt="image" src="https://github.com/user-attachments/assets/9fb1d591-682b-48c4-ae3d-1bc4cb11b1ad" />

```
ir.discribe()
```
<img width="554" height="288" alt="image" src="https://github.com/user-attachments/assets/752bb7e6-2acf-49d6-9eff-3cc709ba0da0" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="617" height="468" alt="image" src="https://github.com/user-attachments/assets/ec0c8e6e-7baa-4880-adec-1143ba006247" />

```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="217" height="35" alt="image" src="https://github.com/user-attachments/assets/8d222d78-0a4f-462c-b730-2edd7d2829fc" />

```
ran=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="259" height="210" alt="image" src="https://github.com/user-attachments/assets/d2a88091-8556-4757-bb4f-95ad0a972cc2" />

```
ran=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="284" height="460" alt="image" src="https://github.com/user-attachments/assets/b6649691-960d-4100-b837-5f46c83afb62" />

```
sns.boxplot(x='sepal_width',data=ran)
```
<img width="612" height="470" alt="image" src="https://github.com/user-attachments/assets/1227f362-eb71-4f73-b9e1-f52464d0939d" />

```
import numpy as np
import scipy.stats as stats
```
```
z=np.abs(stats.zscore(ir['petal_length']))
z
```
<img width="600" height="538" alt="image" src="https://github.com/user-attachments/assets/f93e4626-779d-4efa-a8f4-33c7d4f2c878" />

```
ir1=ir[z<3]
ir1
```
<img width="567" height="420" alt="image" src="https://github.com/user-attachments/assets/6ba5d2bd-b958-4ca7-aa09-48a8ee493b35" />

# Result:
Thus the given data successfully performed data cleaning and saved the cleaned data to a file.
