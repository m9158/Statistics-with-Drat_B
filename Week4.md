# 통계학 4주차 정규과제

📌통계학 정규과제는 매주 정해진 분량의 『*데이터 분석가가 반드시 알아야 할 모든 것*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **Statistics_4th_TIL**에 나열된 분량을 읽고 `학습 목표`에 맞게 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 추가자료와 교재를 다시 참고하여 보완하는 것이 좋습니다.

4주차는 `2부-데이터 분석 준비하기`를 읽고 새롭게 배운 내용을 정리해주시면 됩니다


## Statistics_4th_TIL

### 2부. 데이터 분석 준비하기

### 10. 데이터 탐색과 시각화

<!-- 10. 데이터 탐색과 시각화에서 10.1 탐색적 데이터 분석부터 10.4 비교 시각화 파트까지 진행해주시면 됩니다. -->



**(수행 인증샷은 필수입니다.)** 

<!-- 이번주는 확인 문제가 없고, 교재의 실습에 있는 부분을 따라해주시면 됩니다. 데이터셋과 참고자료는 노션의 정규과제란에 있는 깃허브를 활용해주시면 됩니다. -->



## Study ScheduleStudy Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | 1부 p.2~46    | ✅         |
| 2주차 | 1부 p.47~81   | ✅         |
| 3주차 | 2부 p.82~120  | ✅         |
| 4주차 | 2부 p.121~167 | ✅         |
| 5주차 | 2부 p.168~202 | 🍽️         |
| 6주차 | 3부 p.203~250 | 🍽️         |
| 7주차 | 3부 p.251~299 | 🍽️         |

<!-- 여기까진 그대로 둬 주세요-->



---

# 1️⃣ 개념 정리 

## 10. 데이터 탐색과 시각화

```
✅ 학습 목표 :
* EDA의 목적을 설명할 수 있다.
* 주어진 데이터셋에서 이상치, 누락값, 분포 등을 식별하고 EDA 결과를 바탕으로 데이터셋의 특징을 해석할 수 있다.
* 공분산과 상관계수를 활용하여 두 변수 간의 관계를 해석할 수 있다.
* 적절한 시각화 기법을 선택하여 데이터의 특성을 효과적으로 전달할 수 있다.
```
1. EDA의 목적
  - 데이터의 형태와 척도가 분석에 맞게 알맞게 되어있는지 확인
  - 데이터의 평균, 분산, 분포, 패턴 등의 확인을 통해 데이터 특성 파악
  - 데이터의 결측값이나 이상치 파악 및 보완
  - 변수 간의 관계성 파악
  - 분석 목적과 방향성 점검 및 보정

2. 공분산과 상관성 분석
  - 공분산: 서로 공유하는 분산 => 두 분산의 관계를 뜻함. 공통적인 분산의 정도 파악
      - 값이 0이면 두 변수는 상관관계가 없는 것이고, 양수면 양의 관계, 음수면 음의 관계를 나타낸다고 볼 수 있다.
      - 그러나 공분산의 크기가 상관성의 정도를 알려주지는 않음.
  - 피어슨 상관계수: 변수 1, 2가 함께 변하는 정도(공분산)을 변수 1, 2가 변하는 전체 정도로 나누어준 것.
      - 일반적으로 0.7 이상이면 상관관계가 매우 높다, 0.4 이상이면 어느 정도 상관관계가 있다고 해석한다.
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



<br>
<br>

---

# 2️⃣ 확인 과제

> **교재에 있는 실습 파트를 직접 따라 해보세요. 실습을 완료한 뒤, 결과화면(캡처 또는 코드 결과)을 첨부하여 인증해 주세요.단순 이론 암기보다, 직접 손으로 따라해보면서 실습해 보는 것이 가장 확실한 학습 방법입니다.**
>
> > **인증 예시 : 통계 프로그램 결과, 시각화 이미지 캡처 등**



**1. 탐색적 데이터 분석(EDA)**

<img width="945" height="740" alt="image" src="https://github.com/user-attachments/assets/b2325da7-142e-4b29-86cd-e8444f417ba7" />

=> 0이 확연히 많은 것으로 봐서 당일 체크인하는 투숙객이 많은 편이라는 것을 확인할 수 있다.

<img width="755" height="558" alt="image" src="https://github.com/user-attachments/assets/c7a5367c-d11a-4aa3-afde-a558fcd0b258" />

=> 리조트 호텔은 리드 타임의 최대값이 시티 호텔보다 높지만, 대체적으로 더 작은 값에 분포하는 것을 알 수 있다.



**2. 공분산과 상관성 분석**


<img width="1807" height="791" alt="image" src="https://github.com/user-attachments/assets/562f709b-c65c-4ab2-9149-92a5525284ec" />
<img width="1788" height="808" alt="image" src="https://github.com/user-attachments/assets/17955593-9726-4875-972b-bdb90372b459" />

=> 몇 개의 산점도는 어느 정도 상관성이 보이는것을 확인할 수 있다. 종속변수라 할 수 있는 quality 변수는 자연수 형태로 3~9로만 이루어져 있기 때문에 다른 변수들과 줄무늬 형태의 산점도를 보인다.

<img width="1575" height="488" alt="image" src="https://github.com/user-attachments/assets/e1932c7b-4b9b-4827-b203-98d5bd603ee6" />

=> 공분산으로는 역시 변수 간 상관성을 분석하기에는 가독성이 떨어진다.

<img width="1550" height="501" alt="image" src="https://github.com/user-attachments/assets/8960b6b3-7b32-48fd-96e8-1bdd22d2ed2a" />

=> 동일한 변수 간에는 상관계수가 1로 나오고 있으며, -1~1 사이의 값을 가지고 있다.

<img width="2054" height="1699" alt="image" src="https://github.com/user-attachments/assets/161f28db-1b49-4874-8cdb-f62cdf50efd5" />

=> 노란색에 가까울수록, 양의 상관관계를 보이고 보라색에 가까울수록 음의 상관관계를 보임. 그러나 정확한 수치 확인이 필요.

<img width="2941" height="2959" alt="image" src="https://github.com/user-attachments/assets/5cd5e0a4-071b-4544-b245-0e41fa112311" />

=> total_sulfur_diocide 변수와 free sulfur dioxide 변수의 상관계수는 0.72로 강한 양의 상관관계를 보이는 것을 직관적으로 알 수 있다.

<img width="3845" height="2986" alt="image" src="https://github.com/user-attachments/assets/711cdd1b-0263-4047-af80-b230f25e7061" />

=> 동일한 두 변수 조합이 두번씩 나오는 것을 방지. 가독성을 높인 히트맵 방식


**3. 시간 시각화**

<img width="597" height="542" alt="image" src="https://github.com/user-attachments/assets/a154bfdf-bd23-4394-b2ff-292f5e679486" />

=> 선그래프 시각화에 앞서 일자별 매출액 데이터를 가공

<img width="1748" height="1296" alt="image" src="https://github.com/user-attachments/assets/9165af33-26dd-426b-b078-f88d1ee15b61" />

=> 선그래프 생성. 30일 이동평균선을 삽입하기 위해 rolling()함수를 사용하여 Month의 칼럼 제작. 매출액 편차가 커서 일 매출 선으로는 전체적인 추이 가늠 힘들기 때문에 이동평균선이 도움이 됨.

<img width="2617" height="1373" alt="image" src="https://github.com/user-attachments/assets/e5f3a7f5-030f-4ba3-b6b5-54bca56d747f" />

=> 막대 그래프 생성. 2016년도에 매출액이 다소 감소했다가 이후 증가한 것을 확인 가능.(만약 x축 레이블이 길어서 글자가 겹치는 경우에는 rot옵션 사용)

<img width="2617" height="1915" alt="image" src="https://github.com/user-attachments/assets/df945273-8607-4797-a542-52f668773624" />

=> 누적 막대 그래프 생성. 매출액은 단순 앞의 막대 그래프와 동일하지만, 세 가지 세그먼트의 각 매출액이 구분되어 표현된 것을 확인. 이를 통해 각 연도에서 세그먼트별 매출액 비중이 어느 정도 되는지 파악 가능.


**4. 비교 시각화**

<img width="2011" height="2052" alt="image" src="https://github.com/user-attachments/assets/1a7f3f92-b6f2-4101-a2cf-bc49f813d0bd" />

=> 각 팀별 요소들을 히트맵으로 시각화. x축에는 각 요소들이,  y축에는 각 팀이 들어감. 팀간의 큰 차이는 보이지 않음.

<img width="2011" height="2069" alt="image" src="https://github.com/user-attachments/assets/0d97491b-93bf-41be-8d2c-933bf24874e2" />

=> 팀별로 19세부터 34세까지의 나이대에 따라 게임 참여 횟수에 대한 히트맵. 흰색은 Null 값. BRK 팀은 34세 선수의 게임 참여 획수가 약 30회 정도로 확연히 높음.

<img width="4159" height="5832" alt="image" src="https://github.com/user-attachments/assets/fad6cf2c-8d83-4185-9bfa-3603aeb82045" />

=> 방사형 차트를 위해, 하나씩 시각화.

<img width="2183" height="2049" alt="image" src="https://github.com/user-attachments/assets/c55bf4d8-af8c-4714-932b-52562b9a53ba" />

=> 방사형 차트 생성. 하나의 방사형 차트의 5개 팀 모두가 표현됨. 그룹이 많지 않은 경우에 용이. 전체적으로 CHO팀이 우세하다는 것을 알 수 있음.

<img width="1734" height="1242" alt="image" src="https://github.com/user-attachments/assets/587a8e3c-fd2b-447b-9ea4-dbc698d659d8" />

=> 같은 데이터 셋을 활용해 평행 좌표 그래프 시각화. 같은 결과를 눈으로 확인 가능.






~~~
인증 이미지가 없으면 과제 수행으로 인정되지 않습니다.
~~~





### 🎉 수고하셨습니다.
