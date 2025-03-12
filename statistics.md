[Z Score]

## Detecting and removing outlier using z-score
Data가 적을때 사용할 수 있음
Z-score는 데이터가 평균으로부터 표준편차의 몇 배 만큼 떨어져 있는지를 보여줌
예를 들어, z score가 3이면 평균으로부터 3시그마(표준편차) 만큼 떨어져 있다고 하는 것임
그렇기 때문에 Outlier일 가능성이 높다고 판단함
Z-score의 값이 (+) 이면 평균보다 높음을 의미함
Z-score의 값이 (-) 이면 평균보다 낮음을 의미함
Z-score = (x - x의평균) / 표준편차

의학분야에서는 보수적이기 때문에 Outlier에 대해 학습하지 않음
최대한 데이터를 잘 Preprocessing하고 데이터 분석에 들어가게 됨

