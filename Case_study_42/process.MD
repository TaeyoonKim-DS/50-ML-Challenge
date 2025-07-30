1. duplicate를 체크한다.
2. 각 column의 dtype과 unique 값을 확인한다.
3. categorical type인데도, int나 float으로 되어있는 부분들을 categorical로 변경해준다. 이 경우 object.
4. Nan값이 있는 컬럼들을 확인하며 지워준다. handsetprice에 nan값이 많다.
5. Handsetprice의 컬럼값을 drop한다.
6. target 컬럼이 무엇인지 확인하고, categorical과 numeric column을 int,float 그리고 object 타입으로 나눈다.
7. Nan값을 확인해준다.
8. target의 비율을 본다.
9. 타겟 컬럼이 categorical column 부분에 있어서, 지워준다.
10. 각 컬럼에 몇개의 유니크한 값이 있는지 확인한다. ServiceArea에 747개의 unique값이 있는 것을 확인한다.
11. Customer ID는 필요없어서 지워준다.
12. categorical column중에 nan값이 몇개가 있는지 확인해준다.
13. categorical column별 분포를 plot을 그려서 확인해준다.
    - NewCellphoneUser와 NotNewCellphoneUser가 매우 겹치는 것 보임. 컬럼에 대한 이해 더 필요.
    - Homeonwership이 known 혹은 unknown으로 되어있음. 
    - income group은 10개의 카테고리로 나뉨.
    - creditrating이 object타입이지만 사실은 numeric한 값. 
    - occupation에도 other이 압도적으로 많음.
    - martial status에 unknown도 굉장히 많음.
14. ServiceArea에는 747개의 유니크값이 있는 것을 확인.
15. Categorical Column과 dependent data분포를 분석.
16. serviceArea와 HandsetModels의 nan값을 지우기로 결정함.
17. Target column과 categorical column관계 분포를 plot을 그려서 확인.
18. ChiSquare 검정을 진행해서 어떤 column값이 target값과 독립/종속인지 확인한다.
19. categorical 컬럼 검정이 끝났으므로 다음으로 넘어간다.
20. numerical columns중에 unique 갯수를 확인한다.
21. numerical values중에 0이 몇개나 포함되어 있는지 확인한다.
22. 0이 95%이상 속한 데이터 제외하기 전에 kruskal 검정을 통해서 실제로 의미있는지 확인해보기. 
23. 의미있는 변수 3개를 제외한 컬럼은 삭제.
24. numerical value의 plot을 그려서 확인해보기.
25. imputer는 KNNimputer를 이용해서 결측치 채워넣기.
26. skewness와 kurtosis 확인. 대략적으로 0주변의 skeness가 좋고 >1< 사이로 확인. Kurtioss는 3사이로 확인.
27. Correlation analysis heatmap.
28. 너무 높은 correlation을 갖는 데이터 삭제. 0.8에서 1사이.
29. 정규성 검정 -> 샤피로 윌크, 비모수 검정 -> 윌콕슨.
30. 