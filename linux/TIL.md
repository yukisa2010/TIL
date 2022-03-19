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

# パッケージ管理
- フロントエンド
    - 外部リポジトリからパッケージ取得
    - APT(Advanced Package Tool)
        - apt-get
        - apt-get install  
    - YUM(yum) YellowData Update Modified
- パッケージ管理ツール
    - rpm
        - RedHat Package Manager
    - dpkg
        - Debian系

## chromeのダウンロード・インストール
- webから通常ダウンロード
- sudo dpkg -i chrome...
    - install, but pkg足りない
    - sudo apt-get install A

# ジョブスケジューリング
- crontab -e > 自動実行の一覧

# ファイルシステム
- df (disk free)
    - 空き容量の確認
    - -h GB,MBで表示
- du (disk usage)
    - 使用量の確認
    - directoryの容量など見ることができる
- fsck(file system check)
    - df -T でext系かどうか確認
- debugfs
    - デバッグモード
    - q or quitで終了
- tune2fs
- xfsinfo
    - XFS管理ツール
    - CentOS
# クォータ制御
- ユーザーが使えるDisk領域の制御
    - {ハードリミットとソフトリミット} x {ユーザー単位・グループ単位}
    - 猶予期間(soft >>> hard)
- 設定
    - /etc/fstab user,group単位、指定してマウント
    - fstab = file system table
    - edquota
        - -u/-g/-t ユーザー・グループ・期間
- quotacheck(初期化)
    - -b backup
    - -c create new
    - -v detail view
- quotaon/off
# FHS(File Hierarchy Standard)
## ファイルシステム標準
- /
- /bin > 実行形式のファイル
- /sbin > システム管理関係の実行ファイル
- /lib > library
- /var > 変化する ex)logなど
- /etc > システムの共通設定など
- /dev > device
- /tmp > 一時情報・sessionなど
- /boot > 起動時に使う
- /proc > process
- /usr > システムユーザーが独自に入れたものapplication
    - /usr/share/man > manual保管場所
    - /usr/src > kernel source > rebuildに使用
    - /usr/local
        - /bin ユーザーが独自に追加したもの
        - /sbin システム管理コマンド
- /home > user home directory
- /root > 特権ユーザのhome directory
- /mnt > --mount CD ROM/SD/DVDなどを一時的にマウントするための
- /media > CD
- /opt option application
- /srv system関係の一時ファイル

# 検索系コマンド
- locate
    - dbから検索
    - updatedb > 前提として実行の必要
- whereis
    - whereis コマンド名 >> マニュアルの場所や実行ファイルの場所など
    - -b > binary
    - -m > manual
    - -s > source
- which
    - PATHの探索
    - 組み込みコマンドには無効
- type
    - PATHの探索

# TerraTerm
- Windows

# bash構成ファイル
- 読み込み順序(基本)
    1. profile
    2. bashrc
    - etc > ~ > etc
- /etc/profile > シェルの基本設定
- /etc/bashrc or /etc/bash.bashrc> bash起動毎に実行
- ~/.bashrc > シェル毎の設定
- ~/.bash_login .bash_logout ~/.bash_profile ~/.profile > ログイン・ログアウト時に実行
## スケルトンファイル
- ユーザーごとの設定・ログインログアウト時の処理など
- /etc/skel/.profile
# シェルスクリプト
- #! > シーバン
    - コマンドへのフルパス
- #コメント
- 実行方法
    - bash sample.sh
    - sample.sh
        - ただし、通常だと実行権限がないので、以下を実行して実行権限を付与する
        - ls -l sample.sh > 実行権限確認
        - chmod +x sample.sh
        - 実行 > ./sample.sh ※./の記述重要
    - source sample.sh
    - . sample.sh
# localization
env > LANG=...


## VSCODE Terminalタブのリネーム

Command + Shift + P
> Terminal Rename


# eval
- eval echo hello
    - echo helloを実行。
    - 変数内にコマンドを入れて、入れ子構造で実行することができる

# sed
- find . -type f | xargs sed -i '' 's/置換前/置換後文字列/g'
    - 対象のファイルの文字列を全て置換
    - LC_CTYPE=C