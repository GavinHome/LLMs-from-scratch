# 对 50k IMDB 电影评论的情绪进行分类的附加实验

&nbsp;
## 步骤 1：安装依赖项

通过以下方式安装额外的依赖项

```bash
pip install -r requirements-extra.txt
```

&nbsp;
## 步骤 2：下载数据集

代码使用来自 IMDb 的 50k 电影评论（[数据集来源](https://ai.stanford.edu/~amaas/data/sentiment/)) 来预测电影评论是正面的还是负面的。

运行以下代码以创建 `train.csv`、`validation.csv` 和 `test.csv` 数据集：

```bash
python download_prepare_dataset.py
```

&nbsp;
## 步骤 3：运行模型

主要章节中使用的 124M GPT-2 模型，从预训练权重开始，并对所有权重进行微调：

```bash
python train_gpt.py --trainable_layers "all" --num_epochs 1
```

```
Ep 1 (Step 000000): Train loss 3.706, Val loss 3.853
Ep 1 (Step 000050): Train loss 0.682, Val loss 0.706
...
Ep 1 (Step 004300): Train loss 0.199, Val loss 0.285
Ep 1 (Step 004350): Train loss 0.188, Val loss 0.208
Training accuracy: 95.62% | Validation accuracy: 95.00%
Training completed in 9.48 minutes.

Evaluating on the full datasets ...

Training accuracy: 95.64%
Validation accuracy: 92.32%
Test accuracy: 91.88%
```

<br>

---

<br>

340M 参数编码器样式 [BERT](https://arxiv.org/abs/1810.04805) 模型：

```bash
python train_bert_hf.py --trainable_layers "all" --num_epochs 1 --model "bert"
```

```
Ep 1 (Step 000000): Train loss 0.848, Val loss 0.775
Ep 1 (Step 000050): Train loss 0.655, Val loss 0.682
...
Ep 1 (Step 004300): Train loss 0.146, Val loss 0.318
Ep 1 (Step 004350): Train loss 0.204, Val loss 0.217
Training accuracy: 92.50% | Validation accuracy: 88.75%
Training completed in 7.65 minutes.

Evaluating on the full datasets ...

Training accuracy: 94.35%
Validation accuracy: 90.74%
Test accuracy: 90.89%
```

<br>

---

<br>

66M 参数编码器样式 [DistilBERT](https://arxiv.org/abs/1910.01108) 模型（从 340M 参数 BERT 模型中提炼而来），从预训练权重开始，仅训练最后一个转换器块和输出层：

```bash
python train_bert_hf.py --trainable_layers "all" --num_epochs 1 --model "distilbert"
```

```
Ep 1 (Step 000000): Train loss 0.693, Val loss 0.688
Ep 1 (Step 000050): Train loss 0.452, Val loss 0.460
...
Ep 1 (Step 004300): Train loss 0.179, Val loss 0.272
Ep 1 (Step 004350): Train loss 0.199, Val loss 0.182
Training accuracy: 95.62% | Validation accuracy: 91.25%
Training completed in 4.26 minutes.

Evaluating on the full datasets ...

Training accuracy: 95.30%
Validation accuracy: 91.12%
Test accuracy: 91.40%
```
<br>

---

<br>

355M 参数编码器样式 [RoBERTa](https://arxiv.org/abs/1907.11692) 模型，从预训练权重开始，仅训练最后一个转换器块和输出层：

```bash
python train_bert_hf.py --trainable_layers "last_block" --num_epochs 1 --model "roberta"
```

```
Ep 1 (Step 000000): Train loss 0.695, Val loss 0.698
Ep 1 (Step 000050): Train loss 0.670, Val loss 0.690
...
Ep 1 (Step 004300): Train loss 0.126, Val loss 0.149
Ep 1 (Step 004350): Train loss 0.211, Val loss 0.138
Training accuracy: 92.50% | Validation accuracy: 94.38%
Training completed in 7.20 minutes.

Evaluating on the full datasets ...

Training accuracy: 93.44%
Validation accuracy: 93.02%
Test accuracy: 92.95%
```

<br>

---

<br>

scikit-learn 逻辑回归分类器作为基线：

```bash
python train_sklearn_logreg.py
```

```
Dummy classifier:
Training Accuracy: 50.01%
Validation Accuracy: 50.14%
Test Accuracy: 49.91%


Logistic regression classifier:
Training Accuracy: 99.80%
Validation Accuracy: 88.62%
Test Accuracy: 88.85%
```