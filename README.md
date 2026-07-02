# 英国线上零售商客户与销售分析
# UK Online Retail — Customer & Sales Analysis

一个端到端的数据分析项目：从原始交易数据出发，完成清洗、SQL 分析、客户分群（RFM）、可视化，最终产出一份面向管理层的分析报告。

An end-to-end data analysis project: from raw transaction data to data cleaning, SQL analysis, customer segmentation (RFM), visualization, and a management-facing report.

## 项目背景 | Background

本项目基于一家英国线上零售商 2010–2011 年的真实交易数据，尝试回答三个业务问题：

- 收入结构是否健康？是否集中于少数客户？
- 哪些客户最值得投入资源维护？
- 基于以上，运营资源应该如何优先分配？

This project uses real transaction data from a UK-based online retailer (2010–2011) to answer three business questions: Is the revenue structure healthy? Which customers are worth prioritizing? How should resources be allocated based on the data?

## 数据 | Data

- 来源 | Source: [Online Retail Dataset — Kaggle](https://www.kaggle.com/datasets) / UCI Machine Learning Repository
- 原始规模 | Raw size: ~541,909 条交易记录 | rows
- 字段 | Fields: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country

> 数据文件未包含在本仓库中，请自行从上述来源下载。
> The raw data file is not included in this repo — please download it from the source above.

## 分析流程 | Workflow

1. **数据清洗 | Data Cleaning**（Pandas）— 剔除退货订单、异常价格、缺失客户 ID，新增 Revenue 字段
2. **SQL 分析 | SQL Analysis**（SQLite）— 按国家/客户/产品的收入排名，验证收入集中度
3. **客户分群 | Customer Segmentation**（RFM 模型）— 按 Recency / Frequency / Monetary 将客户分为四类
4. **可视化 | Visualization**（Matplotlib）— 收入分布、客户价值对比、月度销售趋势
5. **报告 | Report** — 面向管理层的分析结论与业务建议

## 关键发现 | Key Findings

- 前 20% 的客户贡献了 **74.6%** 的总收入；RFM 模型交叉验证后，核心客户群体（21.5%）贡献 **70.2%** 的收入
- 核心客户人均消费是低价值客户的 **24 倍**
- 存在一批历史高消费、但已长期未购买的客户，具备较高的挽回价值
- 销售存在明显季节性，**9–11 月**为全年高峰

完整分析过程与业务建议见 [`retail_analysis.ipynb`](./retail_analysis.ipynb) 及分析报告。

## 技术栈 | Tech Stack

Python · Pandas · SQLite · Matplotlib

## 使用方法 | How to Run

```bash
pip install pandas matplotlib jupyter
jupyter notebook retail_analysis.ipynb
```

## 作者 | Author

[你的名字 / Your Name] — [LinkedIn / 邮箱，可选]
