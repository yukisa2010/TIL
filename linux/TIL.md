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
- ls
    - -aで隠しファイル表示
    - -lで詳細情報表示(rw)
    - -iでファイルのインデックス
- clear
    - 画面のクリア
- file
    - どういう種類のファイルなのかかくにんできる
- dd
    - 「dd if=ファイル1 of=ファイル2」でファイル1をファイル2にコピーできます。
- cp
    - copy A B　AをBと言う名前でコピー
- mv
    - 移動
    - リネーム
    - フォルダ名のみで省略もできる
        - ex) mv hello.txt src/
- rm
    - 削除
    - rm -fR フォルダごと削除
    - rm -rd 上記と同様
    - -r recursive /-d directory
- find
    - 特定のディレクトリにファイルがあるか、どこに位置しているか
    - find . --name searchword
    - sudo
## 圧縮・解凍コマンド
- tar(圧縮・ファイルのアーカイブ)
    - 元のデータは残る
    - -f /ファイル名
    - -c create
    - -x extract(展開)
    - -r 末尾に追加
    - -v verbose(詳細を表示/圧縮の経過)
    - -j bzip/ -z gzip
    - ex)tar czf work2.tar.gz work2 ->圧縮
    - ex)tar xvzf pressure.tar.gz -> 解凍
    - ex)tar rf pressure.tar.gz a.txt -> 追加
- gzip
    - gzip a.txt ->a.txt.gzに置き換わる(圧縮)
    - gzip -d a.txt.gz -> 解凍
- bzip
    - bzip2 g.txt -> g.txt.bz2が作成される(g.txtはそのまま)
    - bzip2 -d g.txt.bz2 -> g.txtに置き換わる
- xz
    - 圧縮・解凍
    - xz test.txt
    - xz -d text.txt
- CPIOコマンド
    - リストからまとめてzip
    - copyout mode
        - cpio -o < filelist.txt > files.cpio
    - insert mode
    - copypath mode
        - cpio copyto -pd < filelist.txt
        - ファイル内に記載されたファイルを移動する
- ln
    - ハードリンク => コピーに近い。同じiノードを使用する
        - ln A B
    - シンボリックリンク => ショートカットみたいなもの
        - ln -s A B
- cut
    - cut -d: -f1,6 passwd
    - => delimeter(区切文字は「:」), fieldは1,6番目を抜き出し
    - 対象文字列 A:B:C:D...

### 正規表現
### ジョブとタスク
- 「ls -l | more」 はジョブ
- 「ls -l」「more」はタスク
- ps PIDの確認
    - ps au => 全てのユーザーが使用しているプロセスも確認
    - ps aux => dbサーバーなど、端末を持たないもの常時起動のプロセス(daemon?)も確認できる
- top => 消費量
    - q コマンドで終了

> 上記、ps, topコマンドを利用して、メモリ増設などを検討
- !ssh サーバー接続
    - Windowsで試す

- uptime
    - このプロセスをいつ起動したか
- free
    - memoryの空きなど
- kill
    - kill -9 [プロセス番号]
    - シグナル名
        - kill -SIGKILL [プロセス番号]
- fore-ground & back-ground
    - fore >> vi test.txt
        - fg PID コマンド
    - back >> tail test.txt & 
        - bg PID コマンド

## ユーザー管理
- /etc/passwd
    - ユーザー名:パスワード(x):UserID:GroupID:GECOS(Comment):home directory:default shell
        - パスワードはshadowファイルで管理
        - /etc/shadow
- アクセス許可・パーミッション
    - r > read / w > write / x > execute
    - ls -la
        - drwxrwxrwx Username Groupname
        - ->先頭 d > directoryかどうか
        - 最初のrwx > ownerの権限
        - 次のrwx > ownerと同じグループ所属の権限
        - 最後のrwx > other その他
- chown root:root a.txt
    - a.txtをrootユーザー権限のファイルにする
        - -> UserName, GroupNameが変わる
        - ownerを変更する
- chmod o+w a.txt
    - owner に対し、a.txtを対象として、 write(w)の権限を付与する

