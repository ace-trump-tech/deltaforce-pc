# DeltaForce PC

[![Stars](https://img.shields.io/github/stars/ace-trump-tech/deltaforce-pc?style=social)](https://github.com/ace-trump-tech/deltaforce-pc/stargazers) [![Forks](https://img.shields.io/github/forks/ace-trump-tech/deltaforce-pc?style=social)](https://github.com/ace-trump-tech/deltaforce-pc/network/members) [![Python](https://img.shields.io/badge/Python-3.8--3.11-3776AB?logo=python&logoColor=white)](https://www.python.org/)

DeltaForce-OBS-Locker 的 PC 端独立代码仓库。它保留桌面端 GUI、模型抽象、配置和示例资源，方便单独阅读、复现和二次开发。

> 本仓库用于计算机视觉与桌面交互原理学习。请勿用于真实游戏对局、绕过反作弊或破坏公平竞争。运行任何未知的二进制资源前，请先在隔离环境中审查。

## 项目关系

- 主项目：[DeltaForce-OBS-Locker](https://github.com/ace-trump-tech/DeltaForce-OBS-Locker)
- Mobile 端：[deltaforce-mobile](https://github.com/ace-trump-tech/deltaforce-mobile)
- 相关模型项目：[z637826/yolo-omni](https://github.com/z637826/yolo-omni)

## 快速开始

### 1. 获取代码

```bash
git clone https://github.com/ace-trump-tech/deltaforce-pc.git
cd deltaforce-pc
```

### 2. 创建环境并安装依赖

Windows PowerShell：

```powershell
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
```

如果 PowerShell 禁止激活脚本，可直接使用：

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

### 3. 检查配置

从 `config.yaml` 开始。不要把密钥、个人路径或本地模型权重提交到 Git；建议将本地覆盖项放在未跟踪的 `config.local.yaml` 中。

### 4. 运行入口

```bash
python gui.py
python main.py
```

GUI 和主入口依赖桌面环境；在 macOS/Linux 上可以阅读和测试纯 Python 模块，但部分 Windows 能力不适用。

## 目录结构

```text
.
├── core/              # 核心流程与示例组件
├── data/              # 消息、资源与二进制示例
├── models/            # 模型接口、预处理和后处理
├── utils/             # 日志、注册表等辅助模块
├── config.yaml        # 默认配置
├── gui.py             # 桌面 GUI 入口
├── main.py            # 主程序入口
└── requirements.txt   # Python 依赖
```

## 开发建议

- 使用 Python 3.8--3.11，并在虚拟环境中安装依赖。
- 模型权重、下载文件和日志默认不应进入 Git。
- 修改模型接口时，同时补充输入尺寸、坐标映射和异常路径测试。
- 提交前运行 `python -m compileall .` 做基础语法检查。

## 常见问题

**找不到 `config.yaml`**

请在仓库根目录运行命令，或在代码中使用基于 `__file__` 的绝对路径解析。

**提示缺少 `cv2`、`torch` 或 `yaml`**

确认虚拟环境已激活，并重新执行 `pip install -r requirements.txt`。大型深度学习依赖可能需要根据 Windows/Python 版本选择对应 wheels。

**模型权重在哪里？**

仓库不包含大体积权重。请按照模型项目的许可证和发布说明获取，并在本地配置路径。

## 许可证与责任

当前代码快照沿用主项目的学习用途声明。使用前请自行确认第三方模型、资源和二进制文件的许可证；任何账号、系统或数据损失由使用者自行承担。
