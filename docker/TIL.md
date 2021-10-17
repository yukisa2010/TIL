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


