# Webとネットワーク技術

## Webを実現するコンピュータネットワーク
- クライアント
  - Webサイトの表示
- サーバー
  - 情報・サービスの提供
  
- インターネット
  - 世界中のネットワークが繋がった環境のこと
- インターネットサービスプロバイダー
  - プロバイダー/ISPと略される
  - PC・スマホはプロバイダーと接続・プロバイダーとプロバイダーが接続することでインターネットとして成立
  - IX(InternetExchange)
    - 上位プロバイダー

## インターネットの標準プロトコル
- プロトコル
  - 機器同士の通信の共通ルール
  - HTTP/FTP/SMTP/POP
- TCP/IP
  - Transmission Control Protocol/Internet Protocol
    - プロトコルの集まり
    - かつてはOS・機種などにより独自のプロトコルが使用されていた

## TCP/IP
- 四つの階層に分かれている
  - アプリケーション層(4)
  - トランスポート層(3)  -データ分割・品質保証
  - インターネット層(2)  -ネットワーク間通信を規定
  - ネットワークインターフェース層(1)  -ハードウェアに関する規定
> アプリケーション層から深い層へ

- TCP
  - 送受信双方で確認を取りながら通信を行う
- UDP
  - User Datagram Protocol
  - データの順序・欠落を保証しない
  - その分、効率よく通信できるので動画ストリーミングなどで利用される
  
## IPアドレスとポート番号
- IPアドレス
  - 識別番号-コンピュータの特定
  - Unique
  - 192.168.1.1(8bit x 4 = 32bit/IPv4)
  - グローバルIP > インターネット上
  - プライベートIP > 自宅・社内など
    - 別LAN内であれば同一IPを指定可能
    - ルーター等でプライベート<>グローバル、変換
- ポート番号
  - IPからさらに提供されるサービスを指定するもの
  - Webサーバは80番、ポートによりサービスを識別できる
  
## URLとドメイン
- URL
  - http://example.com:80/test.html
    - 「HTTP」プロトコルを使用して「example.com」サーバーにある「test.html」ファイルを取得するの意
    - :80はポート番号、通常省略される
- ドメイン
  - IPアドレスを扱いやすくしたもの
  - unique
- FQDN
  - Fully Qualified Domain Name

## DNS
- DNS
  - ドメインをIPアドレスへと変換する仕組み（DNSサーバー）
  - 複数のDNSサーバーが階層構造で分散処理を行ってドメイン<>IP変換を行う
  - 同じDNSについて問い合わせが発生した場合、DNSキャッシュサーバー

## HTTP
1. request
2. WebServerがrequestを解析
3. Browserへresponse
4. Browserで表示
- ※request/responseでHTTP通信は使われる

- データの流れ
  - TCPヘッダー
  - IPヘッダー
  - イーサネットヘッダー
    
- IPv4 & IPv6
  - IPアドレスの数
