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
>    - Handling Missing Values : Missing Values를 다른 값으로 대체하거나 제거.
>    - Data Types and Conversion : DM algorithm에 맞는 input type으로 변환.
>    - Transformation : 단위등이 다른 경우 표준화를 시켜 모든 특성을 (0,1) 범위에 위치시킨다.
>    - Feature Selection : 너무 많은 특성은 오히려 예측성능을 저하시키기도 하므로, 연관성 깊은 몇개의 특성만 고르는 작업.
>    - Data Sampling : 빠른 insight를 얻기위해 모집단에서 표본집단을 추리는 작업. 에러가 발생할 수도 있지만 빠른 예측모델을 세울 수 있는 이점이 있다.
> 3. Modeling
>    - 모델이란 데이터사이의 관계를 추상적으로 표현하는 것.
>    - 모델의 두 종류
>      - Predictive models for classification, regression tasks : 타겟 변수를 예측, 라벨된 트레이닝 셋이 필요.
>      - Descriptive (or explanatory) models for association analysis, clustering tasks : 예측을 위한 타겟변수가 필요없음.
> 4. Application or Deployment
> 5. Knowledge

> ## Data Exploration
>
> - Data Exploration 의 목적
>
>   - 데이터 구조 파악.
>   - 데이터 분포 파악.
>   - outlier 확인
>   - 데이터셋에서 연관성 파악
>
>   => 데이터에 올바른 종류의 추가 통계 및 데이터 마이닝 처리를 적용하기 위한 지침 제공.
>
> - Types of Data Attributes
>   - Nominal : distinctness
>   - Ordinal : distinctness, order
>   - Interval : distinctness, order, addition
>   - Ratio : distinctness, order, addition, Multiplication
> - Types of Data Exploration
>   - By descriptive statistics : 평균, 분포, correlation 등을 파악
>   - By visualization techniques : 다차원 공간에 데이터를 찍어봄으로써 시각적으로 파악.

> ## Classification
>
> -> 과거의 데이터를 사용해서 미래의 특정 값을 예측하는 것.이때 미래의 특정 값은 범위가 정해져 있다. 핵심 작업은 입력에 의한 출력을 정하는 모델을 세우는 것이다.
>
> - ### Classification Techniques
>
>   - Decision Tree Induction
>
>     - Hunt’s Algorithm : 동일한 class label을 갖도록 노드를 계속 나눈다.
>     - Design issues of Decision Tree
>       - Determine how to split the records at each iteration
>         - How to specify the test condition for attributes
>         - How to determine the best split
>       - Determine when to stop splitting
>     - How to determine the best split : Measures of Impurity
>
>       - GINI
>
>           <img src="https://latex.codecogs.com/svg.latex?\inline&space;1&space;-&space;\sum[p(j|t)]^2"/>
>
>       - GINI(split)
>
>           <img src="https://latex.codecogs.com/svg.latex?\inline&space;\sum\limits_{i=1}^k\frac{n_i}{n}GINI(i)" title="\sum\limits_{i=1}^k\frac{n_i}{n}GINI(i)" />
>
>       - Entropy(t)
>
>           <img src="https://latex.codecogs.com/svg.latex?\inline&space;-\sum\limits_jp(j|t)\log_{2}p(j|t)" title="-\sum\limits_jp(j|t)\log_{2}p(j|t)" />
>
>       - GAIN for the split
>
>            <img src="https://latex.codecogs.com/svg.latex?\inline&space;Entropy(before)&space;-&space;[\sum\limits_{i=1}^k\frac{n_i}{n}Entropy(i)](after)" title="Entropy(before) - [\sum\limits_{i=1}^k\frac{n_i}{n}Entropy(i)](after)" />
>
>         -> split 이후 얻는 GAIN은 최대한 많은 partition들을 가지면서 각 partition이 최대한 작을때 커진다. 그러나 partition이 작으면 합리적인 예측을 하는데 도움이 되지 않는다.
>
>       - GAIN Ratio : partition의 개수가 많아질수록 값이 적게 나온다.
>
>         <img src="https://latex.codecogs.com/svg.latex?\inline&space;GainRATIO_{split}&space;=&space;\frac{GAIN_{split}}{SplitINFO}" title="GainRATIO_{split} = \frac{GAIN_{split}}{SplitINFO}" />,
>
>           <img src="https://latex.codecogs.com/svg.latex?\inline&space;SplitINFO&space;=&space;-\sum\limits_{i=1}^k\frac{n_i}{n}log\frac{n_i}{n}" title="SplitINFO = -\sum\limits_{i=1}^k\frac{n_i}{n}log\frac{n_i}{n}" />
>
>       - Classification Error
>
>           <img src="https://latex.codecogs.com/svg.latex?\inline&space;Error(t)&space;=&space;1-&space;max_jp(j|t)" title="Error(t) = 1- max_jp(j|t)" />
>
>     - Determine when to stop splitting : training set에 맞출수록 test set에 대한 적중률이 떨어질 수 있다. Overfitting이라는 것이 존재하기 때문. Overfitting은 outliers에 의해 발생.
>       - Early stopping
>       - Post-pruning
>
>   - Rule-based Classifier : "if ... then"규칙을 써서 records을 분류하는 것.
>     - Quality Measures for Classification Rule
>       - Coverage of a rule : 룰이 다루는 레코드가 전체중에 몇개 인지 측정.
>       - Accuracy of a rule : 룰이 맞추는 정확도가 몇인지 측정.
>     - Properties of Rule-Based Classifier
>       - Mutually exclusive rule set : 모든 인스턴스들이 많아야 1개의 규칙에 의해 커버된다. 이 특성을 갖추기 위해 default rule을 추가한다.
>       - Exhaustive rule set : 모든 인스턴스들이 최소 1개의 규칙에 의해 커버된다. 이 특성을 갖추기 위해 규칙에 순서를 부여하거나 또는 투표를 한다.
>     - Sequential Covering Algorithm : 바로 데이터셋으로 부터 규칙을 추출하는 알고리즘.
>       1.  class 1개를 고른다.
>       2.  가장 많은 positive값과 가장 적은 negative 값을 커버하는 규칙을 고른다.
>       3.  2번의 규칙에 의해 커버되는 요소들을 제거한다.
>       4.  반복한다.
>     - Metrics for Rule Evaluation
>       - <img src="https://latex.codecogs.com/gif.latex?Accuracy&space;=&space;\frac{n_c}{n}" title="Accuracy = \frac{n_c}{n}" />
>       - <img src="https://latex.codecogs.com/gif.latex?Laplace&space;=&space;\frac{n_c&plus;1}{n&plus;k}" title="Laplace = \frac{n_c+1}{n+k}" />
>       - <img src="https://latex.codecogs.com/gif.latex?M-estimate&space;=&space;\frac{n_c&plus;kp}{n&plus;k}" title="M-estimate = \frac{n_c+kp}{n+k}" />
>       - <img src="https://latex.codecogs.com/gif.latex?FOIL's&space;information&space;gain&space;=&space;p_1*(log_2{\frac{p_1}{p_1&plus;n_1}}-log_2{\frac{p_0}{p_0&plus;n_0}})" title="FOIL's information gain = p_1*(log_2{\frac{p_1}{p_1+n_1}}-log_2{\frac{p_0}{p_0+n_0}})" />
>   - K-Nearest Neighbor Classifier : 가장 가까운 K개의 요소중 다수를 차지하는 것을 class label로 한다. 가까운 정도를 측정하는 여러 방법들이 존재한다.
>     - Distance Measures : 직선거리
>     - Correlation : Pearson
>     - Similarity Measures : simple matching coefficient, Jaccard Similarity, Cosine Similarity
>   - Bayesian Classifiers : 특성들 사이의 관계에서 입력이 같아도 결과가 다른 경우 (non-deterministic)가 존재한다. noisy data 또는 다른 factor의 존재 때문이다. 이를 해결하기 위한 방법으로 특성들과 class variable 사이의 확률을 제공한다.
>     - <img src="https://latex.codecogs.com/gif.latex?P(Y|X)=\frac{P(Y)*P(X|Y)}{P(X)}" title="P(Y|X)=\frac{P(Y)*P(X|Y)}{P(X)}" />
>     - 조건부 확률을 구할때, 각 사건이 독립적이라 가정하고 확률을 구한다.<img src="https://latex.codecogs.com/gif.latex?P(A_1,A_2,...,A_n|C)=\prod_{i=1}^{n}P(A_i|C)" title="P(A_1,A_2,...,A_n|C)=\prod_{i=1}^{n}P(A_i|C)" />
>     - 연속값을 가지는 특성에 대해서는 확률밀도함수를 사용한다.
>   - Artificial Neural Networks
>
>     - Perceptron : 입력에 대한 가중치를 정하는 모델. linearly separable problem만 해결가능
>
>       <a href="https://www.codecogs.com/eqnedit.php?latex=w_j^{(k&plus;1)}=w_j^{(k)}&plus;\lambda{(y_i-\hat{y}_i^{(k)})}x_{ij}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w_j^{(k&plus;1)}=w_j^{(k)}&plus;\lambda{(y_i-\hat{y}_i^{(k)})}x_{ij}" title="w_j^{(k+1)}=w_j^{(k)}+\lambda{(y_i-\hat{y}_i^{(k)})}x_{ij}" /></a>
>
>     - Multilayer Perceptron : not linearly separable problem을 해결하기 위해 hidden layers를 삽입.
>
>   - Ensemble Methods : 다수의 classifier들의 예측을 합쳐서 예측정확도를 높이는 기술. 이사회(classifiers)의 의사결정방식과 유사하다.
>     - 중요 조건 :
>       1. 각 classifier의 결과는 독립적이어야 한다.
>       2. 각 classifier의 error rate은 50% 미만이어야 한다.
>     - 각 classifier의 독립성을 이루는 방법
>       - Bagging : training set을 변화시켜 독립적인 classifier model을 만든다.
>         1. original data set의 사이즈만큼 data를 복원추출한다.
>         2. 복원추출된 데이터set들로 classifier model을 만든다.
>       - Boosting : 이전의 잘못 분류된 데이터에 집중하여 training examples의 분포를 변화시키는 절차.
>         1. 처음 N개의 examples에 동일한 weight를 할당한다.
>         2. training examples의 weight에 기반하여 boosting sample을 만든다.
>         3. boosting sample에 기반하여 classifier를 만들고 원래의 training data에 테스트한다.
>         4. 3번의 결과에 따라 weight를 업데이트한다.
>         5. 원하는 모델의 수를 만족시킬때 까지 반복한다.
>         6. 결과를 취합한다.
>       - Adaboost : base model의 성능에 따라 가중치를 부여하고, training record의 가중치를 변화시킨다.<br><a href="https://www.codecogs.com/eqnedit.php?latex=\epsilon&space;_i&space;=&space;\frac{1}{N}\sum_{j=1}^{N}\omega_j\delta(C_i(x_j)&space;\neq&space;y_j)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\epsilon&space;_i&space;=&space;\frac{1}{N}\sum_{j=1}^{N}\omega_j\delta(C_i(x_j)&space;\neq&space;y_j)" title="\epsilon _i = \frac{1}{N}\sum_{j=1}^{N}\omega_j\delta(C_i(x_j) \neq y_j)" /></a><br><a href="https://www.codecogs.com/eqnedit.php?latex=\alpha&space;_i=\frac{1}{2}ln(\frac{1-\epsilon&space;_i}{\epsilon&space;_i})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\alpha&space;_i=\frac{1}{2}ln(\frac{1-\epsilon&space;_i}{\epsilon&space;_i})" title="\alpha _i=\frac{1}{2}ln(\frac{1-\epsilon _i}{\epsilon _i})" /></a><br><a href="https://www.codecogs.com/eqnedit.php?latex=\omega&space;_i^{(j&plus;1)}=\frac{\omega&space;_i^{(j)}}{Z_j}\left\{\begin{matrix}&space;exp^{-\alpha&space;_j}\\&space;exp^{\alpha&space;_j}&space;\end{matrix}\right." target="_blank"><img src="https://latex.codecogs.com/gif.latex?\omega&space;_i^{(j&plus;1)}=\frac{\omega&space;_i^{(j)}}{Z_j}\left\{\begin{matrix}&space;exp^{-\alpha&space;_j}\\&space;exp^{\alpha&space;_j}&space;\end{matrix}\right." title="\omega _i^{(j+1)}=\frac{\omega _i^{(j)}}{Z_j}\left\{\begin{matrix} exp^{-\alpha _j}\\ exp^{\alpha _j} \end{matrix}\right." /></a>
>       - Random Forest : bagging과 같이 training record들을 복원추출하여 독립적인 decision tree들을 만든다. 이때, 각 node의 split을 정할때 training set의 특성들의 임의의 subset만 고려한다.
>   - Model Evaluation
>     - Metrics for Performance Evaluation
>     - Holdout Method : original data를 training data와 test data로 나누는 것.
>     - Random subsampling : Holdout Method를 여러번 반복하여 정확도의 평균을 내보는 것.
>     - K-fold cross validation : partition을 k개로 구성한다. 1개는 test용, k-1개는 training용으로 사용한다. k번 반복하여 모든 경우에 대해 평가한다.

> ## Clustering
>
> : 데이터셋에서 의미있는 그룹을 식별하는 과정
>
> - K-Means Clustering : 데이터셋을 k개의 cluster로 나누는 방법.
>
>   1. k개의 초기의 centroid를 임의로 정한다.
>   2. k개의 centroid에 가까운 점들을 cluster로 묶는다.
>   3. 각 cluster의 centroid를 계산한다.
>   4. centroid가 더이상 변하지 않을때까지 반복한다.
>
>   - Key Issue
>     1. Initiation : 초기의 centroid들에 따라 다른 cluster들이 만들어진다.
>     2. Empty Clusters : cluster가 할당되지 않는 point들이 생길 수 있다.
>     3. Outliers : SSE가 centroid를 정하는데 사용되므로, outlier들에 취약하다.
>     4. Post Processing : 초기의 centroid에 영향을 많이 받으므로, Post Processing으로 더 나은 solution을 찾는데 도움이 될 수 있다.
>   - Limitations
>     1. Differing sizes of clusters
>     2. Differing densities of clusters
>     3. Finding non-globular shapes of clusters
