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

