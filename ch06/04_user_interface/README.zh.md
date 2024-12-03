# 构建用户界面以与基于 GPT 的垃圾邮件分类器交互

此奖励文件夹包含用于运行类似 ChatGPT 的用户界面的代码，以便与第 6 章中经过微调的基于 GPT 的垃圾邮件分类器交互，如下所示。

![Chainlit UI 示例](https://sebastianraschka.com/images/LLMs-from-scratch-images/bonus/chainlit/chainlit-spam.webp)

为了实现此用户界面，我们使用开源 [Chainlit Python 包](https://github.com/Chainlit/chainlit)。

&nbsp;
## 步骤 1：安装依赖项

首先，我们通过

```bash
pip install chainlit
```

安装 `chainlit` 包（或者，执行 `pip install -r requirements-extra.txt`。）

&nbsp;
## 第 2 步：运行 `app` 代码

[`app.py`](app.py) 文件包含基于 UI 的代码。打开并检查这些文件以了解更多信息。

此文件加载并使用我们在第 6 章中生成的 GPT-2 分类器权重。这要求您首先执行 [`../01_main-chapter-code/ch06.ipynb`](../01_main-chapter-code/ch06.ipynb) 文件。

从终端执行以下命令以启动 UI 服务器：

```bash
chainlit run app.py
```

运行上述命令应该会打开一个新的浏览器选项卡，您可以在其中与模型交互。如果浏览器选项卡没有自动打开，请检查终端命令并将本地地址复制到浏览器地址栏中（通常，地址为 `http://localhost:8000`）。