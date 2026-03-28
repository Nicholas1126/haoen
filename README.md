# 电商 GUI 自动化测试环境配置指南

> 作者：张明 | 更新时间：2026-03-28
> 
> 本文档介绍如何配置 xiaoyi_gui_agent 进行电商自动化测试。

## 背景

团队正在开发电商自动化测试框架，使用 `xiaoyi_gui_agent` 作为 GUI 操作引擎。本文记录环境配置的完整流程。

## xiaoyi_gui_agent 简介

`xiaoyi_gui_agent` 是一个智能 GUI 自动化工具，支持：
- 📱 手机应用自动化操作
- 🛒 电商购物流程自动化
- 🤖 自然语言驱动的 GUI 操作

## 快速开始

### 1. 环境要求

- Python 3.8+
- uv 包管理器
- 手机设备（已连接并开启调试模式）

### 2. 安装依赖

```bash
# 使用 uv 创建虚拟环境
uv venv
source .venv/bin/activate

# 安装 xiaoyi_gui_agent
uv pip install xiaoyi_gui_agent
```

### 3. 配置设备

```bash
# 验证设备连接
xiaoyi_gui_agent --check-device
```

## 详细配置步骤

完整的配置步骤和常见问题解决方案，请参考 **[配置步骤详解](https://github.com/Nicholas1126/haoen/blob/master/issue.md)**。

## 测试用例示例

配置完成后，可以运行以下测试用例验证环境：

```python
# 测试：电商购物流程
from xiaoyi_gui_agent import Agent

agent = Agent()
agent.run("打开淘宝淘一件羽绒服，选择第1个出现的羽绒服，选择L尺码，颜色默认")
```

## 参考资料

- [xiaoyi_gui_agent 文档](https://docs.xiaoyi-gui-agent.com)
- [uv 官方文档](https://docs.astral.sh/uv/)

---

*如果本文对你有帮助，欢迎 star ⭐*