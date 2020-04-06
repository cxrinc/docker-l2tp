## 概要

以下の docker をベースに修正したものです。  
https://hub.docker.com/r/teddysun/l2tp/

修正点
* コンテナ起動時にパスワードファイルを上書きしないように修正。  
  オリジナルのものは起動時に l2tp.env ファイルで指定した１ユーザのみを含むパスワードファイルを再生成する仕様。

## セットアップ手順

1. l2tp.env を修正してください。

設定の詳細は以下のドキュメントを参照ください。  
https://hub.docker.com/r/teddysun/l2tp/

2. 起動

```
docker-compose up -d
```

## コマンド一覧

ユーザ一覧表示

```
docker-compose exec l2tp l2tpctl -l
```

ユーザ追加

```
docker-compose exec l2tp l2tpctl -a
```

ユーザ削除

```
docker-compose exec l2tp l2tpctl -d
```

## データファイル

config ディレクトリには登録されたユーザとパスワードを含むファイルが保存されます。
