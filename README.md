NAME:HARISH S
# EX NO 2 DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

# CODING AND OUTPUT
```
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
print(df)
```
<img width="648" height="687" alt="image" src="https://github.com/user-attachments/assets/3323d295-cf33-4c44-97a0-a4d793a11c99" />

```
df.info()
```

<img width="417" height="335" alt="image" src="https://github.com/user-attachments/assets/1ff331c3-c9ea-44ce-8fab-0d729cf10e71" />

```
df.describe()
```

<img width="715" height="268" alt="Screenshot 2026-08-02 221225" src="https://github.com/user-attachments/assets/5626e119-e9cb-4ebb-b0b1-a1a1c61a39a9" />


```
df.shape
```

<img width="190" height="35" alt="image" src="https://github.com/user-attachments/assets/2276b5b4-9eb7-48f2-9aa6-aee8fae4e39e" />

```
df.dtypes
```

<img width="320" height="233" alt="image" src="https://github.com/user-attachments/assets/7ceed50a-3aaa-46ef-bd90-513996ffac84" />

# Categorical data analysis


```
df["Survived"].value_counts()
```

<img width="503" height="102" alt="image" src="https://github.com/user-attachments/assets/2b1bf54f-2261-4ac3-86ad-c1237da8d30f" />

```
df.nunique()
```

<img width="455" height="365" alt="image" src="https://github.com/user-attachments/assets/2748ca28-c3bf-4623-b908-530a2353824f" />

```
import seaborn as sns
sns.countplot(data=df,x="Survived")
```

<img width="685" height="472" alt="image" src="https://github.com/user-attachments/assets/5dc117aa-40a3-496f-994c-46a3ba88c9c5" />

```
sns.boxplot(data=df,x="Age")
```

<img width="688" height="471" alt="image" src="https://github.com/user-attachments/assets/bdd6cf9a-bd55-42af-afe2-ce161dce5002" />

```
sns.histplot(data=df,x="Age")
```

<img width="696" height="466" alt="Screenshot 2026-08-02 212131" src="https://github.com/user-attachments/assets/7dc16e8c-3859-4971-9905-6af5f0d2ec1d" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
print(df)
```
<img width="675" height="690" alt="Screenshot 2026-08-02 212211" src="https://github.com/user-attachments/assets/beb5b8d4-24ab-4d32-862b-11bc72408c09" />


# Bivariate Analysis


```
sns.catplot(x='Survived',hue="Gender",data=df,kind='count')
```
<img width="685" height="531" alt="Screenshot 2026-08-02 212244" src="https://github.com/user-attachments/assets/10016e64-6733-4dff-92ce-f6ce7b429659" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="681" height="493" alt="image" src="https://github.com/user-attachments/assets/ba2bff4a-8f3c-48cb-af6a-7bdc01216811" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="715" height="467" alt="image" src="https://github.com/user-attachments/assets/2583d191-5b1f-4cc0-8875-ab3335608e67" />

```
sns.boxplot(x=df["Survived"],y=df["Fare"])
```

<img width="737" height="472" alt="image" src="https://github.com/user-attachments/assets/f5398654-e259-46e9-9f20-070a67bf262d" />

```
sns.barplot(x=df["Survived"],y=df["Fare"])
```

<img width="693" height="460" alt="image" src="https://github.com/user-attachments/assets/28c14978-b163-4719-b6aa-4fb83277809d" />

# Multivariate Analysis

```
sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)
```

<img width="692" height="462" alt="image" src="https://github.com/user-attachments/assets/36b5bfe3-e8cd-432c-8e07-6994df224944" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="695" height="336" alt="image" src="https://github.com/user-attachments/assets/8402ad11-f6a9-4e9b-9fa8-edbcbd6c8887" />

# Co-relation

```
sns.heatmap(df.corr(),annot=True)
```

<img width="712" height="535" alt="image" src="https://github.com/user-attachments/assets/d64e240d-b1a8-44aa-98b0-d71cae9396ce" />


# RESULT

Successfully performed Exploratory Data Analysis (EDA) by handling missing values, detecting and removing outliers, analyzing categorical and numerical data, and visualizing relationships using countplot, displot, crosstab, and heatmap.
