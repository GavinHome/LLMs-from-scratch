# 第 5 章：使用未标记的数据进行预训练

&nbsp;
## 主要章节代码

- [01_main-chapter-code](01_main-chapter-code/README.zh.md) 包含主要章节代码

&nbsp;
## 奖励材料

- [02_alternative_weight_loading](02_alternative_weight_loading/README.zh.md) 包含用于在 OpenAI 无法获取模型权重的情况下从其他位置加载 GPT 模型权重的代码
- [03_bonus_pretraining_on_gutenberg](03_bonus_pretraining_on_gutenberg/README.zh.md) 包含用于在 Project Gutenberg 的整个书籍语料库上对 LLM 进行更长时间预训练的代码
- [04_learning_rate_schedulers](04_learning_rate_schedulers/README.zh.md) 包含实现更复杂训练函数的代码，包括学习率调度程序和梯度裁剪
- [05_bonus_hparam_tuning](05_bonus_hparam_tuning/README.zh.md) 包含可选的超参数调整脚本
- [06_user_interface](06_user_interface/README.zh.md) 实现交互式用户界面以与预训练的 LLM 进行交互
- [07_gpt_to_llama](07_gpt_to_llama/README.zh.md) 包含将 GPT 架构实现转换为 Llama 3.2 的分步指南，并从 Meta AI 加载预训练权重
- [08_memory_efficient_weight_loading](08_memory_efficient_weight_loading/README.zh.md) 包含一个额外的笔记本，展示了如何更有效地通过 PyTorch 的 `load_state_dict` 方法加载模型权重