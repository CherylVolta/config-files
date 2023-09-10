# 注意 Attention

## 1. 问题 Problem

某些情况下 **Clash for Windows**（以下简称 CFW）会出现由“任务计划”中的错误设置致使的在开启/运行 Tun 时出现 **“Access is denied”** 之类表示 **“权限不足”** 的提示。

### 发生场景 Occurrence Scenario

多发生于第一次安装 CFW，偶然发生于更新 CFW，不排除其它场景。

### 详情 Details

CFW 需要使用任务计划来开机自启动 `clash-core-service.exe` 提供核心服务支持。由于 Windos 的默认程序安装路径是 `C:\Program Files\`，含有空格，CFW 在设置任务计划程序时将其启动程序路径设置为 `C:\Program Files\Clash for Windows Service\clash-core-service.exe`（无引号），如下图所示：

![Details 1](images/1.png)

这样的配置看似正确，但实际上 Windows 会误认为启动程序路径是 `C:\Program`，参数为 `Files\Clash for Windows Service\clash-core-service.exe`，如下图所示：

![Details 2](images/2.png)

正确的方法是将启动程序路径设置为 `"C:\Program Files\Clash for Windows Service\clash-core-service.exe"`（带引号），如下图所示：

![Details 3](images/3.png)

如果你使用 Tun 模式，并且某天打开 CFW 时出现类似的 **“权限不足”** 的提示，请记得检查任务计划程序。

## 2. 更好的使用 Better Usage

见 <https://github.com/Hackl0us/GeoIP2-CN>
