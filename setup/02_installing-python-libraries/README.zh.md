# 安装本书中使用的 Python 包和库

本文档提供了有关仔细检查已安装的 Python 版本和包的更多信息。（有关安装 Python 和 Python 包的更多信息，请参阅 [../01_optional-python-setup-preferences](../01_optional-python-setup-preferences/README.zh.md) 文件夹。）

我为本书使用了 [此处](https://github.com/rasbt/LLMs-from-scratch/blob/main/requirements.txt) 列出的以下库。这些库的较新版本也可能兼容。但是，如果您遇到任何代码问题，您可以尝试使用这些库版本作为后备。

为了最方便地安装这些要求，您可以使用此代码存储库根目录中的“requirements.txt”文件并执行以下命令：

```bash
pip install -r requirements.txt
```

或者，您可以通过 GitHub URL 安装它，如下所示：

```bash
pip install -r https://raw.githubusercontent.com/rasbt/LLMs-from-scratch/main/requirements.txt
```

然后，完成安装后，请使用以下方法检查所有软件包是否已安装且是否是最新的：

```bash
python python_environment_check.py
```

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/02_installing-python-libraries/check_1.jpg" width="600px">

还建议检查版本JupyterLab，通过在此目录中运行 `python_environment_check.ipynb`，理想情况下应该会给出与上述相同的结果。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/02_installing-python-libraries/check_2.jpg" width="500px">

如果您看到以下问题，则可能是您的 JupyterLab 实例连接到了错误的 conda 环境：

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/02_installing-python-libraries/jupyter-issues.jpg" width="450px">

在这种情况下，您可能需要使用 `watermark` 来检查您是否使用 `--conda` 标志在正确的 conda 环境中打开了 JupyterLab 实例：

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/02_installing-python-libraries/watermark.jpg" width="350px">

<br>
<br>

## 安装 PyTorch

PyTorch 可以像任何其他 Python 库或包一样使用 pip 安装。例如：

```bash
pip install torch
```

但是，由于 PyTorch 是一个具有与 CPU 和 GPU 兼容的代码的综合库，因此安装可能需要额外的设置和说明（有关更多信息，请参阅书中的 *A.1.3 安装 PyTorch*）。

强烈建议查阅 PyTorch 官方网站 [https://pytorch.org](https://pytorch.org) 上的安装指南菜单。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/02_installing-python-libraries/pytorch-installer.jpg" width="600px">

<br>

---

有任何问题吗？请随时在 [讨论论坛](https://github.com/rasbt/LLMs-from-scratch/discussions) 中提出问题。