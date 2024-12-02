# 可选设置说明

本文档列出了设置您的机器和使用此存储库中的代码的不同方法。我建议从上到下浏览不同的部分，然后决定哪种方法最适合您的需求。

&nbsp;

## 快速入门

如果您的机器上已经安装了 Python，最快的入门方法是从 [../requirements.txt](../requirements.txt) 文件中安装软件包要求，方法是从此代码存储库的根目录执行以下 pip 安装命令：

```bash
pip install -r requirements.txt
```

&nbsp;

# 本地设置

本节提供在本地运行本书代码的建议。请注意，本书主要章节中的代码旨在在合理的时间范围内在传统笔记本电脑上运行，不需要专门的硬件。我在 M3 MacBook Air 笔记本电脑上测试了所有主要章节。此外，如果您的笔记本电脑或台式电脑有 NVIDIA GPU，代码将自动利用它。

&nbsp;
## 设置 Python

如果您尚未在计算机上设置 Python，我在以下目录中写了关于我个人 Python 设置首选项的内容：

- [01_optional-python-setup-preferences](./01_optional-python-setup-preferences)
- [02_installing-python-libraries](./02_installing-python-libraries)

下面的 *使用 DevContainers* 部分概述了在您的计算机上安装项目依赖项的替代方法。

&nbsp;

## 使用 Docker DevContainers

作为上述 *设置 Python* 部分的替代方案，如果您更喜欢隔离项目依赖项和配置的开发设置，使用 Docker 是一种非常有效的解决方案。这种方法无需手动安装软件包和库，并确保了一致的开发环境。您可以找到有关设置 Docker 和使用 DevContainer 的更多说明：

- [03_optional-docker-environment](03_optional-docker-environment)

&nbsp;

## Visual Studio Code 编辑器

有很多不错的代码编辑器选项。我首选的是流行的开源 [Visual Studio Code (VSCode)](https://code.visualstudio.com) 编辑器，它可以通过许多有用的插件和扩展轻松增强（有关更多信息，请参阅下面的 *VSCode 扩展* 部分）。可以在 [主 VSCode 网站](https://code.visualstudio.com) 上找到适用于 macOS、Linux 和 Windows 的下载说明。

&nbsp;

## VSCode 扩展

如果您使用 Visual Studio Code (VSCode) 作为主要代码编辑器，您可以在 `.vscode` 子文件夹中找到推荐的扩展。这些扩展提供了对此存储库有用的增强功能和工具。

要安装这些，请在 VSCode 中打开此“setup”文件夹（文件 -> 打开文件夹...），然后单击右下角弹出菜单中的“安装”按钮。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/README/vs-code-extensions.webp?1" alt="1" width="700">

或者，您可以将 `.vscode` 扩展文件夹移动到此 GitHub 存储库的根目录中：

```bash
mv setup/.vscode ./
```

然后，每次打开 `LLMs-from-scratch` 主文件夹时，VSCode 都会自动检查系统上是否已安装推荐的扩展。

&nbsp;

# 云资源

本节介绍运行本书中介绍的代码的云替代方案。

虽然代码可以在没有专用 GPU 的传统笔记本电脑和台式电脑上运行，但配备 NVIDIA GPU 的云平台可以大幅提高代码的运行时间，尤其是在第 5 章至第 7 章中。

&nbsp;

## 使用 Lightning Studio

为了在云端获得流畅的开发体验，我推荐 [Lightning AI Studio](https://lightning.ai/) 平台，它允许用户设置持久环境并在云 CPU 和 GPU 上使用 VSCode 和 Jupyter Lab。

启动新的 Studio 后，您可以打开终端并执行以下设置步骤来克隆存储库并安装依赖项：

```bash
git clone https://github.com/rasbt/LLMs-from-scratch.git
cd LLMs-from-scratch
pip install -r requirements.txt
```

（与 Google Colab 相比，这些只需要执行一次，因为 Lightning AI Studio 环境是持久的，即使您在 CPU 和 GPU 机器之间切换也是如此。）

然后，导航到要运行的 Python 脚本或 Jupyter Notebook。或者，您还可以轻松连接 GPU 来加速代码的运行时间，例如，当您在第 5 章中预训练 LLM 或在第 6 章和第 7 章中对其进行微调时。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/README/studio.webp" alt="1" width="700">

&nbsp;

## 使用 Google Colab

要在云端使用 Google Colab 环境，请前往 [https://colab.research.google.com/](https://colab.research.google.com/) 并从 GitHub 菜单或通过拖动打开相应章节的笔记本将笔记本放入*上传*字段，如下图所示。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/README/colab_1.webp" alt="1" width="700">

还要确保将相关文件（笔记本要从中导入的数据集文件和 .py 文件）也上传到 Colab 环境，如下所示。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/README/colab_2.webp" alt="2" width="700">

您可以选择通过更改*运行时*在 GPU 上运行代码，如下图所示。

<img src="https://sebastianraschka.com/images/LLMs-from-scratch-images/setup/README/colab_3.webp" alt="3" width="700">

&nbsp;

# 有问题？

如果您有任何问题，请随时通过此 GitHub 存储库中的 [讨论](https://github.com/rasbt/LLMs-from-scratch/discussions) 论坛与我们联系。