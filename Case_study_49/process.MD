1. data를 받았다. pd.read_csv를 통해서 data를 열어보았다. df.sample(n=5)을 통해서 여러번 돌려보다보면 좀 더 데이터를 훑어볼 수 있다.
2. df.info()를 통해서 총 shape는 어떤것인지, 어떤 column이 object/int/float으로 나뉘어져잇는지, object로 되어있어야하는데 숫자라고해서 int/float으로 잘못 들어가 있는 것은 아닌지 확인해준다.
3. 좀 더 값을 보기위해서, for column in list(df.columns): print(column, df[column].dtype, df[column].unique())를 해준다. 그러면 column의 이름과, column의 dtype (info에서 한번 본 것이다.), value들의 유니크한 값들이 나온다.
4. object타입으로 되어있어야 할 column이 numeric으로 되어있다면, list_cast_as_object = ['X1', 'X2', 'X3']실제로 assign을 해줘야한다. 그리고 for column_name in list_cast_to_object: df[column_name] = df[column_name].astype(object)로 바꿔준다.
list_categorical_columns = list(df.select_dtypes(include=['object']).columns)로,
list_numeric_columns = list(df.select_dtypes(include=['float64', 'int64]).columns)로 확인해준다.
target_column = 'Machine Failure'
5. 그리고 df.isnull.sum()을 해줘서, 어떤 결측치가 있는지 확인해준다. 결측치는 fillna로 채워주거나, drop을 이용해서 drop 해준다.
6. 그러면 이제 UDI, productID, type, 등 column의 dtype등은 처리가되었다.
7. duplicated 의 갯수를 세어준 후에 duplicated 를 제거해준다.
8. target column을 결정한 후에, target column의 0/1 비율을 봐준다. imbalance인지 정상적인지, 이진분류인지, 회귀인지 등을 확인한다. df[target_column].value_counts()/10000*100 을 통해서 비율을 확인해준다.
9. Drop해야할 컬럼값을 휴리스틱하게 결정한 후에 드롭해준다.
10. 중요해보이는 column에 대해서, 비율을 알고싶다면, pd.crosstab(df[target_column], df[list_categorical_columns[0]])이런식으로 하나씩 확인해줄 수 있다. H일때 0은 몇개인지 1은 몇개인지 등이다.
11. 그런데 imbalance하다면, 0과 1의 비중이 달라서, 스케일링을 해주어야한다.
12. pd.crosstab(df[target_column], df[list_categorical_columns[0]], normalize='index')를 해보자. 
13. df_poutcome_dependent_ratio = pd.crosstab(df[target_column], df[list_categorical_column[0]], normalize='index')
df_poutcome_dependent_ratio.plot.barh(fig_size=(10,5))
14. 그럼 여기서 어떤 column들이 target값과 연관이 있을지 검정을 해야하는데, 카테고리컬 컬럼은 카이제곱으로, 뉴머릭 컬럼은 ANOVA를 먼저 하는데, 정규성을 만족하는지 확인하고 정규성을 만족하지 못하면 크루스칼 왈리스로 가준다.
15. 






# Mapping for channels
channel_dict = {"House Ads": 1, "Instagram": 2, 
                "Facebook": 3, "Email": 4, "Push": 5}

# Map the channel to a channel code
marketing['channel_code'] = marketing['subscribing_channel'].map(channel_dict)
marketing['DoW'] = marketing['date_subscribed'].dt.dayofweek

- Groupby date, for user id, nunique and check the numbers.
- then create a graph with pyplot