# python
## coding for bike_buyers

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

**Import File**

from google.colab import files
uploaded = files.upload()

**view 5 rows**

display(df.head())

**Total Row And Column**


print("Total Row And Column:", df.shape)

Cek dtype

df.info()

**change dtype to int64**

df['Age'] = df['Age'].astype('Int64')

**cek null**

display(df.isnull().sum().to_frame('Jumlah_NULL'))

**view data null**

display(df[df.isnull().any(axis=1)].head(40))

**repair data null**

median_columns = ['Age', 'Cars', 'Children', 'Income']

for col in median_columns:
    df[col] = df[col].fillna(df[col].median())


object_columns = ['Home Owner', 'Gender', 'Marital Status']

for col in object_columns:
    df[col] = df[col].fillna(df[col].mode()[0])

**cek duplikat**
print("Jumlah duplikat:", df.duplicated().sum())

**viusalization**

sns.countplot(data=df, x='Purchased Bike')

plt.title('Bike Purchase Distribution')

plt.xlabel('Purchased Bike')

plt.ylabel('Number of Customers')

plt.show()
<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/e9c28404-dc94-4b7f-92d2-db6b6b0325d9" />

**Link Excel**
https://drive.google.com/drive/folders/11uQI7oPP5Il-34XYNQwCD90JI9QKPZWL

