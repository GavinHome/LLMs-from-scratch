# Docker 环境设置指南

如果您更喜欢隔离项目依赖项和配置的开发设置，使用 Docker 是一种非常有效的解决方案。这种方法消除了手动安装软件包和库的需要，并确保了一致的开发环境。

如果您更喜欢使用 [../01_optional-python-setup-preferences](../01_optional-python-setup-preferences/README.zh.md) 和 [../02_installing-python-libraries](../02_installing-python-libraries/README.zh.md) 中介绍的 conda 方法，本指南将引导您完成为本书设置可选 docker 环境的过程。

<br>

## 下载和安装 Docker

开始使用 Docker 的最简单方法是安装适用于您相关平台的 [Docker Desktop](https://docs.docker.com/desktop/)。

Linux (Ubuntu) 用户可能更喜欢安装 [Docker Engine](https://docs.docker.com/engine/install/ubuntu/) 并按照 [安装后](https://docs.docker.com/engine/install/linux-postinstall/) 步骤操作。

<br>

## 在 Visual Studio Code 中使用 Docker DevContainer

Docker DevContainer 或开发容器是一种允许开发人员使用 Docker 容器作为成熟开发环境的工具。这种方法可确保用户能够快速启动并运行一致的开发环境，无论其本地计算机设置如何。

虽然 DevContainer 也可以与其他 IDE 配合使用，但用于与 DevContainer 配合使用的常用 IDE/编辑器是 Visual Studio Code (VS Code)。以下指南介绍了如何在 VS Code 上下文中使用本书的 DevContainer，但类似的过程也适用于 PyCharm。如果您没有它并且想要使用它，请[安装]（https://code.visualstudio.com/download）。

1. 克隆此 GitHub 存储库并 `cd` 进入项目根目录。

```bash
git clone https://github.com/rasbt/LLMs-from-scratch.git
cd LLMs-from-scratch
```

2. 将 `.devcontainer` 文件夹从 `setup/03_optional-docker-environment/` 移动到当前目录（项目根目录）。

```bash
mv setup/03_optional-docker-environment/.devcontainer ./
```

3. 在 Docker Desktop 中，确保 **_desktop-linux_ builder** 正在运行，并将用于构建 Docker 容器（请参阅 _Docker Desktop_ -> _更改设置_ -> _Builders_ -> _desktop-linux_ -> _..._ -> _使用_）

4. 如果您有 [支持 CUDA 的 GPU](https://developer.nvidia.com/cuda-gpus)，则可以加快训练和推理速度：

3.1 按照 [此处](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#installing-with-apt) 所述安装 **NVIDIA Container Toolkit**。 NVIDIA Container Toolkit 的支持情况如 [此处](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#nvidia-compute-software-support-on-wsl-2) 所述。

3.2 在 Docker Engine 守护进程配置中添加 _nvidia_ 作为运行时（参见 _Docker Desktop_ -> _更改设置_ -> _Docker Engine_）。将这些行添加到您的配置中：

```json
“runtimes”：{
“nvidia”：{
“path”：“nvidia-container-runtime”，
“runtimeArgs”：[]
```

例如，完整的 Docker Engine 守护进程配置 json 代码应如下所示：

```json
{
“builder”：{
“gc”：{
“defaultKeepStorage”：“20GB”，
“enabled”：true
}
},
“experimental”：false，
“runtimes”：{
“nvidia”：{
“path”：“nvidia-container-runtime”，
“runtimeArgs”：[]
}
}
}
```

并重新启动 Docker Desktop。

5. 在终端中输入“code .”以在 VS Code 中打开项目。或者，您可以启动 VS Code 并从 UI 中选择要打开的项目。

6. 从左侧的 VS Code _Extensions_ 菜单安装 **Remote Development** 扩展。

7. 打开 DevContainer。

由于 `.devcontainer` 文件夹位于主 `LLMs-from-scratch` 目录中（根据您的设置，以 `.` 开头的文件夹可能在您的操作系统中不可见），VS Code 应该会自动检测它并询问您是否要在 devcontainer 中打开项目。如果没有，只需按 `Ctrl + Shift + P` 打开命令面板并开始输入 `dev containers` 即可查看所有 DevContainer 特定选项的列表。

8. 选择 **Reopen in Container**。

如果之前没有构建过 Docker 映像，Docker 现在将开始构建 `.devcontainer` 配置中指定的 Docker 映像的过程，或者如果映像可从注册表中获取，则提取该映像。

整个过程是自动化的，可能需要几分钟，具体取决于您的系统和互联网速度。可选择点击 VS Code 右下角的“启动开发容器（显示日志）”查看当前构建进度。

完成后，VS Code 将自动连接到容器并在新创建的 Docker 开发环境中重新打开项目。您将能够像在本地计算机上运行一样编写、执行和调试代码，但同时还具有 Docker 隔离和 c 的额外优势持续性。

> [!WARNING]
> 如果您在构建过程中遇到错误，这可能是因为您的机器不支持 NVIDIA 容器工具包，因为您的机器没有兼容的 GPU。在这种情况下，编辑 `devcontainer.json` 文件以删除 `"runArgs": ["--runtime=nvidia", "--gpus=all"],` 行并再次运行“重新打开开发容器”过程。

9. 完成。

提取并构建映像后，您应该将项目安装在容器内，并安装所有软件包，以备开发。

<br>

## 卸载 Docker 映像

如果您不再打算使用 Docker 容器和映像，以下是卸载或删除它们的说明。此过程不会从系统中删除 Docker 本身，而是清理特定于项目的 Docker 工件。

1. 列出所有 Docker 映像以找到与您的 DevContainer 关联的映像：

```bash
docker image ls
```

2. 使用其映像 ID 或名称删除 Docker 映像：

```bash
docker image rm [IMAGE_ID_OR_NAME]
```

<br>

## 卸载 Docker

如果您认为 Docker 不适合您并希望卸载它，请参阅[此处](https://docs.docker.com/desktop/uninstall/) 的官方文档，其中概述了适用于您的特定操作系统的步骤。