# WeChatMsg

`WeChatMsg` is a Windows desktop tool built with `PyQt5` for viewing, decrypting, exporting, and analyzing locally stored WeChat chat data.

## Features

- Read local WeChat data on Windows
- Extract account and database information from a logged-in WeChat client
- Decrypt local message databases
- View chats and contacts in a desktop UI
- Export records to `CSV`, `TXT`, and `HTML`
- Generate simple chat analysis reports

## Project Structure

```text
app/
  analysis/      Chat analysis
  DataBase/      Database access and export logic
  decrypt/       WeChat info detection and decryption
  ui/            PyQt desktop interface
  util/          Utility helpers
  web_ui/        HTML report pages
resource/        Static render resources
main.py          Application entry point
```

## Requirements

- Windows
- Python `3.10` to `3.13` recommended
- Desktop WeChat installed and logged in

## Install

```powershell
pip install -r requirements.txt
```

## Run

```powershell
python main.py
```

## Build EXE

Example build command:

```powershell
py -m PyInstaller --noconfirm --clean --windowed --name WeChatMsg --paths . --add-data "app;app" --add-data "resource;resource" --collect-data jieba --collect-data pyecharts main.py
```

After packaging, the executable is generated under:

```text
dist/WeChatMsg/WeChatMsg.exe
```

Keep the whole `dist/WeChatMsg` directory together when distributing the app.

## Notes

- Run the program with appropriate permissions if WeChat process information cannot be read.
- Generated databases and exported files may be written under the project directory.
- Some dependencies can be sensitive to Python version changes. If packaging fails on newer Python versions, use Python `3.10` to `3.13`.

## Disclaimer

This project is intended for viewing and managing your own local WeChat data only. Do not use it for unauthorized access, collection, or distribution of other people's data.
