# DataMining

> ## Category of Data Mining Tasks
>
> - Predictive tasks : 다른 특성값들을 기반으로 특정한 특성의 미래값 또는 알려지지 않은 값을 예측하는 것. 관찰된 데이터에 적합한 대표모델을 세우는 것.
> - Descriptive tasks : 데이터의 행간을 요약하는 인간이 이해가능한 패턴을 찾는 것. 관찰된 데이터를 요약하는 과정.

> ## Learning Models for DM Tasks
>
> - Supervised learning : 라벨된 훈련데이터에 기반한 관계 또는 함수를 추론하는 것. 입력변수에 기반하여 출력값을 예측하는 것.  
>   ex) Classification,regression
> - Unsupervised learning : 라벨되지 않은 데이터에서 숨겨진 패턴을 찾는 것. 예측하기 위한 출력값이 없다. 인스턴스 사이에 관계에 기인하여 패턴을 찾는다.  
>   ex) Clustering,association analysis...

> ## Data Mining Tasks
>
> - Classification : 개체를 미리 정의된 여러 범주중 하나에 할당하는 작업.
> - Clustering : object를 비슷한 의미로 묶는 작업.
> - Association Analysis : 데이터들 사이에 관계를 분석.
> - Regression : 연속적인 값을 가지는 타겟을 예측하는 기법.
> - Anomaly Detection : 나머지 개체들과는 다른 개체를 찾는 것.
> - Time Series Forecasting
> - Text Mining

> ## Data Mining Process
>
> 1. Understanding Business/Data
> 2. Data Preparation       
>    - Data Exploration
>    - Handling Data Quality : 중복데이터 제거, outlier 제외, 특성값 표준화등 데이터를 정제하는 작업.
>    - Handling Missing Values :  Missing Values를 다른 값으로 대체하거나 제거.
>    - Data Types and Conversion : DM algorithm에 맞는 input type으로 변환.
>    - Transformation : 단위등이 다른 경우 표준화를 시켜 모든 특성을 (0,1) 범위에 위치시킨다.
>    - Feature Selection : 너무 많은 특성은 오히려 예측성능을 저하시키기도 하므로, 연관성 깊은 몇개의 특성만 고르는 작업.  
>    - Data Sampling : 빠른 insight를 얻기위해 모집단에서 표본집단을 추리는 작업. 에러가 발생할 수도 있지만 빠른 예측모델을 세울 수 있는 이점이 있다. 
> 3. Modeling
>    - 모델이란 데이터사이의 관계를 추상적으로 표현하는 것.
>    - 모델의 두 종류
>       - Predictive models for classification, regression tasks : 타겟 변수를 예측, 라벨된 트레이닝 셋이 필요.
>       - Descriptive (or explanatory) models for association analysis, clustering tasks : 예측을 위한 타겟변수가 필요없음.
> 4. Application or Deployment
> 5. Knowledge

> ## Data Exploration 
>  - Data Exploration 의 목적
>     - 데이터 구조 파악.
>     - 데이터 분포 파악.
>     - outlier 확인
>     - 데이터셋에서 연관성 파악
> 
>    => 데이터에 올바른 종류의 추가 통계 및 데이터 마이닝 처리를 적용하기 위한 지침 제공.
>  - Types of Data Attributes
>     - Nominal : distinctness
>     - Ordinal : distinctness, order
>     - Interval : distinctness, order, addition
>     - Ratio : distinctness, order, addition, Multiplication
>  - Types of Data Exploration
>     - By descriptive statistics : 평균, 분포, correlation 등을 파악
>     - By visualization techniques : 다차원 공간에 데이터를 찍어봄으로써 시각적으로 파악.

