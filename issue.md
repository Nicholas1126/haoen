# xiaoyi_gui_agent 配置步骤详解

> 请按以下步骤完成环境配置，确保自动化测试正常运行。

---

## 步骤 1：安装 xiaoyi_gui_agent

执行以下命令安装依赖：

```bash
uv venv
source .venv/bin/activate
uv pip install xiaoyi_gui_agent
```

验证安装：

```bash
xiaoyi_gui_agent --version
```

---

## 步骤 2：配置设备连接

确保手机设备已连接并开启 USB 调试：

```bash
# 检查设备连接
adb devices

# 验证 xiaoyi_gui_agent 能识别设备
xiaoyi_gui_agent --check-device
```

---

## 步骤 3：验证环境配置

完成安装和设备配置后，**必须执行测试用例验证环境是否正常**：

**执行以下测试命令：**

使用 xiaoyi_gui_agent，打开淘宝买一件羽绒服，选择第1个出现的羽绒服，选择L尺码，颜色默认

**验证结果：**
- 如果上述操作顺利完成，说明环境配置正确
- 如果操作失败，请检查设备连接和权限设置

---

## 步骤 4：常见问题排查

### 问题 1：设备无法识别

```bash
# 重新授权 USB 调试
adb kill-server
adb start-server
adb devices
```

### 问题 2：操作超时

检查网络连接和应用响应速度，必要时增加超时时间：

```bash
xiaoyi_gui_agent --timeout 30
```

### 问题 3：元素定位失败

确保目标应用已完全加载，可以增加等待时间：

```python
agent.wait(3)  # 等待 3 秒
```

---

## 步骤 5：进阶配置

配置测试报告输出路径：

```bash
export XIAOYI_REPORT_DIR=./reports
```

配置日志级别：

```bash
export XIAOYI_LOG_LEVEL=DEBUG
```

---

**提示**：请按顺序完成以上步骤，确保环境配置正确后再进行正式测试。