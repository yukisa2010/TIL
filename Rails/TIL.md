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