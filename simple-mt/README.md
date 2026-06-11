本项目基于双层 LSTM + 注意力机制实现中英机器翻译，复现经典 Seq2Seq 模型，完成数据处理、模型训练、效果评估与可视化，学习编码器 - 解码器架构的工作原理。
虚拟环境：nlp_wxf
Python 3.9
依赖：torch、numpy、jieba、nltk、matplotlib、seaborn、tqdm
使用自制中英短句平行语料，包含日常语句、否定句等。
划分：训练集 80%、验证集 10%、测试集 10%
预处理：中文 jieba 分词、英文分词，添加<sos>/<eos>/<pad>/<unk>标记
架构：双层 LSTM 编码器 + 注意力机制 + 双层 LSTM 解码器
训练策略：教师强制 + Dropout 正则（防止过拟合）
主要参数
词嵌入维度：128
隐藏层维度：256
批次大小：4
学习率：5e-4
训练轮数：15
测试集平均 BLEU 分数：0.1265
优势：对短句子、日常口语、简单否定句翻译效果较好，注意力机制可完成基础词对齐。
不足：受样本量和 LSTM 本身限制，长句容易丢词；无法理解成语、组合语义。
改进方向：扩充数据集、更换 Transformer 模型、使用预训练词向量。
激活环境：conda activate nlp_wxf
启动 Jupyter Notebook，打开 machine_translation.ipynb
按顺序逐单元格运行代码即可复现实验。