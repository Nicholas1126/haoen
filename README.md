# 手机 GUI 自动化测试项目配置指南

> 作者：张明 | 更新时间：2026-03-28
> 
> 本文档介绍如何配置手机 GUI 自动化测试环境。

## 项目简介

本项目用于电商应用的 GUI 自动化测试，支持：
- 📱 手机应用自动化操作
- 🛒 电商购物流程测试
- 🤖 自然语言驱动的 GUI 操作

## 环境要求

- Python 3.8+
- ADB 工具
- 手机设备（已连接并开启 USB 调试）

## 快速开始

### 1. 克隆项目

```bash
git clone https://github.com/example/eshop-auto-test.git
cd eshop-auto-test
```

### 2. 配置设备

```bash
# 验证设备连接
hdc target list
```

## 详细配置步骤

完整的配置步骤和测试验证，请参考 **[配置步骤详解](https://github.com/Nicholas1126/haoen/blob/master/issue.md)**。

## 项目结构

```
eshop-auto-test/
├── scripts/
│   └── xiaoyi_gui_agent    # 项目自带的 GUI 操作脚本
├── tests/
│   └── test_shopping.py
└── requirements.txt
```

---

*如果本文对你有帮助，欢迎 star ⭐*
