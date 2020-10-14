```sudo apt-get install ssh-server```

ssh-server接続
実機から仮想機へ接続できる。

- GNU
    - ls --helpなどのようにハイフンが2つ続くコマンド

- pwd
    - Print Working Directoryの略
- cd
    - Change Directory
    - cd / ルートフォルダへ移動
    - cd ~ ユーザーのホームディレクトリに戻る

- shellの種類
    - bash
    - csh
    - tcsh

- history
    - 今までに使用したコマンドが表示される
    - 当該コマンド一覧は[vi ~/.bash_history]コマンドでも確認可能
    - ！＋インデックス番号で該当のコマンド処理の実行　ex)!123
- tabキー
    - 予測変換
- shortcut
    - ctrl + a => 先頭
    - ctrl + e => 末尾

- シェル変数
    - 代入 > INFILE="infile.txt"
    - 参照 >  echo $INFILE
    - echo '$INFILE' 
        - シングルクオートは文字列として認識
        - ダブルクオートは変数として認識してくれる
    - unset INFILE >> 変数を空にする
- 環境変数
    - envコマンドで環境変数の一覧を表示
    - env | more >> Enterキーで下へスクロール
    - export 変数 >> 環境変数へシェル変数を登録

- viエディター
    - Command ModeとInsert Mode
    - kで↑、jで↓
    