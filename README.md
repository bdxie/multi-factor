alpha, 多因子选股
================

从数据库提取数据构建因子，测试因子的有效性，包括因子收益率、因子收益率T值、IC值，分层测试以观察因子收益率的按照因子大小排序分组的不同组合的组合收益率、波动率、收益率的单调性、最大回测、夏普比率、信息比率等。

## self_libs, 自定义的一些模块

  **1. data_clean.py, 数据清洗**  
  * 剔除存在ST标记的数据和上市不满一年的股票
  * MAD法去除异常值，Z-值标准化，然后对行业哑变量和对数值回归取残差，得到行业与市值中性化的因子值
  
  **2. factor_test.py, 单因子有效性的评价指标** 
  * 因子收益率（均值、标准差)  
  $$R_{it} = \beta_{0t} + \beta_{1t} * f_{it}$$
  * 因子收益率的T值（均值、标准差、大于0的概率、大于2的概率）
  * 因子收益率序列的T检验
  * IC值（均值、标准差、大于0的概率、大于0.02的概率、IC的IR）
  
  **3. class_test.py, 大类因子之间有效的比较**   
  * 因子累计收益率
  * 组合年化收益率单调性
  * 组合的夏普比率、信息比率
  * IC值相关性  
  
## factor_code, 因子的构建和测试  

 * 估值类因子（7个）
 * 动量类因子（6个）
 * 波动率类因子（10个）
 * 一致预期类因（18个）
