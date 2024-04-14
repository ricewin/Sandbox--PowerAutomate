# File - FileStore

## ファイルを指定されたフォルダーに振り分けます

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
- MoveDestDir
  - 移動先のフォルダー (カスタムフィルターを適用する)
- FileNameFilter
  - 処理対象のファイル
  - 正規表現文字列

```json:AppConfig.json
{
    "AppSettings": {
        "StrategyFile": "\\filter.json",
        "StoreLog": "\\fslog.txt",
        "WatchDirectory": "\\\\hogehoge\\hoge",
        "MoveDestDir": "\\\\hogehoge\\hoge",
        "FileNameFilter": "*.ts"
    }
}
```

#### カスタムフィルター

MoveDestDir
├ [dir1]
├ [dir2]
└ [dir3]

- filter.json で定義して、任意のキーワードフィルターを構築できる
- 上から順に比較する。ヒットすると以降の照合はしない

```json:filter.json
{
    "filters": [
        {
            "storeDir": "\\dir1",
            "text": "text1"
        },
        {
            "storeDir": "\\dir1",
            "text": "text2"
        },
        {
            "storeDir": "\\dir2",
            "text": "text3"
        },
        {
            "storeDir": "\\dir3",
            "text": ""
        }
    ]
}
```
