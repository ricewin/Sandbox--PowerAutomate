# File - AddSettingsDownloader

## Downloader の filter に設定を追加します

### 動作確認

- Windows 11

### 設定ファイル

```text
BaseDir
└ AppConfig.json
```

#### AppConfig.json

- StoreLog
  - ログファイル
- MasterFile
  - 編集する filter ファイルのパス

```json:AppConfig.json
{
    "AppSettings": {
        "StoreLog": "\\fslog.txt",
        "MasterFile": "\\xxx\\xxx\\filter.xml"
    }
}
```
