# MTL-FinBERT  
---


## 📌 项目简介

本项目是论文《MTL-FinBERT：数字金融生态系统中异构金融文本情感分析的多任务学习框架》的配套代码。  
旨在通过作者提出的多任务学习 的 FinBERT 架构，提升金融市场中跨模态、异质化文本情感分析的准确性和可扩展性。


---
## ✨ 技术介绍
![概念流程图](images/ch/概念流程图.pdf)
![技术流程图](images/ch/技术流程图.pdf)
---
## 🚀 快速开始

```bash
pip install -r requirements.txt
```

## 📂 项目结构

```
Multi-Task-Learning/
├── A_Emo_Measure/                 # 情绪测度模块
│   ├── bert-base-chinese/         # BERT中文预训练模型
│   ├── data/                      # 情绪模型训练数据与预测数据（后续均采用悲观估计结果）(Input)
│   ├── Deep-learning/                   # 深度学习模块
│   │    ├── Multi-Task-Model/          # 多任务学习模型 <----Ours
│   │    │    ├── A_Pre_Train/           # 预训练模块
│   │    │    ├── B_Fine_Tuning/         # 微调模块
│   │    │    ├── loss/                  # 损失记录(Output)
│   │    │    ├── model/                 # 权重保存(Output)
│   │    │    └── results/               # 结果输出(Output)
│   │    └── Simple-Task-Model/         # 单任务学习模型
│   ├── Emo-Dict/                        # 情绪词典模块
│   │    ├── Bian/                      # 上海财经大学卞世博等开发的中文财经领域情绪词典(卞等，2019)
│   │    ├── DLUT/                      # 大连理工大学情感词典(DLUT)
│   │    ├── Jiang/                     # 中央财经大学姜富伟等开发的中文金融文本情绪词典(姜富伟等，2021)
│   │    ├── EmoMeasure.py              # 词典法情绪测度主程序
│   │    ├── utils.py                   # 工具脚本
│   └── Machine-learning/                # 机器学习模块
│        ├── LR/                        # 逻辑回归
│        └── RF/                        # 随机森林
│
├── B_Result_Analysis/             # 结果分析模块
│   ├── evaluate_models_every_day.py  # 按每天综合情绪进行误差检验
│   ├── evaluate_models_every_texts.py # 按每条文本情绪进行误差检验
│   ├── evaluation/                # 评估指标存放(Output)
│   └── Measurement_Result/        # 三类模型的情绪测度结果(Input)
│
├── C_Empirical_Analysis/          # 实证分析模块
│   ├── data/                      # 实证所需数据(Input)
│   │    ├── Emo_data              # 文本情绪数据
│   │    ├── Financial_data        # 金融经济数据
│   ├── Data_Mine/                 # 数据挖掘——提取情绪结果的结构信息
│   └── Statistical_test/          # 统计检验——四类宏观经济变量统计检验
│
└── D_Investment_Portfolio/        # 投资组合模块
    ├── data/                      # 投资所需数据(Input)
    ├── Emotion_Extraction/        # 个股情绪测度——深度迁移学习
    └── Investment_portfolio/      # 个股实证分析与与投资组合策略
```
