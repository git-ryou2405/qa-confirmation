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
docker-compose ps
```
### railsコマンドを実行する
例えば、docker環境下で`rails db:migrate`を実行する場合は以下のコマンドを使う
##### docker-composeで起動しているコンテナに入る
コンテナに入った後、railsコマンドが実行できる
```
docker-compose exec web bash
```
- DBを作成する
```
# rails db:create
```
- マイグレーション実行
```
# rails db:migrate
```
※railsページが見れるようになります。http://localhost:3000/

- コンテナから出る
```
# exit
```
##### ※コンテナに入らずrailsコマンド実行する方法
コンテナに入らず`docker-compose exec web`の引数に指定したrailsコマンドを実行します。
```
例：  

docker-compose exec web rails db:create  

docker-compose exec web rails db:migrate  
```
### 起動中のdocker-composeコンテナを停止
```
docker-compose stop
```
`docker-compose down`を実行すると、`docker-compose stop`後に`docker-compose rm`を自動的に実行してくれる  
停止した後起動したい場合は、`docker-compose up`,又は`docker-compose start`を実行する

### ログの確認
```
docker-compose logs
```
### 停止中のdocker-composeコンテナの削除
※対象：カレントディレクトリのdocker-composeコンテナ
```
docker-compose rm
```
### Dockerのイメージ、コンテナ、ネットワーク、ボリューム一括削除
- 未使用なイメージ、コンテナ、ネットワークを一括削除
```
docker system prune -a
```
- 未使用なイメージ、コンテナ、ネットワークを一括削除（volumeも含め全て削除）
```
docker system prune -a --volumes
```
- 停止中のコンテナ一括削除
```
docker container prune
```
- 未使用のイメージ一括削除
```
docker image prune
```
- 未使用のボリューム一括削除
```
docker volume prune
```
- 未使用のネットワーク一括削除
```
docker network prune
```
※デフォルトで作成されている bridge、host、noneは消えずに残る。
### Dockerのイメージ、コンテナ、ネットワーク、ボリューム一覧表示
- コンテナ一覧表示
```
docker ps -a

docker-compose ps
```
- イメージ一覧表示
```
docker images

docker images -a     #タグ付けしてないimage含め全て
```
- ボリューム一覧表示
```
docker volume ls
```
- ネットワーク一覧表示
```
docker network ls
```
