# difyの使い方

## はじめに
これはDify公式のドキュメントから転記しています。  
正確な情報はDify公式HPを見てください。  
https://docs.dify.ai/v/ja-jp

### 前提条件
- Docker Desktopのインストール  
https://docs.docker.com/desktop/install/windows-install/#wsl-2-backend

### Difyのクローン
Difyのソースコードをローカルにクローンする  
```sh
git clone https://github.com/langgenius/dify.git
```

### Difyの開始
difyソースコードのdockerディレクトリに移動し、次のコマンドを実行してdifyを起動する  
```sh
cd dify/docker
cp .env.example .env
docker compose up -d
```

デプロイメント結果：
```
[+] Runnning 7/7
✓ Container docker-web-1      Started
✓ Container docker-redis-1    Started
✓ Container docker-weaviate-1 Started
✓ Container docker-db-a       Started
✓ Container docker-worker-1   Started
✓ Container docker-api-1      Started
✓ Container docker-nginx-1    Started
```

最後に、すべてのコンテナが正常に稼働しているか確認：
```sh
docker compose ps
```

### Difyへのアクセス
```http://localhost```にアクセスして、Difyを使用します。


### Difyの更新
difyソースコードのdockerディレクトリに移動し、以下のコマンドを順に実行：
```sh
cd dify/docker
git pull origin main
docker compose down
docker compose pull
docker compose up -d
``` 
