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
# ---重要----
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
1. ユーザーのログインが失敗の場合の実装


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

- SessionsHelperの読み込み
    - Sessionの追加
        - <app/controllers/application_controller.rb>
        - ```Ruby
            class ApplicationController < ActionController::Base
                include SessionsHelper
            end
            ```
    - Helper内
        - <app/helpers/sessions_helper.rb>
        - ```Ruby
            module SessionsHelper            
                # 渡されたユーザーでログインする
                def log_in(user)
                    session[:user_id] = user.id
                end
            end
            ```
## cookiesのかくにん方法
1. 開発コンソールでApplicationを選択
1. かくにん方法、求めらているかくにんについて質問

## ログインの実装・フィールド名について
- User class
    - remember()
    - remember_token: 仮想的なフィールドめい（passwordと同じく）
    - remember_digest: 上記のトークンを暗号化したもの。

## ログインの仕組み（セッション）

- frondend
    - cookies >> user_id と　remember_tokenを保存
- backend
    - session >> 
        - 仮想フィールド：remember_token
        - 実フィールド：remember_digest
            - remember()メソッドにより、remember_tokenを暗号化したものが入る
1. ログイン実行時にtokenが作成される >> 仮想フィールドとして存在
> remember meの実装
1. remember()メソッドの実行
    - remember_tokenから作成したremember_digestがテーブルに保存される
    - cookiesにもremember_tokenを保持
> 呼び出し時
1. テーブル保持のremember_digestとcookiesのremember_tokenを用いて暗号化を解除
    - ※「==」は再定義されている
