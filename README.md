# UV 环境配置指南

> 作者：张明 | 更新时间：2026-03-28
> 
> 本文记录了在 Python 项目中配置 uv 包管理环境的完整流程。

## 背景

最近团队项目从 pip 迁移到 uv，体验非常不错。uv 是 Astral 团队开发的下一代 Python 包管理器，速度极快，兼容性好。但在配置过程中踩了一些坑，记录下来供大家参考。

## 安装步骤

### 1. 安装 uv

**Linux/macOS:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows (PowerShell):**
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 2. 创建虚拟环境

```bash
# 在项目目录下创建虚拟环境
uv venv

# 指定 Python 版本
uv venv --python 3.11
```

### 3. 激活环境

```bash
# Linux/macOS
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

### 4. 安装依赖

```bash
# 从 requirements.txt 安装
uv pip install -r requirements.txt

# 从 pyproject.toml 安装
uv sync
```

## 常见问题

配置过程中遇到了一些问题，踩坑记录和解决方案请参考 **[常见问题汇总](https://github.com/Nicholas1126/haoen/blob/master/issue.md)**。

## 性能对比

| 操作 | pip | uv |
|------|-----|-----|
| 安装 100 个包 | ~45s | ~3s |
| 创建虚拟环境 | ~2s | ~0.1s |
| 解析依赖 | ~5s | ~0.5s |

## 参考资料

- [uv 官方文档](https://docs.astral.sh/uv/)
- [uv GitHub 仓库](https://github.com/astral-sh/uv)
- [从 pip 迁移指南](https://docs.astral.sh/uv/guides/integration/pip/)

---

*如果本文对你有帮助，欢迎 star ⭐*