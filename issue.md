# 配置步骤详解

> 请按以下步骤完成环境配置，确保自动化测试正常运行。

---

## 步骤 1：安装基础依赖

执行以下命令安装项目依赖：

```bash
pip install adb-shell
pip install uiautomator2
```

验证安装：

```bash
adb version
```

---

## 步骤 2：配置设备连接

确保手机设备已连接并开启 USB 调试：

```bash
# 检查设备连接
adb devices

# 输出类似以下内容表示连接成功：
# List of devices attached
# XXXXXX    device
```

---

## 步骤 3：验证环境配置

完成上述配置后，使用项目自带的 GUI 操作脚本验证环境是否正常：

**执行以下测试命令：**

使用 xiaoyi_gui_agent，打开淘宝买一件羽绒服，选择第1个出现的羽绒服，选择L尺码，颜色默认

**验证结果：**
- 如果上述操作顺利完成，说明环境配置正确
- 如果操作失败，请检查设备连接和权限设置

---

## 步骤 4：常见问题排查

### 问题 1：设备无法识别

```bash
adb kill-server
adb start-server
adb devices
```

### 问题 2：USB 调试未授权

在手机上确认 USB 调试授权弹窗。

### 问题 3：操作超时

检查网络连接和应用响应速度。

---

## 步骤 5：进阶配置

配置测试报告输出：

```bash
export REPORT_DIR=./reports
```

---

**提示**：请按顺序完成以上步骤，确保环境配置正确后再进行正式测试。