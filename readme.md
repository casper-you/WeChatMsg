# WeChatMsg

`WeChatMsg` 是一个基于 `PyQt5` 的 Windows 桌面工具，用于读取、解密、浏览、导出和分析本机微信聊天数据。

## 功能简介

- 获取当前已登录微信账号的本地信息
- 读取并解密微信数据库
- 桌面界面浏览聊天记录和联系人
- 导出聊天记录到 `CSV`、`TXT`、`HTML`
- 生成简单的聊天分析与词云页面

## 项目结构

```text
app/
  analysis/      聊天分析
  DataBase/      数据库读取、合并、导出
  decrypt/       微信信息提取与解密
  ui/            PyQt 桌面界面
  util/          工具函数
  web_ui/        HTML 报告页面
resource/        渲染资源
main.py          程序入口
```

## 运行环境

- 操作系统：`Windows`
- Python：推荐 `3.10` 到 `3.13`
- 需要已安装并登录 Windows 版微信

## 安装依赖

```powershell
pip install -r requirements.txt
```

## 启动项目

```powershell
python main.py
```

## 打包 EXE

示例命令：

```powershell
py -m PyInstaller --noconfirm --clean --windowed --name WeChatMsg --paths . --add-data "app;app" --add-data "resource;resource" --collect-data jieba --collect-data pyecharts main.py
```

打包完成后可执行文件位于：

```text
dist/WeChatMsg/WeChatMsg.exe
```

分发时请保留整个 `dist/WeChatMsg` 目录，不要只单独复制 `exe`。

## 使用说明

1. 先登录 PC 版微信
2. 运行程序并获取微信信息
3. 选择微信数据目录或使用自动识别结果
4. 执行解密
5. 在界面中浏览聊天记录，或导出聊天数据

## 注意事项

- 如果无法读取微信进程信息，可尝试使用管理员权限运行
- 解密后的数据库和导出文件会写入项目目录下的相关文件夹
- 某些依赖对 Python 新版本兼容性较敏感，若遇到安装或打包问题，优先使用 `Python 3.10` 到 `3.13`

## 免责声明

本项目仅用于查看和管理你自己的本地微信数据。禁止用于任何未授权的数据获取、传播或其他违法用途。使用本项目造成的后果由使用者自行承担。
