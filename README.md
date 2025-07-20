# Aviation-Customer-churn
# 航空客户信息挖掘 / Airline Customer Information Mining

## 🧪 实验目标 / Experiment Objectives
本次实验基于航空公司提供的数据，分析用户行为背后的规律，构建预测模型以实现客户流失预警、客户分类与客户价值评估，提升服务效率与客户留存率。

This experiment uses data provided by an airline company to analyze patterns in customer behavior. The goal is to build predictive models to enable churn prediction, customer segmentation, and customer value evaluation, thereby improving service efficiency and customer retention.

---

## 🔍 分析方法与过程 / Analysis Methods and Process

### 📊 总体流程 / Overall Workflow
1. 数据读取 / Data Reading  
2. 数据清洗与预处理 / Data Cleaning & Preprocessing  
3. 构造客户流失标签 / Label Construction (Churn)  
4. 特征提取与标准化 / Feature Extraction & Normalization  
5. 客户流失预测 / Churn Prediction  
6. 客户分类 / Customer Segmentation  
7. 客户价值评估 / Customer Value Evaluation  

---

## 🧭 具体步骤 / Detailed Steps

**步骤 1：数据读取 / Step 1: Load Data**  
航空公司提供两年（8季度）的客户行为数据，共计 62,988 个样本，63 个特征。

**步骤 2：数据预处理 / Step 2: Data Preprocessing**  
- 删除缺失值过多的列  
- 用中位数填补缺失  
- 统一字段命名  

**步骤 3：构造流失标签 / Step 3: Churn Labeling**  
采用逻辑规则构造标签：
- 若最后一次乘机距观察期末时间 > 3×平均间隔 或 > 最大间隔，则认定为流失客户  
- 结果输出为二分类标签（流失/未流失）

**步骤 4：特征提取与标准化 / Step 4: Feature Selection & Scaling**  
- 筛选关键词相关特征（如 FLIGHT、POINT、EXPENSE 等）  
- 对数值特征进行标准化处理  

**步骤 5：客户流失预测 / Step 5: Churn Prediction**  
- 使用 XGBoost 模型进行二分类预测  
- 输出混淆矩阵与分类报告，Precision 和 Recall 均超过 95%

**步骤 6：客户分类 / Step 6: Clustering**  
- 使用 K-Means 聚类将客户划分为 5 个簇  
- 各簇分布紧密，说明客户群体差异小，聚类以消费频率和金额为主

**步骤 7：客户价值评估 / Step 7: Customer Value (RFM)**  
- 构建 RFM 模型（Recency, Frequency, Monetary）  
- 结合是否流失进行打分，为精准营销提供依据

---

## 📈 实验结果分析 / Results Analysis

1. **客户流失预测**  
XGBoost 模型表现优异，Precision 和 Recall 均超 95%，可以有效识别流失客户。

2. **客户分类分析**  
K-Means 聚类结果清晰，客户可按行为特征划分为不同层级。

3. **RFM 客户价值评估**  
结合消费金额、频率与时间构建的 RFM 模型可有效划分客户等级。

---

## ✅ 结论 / Conclusion
本次实验构建了以客户行为为核心的建模流程，实现了客户流失预测、客户聚类与客户价值评分。对航空公司客户管理和营销策略提供了量化支持。但模型在聚类方面仍可优化，如考虑更多变量组合提升分类精度。

---

## 📚 参考文献 / References
1. Chen et al. *Predicting Customer Churn in the Airline Industry Using Ensemble Learning*. J. Air Transport Management, 2023.  
2. Kim et al. *Enhancing RFM Model with Machine Learning*. Expert Systems with Applications, 2022.  
3. Gupta et al. *Interpretable Machine Learning for Customer Churn*. ACM SIGKDD, 2023.  
4. Müller & Schmidt. *An Integrated CLV-RFM Model for Airline Customer Segmentation*, 2021.

---

## 🗂️ 项目结构建议 / Suggested Project Structure

