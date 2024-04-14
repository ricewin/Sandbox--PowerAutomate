# File - FileStore

## ファイルを複数のフォルダーに格納します

### 動作確認

- Windows 11

### 設定ファイル

BaseDir
├ AppConfig.json
└ filter.json

#### AppConfig.json

- StrategyFile
  - フィルターファイル
- StoreLog
  - ログファイル
- WatchDirectory
  - 監視先のフォルダー
- CopyAutoDestDir
  - コピー先のフォルダー
- CopyFilterDestDir
  - コピー先のフォルダー (カスタムフィルターを適用する)
- MoveDestDir
  - 移動先のフォルダー
- FileNameFilter
  - 処理対象のファイル
  - 正規表現文字列

```json:AppConfig.json
{
    "AppSettings": {
        "StrategyFile": "\\filter.json",
        "StoreLog": "\\fslog.txt",
        "WatchDirectory": "G:\\tmp",
        "CopyAutoDestDir": "\\\\192.168.xxx.xxx\\aaa",
        "CopyFilterDestDir": "D:\\hogehoge\\bbb",
        "MoveDestDir": "F:\\hogehoge\\ccc",
        "FileNameFilter": "*.mp4"
    }
}
```

#### カスタムフィルター

- filter.json で定義して、任意の除外フィルターを構築できる
- 上から順に比較する。ヒットすると以降の照合はしない

```json:filter.json
{
    "filters": [
        {
            "text": "FileName1"
        },
        {
            "text": "FileName2"
        },
        {
            "text": "FileName3"
        }
    ]
}
```
