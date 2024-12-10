# 其他分类微调实验

下表添加了实验以回答有关各种设计选择的其他问题。第一行使用与主要章节相同的设置，并用作参考。
例如，

- 比较第 1 行和第 2 行回答了以下问题：“当我们训练最后一个或第一个 token 时，性能有什么不同？”；
- 比较第 1 行和第 3 行回答了以下问题：“当我们只训练最后一层而不是最后一个块时，性能有什么不同？”；
- 等等。

&nbsp;

| | 模型 | 权重 | 可训练 token 位置 | 可训练层 | 上下文长度 | 训练 acc | 验证 acc | 测试 acc | 训练时间 | CPU/GPU |
| ---- | ------------------ | ---------- | ------------------------ | ---------------- | ------------------------------------------------------ | ------------ | -------------- | -------- | ------------- | ------- |
| 1 | gpt2-small (124M) | 预训练 | last | last_block | longest train ex. （120）| 96.63% | 99.33% | 95.00% | 0.28 分钟 | A100 |
| 2 | gpt2-small（124M）| 预训练 | first | last_block | 最长的训练示例。（120）| 78.46% | 80.54% | 75.00% | 0.28 分钟 | A100 |
| 3 | gpt2-small（124M）| 预训练 | last | last_layer | 最长的训练示例。（120）| 78.65% | 79.87% | 72.00% | 0.25 分钟 | A100 |
| 4 | gpt2-small（124M）| 预训练 | last | last_two_blocks | 最长的训练示例。（120）| 98.85% | 98.66% 98.33% | 0.33 分钟 | A100 |
| 5 | gpt2-small (124M) | 预训练 | last | 全部 | 最长训练示例 (120) | 99.62% | 96.64% | 96.67% | 0.69 分钟 | A100 |
| 6 | gpt2-medium (355M) | 预训练 | last | last_block | 最长训练示例 (120) | 87.50% | 91.28% | 84.67% | 0.75 分钟 | A100 |
| 7 | gpt2-large (774M) | 预训练 | last | last_block | 最长训练示例 (120) | 99.52% | 98.66% | 96.67% | 1.50 分钟 | A100 |
| 8 | gpt2-xl (1558M) | 预训练 | last | last_block | 最长的训练示例 (120) | 99.81% | 99.81% | 98.33% | 2.83 分钟 | A100 |
| 9 | gpt2-xl (1558M) | 预训练 | last | 全部 | 最长的训练示例 (120) | 100.00% | 98.66% | 98.67% | 8.12 分钟 | A100 |
| 10 | gpt2-small (124M) | 随机 | last | 全部 | 最长的训练示例 (120) | 100.00% | 96.64% | 93.67% | 0.69 分钟 | A100 |
| 11 | gpt2-small (124M) | 预训练 | last | LoRA | 最长的训练示例（120）| 100.00% | 97.32% | 96.67% | 0.75 分钟 | A100 |
| 12 | gpt2-xl（1558M）| 预训练 | last | LoRA | 最长训练示例。（120）| 100.00% | 98.66% | 98.33% | 5.79 分钟 | A100 |
| 13 | gpt2-small（124M）| 预训练 | last | last_block | 上下文长度（1024）| 83.08% | 87.92% | 78.33% | 2.46 分钟 | A100 |
| 14 | gpt2-small（124M）| 预训练 | last | last_block | 变量：无填充（批量大小 1）| 100.00% | 98.66% | 98.00% | 1.75 分钟 | A100 |
| 15 | gpt2-small (124M) | 预训练 | last | last_block | 变量：无填充（批量大小 8）| 99.33% | 98.66% | 98.33% | 1.70 分钟 | A100 |
| 16 | gpt2-small (124M) | 预训练 | last | last_block | 灵活（最后一个非填充位置）| 99.42% | 98.66% | 98.33% | 0.30 分钟 | A100 |
| 17 | gpt2-small (124M) | 预训练 | last | last_block | 最长的训练示例（120）；但没有因果掩码 | 99.23% | 98.66% | 95.33% | 0.29 分钟 | A100 |
| 18 | gpt2-small (124M) | 预训练 | last | last_block | 最长的训练示例。 (120) 和 `ignore_index` 用于填充 | 96.63% | 99.33% | 95.00% | 0.28 分钟 | A100 |
| 19 | gpt2-small (124M) | 预训练 | last + 池化嵌入 | last_block | 最长的训练示例。 (120) | 97.79% |99.33% | 96.33% | 0.32 分钟 | A100 |

&nbsp;

### 用法

您可以使用以下代码重现实验：

- 第 1 行：`python additional_experiments.py`
- 第 2 行：`python additional_experiments.py --trainable_token_pos first`
- 第 3 行：`python additional_experiments.py --trainable_layers last_layer`
- 第 4 行：`python additional_experiments.py --trainable_layers last_two_blocks`
- 第 5 行：`python additional_experiments.py --trainable_layers all`
- 第 6 行：`python additional_experiments.py --model_size "gpt2-medium (355M)"`
- 第 7 行：`python additional_experiments.py --model_size "gpt2-large (774M)"`
- 第 8 行：`python additional_experiments.py --model_size "gpt2-xl (1558M)"`
- 第 9 行：`python additional_experiments.py --model_size "gpt2-xl (1558M)"--trainable_layers all`
- 第 10 行：`python additional_experiments.py --weights random --trainable_layers all`
- 第 11 行：`python additional_experiments.py --trainable_layers lora --lora_rank 16 --lora_alpha 16`
- 第 12 行：`python additional_experiments.py --trainable_layers lora --lora_rank 16 --lora_alpha 8 --model_size "gpt2-xl (1558M)"`
- 第 13 行：`python additional_experiments.py --context_length "model_context_length"`
- 第 14 行：`python additional_experiments.py --no_padding --batch_size 1`
- 第 15 行：`python additional_experiments.py --no_padding --batch_size 1 --accumulation_steps 8`
- 第 16 行：`python additional_experiments.py --last_token_pos "flexible"`
- 第 17 行：`python additional_experiments.py --disable_causal_mask`
- 第 18 行：`python additional_experiments.py --ignore_index 50256`
- 第 19 行：`python additional_experiments.py --average embeddings`

我故意将 LLM 和数据集保持在较小规模，这样如果您无法使用 GPU，您可以在 MacBook Air M3 等普通笔记本电脑上大约 15 分钟（默认设置）运行训练。

&nbsp;

### 解释

1. **训练最后一个与第一个输出标记位置（第 1 行与第 2 行）**：训练最后一个输出标记位置与第一个相比，性能明显更好。由于因果自注意力掩码，这种改进是可以预期的。
2. **训练最后一个 Transformer 块与最后一层（第 1 行与第 3 行）**：训练整个最后一个 Transformer 块也比仅训练最后一层产生更好的结果。
3. **训练最后一个 Transformer 块与最后两个 Transformer 块（第 1 行与第 4 行）**：训练最后两个 Transformer 块而不是仅训练最后一个 Transformer 块可使准确率明显提高 3.33%。
4. **训练最后一个 Transformer 块与所有层（第 1 行与第 5 行）**：训练所有层比仅训练最后一个 Transformer 块显示出约 2% 的适度改进，但训练时间几乎是后者的三倍。此外，它的表现不如仅训练 12 个 Transformer 块中的最后两个。
5. **使用更大的预训练模型（第 1 行与第 6 行，以及第 1 行与第 7 行和第 8 行）**：使用 3 倍大的预训练模型会导致更糟糕的结果。但是，与预期相比，使用 5 倍大的模型可以提高与初始模型相比的性能。同样，12 倍大的模型可以进一步提高预测性能。（中等模型可能未经过很好的预训练，或者特定的微调配置对该模型不太适用。）
6. **使用具有随机权重的模型与预训练权重的模型（第 1 行和第 5 行与第 10 行）**：与使用预训练权重相比，使用具有随机权重的模型产生的结果仅略差（分别差 3% 和 1.3%）。
7. **使用 LoRA（低秩自适应）与训练所有层（第 11 行与第 5 行，第 12 行与第 9 行）**：保持模型冻结并添加可训练的 LoRA 层（有关详细信息，请参阅 [附录 E](../../appendix-E/01_main-chapter-code/appendix-E.zh.ipynb)）是训练所有模型参数的可行替代方案，甚至可以将性能提高 1%（第 11 行与第 5 行）。从使用 LoRA 时训练和验证准确率之间的差距缩小约 1% 可以看出，这可能是由于过度拟合较少。此外，使用 LoRA 也更节省内存，因为需要更新的参数更少。在训练较大的模型（第 12 行与第 9 行）时，我们还可以看到 LoRA 训练速度要快得多（5.79 分钟而不是 8.12 分钟）。
8. **将输入填充到完整上下文长度与最长训练示例（第 1 行与第 13 行）**：将输入填充到完整支持的上下文长度结果明显更差。
9. **填充与无填充（第 1 行与第 14 行、第 15 行和第 16 行）**：`--no_padding` 选项禁用数据集中的填充，这需要使用 1 的批大小训练模型，因为输入的长度可变。这可以提高测试准确率，但需要更长的时间来训练。在第 15 行中，我们另外启用了 8 步梯度累积，以实现与其他实验相同的批大小，这有助于减少过度拟合并略微提高测试集准确率。在第 16 行中，我们应用填充，但根据最后一个非填充 t 选择标记位置oken。第 16 行在数学上应该与使用梯度累积的第 15 行相似。但是，由于在 token 计数不相等的情况下梯度累积存在一些挑战，因此可能会存在微小差异（这在 [这篇](https://unsloth.ai/blog/gradient) 博客文章中进行了讨论）。
10. **禁用因果注意掩码（第 1 行与第 17 行）**：禁用多头注意模块中使用的因果注意掩码。这意味着所有 token 都可以关注所有其他 token。与使用因果掩码的 GPT 模型相比，模型准确率略有提高。
11. **忽略损失和反向传播中的填充索引（第 1 行与第 18 行）**：设置 `--ignore_index 50256` 会排除 PyTorch 中 `cross_entropy` 损失函数中的 `|endoftext|` 填充 token。在这种情况下，它没有任何效果，因为我们替换了输出层，以便二进制分类示例的标记 ID 为 0 或 1。但是，此设置在第 7 章中指导微调模型时很有用。
13. **对所有标记的嵌入取平均值（第 1 行与第 19 行）**：设置 `--average_embeddings` 将对所有标记的嵌入取平均值。如果不使用此选项（默认），则仅考虑所选标记位置（由 `--trainable_token_pos` 指定）的输出嵌入；例如，最后一个标记的嵌入。启用 `--average_embeddings` 将把所有标记的嵌入均值池化到 `--trainable_token_pos` 选择的位置（默认为最后一个标记）。我们可以看到，这将性能从 95.00％ 提高到 96.33％，而运行时间仅略有增加（0.28 分钟到 0.32 分钟），在实践中值得考虑。