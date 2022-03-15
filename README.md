# ml-studies

> ### Detection
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
