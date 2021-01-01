### Sinatraでセッションが使えなかった時の対処方法
<controller/application_controller>
```Ruby
    class ApplicationController < ActionController::Base
        # 下記を追加
        protect_from_forgery
    end
```

### ルートディレクトリへの追加
- config/routes.rb
```Ruby
    root 'home#index'
```

### バリデーションはモデルに付与する 
- model
```Ruby
    class XXX
        validates :name, presence: true
    end

```
### テーブルを作成
- terminal
```
    # for example
    bin/rails g migration create_table
```

### serverを再起動する
- migrationした時
- gemをインストールした時
- config変えたとき


### test

```Ruby
# 正しいこと
assert xxxx
# 正しくないこと
assert_not xxx
# 等しいこと
assert_equal xxx, xxx
```


## validates

```Ruby
class User
  # passwordのハッシュ化
  # ハッシュ化=暗号化
  has_secure_password

  # パスワードの入力必須、最小値：6文字
  validates :password, presence:true, length: {minimum: 6}
end
```

## views

```Ruby
# 開発環境でのみ表示
<%= debug(params) if Rails.env.development? %>
```

## SSL
### https

<config/environments/production.rb>
```Ruby
 # Force all access to the app over SSL, use Strict-Transport-Security,
  # and use secure cookies.
  config.force_ssl = true
```

# ログイン
## 概要
1. ユーザー登録
1. パスワードのハッシュ化
1. sessionコントローラの作成
1. ログイン画面の作成
1. login(new, create)/logoutの実装

## session
- newアクションで作成
    - ```rails generate controller Sessions new```
- formで送信される値：
    - ```params[:session][:email]``
- Sessionsアクション
    - new >> ログインページの表示
    - create
        - ユーザー情報のpost >> セッション変数への代入
        - セッションの作成
        - すなわち、ログイン
    - destroy
        - ログアウト
