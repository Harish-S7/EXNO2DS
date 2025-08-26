NAME:S.HARISH

Reg.no:212224230086
# EXNO2DS
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

## CODING AND OUTPUT
```
import pandas as pd
import seaborn as sns
df = pd.read_csv("titanic_dataset.csv")
df
```
<img width="1236" height="444" alt="Screenshot 2025-08-26 160702" src="https://github.com/user-attachments/assets/430a6639-61cc-4714-8d22-0954800c3a2c" />

```
df.shape
```
<img width="126" height="28" alt="image" src="https://github.com/user-attachments/assets/ec66fb48-054f-44f5-b243-c4b335406a99" />

```
df.set_index("PassengerId",inplace = True)
df
```
<img width="1201" height="468" alt="image" src="https://github.com/user-attachments/assets/0a77d89c-708c-47f0-84a3-b07d7ba74c33" />

```
df.nunique()
```
<img width="170" height="264" alt="image" src="https://github.com/user-attachments/assets/d04275ab-b64e-4b23-8cb7-95b3f2bd0da3" />

```
df['Survived'].value_counts()
```
<img width="316" height="74" alt="image" src="https://github.com/user-attachments/assets/73e4ee67-2a57-4eae-b747-eafe75d0527c" />

```
df['Sex'].value_counts()
```
<img width="252" height="71" alt="image" src="https://github.com/user-attachments/assets/cf6ae238-0ef0-410e-a3af-d63a02a0764e" />

```
df.Survived.unique()
```
<img width="285" height="26" alt="image" src="https://github.com/user-attachments/assets/587a5fe7-ae03-4043-bcc4-f84ba519220f" />

```
df.rename(columns = {"Sex":"Gender"},inplace = True)
df
```
<img width="1199" height="473" alt="image" src="https://github.com/user-attachments/assets/809076d0-1546-42c7-9256-1ad12219243a" />

```
sns.countplot(data = df)
```
<img width="738" height="553" alt="image" src="https://github.com/user-attachments/assets/06456011-bb57-4d32-94a5-1833e58b15be" />

```
sns.countplot(x = "Survived",hue = "Gender", data = df)
```
<img width="725" height="570" alt="image" src="https://github.com/user-attachments/assets/b60ce545-d8b6-462e-8da0-6dfbf2b8e8c8" />

```
sns.catplot(x = "Survived",hue = "Gender",data = df,kind = "count")
```
<img width="735" height="643" alt="image" src="https://github.com/user-attachments/assets/d862efb0-4d3b-4b92-81eb-304441f974b4" />

```
sns.catplot(x="Survived", y="Fare", hue="Gender", data=df, kind="box")
```
<img width="727" height="638" alt="image" src="https://github.com/user-attachments/assets/f05c83cd-ad8e-4ae2-8d5f-4047497aaff0" />

```
sns.boxplot(data=df)
```
<img width="725" height="555" alt="image" src="https://github.com/user-attachments/assets/089289f7-87a7-44b3-81c7-72ddf2cf46c4" />

```
df.boxplot(column="Survived",by="Gender")
```
<img width="749" height="608" alt="image" src="https://github.com/user-attachments/assets/80964b17-aef8-47d2-a385-68915d1aa813" />

```
sns.scatterplot(data=df)
```
<img width="724" height="571" alt="image" src="https://github.com/user-attachments/assets/cdce4863-0928-4b5c-9c42-4f7045f92a1c" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="728" height="578" alt="image" src="https://github.com/user-attachments/assets/887e2309-8c9b-429e-81c5-2e8ba0620713" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind='kde')
```
<img width="697" height="691" alt="image" src="https://github.com/user-attachments/assets/5cff928c-0c4f-4787-b59c-3b4462ba0cee" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind='hist')
```
<img width="686" height="695" alt="image" src="https://github.com/user-attachments/assets/a8e8cb4a-c457-4965-a590-eef52ac7ed12" />

```
sns.pairplot(data=df)
```
<img width="827" height="817" alt="image" src="https://github.com/user-attachments/assets/e7df456f-49b0-4107-be76-27ef8549c860" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)
```
<img width="673" height="561" alt="image" src="https://github.com/user-attachments/assets/d7fc65b2-7a5e-4f1a-ab9c-d81df0176d6a" />

# RESULT
Thus exploratory data analysis on the given data set has been executed successfully.
