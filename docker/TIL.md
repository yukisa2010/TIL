# Docker
- Udemy

- 事前知識
- IPアドレスとサブネット
    - 168.123.44.0 > IPアドレス
    - 255.255.255.0 > サブネット
    - 1~3オクテット=network部, 4オクテット=host部
    - 上記は基本。2進数での共通部分がnetwork部に該当する
    - サブネットはhost部が足りない場合にNW部から間借りして割り振ること
- DNS
    - ドメイン<　相互変換　>IPアドレス

## docker実行
- docker run docker/whalesay cowsay Hello!
    - 吹き出しのアスキーアートを表示
- docker images
    - イメージの一覧
- docker tag docker/whalesay my_whalesay
- docker tag docker/whalesay my_whalesay:ver1
    - エイリアスの作成

- docker inspect docker/whalesay
    - 詳細情報の表示
- docker rmi docker/whalesay
- docker rmi -f docker/whalesay
    - dockerイメージの削除

- docker build -t docker-whale .
    - dockerイメージの作成
    - 一番最後の引数で、カレントディレクトリを指定している（Dockerfileを置いておく）
- `Dockerfile`を編集する
    - `FROM` => 元となるDockerイメージ
    - `RUN` => 実行するコマンド
    - `CMD`
- docker build --no-cache -t docker-whale .
    - ノーキャッシュで実行

## Docker　push
- Docker Hubからリポジトリ作成
- docker tag docker-whale yukisa2010/docker-whale:ver1
- docker login
- docker push yukisa2010/docker-whale:ver1
## docker pull
- docker pull yukisa2010/docker-whale:ver1

ip確認
- docker-machine ip default

- docker run --name test-nginx -d -p 8080:80 nginx
    - --name => コンテナに名前をつける
    - -d => デタッチモード(BackGroundで起動)
    - -p => ポート番号の指定 ホストOS : docker内部

### バインドマウント
- docker run --name some-nginx -v /some/content:/usr/share/nginx/html:ro -d nginx
    - -v => volume
        - -v <Host directory> : <docker container pos> : <option>
            - <option>: ro => readonly /つけなくても動作する


- docker create --name <name> -it apline /bin/sh
    - -i　双方向接続
    - -t コンテナ内にttyを割り当てる

- docker run
    - create => start
- docker pause
- docker unpause
- docker stop

- docker exec -it <name> /bin/bash
 - docker内のターミナルに接続する

- docker commit <name> <イメージ名>:<タグ名>
 - コンテナを修正して作成

- docker attach
    - 接続
- docker attach --link

# リバースプロキシ
static-pageとreverse-proxyの二つを起動
reverse-proxyへ設定ファイルを配置
static-pageにはAUTHORの環境変数を設定
    http://ss => SS_から始まる環境変数が作成されている
    env | grep SS_で確認

    cat /etc/hosts

# docker-machine
- docker-machine ssh default
- docker-machine ip default
    - dockerホストのip確認
    - 表示されるip 000.000.00.000:8000でブラウザアクセス

# aws
- プロビジョニングできる
- IAM


