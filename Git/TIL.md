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


