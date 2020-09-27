# Web技術とは

## Webとは
- WorldWideWeb
- ハイパーテキストとハイパーリンクで繋がっている
- CERN（欧州原子核研究機構）で開発された

## インターネットとWeb
- Web
  - 原型となる「ENQUIRE」---ティム・バーナーズリー
  - 各コクの実験者がすぐにアクセスできるように
  - その後、WebブラウザとWebサーバーを開発
- インターネット
  - ARPANET
    - ARPA(アメリカ国防総称省の高等研究計画局)
    - 通信方式（プロトコル）の見直し
    - 接続回線が安価となり、一般ユーザーにも普及

## さまざまなWebの用途
- 文書の閲覧
- ユーザーインターフェース
- プログラム用API

## HTMLとWebブラウザ
- Hyper Text Markup Language
  - タグ
- Webブラウザ
  - 読みやく変換

## WebサーバーとHTTP
- 配信プログラムWebサーバー
  - Webサーバー
    - Webブラウザからのコンテンツの要求に応える
    - ex.Apache, IIS(Internet Information Service)
  - HTTP
    - Webブラウザ >> Webサーバー >> Webブラウザ
    - HyperText Transfer Protocol (世界標準のハイパーテキストのやり取りの手順)
    
## Webページが表示される流れ
- URL(Uniform Resouce Locator)
  - やり取りの手順/どのWebサーバー/何のコンテンツを
- HTTP
- HTTPS(HTTPのセキュリティを高めたもの)
- 画像はあとで要求される

## 静的ページと動的ページ
- 静的ページ
  - HTMLのみ
- 動的ページ
  - アクセスした時の状態に応じて異なる内容が表示される
  - ex.Googleなどの検索結果・掲示板・ログイン

## 動的ページの仕組み
- CGI(CommonGatewayInterface)
  - ブラウザからの要求があるとプログラムを起動し、HTMLを生成する
  - サーバーサイド・スクリプト >> Perl/Ruby/PHP/JavaScript(ex>Node.js)
  - クライアントサイド・スクリプト >> JavaScript

## Webの標準化
- 規格を設けて標準化(HTML,CSS,XML,XHTML)　>> 互換性が保てる
- W3C(Consortium) 
  - Webの標準化を進める団体
  - Webの生みの親が開発

## Webの設計思想
- RESTful(REpresentational State Transfer)
  - 統一のインターフェース(Web >> HTTP)
  - アドレス可用性
  - 接続性
  - ステートレス性
    - 「前回のやりとり結果」のような情報を保持しなくて良い
- セマンティックWeb
  - Webページの情報に意味を付与する
  - 検索精度を上げる

## 定義
- Webページ >文書
- Webサイト > Webページの集まり
- トップーぺーじ > サイトの表紙にあたるページ

- Webアプリケーション 
  - Webを介して人が利用するサービスを提供する(ex.ショッピングサイト
- Webサービス 
  - プログラムが利用するサービスを提供する(ex.API
- Webシステム 
  - Webサービスを提供するための仕組み(ex.Webサーバ/APサーバ



















