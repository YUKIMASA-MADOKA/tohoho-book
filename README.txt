tohohoの実践

https://bty.sakura.ne.jp/wp/archives/1075

adminエリアはadmin/admin



■Django とは
　解説なので（略）
■注意
　（略）Djangoは「Django Girls」と同じバージョン
■インストール
　Windowsなので異なる
　pythonはインストール済とする
　djangoは「Django Girls」と同じ手順でインストール
　　・ディレクトリ作成：> mkdir tohoho
　　・仮想環境作成：> python -m venv myvenv
　　・仮想環境起動：> myvenv\Scripts\activate
　　・pipのupgrade：> python -m pip install --upgrade pip
　　・requirements.txt（Django~=3.2.10）を作成
　　・インストール：> pip install -r requirements.txt　　　　>

■SQLite3をバージョンアップする
　（略）Windowsなので
　ただし後述のモデル後の確認で
　sqlite-tools-win32-x86-3400100.zipの中のsqlite3.exeをmanae.pyと同じ場所にコピーする
　※パスが通った場所に置けばいいが、

■プロジェクトを作成する
　※config という名前でプロジェクトを作成し、その後、ディレクトリ名を変更するのがおすすめ
　の手順とする

　> django-admin startproject config
　> rename ./config ./myproj
　> cd ./myproj


■簡易サーバを起動する
１）./config/settings.pyを編集
　　ALLOWED_HOSTS = ['*']

２）起動
　> python manage.py runserver 0.0.0.0:80

★ブラウザから確認する
　http://localhost/


■アプリケーションを作成する

> python manage.py startapp books

・./books/urls.py を新規に作成
・./books/views.py ビューに list_books() を実装
・./config/settings.py の INSTALLED_APPS に ./books/apps.py に定義されたクラスを登録
・./config/urls.py に、http://server/books/ が要求されたら、./books/urls.py を参照するように指定


■アプリケーションディレクトリを集約する

> mkdir ./apps

・./config/settings.py に ./apps ディレクトリを登録
・$ mv ./books ./apps

★ブラウザから確認する
　http://localhost/books/

■モデルを作成する

・./apps/books/models.pyに追記

> python manage.py makemigrations
> python manage.py migrate

確認

> python manage.py dbshell
注１）

sqlite> .tables
sqlite> .schema books_book
sqlite> select * from books_book; 

■管理者サイトを使用する

> python manage.py createsuperuser

※admin/adminにしました

・./apps/books/admin.pyを編集し管理者サイトで編集できるように追記

★ブラウザから確認する（データも登録）
　http://localhost/admin/


■テンプレートを使用する
■テンプレートで共通なレイアウトページを参照する
■スタティックファイルを読み込む
■ヘッダやメニューバーを表示する
■詳細画面
■編集画面
■多言語対応
■言語設定画面を用意する
■Apacheから起動する
■MariaDBと接続する


