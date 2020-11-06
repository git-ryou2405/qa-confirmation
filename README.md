# qa-coin

## Member
#### 名前と好きなメソッドを記入してください
- 名前: 海老名翔平
  - 好きなメソッド: where
- 名前: Tatty
  - 好きなメソッド: pluck
- 名前：yukihiko
  _ 好きなメソッド: to_s
- 名前：yuu_tanaka
  _ 好きなメソッド: to_i
- 名前：yama_ryoji
  - 好きなメソッド: present

## Docker操作
ゼロからdocker環境を立ち上げる場合は、上から順にコマンドを実行すればOK
### docker imageのビルド
```
docker-compose build
```
### docker-compose起動
```
docker-compose up
```
`docker-compose up --build`にすると、`docker-compose up` の前に`docker-compose build`を自動的に実行してくれる
`docker-compose up -d`にすると、バックグラウンドでdocker-composeが起動する
### docker-composeで起動しているコンテナを確認する
```
```
### railsコマンドを実行する
例えば、docker環境下で`rails db:migrate`を実行する場合は以下のコマンドを使う
```
```
### 起動中のコンテナを停止
```
```
停止した後起動したい場合は、`docker-compose up`を実行する
### docker-composeコンテナの削除
```
```
### Dockerのイメージ、ネットワーク、ボリュームを全て削除する
```
```
