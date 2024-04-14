# sharepoint-indexer

## 手順

### 必要ライブラリのインストール
```
pip install -r requirements.txt 
```

### AOAI リソースの作成
Azure ポータルから、embedding モデルのデプロイを行ってください。

### Entra ID アプリの登録
[Microsoft の公式ドキュメント](https://learn.microsoft.com/ja-jp/azure/search/search-howto-index-sharepoint-online) を参考に Entra ID アプリの登録を行ってください。

### .env ファイルの作成
.env.sample を参考にして .env を作成してください

> `AI_SEARCH_SERVICE_NAME` は `https://<テナント ID>.sharepoint.com/sites/<サイト名>` の形式で表現されます。

### データソースの作成
以下のコマンドを実行し、「データソースが作成されました。」と表示されれば成功です。
```
python create-datasource.py
```

以下のコマンドを実行し、「インデックスが作成されました。」と表示されれば成功です。
```
python create-index.py
```

以下のコマンドを実行し、「スキルセットが作成されました。」と表示されれば成功です。
```
python create-skillset.py
```

以下のコマンドを実行し、「インデクサーが作成されました。」と表示されれば成功です。
```
python create-indexer.py
```

> インデクサーの作成に関して、同期処理しているため、表示までに時間がかかる可能性があります。
