[英文](./README.en.md) | 中文

# 构建大型语言模型（从零开始）

此存储库包含用于开发、预训练和微调类似 GPT 的 LLM 的代码，是本书 [构建大型语言模型（从零开始）](https://amzn.to/4fqvn0D) 的官方代码存储库。

<br>
<br>

<a href="https://amzn.to/4fqvn0D"><img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/cover.jpg?123" width="250px"></a>

<br>

在 [*构建大型语言模型（从零开始）*](http://mng.bz/orYv) 中，您将通过从零开始逐步编码大型语言模型 (LLM)，从内到外学习和了解大型语言模型 (LLM) 的工作原理。在本书中，我将指导您创建自己的 LLM，并用清晰的文本、图表和示例解释每个阶段。

本书中描述的用于训练和开发您自己的小型但功能齐全的教育模型的方法反映了创建大型基础模型（例如 ChatGPT 背后的模型）所使用的方法。此外，本书还包括用于加载较大预训练模型的权重以进行微调的代码。

- 链接到官方[源代码存储库](https://github.com/rasbt/LLMs-from-scratch)
- [链接到 Manning（出版商网站）上的书籍](http://mng.bz/orYv)
- [链接到 Amazon.com 上的书籍页面](https://www.amazon.com/gp/product/1633437167)
- ISBN 9781633437166

<a href="http://mng.bz/orYv#reviews"><img src="https://sebastianraschka.com//images/LLMs-from-scratch-images/other/reviews.png" width="220px"></a>


<br>
<br>

要下载此存储库的副本，请单击[下载ZIP](https://github.com/rasbt/LLMs-from-scratch/archive/refs/heads/main.zip) 按钮或在终端中执行以下命令：

```bash
git clone --depth 1 https://github.com/rasbt/LLMs-from-scratch.git
```

<br>

（如果您从 Manning 网站下载了代码包，请考虑访问 GitHub 上的官方代码存储库 [https://github.com/rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) 以获取最新更新。）

<br>
<br>

# 目录

请注意，此 `README.md` 文件是 Markdown（`.md`）文件。如果您已从 Manning 网站下载此代码包并在本地计算机上查看它，我建议使用 Markdown 编辑器或预览器进行正确查看。如果您尚未安装 Markdown 编辑器，[MarkText](https://www.marktext.cc) 是一个不错的免费选择。

您也可以在浏览器中通过 [https://github.com/rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) 查看此文件和 GitHub 上的其他文件，浏览器会自动呈现 Markdown。

<br>
<br>
<!-- -->

> [!TIP]
> 如果您正在寻求有关安装 Python 和 Python 包以及设置代码环境的指导，我建议您阅读位于 [setup](setup) 目录中的 [README.zh.md](setup/README.zh.md) 文件。

<br>
<br>

[![代码测试 (Linux)](https://github.com/rasbt/LLMs-from-scratch/actions/workflows/basic-tests-linux.yml/badge.svg)](https://github.com/rasbt/LLMs-from-scratch/actions/workflows/basic-tests-linux.yml)
[![代码测试 (Windows)](https://github.com/rasbt/LLMs-from-scratch/actions/workflows/basic-tests-windows.yml/badge.svg)](https://github.com/rasbt/LLMs-from-scratch/actions/workflows/basic-tests-windows.yml)
[![代码测试(macOS)](https://github.com/rasbt/LLMs-from-scratch/actions/workflows/basic-tests-macos.yml/badge.svg)](https://github.com/rasbt/LLMs-from-scratch/actions/workflows/basic-tests-macos.yml)

<br>

| 章节标题 | 主代码（用于快速访问） | 所有代码 + 补充 |
|------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| [设置建议](./setup/README.zh.md) | - | - |
| 第 1 章：了解大型语言模型 | 无代码 | [./ch01](./ch01/README.zh.md)   |
| 第 2 章：处理文本数据 | - [ch02.ipynb](ch02/01_main-chapter-code/ch02.zh.ipynb)<br/>- [dataloader.ipynb](ch02/01_main-chapter-code/dataloader.ipynb) (摘要)<br/>- [exercise-solutions.ipynb](ch02/01_main-chapter-code/exercise-solutions.ipynb) | [./ch02](./ch02/README.zh.md) |
| 第 3 章：编写注意力机制 | - [ch03.ipynb](ch03/01_main-chapter-code/ch03.zh.ipynb)<br/>- [multihead-attention.ipynb](ch03/01_main-chapter-code/multihead-attention.ipynb) (摘要) <br/>- [exercise-solutions.ipynb](ch03/01_main-chapter-code/exercise-solutions.ipynb)| [./ch03](./ch03/README.zh.md) |
| 第 4 章：从零开始实现 GPT 模型 | - [ch04.ipynb](ch04/01_main-chapter-code/ch04.zh.ipynb)<br/>- [gpt.py](ch04/01_main-chapter-code/gpt.py) (摘要)<br/>- [exercise-solutions.ipynb](ch04/01_main-chapter-code/exercise-solutions.ipynb) | [./ch04](./ch04/README.zh.md) |
| 第 5 章：使用未标记的数据进行预训练 | - [ch05.ipynb](ch05/01_main-chapter-code/ch05.zh.ipynb)<br/>- [gpt_train.py](ch05/01_main-chapter-code/gpt_train.py) (摘要) <br/>- [gpt_generate.py](ch05/01_main-chapter-code/gpt_generate.py) (摘要) <br/>- [exercise-solutions.ipynb](ch05/01_main-chapter-code/exercise-solutions.ipynb) | [./ch05](./ch05/README.zh.md) |
| 第 6 章：文本分类的微调 | - [ch06.ipynb](ch06/01_main-chapter-code/ch06.zh.ipynb) <br/>- [gpt_class_finetune.py](ch06/01_main-chapter-code/gpt_class_finetune.py) <br/>- [exercise-solutions.ipynb](ch06/01_main-chapter-code/exercise-solutions.ipynb) | [./ch06](./ch06/README.zh.md) |
| 第 7 章：根据指令进行微调 | - [ch07.ipynb](ch07/01_main-chapter-code/ch07.zh.ipynb)<br/>- [gpt_instruction_finetuning.py](ch07/01_main-chapter-code/gpt_instruction_finetuning.py) (摘要)<br/>- [ollama_evaluate.py](ch07/01_main-chapter-code/ollama_evaluate.py) (摘要)<br/>- [exercise-solutions.ipynb](ch07/01_main-chapter-code/exercise-solutions.ipynb) | [./ch07](./ch07/README.zh.md) |
| 附录 A：PyTorch 简介 | - [code-part1.ipynb](./appendix-A/01_main-chapter-code/code-part1.ipynb)<br/>- [code-part2.ipynb](./appendix-A/01_main-chapter-code/code-part2.ipynb)<br/>- [DDP-script.py](./appendix-A/01_main-chapter-code/DDP-script.py)<br/>- [exercise-solutions.ipynb](./appendix-A/01_main-chapter-code/exercise-solutions.ipynb) | [./appendix-A](./appendix-A/README.zh.md) |
| 附录 B：参考资料和进一步阅读                 | 无代码                                                                                                                          | -                             |
| 附录 C：练习解决方案                             | 无代码                                                                                                                         | -                             |
| 附录 D：为训练过程添加额外的功能和特性 | - [appendix-D.ipynb](appendix-D/01_main-chapter-code/appendix-D.ipynb)                                                          | [./appendix-D](./appendix-D/README.zh.md) |
| 附录 E：使用 LoRA 进行参数高效微调       | - [appendix-E.ipynb](appendix-E/01_main-chapter-code/appendix-E.ipynb)                                                          | [./appendix-E](./appendix-E/README.zh.md) |

<br>
&nbsp;

下面的心智模型总结了本书涵盖的内容。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/mental-model.jpg" width="650px">

<br>
&nbsp;

## 硬件要求

本书主要章节中的代码旨在在合理的时间范围内在传统笔记本电脑上运行，并且不需要专门的硬件。这种方法可确保广大受众能够参与其中。此外，如果 GPU 可用，代码会自动利用它们。（请参阅 [setup](https://github.com/rasbt/LLMs-from-scratch/blob/main/setup/README.zh.md) 文档以获取更多建议。）

&nbsp;
## 奖励材料

几个文件夹包含可选材料，作为对感兴趣的读者的奖励：

- **设置**
  - [Python 设置提示](setup/01_optional-python-setup-preferences/README.zh.md)
  - [安装本书中使用的 Python 包和库](setup/02_installing-python-libraries/README.zh.md)
  - [Docker 环境设置指南](setup/03_optional-docker-environment/README.zh.md)
- **第 2 章：处理文本数据**
  - [比较各种字节对编码 (BPE) 实现](ch02/02_bonus_bytepair-encoder/README.zh.md)
  - [理解嵌入层和线性层之间的区别](ch02/03_bonus_embedding-vs-matmul/README.zh.md)
  - [使用简单数字的数据加载器直觉](ch02/04_bonus_dataloader-intuition/README.zh.md)
- **第3：编写注意力机制**
  - [比较有效的多头注意力实现](ch03/02_bonus_efficient-multihead-attention/mha-implementations.ipynb)
  - [理解 PyTorch 缓冲区](ch03/03_understanding-buffers/understanding-buffers.ipynb)
- **第 4 章：从零开始实现 GPT 模型**
  - [FLOPS 分析](ch04/02_performance-analysis/flops-analysis.ipynb)
- **第 5 章：使用未标记的数据进行预训练：**
  - [使用 Transformers 从 Hugging Face Model Hub 进行替代权重加载](ch05/02_alternative_weight_loading/weight-loading-hf-transformers.ipynb)
  - [在 Project Gutenberg 上对 GPT 进行预训练数据集](ch05/03_bonus_pretraining_on_gutenberg/README.zh.md)
  - [为训练循环添加额外功能](ch05/04_learning_rate_schedulers/README.zh.md)
  - [优化预训练的超参数](ch05/05_bonus_hparam_tuning/README.zh.md)
  - [构建用户界面与预训练的 LLM 交互](ch05/06_user_interface/README.zh.md)
  - [将 GPT 转换为 Llama](ch05/07_gpt_to_llama/README.zh.md)
  - [从零开始构建 Llama 3.2](ch05/07_gpt_to_llama/standalone-llama32.ipynb)
  - [内存高效的模型权重加载](ch05/08_memory_efficient_weight_loading/memory-efficient-state-dict.ipynb)
- **第 6 章：分类微调**
  - [对不同层进行微调并使用更大模型的其他实验](ch06/02_bonus_additional-experiments/README.zh.md)
  - [在 50k IMDB 电影评论数据集上对不同模型进行微调](ch06/03_bonus_imdb-classification/README.zh.md)
  - [构建用户界面进行交互使用基于 GPT 的垃圾邮件分类器](ch06/04_user_interface/README.zh.md)
- **第 7 章：根据指令进行微调**
  - [用于查找近似重复和创建被动语态条目的数据集实用程序](ch07/02_dataset-utilities/README.zh.md)
  - [使用 OpenAI API 和 Ollama 评估指令响应](ch07/03_model-evaluation/README.zh.md)
  - [生成用于指令微调的数据集](ch07/05_dataset-generation/llama3-ollama.ipynb)
  - [改进用于指令微调的数据集](ch07/05_dataset-generation/reflection-gpt4.ipynb)
  - [使用 Llama 3.1 70B 和Ollama](ch07/04_preference-tuning-with-dpo/create-preference-data-ollama.ipynb)
  - [LLM 对齐的直接偏好优化 (DPO)](ch07/04_preference-tuning-with-dpo/dpo-from-scratch.ipynb)
  - [构建用户界面以与指令微调 GPT 模型交互](ch07/06_user_interface/README.zh.md)

<br>
&nbsp;

## 问题、反馈和对此存储库的贡献

我欢迎各种反馈，最好通过 [Manning 论坛](https://livebook.manning.com/forum?product=raschka&page=1) 或 [GitHub 讨论](https://github.com/rasbt/LLMs-from-scratch/discussions) 分享。同样，如果您有任何疑问或只是想与他人交流想法，请随时在论坛中发布这些内容。

请注意，由于此存储库包含与印刷书籍相对应的代码，因此我目前无法接受扩展主要章节代码内容的贡献，因为这会引入与实体书的偏差。保持一致有助于确保每个人都能获得流畅的体验。

&nbsp;
## 引用

如果您发现本书或代码对您的研究有用，请考虑引用它。

芝加哥风格引用：

> Raschka, Sebastian. *Build A Large Language Model (From Scratch)*. Manning, 2024. ISBN: 978-1633437166.

BibTeX 条目:

```
@book{build-llms-from-scratch-book,
  author       = {Sebastian Raschka},
  title        = {Build A Large Language Model (From Scratch)},
  publisher    = {Manning},
  year         = {2024},
  isbn         = {978-1633437166},
  url          = {https://www.manning.com/books/build-a-large-language-model-from-scratch},
  github       = {https://github.com/rasbt/LLMs-from-scratch}
}
```
