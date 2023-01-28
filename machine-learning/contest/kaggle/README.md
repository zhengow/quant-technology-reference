# Kaggle

## Competitions
### 种类
- Featured
知名的商业项目（含奖金）
- Research
研究性质的项目，不会有一个寻常的解答。
- Getting Started
入门项目
- Playground
比入门级稍微难一些的项目
- Recruitment
招聘用项目
- Annual
周年项目，有两个组织，分别在-和-月定期举办
- Limited Participation
私有项目，例如用于考试

### 提交格式
- Simple(Classic) Competitions
用户自由下载数据，最后上传结果文件提交
- Two-stage Competitions
第一阶段提交模型，第二阶段用第一阶段的模型去预测测试集
- Code Competitions
提交结果为代码

### 奖励
- cash
- kudos 无实质奖励
- swag(Stuff We All Get) 周边


## Workflow
- Question or problem definition.
问题定义（输入、输出）
- Acquire training and testing data.
获取数据
- Analyze data definition and structure. Visualize, report data
分析数据定义和结构
- Wrangle, prepare, cleanse the data.
数据整理、准备、清洗
    - Converting: `category` 转为数字 (热编码)
    - Completing 填充缺失
      - 使用 `mean` 和 `variance` 生成随机变量
      - 使用相关特征生成
      - 结合上述方法
    - Correcting 校正异常数据
    - Creating 创造新特征
- Model, predict and solve the problem.
建模解决问题
- Supply or submit the results.
提交

## Model 模型

- #### Logistic regression

  - 用途：分类
  - 预测函数：
    - 输入：参数、特征
    - 输出：等于某类别的概率
  $$ P(Y=1) = \sigma(X) = \frac{1}{1+e^{-X\beta}}$$
  - 损失函数：
$$J(\beta) =-log\mathcal{L}(\beta)=- \sum_{i=1}^{n}\left[y_ilogP(y_i)+(1-y_i)log(1-P(y_i))\right]$$
其中$\mathcal{L}(\beta)$为极大似然估计MLE
    - 极大似然估计：
$$\mathcal{L}(\beta)=\prod_{i=1}^{n}f(y_{i},x_{i};\beta)=\prod_{i=1}^{n}\left(\frac{1}{1+e^{ -{x}_{i}{\beta} }}\right)^{y_{i}}\left(1-\frac{1}{1+e^{-{x}_{i}{\beta}}}\right)^{1-y_i}$$


## 其他

- ##### 极大似然估计MLE
  - 条件：已知一批样本点及其概率密度函数，但不知道函数参数
  - 目标：概率密度函数的参数
  - 方法：以联合概率密度最大来估计分布的参数
  - 表现形式：联合概率密度
  - 符号解释：
  $f\left(x_{i} ; \mu, \sigma^{2}\right)$ 中的分号 `;` **不是**表示条件概率
  - 举例：正态分布
  $$\mathcal{L}\left(\mu, \sigma^{2}\right)=\prod_{i=1}^{n} f\left(x_{i} ; \mu, \sigma^{2}\right)=\prod_{i=1}^{n} \frac{1}{\sqrt{2 \pi} \sigma} \exp \left(-\frac{\left(x_{i}-\mu\right)^{2}}{2 \sigma^{2}}\right)$$

- ##### 概率分布和概率密度
  - 概率密度：P(X $ = x_{k}$)
  - 概率分布：P(X $\leq x_{k}$)，实际表示累计概率
  