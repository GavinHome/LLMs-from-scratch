# 第 5 章：对未标记数据进行预训练

### 主要章节代码

- [ch05.ipynb](ch05.ipynb) 包含本章中出现的所有代码
- [previous_chapters.py](previous_chapters.py) 是一个 Python 模块，其中包含前几章中的 `MultiHeadAttention` 模块和 `GPTModel` 类，我们在 [ch05.ipynb](ch05.ipynb) 中导入它们以预训练 GPT 模型
- [gpt_download.py](gpt_download.py) 包含用于下载预训练 GPT 模型权重的实用函数
- [exercise-solutions.ipynb](exercise-solutions.ipynb) 包含本章的练习解决方案

### 可选代码

- [gpt_train.py](gpt_train.py) 是一个独立的 Python 脚本文件，其中包含我们在[ch05.ipynb](ch05.ipynb) 用于训练 GPT 模型（你可以将其视为总结本章的代码文件）
- [gpt_generate.py](gpt_generate.py) 是一个独立的 Python 脚本文件，其中包含我们在 [ch05.ipynb](ch05.ipynb) 中实现的代码，用于加载和使用来自 OpenAI 的预训练模型权重