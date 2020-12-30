
参考
https://railstutorial.jp/chapters/beginning?version=5.1
heroku --version

リスト 1.15: クラウドIDE上でHerokuをインストールするコマンド

$ source <(curl -sL https://cdn.learnenough.com/heroku_install)
$ heroku --version
heroku-cli/6.15.5 (linux-x64) node-v9.2.1
Herokuのコマンドラインインターフェイス (CLI) がインストールされていることが確認できたら、いよいよherokuコマンドでログインしてSSHキーを追加します。

$ heroku login --interactive
$ heroku keys:add
$ heroku create


