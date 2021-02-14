# Github

### 管理対象に入れてるもの全てコミット
```
git commit -a -m "init"
```

### 管理対象に入れていれば「git status」で変更を参照できる

```
$ git checkout -b topic-branch
$ <ココで何か変更を加えてみてください>
$ git add -A
$ git commit -a -m "Make major mistake"
$ git checkout master
$ git branch -D topic-branch
```

# git rm
```linux
$ git rm
```
ワーキングツリー、インデックスから対象のファイルを削除する
# git fetch
対象のファイルをローカルリポジトリにfetch

ワーキングツリー > インデックス > FETCH_HEAD

# git reset 
## --hard HEAD^
直前のコミットの打ち消し

## --soft


# git reset HEAD .
ステージングしたファイルを全てアンステージ


# コンフリクト
merge > コンフリクト発生 > 修正 > commit 

# fork
# git pull
