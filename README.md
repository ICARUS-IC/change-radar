# 变更雷达 / Change Radar

AI 辅助开发的 Windows 本地公开网页正文变化监测工具。当前 v1.0.0 免费内测，无付费激活或内置到期限制。

## 下载

请打开本仓库的 [Releases 版本下载页](https://github.com/ICARUS-IC/change-radar/releases)。

- **直接使用：**下载 `change-radar-v1.0.0-windows-x64.zip`，完整解压后双击“启动变更雷达.exe”。无需安装 Python、注册软件账号或配置 API 密钥。
- **查看完整源码：**下载 `change-radar-v1.0.0-source.zip`。源码包包含 `app.py`、`web/`、`tests/`、构建脚本、依赖说明及许可证。源码在此独立附件中提供；仓库主页用于发布说明。
- **校验下载：**SHA256 文件随版本附件提供。

## 功能

- 定时重新读取公开 HTML 或纯文本网页，最短检查间隔 15 分钟。
- 首次建立正文基线，后续保存前后变化记录。
- 支持关键词段落筛选、HTML 简报导出、JSON 备份恢复。
- 界面和数据保存在本机。仅监听 `127.0.0.1`，不自动公开到互联网。

## 使用边界

- 面向 Windows 64 位；本次在 Windows 11 64 位验证。
- 自动检查需要后台程序运行、电脑保持唤醒且网络可用。关机、休眠或退出程序时不检查，也不会补造遗漏历史。
- 不支持登录、验证码、付费墙或需要执行 JavaScript 才显示的正文，不保证兼容所有网站。
- 没有邮件、手机或系统弹窗通知；变化在软件界面中查看。
- 程序没有商业代码签名。请确认来源及校验值，不要为运行它关闭安全防护。
- 软件不上传至作者服务器，但访问目标网站会正常发送网页请求，目标站可能看到 IP 等访问记录。
- 只监测有权处理的公开内容。公开访问不等于可以随意全文转载或收费分发。
- 演示及预览中的价格、额度均为标记清楚的模拟数据。

## 容量与备份

最多100个监测源，保留最近500条变化，界面列表显示最近200条；重要历史请及时导出或备份。JSON备份恢复上限64MB，超过时请先退出软件，再完整复制程序旁的 `data/` 文件夹。

## 从源码运行和构建

先下载并解压 **source.zip 附件**，在解压后的源码根目录执行以下命令（本次构建使用 Python 3.14.6）。普通使用者无需执行这些步骤。

```text
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python app.py
```

测试：

```text
.venv\Scripts\python -m unittest discover -s tests -v
```

重新构建 Windows 程序：

```text
.venv\Scripts\python -m pip install -r requirements-build.txt
.venv\Scripts\python build_windows.py
```

## 反馈与许可

欢迎通过本仓库 Issues 提交操作步骤、错误提示和可公开的网页地址；不要发送密码、令牌或私人数据。

原创代码采用 [MIT License](LICENSE.txt)，可依许可使用、修改和分发。第三方组件的原始版权与许可证包含在两个版本附件中。当前发布不包含支付、自动续费、托管、群发或获客，不承诺收入或终身维护。
