# 6章まとめ

## ログインパスワード用の設定項目
- model(Active Record)
    - User model に```has_secure_password```を追加
    - -> password_confirmation, authenticate メソッドが追加
    - emailの規則性担保のため、正規表現を使用 ```format: { with: RegularExp }```
- db
    - password_digestカラム追加のmigrationを実行
    - dbのemailへインデックスの追加・一意性の設定




