# File - AddSettingsFileStoreService

## FileStoreService の Config に設定を追加します

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
- Fqdn
  - 格納先のサーバー (FQDN)
- Server
  - 格納先のサーバー
- StoreDir
  - 格納先のフォルダー
- MasterFile
  - 編集する Settings ファイルのパス
- DestDir
  - 格納先のディレクトリ

```json:AppConfig.json
{
    "AppSettings": {
        "StoreLog": "\\fslog.txt",
        "Fqdn": "\\\\hogehoge",
        "Server": "\\\\192.168.xxx.xxx",
        "StoreDir": "\\Video",
        "MasterFile": "\\xxx\\xxx\\MasterSetting.xml",
        "DestDir": "D:\\Q"
    }
}
```
