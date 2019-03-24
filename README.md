# mkcertを使ったローカル環境用サーバ証明書の発行

https://github.com/FiloSottile/mkcert

## インストール

### macOS (Homebrew)

```
$ brew install mkcert
```

#### Firefoxを利用する場合

```
$ brew install nss
```

### Windows (Chocolatey)

```
> choco install mkcert
```

#### Firefoxを利用する場合
1. `mkcert -CAROOT`コマンドを実行してCA証明書格納ディレクトリを調べる
2. オプション→プライバシーとセキュリティ→証明書を表示
3. 認証局証明書→インポート
4. 1のパスにある`rootCA.pem`を選択

## CA証明書をインストール (初回のみ)

```
$ mkcert --install
```

## サーバ証明書を発行

```
$ mkcert -cert-file ./certs/localhost.crt.pem -key-file ./certs/localhost.key.pem localhost
```

## Docker起動

```
$ docker-compose up -d
```

## ブラウザでアクセスしてみる

https://localhost/ を開く
