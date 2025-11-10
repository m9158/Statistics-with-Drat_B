# 통계학 6주차 정규과제

📌통계학 정규과제는 매주 정해진 분량의 『*데이터 분석가가 반드시 알아야 할 모든 것*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **Statistics_6th_TIL**에 나열된 분량을 읽고 `학습 목표`에 맞게 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 추가자료와 교재를 다시 참고하여 보완하는 것이 좋습니다.

6주차는 `2부-데이터 분석 준비하기`를 읽고 새롭게 배운 내용을 정리해주시면 됩니다


## Statistics_6th_TIL

### 2부. 데이터 분석 준비하기

### 11. 데이터 전처리와 파생변수 생성

<!-- 11. 데이터 전처리와 파생변수 생성에서 11.1 결측값 처리부터 11.4 데이터 표준화와 정규화 스케일링 파트까지 진행해주시면 됩니다. -->

## Study ScheduleStudy Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | 1부 p.2~46    | ✅         |
| 2주차 | 1부 p.47~81   | ✅         |
| 3주차 | 2부 p.82~120  | ✅         |
| 4주차 | 2부 p.121~167 | ✅         |
| 5주차 | 2부 p.168~202 | ✅         |
| 6주차 | 2부 p.203~250 | ✅         |
| 7주차 | 2부 p.251~299 | 🍽️         |

> 과제가 많이 남지 않았습니다. 조금만 더 화이팅해주세요!

<!-- 여기까진 그대로 둬 주세요-->



---

# 1️⃣ 개념 정리 

## 11.데이터 전처리와 파생변수 생성

```
✅ 학습 목표 :
* 결측값과 이상치를 식별하고 적절한 방법으로 처리할 수 있다.
* 데이터 변환과 가공 기법을 학습하고 활용할 수 있다.
* 모델 성능 향상을 위한 파생 변수를 생성하고 활용할 수 있다.
```

### 11.1. 결측값 처리

1. 결측치의 종류
  - 완전 무작위 결측(MCAR): 순수하게 결측값이 무작위로 발생한 경우
  - 무작위 결측(MAR): 다른 변수의 특성에 의해 해당 변수의 결측치가 체계적으로 발생한 경우
  - 비무작위 결측(NMAR): 결측값들이 해당 변수 자체의 특성을 갖고 있는 경우

2. 결측값 처리 방법
   - 표본 제거 방법: 결측값이 심하게 많은 변수를 제가하거나 결측값이 포함된 행을 제외하고 데이터 분석을 하는 방법
     
   - 평균 대치법: 결측값을 제외한 온전한 값들의 평균을 구한 다음, 그 평균 값을 결측값들에 대치하는 방법
   - 보간법 : 전 시점 혹은 다음 시점의 평균 값으로 대치하는 방법
     - 단순 순서 보산
     - 시점 고려 보간
       
   - 회귀 대치법: 해당 변수와 다른 변수 사이의 관계성을 고려하여 결측값을 계산하는 방법
     - 확률적 회귀 대치법: 인위적으로 회귀식에 확률 오차항을 추가하는 방법. 즉, 관측된 변동성만큼 결측값에도 같은 변동성을 추가
       
   - 다중 대치법: 단순대치를 여러 번 수행하여 N 개의 가상적 데이터를 생성하여 이들의 평균으로 결측값을 대치하는 방법.
       - 대치 단계: 가능한 대치 값의 분포에서 추출된 서로 다른 값으로 결측치를 처리한 N 개의 데이터셋 생성
       - 분석 단계: 생성된 각각의 데이터셋을 분석하여 모수의 추정치와 표준오차 계산
       - 결합 단계: 계산된 각 데이터셋의 추정치와 표준오차를 결합하여 최종 결측 대치값 산출
    
3. 결측값 처리 실습

<img width="213" height="643" alt="image" src="https://github.com/user-attachments/assets/eefdce98-5081-4118-b93c-ee679c091f25" />

~~~
몇개의 결측값이 있는지부터 확인. temp 칼럼부터 registered 칼럼까지 11~25개의 결측값이 있는 것을 확인
~~~


<img width="2044" height="921" alt="image" src="https://github.com/user-attachments/assets/150d830a-4200-4d0d-82ec-bd17cb226e73" />
<img width="2054" height="959" alt="image" src="https://github.com/user-attachments/assets/b4cae941-f1f8-44c2-8e72-91c6c8f550a4" />

~~~
전체 데이터셋에서 영역별로 결측값이 어떻게 분포해 있는지 시각화. hum 칼럼이 연속적으로 결측값을 많이 가지고 있는 것을 확인할 수 있음.
~~~


<img width="328" height="716" alt="image" src="https://github.com/user-attachments/assets/2d75f655-c073-4886-ba31-699921fcbfda" />

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요. -->

~~~
결측값으로는 인식되지 않지만 실젯값이 빈 문자열인 값이 있는지 확인, 없음.
~~~

<img width="336" height="735" alt="image" src="https://github.com/user-attachments/assets/d8329d61-26cb-49b1-a5f3-bdf66c8f4e18" />

~~~
dropna() 함수, how 옵션을 활용하여 결측치를 제거한다. 제거한 후의 결과.
~~~

<img width="304" height="728" alt="image" src="https://github.com/user-attachments/assets/87449756-ad80-43ce-966b-210e71c32fc6" />

~~~
기본적인 결측값 대치는 fillna() 옵션을 활용할 수 있다. 평균, 중간값, 최빈갑, 최댓값, 최솟값 등의 옵션을 사용하여 대치가 가능하다.
~~~


<img width="455" height="531" alt="image" src="https://github.com/user-attachments/assets/8bf616ab-fcaa-4006-82f9-3cc563601e06" />


~~~
- 전 시점이나 뒤 시점의 값과 동일한 값으로 대치하는 보간법은. method 옵션을 pad나 bfill로 설정하여 적용한다.
- 유의할 점은 첫행과 마지막 행이 결측값인 경우 그 다음 혹은 이전의 값들은 대치되지 않는다.
- 그리고 시점 인덱스를 사용하기 위해서는 우선 시간형 칼럼을 시계열 객체로 변환한 후에 인덱스로 설정해줘야 한다.
- 이후 interpolate() 함수를 사용하여 시점의 정도를 고려한 대치값을 적용해준다.
~~~



<img width="656" height="641" alt="image" src="https://github.com/user-attachments/assets/c8a0c0c0-9078-4a62-bd4d-e35dae41caa9" />


~~~
- 다중 대치는 sklearn의 impute 패키지를 활용한다.
- 우선 대치에 필요 없는 dteady 칼럼을 제거해 준 다음 다중 대치 알고리즘을 적용해준다.
- 다중 대치를 적용할 때는 넘파이 배열로 변환되기 때문에 다시 판다스 데이터프레임으로 변환해준다.
~~~


### 11.2. 이상치 처리


1. 이상치란?
   - 일부 관측치의 값이 전체 데이터의 범위에서 크게 벗어난 아주 작거나 극단적인 값을 갖는 것
  
2. 이상치 처리의 방법
   - 결측값 처리
   - 해당 이상치를 아예 제거
   - 관측값 변경: 하한 값과 상한 값을 결정한 후 하한 값보다 작으면 하한 값으로 대체하고 상한값보다 크면 상한 값으로 대체하는 방법
   - 이상치의 영향을 감소시키는 가중치를 주는 가중치 조정 방법
  
3. 이상치 처리 실습

<img width="230" height="411" alt="image" src="https://github.com/user-attachments/assets/26e29697-8fee-4aea-90ed-7bc281de5b43" />

~~~
우선 컬럼의 분포를 확인. 중위수의 값이 27.34이면서 최댓값은 .94.85로 3배 이상 차이가 난다.
~~~


 <img width="752" height="614" alt="image" src="https://github.com/user-attachments/assets/0ee84f36-efb9-4027-bd46-096e2094ce50" />


~~~
박스 플롯을 통해 이상치를 확인했다. 눈으로 확인해봐도 3 IQR을 넘어서는 관측치가 다수 있을 것으로 판단된다.
~~~

<img width="649" height="592" alt="image" src="https://github.com/user-attachments/assets/31652151-1296-4e64-b311-ca01f8b2a9a2" />


~~~
- 박스 플롯의 이상치 기준인 IQR 1.5는 정규분포로 환산했을 때 2.698 표준편차와 동일하다. 그런데 실무 데이터에서는 분포가 넓은 편이기 때문에 IQR 3을 적용해 준다.
- 이는 약 5 표준편차로, 이상치로 판단하기 충분한 기준이다.
- 최종 아웃풋에서 기존 칼럼의 최댓값 94.85가 53.59로 감소했으며, 관측치는 1,318개가 제거 됐다.
~~~


<img width="743" height="621" alt="image" src="https://github.com/user-attachments/assets/cd6ed6d2-66e5-446c-8e94-07de568beb46" />


~~~
IQR 3 기준의 이상치를 제거한 후 박스 플롯의 이상치가 많이 줄어든 것을 확인할 수 있다.
~~~


<img width="349" height="604" alt="image" src="https://github.com/user-attachments/assets/02d5b3da-1209-40c4-bf1e-73ae2f6854aa" />


~~~
- 이상치를 상하한선 값으로 대치
- 상황에 따라 평균이나 중앙값 등으로 대치해 줄 수 있음
- if 문을 사용하여 상하한선 설정
- 전체 관측치의 수가 그대로 유지되며 최댓값이 53.59로 조정됨을 알 수 있음.
~~~


<img width="759" height="611" alt="image" src="https://github.com/user-attachments/assets/30b305bc-5ac9-49cb-bdb6-7ef63384db65" />


~~~
- 이상치 대치 후에도 이상치 제거 방법과 같이 이상치 수준이 감소한 것을 확인할 수 있다.
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요. -->

### 11.3. 변수 구간화

1. 변수 구간화란?
   - 데이터 분석의 성능을 향상시키기 위해서 혹은 해석의 편리성을 위해서 이산형 변수를 범주형 변수로 변환하는 것.

2. 변수값 효과적인 구간화가 되었는지 확인하는 방법
   - WOE값, IV값 등을 통해 측정 가능
   - IV 수치가 높을 수록 종속변수의 True와 False를 잘 구분할 수 있는 정보량이 많다는 뜻
   - 변수가 종족변수를 제대로 설명할 수 있도록 구간화가 잘되면 IV 값이 높아지는 것

<img width="819" height="522" alt="image" src="https://github.com/user-attachments/assets/6d4b0b22-b1df-47ea-975d-6ce33f89cfd0" />




3. 변수 구간화 실습



<img width="1557" height="622" alt="image" src="https://github.com/user-attachments/assets/024e51f9-bc7a-47a7-9e05-78e2db2b5cc6" />


~~~
- BMI 칼럼 분포를 직관적으로 확인하기 위한 시각화
- 오른 꼬리 분포로 20~40 사이에 대부분 관측치가 분포해 있고 60 이상부터는 관측치가 희소하다
~~~



<img width="1770" height="588" alt="image" src="https://github.com/user-attachments/assets/295f54c1-326a-452e-8022-268efd1d2c80" />


~~~
- 기본적으로 특별한 함수 없이도 변수 구간화를 할 수 있다.
- 실습에서는 임의로 20부터 10단위로 70까지 구간을 설정하고 70이상부터는 하나의 범주로 설정
- 각 범주의 명칭은 상황에 따라 자유롭게 설정 가능
~~~


<img width="1550" height="600" alt="image" src="https://github.com/user-attachments/assets/01d1b25e-2e84-4ddb-95b2-4429e57cf943" />



~~~
- 구간화를 적용한 BMI 칼럼의 분포 확인
- 총 7개의 범주로 구분되어 분포가 단순하게 변화함
- 분포는 기존 형태와 유사함을 알 수 있음
~~~



<img width="1769" height="375" alt="image" src="https://github.com/user-attachments/assets/7c6c7215-4d0a-4c0b-aff0-d59d800d3543" />



~~~
- 판다스의 cut() 함수를 사용하면 간단하게 구간화를 수행 할 수 있다
- cut() 함수는 레이블의 수를 구간 기준 수보다 하나 적게 설정하는 것에 유의해야 함
- 구간 기준은 앞과 동일하게 설정
- BMI_bin2 칼럼을 새로 생성
- 아웃풋 결과를 보면 2와 1이 동일함을 알 수 있음
~~~


<img width="658" height="387" alt="image" src="https://github.com/user-attachments/assets/e4f969d3-54b8-46ad-a251-87f2dacbe147" />


~~~
- 구간별 관측치 수 집계를 확인
- BMI가 20~30에 해당되는 B 구간의 관측치가 가장 많고 70~95에 해당되는 g  구간의 관측치가 가장 적음을 알 수 있다
~~~


<img width="1766" height="384" alt="image" src="https://github.com/user-attachments/assets/ce1d67cd-a752-4602-9965-de197cbb58c5" />


~~~
- 구간별로 포함되는 관측치의 수가 유사한 구간화를 적용하기 위해서는 qcut() 함수를 사용한다
- 나누고자 하는 범주의 수와 각 범주의 명칭만 설정해 주면 자동으로 구간화가 적용된다.
- 아웃풋 테이블을 확인 해보면 새로 생성한 BMI_bin3 칼럼은 앞의 두 칼럼과 동일하게 7개의 범주로 나누었지만 결괏값이 다름
- 각 범주의 기준 값이 다르기 때문이다
~~~


<img width="632" height="376" alt="image" src="https://github.com/user-attachments/assets/12a8de6e-bdf6-410c-8ac6-e662b22a05ec" />


~~~
- qcut()함수를 사용했을때 범주별 관측치의 수가 유사한 수준으로 배치된다
- BMI 칼럼과 같이 긴 꼬리 분포를 가진 경우에는 동일한 간격으로 구간화를 할 경우, 포한되는 관측치가 너무 희소한 범주가 생겨 모델의 성능 저하가 발생한다
- 그래서 이와 같은 구간화 방식이 유용하다
~~~


<img width="1569" height="599" alt="image" src="https://github.com/user-attachments/assets/1c5d15ac-bfcb-43c0-8ecb-97e45dee169b" />



~~~
- 칼럼의 분포를 시각화하여 분포가 일정하게 이루어졌음을 확인
~~~


<img width="988" height="614" alt="image" src="https://github.com/user-attachments/assets/5d84998f-1298-49f0-8a7c-84743116f28c" />


<판다스 오류가 생겨 실습코드로 대체>

~~~
- WOE를 활용하여 종속 변수에 대한 독립변수가 최적의 예측력을 가질 수 있도록 구간화
- 종속변수를 1과 0의 가변수로 전처리
- 종속변수로 신부전증 여부 칼럼 지정
- WOE() 함수를 사용하면 칼럼의 최적 범주 기준 산출
- -0.001~1 범위, 1~30 범위 두가지 범주로 나누는 것이 가장 적합한 것으로 확인 가능
~~~


<img width="990" height="180" alt="image" src="https://github.com/user-attachments/assets/59232594-271b-4590-8a2e-aca85c1b472b" />


~~~
- WOE를 활용한 구간화 기준의 IV는 0.308
- 이는 강한 예측력을 가진 구간화 변수임을 알 수 있음
~~~






<!-- 새롭게 배운 내용을 자유롭게 정리해주세요. -->

### 11.4. 데이터 표준화와 정규화 스케일링

1. 표준화와 정규화
  - 독립 변수들이 서로 단위가 다르거나 편차가 심할 때 값의 스케일을 일정한 수준으로 변환시켜주는 것

  1-1. 표준화
    - 각 관측치의 값이 전체 평균을 기준으로 어느 정도 떨어져 있는지 나타낼 때 사용
    - 평균은 0으로 반환되고, 1표준편차 거리는 +-1, 2표준편차는 +-2로 변환된다.
    - Zero-mean으로부터 얼마나 떨어져 있는지를 나타내기 때문에 이를 Z-score라고 한다.
    - 그렇기 때문에 서로 다른 변수 값의 크기를 직관적으로 비교가 가능하다

  1-2. 정규화
    - 데이터의 범위를 0부터 1까지로 변환하여 데이터 분포를 조정하는 방법이다.
    - 전체 데이터 중에서 해당 값이 어떤 위치에 있는지 파악할 때 유리하다.
    - 0에 가까울 수록 작고 1에 가까울수록 큰 값이다.

2. RobustScaler
   - 기본 표준화, 정규화 방식은 이상치에 민감하다는 단점을 보완한 스케일링 기법
   - 데이터 중앙값(Q2)를 0으로 잡고 Q1(25%)과 Q3(75%) 사분위수와의 IQR 차이를 1이 되도록 하는 스케일링 기법이다
   - 이상치의 영향력을 최소화하여 일반적으로 우수하다
  
3. 데이터 표준화와 정규화 스케일링 실습



<img width="316" height="691" alt="image" src="https://github.com/user-attachments/assets/fb310a40-e042-41b3-9c97-2dee1cf87bbb" />


~~~
- 먼저 각 컬럼의 평균과 분산을 확인한다.
- 마그네슘과 프롤린의 분산이 큰 것을 확인할 수 있다.
~~~


<img width="1439" height="422" alt="image" src="https://github.com/user-attachments/assets/ea9f7424-72cd-4d54-b5d8-3261b3d92a25" />



~~~
- 전체 칼럼의 기존 값에 표준화 스케일링을 적용
- STandardScaler() 함수를 사용하여 표준화된 값으로 변환
- 넘파이로 변환되기 때문에 판다스로 데이터 프레임 변경
~~~



<img width="412" height="680" alt="image" src="https://github.com/user-attachments/assets/45aec3e6-6114-48fb-815d-52319af1ec1e" />



~~~
- 이후 전체 칼럼의 평균과 분산 확인
- 칼럼들의 평균은 0에 가깝고 분산은 1에 가깝게 변경됨
~~~



<img width="1489" height="489" alt="image" src="https://github.com/user-attachments/assets/64640ae7-378d-4f6d-87c8-b10b5c797860" />



~~~
- 표준화된 칼럼들의 분포가 어떻게 변화했는지 확인하기 위해 하나의 칼럼 샘플 분포 시각화
- 분포는 유사하지만 데이터 값의 범위가 달라짐
~~~




<img width="1458" height="427" alt="image" src="https://github.com/user-attachments/assets/5338c5c5-be88-426b-aa7d-0db12e13d017" />





~~~
- MinMaxXSclaer() 함수를 사용하여 데이터 정규화 스케일링 적용
- 적용 방식은 앞의 표준화와 동일
~~~



<img width="266" height="641" alt="image" src="https://github.com/user-attachments/assets/e08d8a8d-b939-44a5-b793-e9f0ee9c5055" />



~~~
- 정규화를 했기 때문에 최댓값은 1, 최솟값은 0이 됨을 알 수 있다
~~~


<img width="419" height="689" alt="image" src="https://github.com/user-attachments/assets/ac0dde62-874e-49db-915f-aac604de516b" />


~~~
- 정규화 스케일링을 적용한 칼럼들의 평균과 분포가 유사하게 변환됨
~~~




<img width="1489" height="489" alt="image" src="https://github.com/user-attachments/assets/6c5ad540-f471-41f4-9d93-8149feac73ee" />




~~~
- 정규화 스케일링을 적용한 칼럼은 0과 1 사이에서 기존의 데이터 값과 유사한 분포를 가지고 있음
~~~



<img width="1461" height="413" alt="image" src="https://github.com/user-attachments/assets/37819fea-2f16-42f5-be15-641b97ac1020" />



~~~
- RObustScaler ()를 적용하여 데이터 스케일링
- 적용 방식은 앞과 동일
~~~




<img width="426" height="668" alt="image" src="https://github.com/user-attachments/assets/77d8b7b7-2df7-4d79-be16-5d309562dc98" />




~~~
- 마찬가지로 평균과 분포가 유사하게 변환됨
- 이는 평균 대신 중앙값을 사용하기 때문에 극단값의 영향을 받지 않게 됨
~~~





<img width="1489" height="489" alt="image" src="https://github.com/user-attachments/assets/033dfe12-7b47-432f-b6b8-07a9f8d930b9" />




~~~
- 칼럼에 RobustSclaer 스케일링을 적용한 분포는 표준화를 적용했던 분포보다 범위가 좁은 것을 알 수 있음
- 이는 이상치의 영향력이 줄어들었기 때문임
~~~


<!-- 새롭게 배운 내용을 자유롭게 정리해주세요. -->



<br>
<br>

---

# 2️⃣ 확인 과제

> **교재에 있는 실습 파트를 직접 따라 해보세요. 실습을 완료한 뒤, 결과화면(캡처 또는 코드 결과)을 첨부하여 인증해 주세요.**
>
> **단순 이론 암기보다, 직접 손으로 따라해보면서 실습해 보는 것이 가장 확실한 학습 방법입니다.**
>
> > **인증 예시 : 통계 프로그램 결과, 시각화 이미지 캡처 등**

<!-- 이 주석을 지우고 “실습 결과 화면(캡처)을 이곳에 첨부해주세요.-->

~~~
인증 이미지가 없으면 과제 수행으로 인정되지 않습니다.
~~~



### 🎉 수고하셨습니다.
