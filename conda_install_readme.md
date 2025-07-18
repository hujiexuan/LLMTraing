
# Conda 安装与使用说明

## 一、下载安装 Miniconda

### 官网下载地址：
[Miniconda 官方下载](https://docs.conda.io/en/latest/miniconda.html)

| 系统    | 推荐下载链接 |
|---------|--------------------------------------------|
| Windows | Miniconda3 Windows 64-bit Installer (exe) |
| macOS   | Miniconda3 macOS 64-bit (Apple silicon 或 Intel) |
| Linux   | Miniconda3 Linux 64-bit Installer (sh) |

### Linux/macOS 快捷命令：
```bash
# Linux:
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh

# macOS (Intel):
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
```

### Windows：
直接下载 `.exe` 文件安装即可，全部默认下一步即可。

---

## 二、初始化 Conda
```bash
conda init
source ~/.bashrc  # Linux/macOS
```
出现 `(base)` 提示符，说明初始化成功。

---

## 三、处理 Terms of Service (ToS) 问题
如果出现 “Terms of Service have not been accepted” 报错：
```bash
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/main
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/r
```

---

## 四、创建 LLM 训练专用环境
```bash
conda create -n LLMTraing_py311 python=3.11 -y
conda activate LLMTraing_py311
```

---

## 五、推荐 LLM/AI 训练包
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install transformers datasets accelerate peft bitsandbytes
pip install sentencepiece tqdm pandas jupyter ipython tensorboard
```

---

## 六、附加可选配置：使用国内镜像源（如清华）
```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
conda config --set show_channel_urls yes
```

---

✅ 至此，Conda 安装和 LLM 环境配置完成。
