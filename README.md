# ml-studies

ML(기계학습, Machine Learning)이란 대체 어디서부터 무엇을 말하는지. 실제 데이터를 다루게 되면서 만나는 여러 상황을 정리하고자 하는 목표를 가지고 생성한 repository입니다. 

## Contexts
* [Data Analysis](#data-analysis)
* [EDA & DP & FE](#eda--dp--fe)
* [Basic ML](#basic-ml)
* [Real Time ML](#real-time-ml)

> ### Data Analysis
데이터 분석 방법론을 나열하자면 다음과 같다.

* CDA(확증적 자료 분석, Confirmatory Data Analysis)
* EDA(탐색적 자료 분석, Exploratory Data Analysis)
* QDA(정성적 자료 분석, Qualitative Data Analysis)

이 외에도 통상 빅데이터 분석에 대해서도 분류하고 있지만, 개인적으로 빅데이터 분석은 특정 필드(혹은 도메인)에서 꽤 많은 이해 및 경험을 기반으로 이루어질 수 있는 영역이라고 생각한다. 그리고 사실 이미 복잡한 현실의 데이터를 분석이 가능하도록 가공한다면, 위의 분석 방법론을 기반으로 하여 진행되었을 것이라는 판단이 들어서 데이터 분석 방법론에서 빅데이터 분석은 배제하겠다.

위에서 나열한 분석론을 간단하게 정의하자면, CDA는 일종의 수치적인 가설(Hypothesis) 검증을 통한 분석을, QDA는 비수치적인 가설 검증을 통한 분석을, EDA는 원시 데이터(비정제 데이터, 관측치)에서 탐구하는 분석을 말한다.

수치 및 통계를 기반으로 분석했다는 점에서 CDA와 EDA는 유사한 부분이 많은데, QDA는 필드에 따라 전개하는 방향이 크게 달라진다고 볼 수도 있다. 이러한 방법론을 융합하면, 요즘 취업 시장에서 분석가에게 요구하는 Funnel [^1], Retention [^2], AARRR [^3], Cohort [^4] 등의 방법으로 활용할 수 있다.

어떤 분께서 정리한 글을 늦게라도 찾아서, 취업 시장에서 분석가에게 요구하는 내용이 더 궁금한 사람은 다음의 [링크](https://blog.naver.com/willie123/222095604766)를 참고하길 바란다.


> ### EDA & DP & FE
* EDA(탐색적 자료 분석, Exploratory Data Analysis)
* DP(데이터 전처리, Data Preprocessing)
* FE(특성 추출, Feature Engineer)

정리할 내용을 기다리기 힘든 분들은 다음의 링크([EDA, Data Preprocessing, Feature Engineering: We are different!](https://medium.com/@ndleah/eda-data-preprocessing-feature-engineering-we-are-different-d2a5fa09f527))를 참고하면 좋을 것 같다.


> ### Basic ML

> ### Real Time ML

* Detection
ELBO(Evidence Lower Bound) 최대화하는 가장 간단한 방법은 BBSVI(Blac Box Stochastic Variational Inference)
```
from sklearn.mixture import GaussianMixture
from sklearn.mixture import BayesianGaussianMixture
from sklearn.covariance import EllipticEnvelope
from sklearn.ensemble import IsolationForest
from sklearn.neighbors import LocalOutlierFactor
from sklearn.svm import OneClassSVM
from sklearn.linear_model import SGDOneClassSVM
```
* GaussianMixture: covariance_type에 따라 계산 복잡도가 달라짐. 특성 개수가 많으면 적용하기 어려움(BayesianGaussianMixture와 계산 복잡도가 비슷하나, 일반적으로는 훨씬 빠름)
* BayesianGaussianMixture: 최적의 클러스터 개수를 수동으로 탐지하기 보다는, 불필요한 클러스터의 가중치를 0에 근사하도록 만듦
* PCA(Principal component analysis): 여러 데이터들이 모여 하나의 분포를 이룰 때, 주 성분을 분석해 주는 방법으로 이상치 탐지 기법으로도 활용됨
* EllipticEnvelope: 가우시안 분포 형태의 데이터에서 이상치 탐지, 통상 데이터셋 정제 시에 사용됨.(Fast-MCD)
* IsolationForest: Isolation Forest Algorithm은 고차원 데이터에서 효율적인 이상치 탐지
* LOF(LocalOutlierFactor): Local Outlier Factor를 사용한 비지도학습 이상치 탐지
* OneClassSVM: Support Vector Machine을 사용한 비지도학습 이상치 탐지. 고차원 데이터에서 잘 작동하나, 대규모 데이터셋으로의 확장은 어려움
* SGDOneClassSVM: 확률적 경사하강법을 사용해서 선형 모델 


---
[^1]: 서버 상에서의 사용자 로그 분석 방법으로, 사용자가 접속 후 어떠한 행동까지 이어졌는지 확인 및 측정을 목적으로 함.
[^2]: 서비스 재사용 여부를 측정하는 방법으로 필드에 따라 재구매가 될 수도, 재방문이 될 수도 있음
[^3]: Acquisition(유입 경로, 유입량 등), Action(방문 횟수, 이탈률 등), Retention(재사용율), Referral(추천, 공유 등), Revenue(ATV, IPT 등)을 통해 분석하는 방법 [ref](https://clevertap.com/blog/aarrr-metrics-vs-rarra-framework/ "AARRR vs. RARRA: Which is Better?")
[^4]: 동일한 기간의 동일한 경험을 공유한 사용자 집단 행동패턴 분석