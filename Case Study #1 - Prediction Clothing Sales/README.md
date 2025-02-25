### 📚 Table of Contents

- Understand the problem and data preparation (EDA)
- Define Problem solving process
- Question and Solution
Please note that all the information regarding the case study has been sourced from the following link: chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://storage.googleapis.com/static.fastcampus.co.kr/prod/uploads/202308/112407-717/[%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4]-%EA%B5%90%EC%9C%A1%EA%B3%BC%EC%A0%95%EC%86%8C%EA%B0%9C%EC%84%9C-%EC%B4%88%EA%B2%A9%EC%B0%A8-%ED%8C%A8%ED%82%A4%EC%A7%80---50%EA%B0%9C-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EB%A1%9C-%EC%99%84%EB%B2%BD%ED%95%98%EA%B2%8C-%EB%81%9D%EB%82%B4%EB%8A%94-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-signature.pdf

-----

### Understand the problem and data preparation (EDA)

A clothing company wants to predict sales volume to adjust production levels.  
Since clothing sales are highly influenced by seasonality depending on the type of clothing, a model that can account for these characteristics is necessary. 
Let's start exploring the data and proceed with forecasting clothing sales.

------

```python
import pandas as pd 
pd.set_option('display.max_columns',100) # Enable upto 100 columns will be displayed
pd.set_option('display.max_rows',100) # Enable upto 100 rows will be displayed

df = pd.read_excel('data/WEAR_TS_ALL.xlsx') # Read Excel file
df.head() # Display only first 5 rows
```

We are going to analyse only domestics.
```python
df = df[df['TYPE']=='국내'] # Display type only domestics
df
```

```python
df = df.groupby('SEASON').sum() # Groupby SEASON and sum
df
```

```python
df = df.T # Transpose rows and columns to handle sales grouping by dates
```

```python
df.index
```

```python
df.index = pd.to_datetie(df.index)
ds

```python
# Create each dataframe of each year and merge them into one dataframe
df = pd.concat([
                    df[df.index.year==2016]['16SS'], 
                    df[df.index.year==2017]['17SS'], 
                    df[df.index.year==2018]['18SS'], 
                    df[df.index.year==2019]['19SS']
            ])
df = pd.DataFrame(df, columns=['sales'])
df
````python
df.plot(figsize=(20, 7))
```

```python
df.plot(figsize=(20, 7))
'''

```python
# Remove outliers
df[(df['sales']<-1000) | (df['sales']>2500)] = 0
'''


```python


'''


```python


'''


```python


'''


```python


'''


```python


'''


```python


'''


```python


'''


```python


'''

```python


'''


```python


'''






#### Problem Definition

#### Expectation

#### Solution

#### Measurement



