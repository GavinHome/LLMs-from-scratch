# Python 设置技巧

有几种不同的方法可以安装 Python 并设置计算环境。这里，我说明了我的个人偏好。

（我使用的是运行 macOS 的计算机，但此工作流程与 Linux 计算机类似，也可能适用于其他操作系统。）

<br>
<br>

## 1. 下载并安装 Miniforge

从 GitHub 存储库 [此处](https://github.com/conda-forge/miniforge) 下载 miniforge。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/download.png" alt="download" width="600px">

根据您的操作系统，这应该会下载 `.sh`（macOS、Linux）或 `.exe` 文件（Windows）。

对于 `.sh` 文件，打开命令行终端并执行以下命令

```bash
sh ~/Desktop/Miniforge3-MacOSX-arm64.sh
```

其中 `Desktop/` 是 Miniforge 安装程序下载到的文件夹。在您的计算机上，您可能需要将其替换为 `Downloads/`。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/miniforge-install.png" alt="miniforge-install" width="600px">

接下来，逐步完成下载说明，按“Enter”确认。

<br>
<br>

## 2. 创建新的虚拟环境

安装成功完成后，我建议创建一个名为“LLMs”的新虚拟环境，您可以通过执行以下指令来执行此操作

```bash
conda create -n LLMs python=3.10
```

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/new-env.png" alt="new-env" width="600px">

> 许多科学计算库并不立即支持最新版本的 Python。因此，在安装 PyTorch 时，建议使用比当前版本早一两个版本的 Python 版本。例如，如果最新版本的 Python 是 3.13，则建议使用 Python 3.10 或 3.11。

接下来，激活新的虚拟环境（每次打开新的终端窗口或选项卡时都必须执行此操作）：

```bash
conda activate LLMs
```

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/activate-env.png" alt="activate-env" width="600px">

<br>
<br>

## 可选：设置终端样式

如果您想将终端样式设置为与我的类似，以便查看哪个虚拟环境处于活动状态，请查看 [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) 项目。

<br>
<br>

## 3. 安装新的 Python 库

要安装新的 Python 库，您现在可以使用 `conda` 包安装程序。例如，您可以按如下方式安装 [JupyterLab](https://jupyter.org/install) 和 [watermark](https://github.com/rasbt/watermark)：

```bash
conda install jupyterlab watermark
```

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/conda-install.png" alt="conda-install" width="600px">

您还可以使用 `pip` 安装库。默认情况下，`pip` 应链接到您的新 `LLms` conda 环境：

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/check-pip.png" alt="check-pip" width="600px">

<br>
<br>

## 4. 安装 PyTorch

PyTorch 可以像使用 pip 安装任何其他 Python 库或包一样安装。例如：

```bash
pip install torch
```

但是，由于 PyTorch 是一个具有与 CPU 和 GPU 兼容的代码的综合库，因此安装可能需要额外的设置和说明（有关更多信息，请参阅书中的 *A.1.3 安装 PyTorch*）。

强烈建议您查阅 PyTorch 官方网站 [https://pytorch.org](https://pytorch.org) 上的安装指南菜单。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/01_optional-python-setup-preferences/pytorch-installer.jpg" width="600px">

## 5. 安装本书中使用的 Python 包和库

请参阅 [安装本书中使用的 Python 包和库](../02_installing-python-libraries/README.md) 文档，了解如何安装所需的库。

<br>

---

有任何问题？请随时在 [讨论论坛](https://github.com/rasbt/LLMs-from-scratch/discussions) 中与我们联系。