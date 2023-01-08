# Djangoに関して

## Djangoに関するコマンド(.gitignoreも作る！)

### 初期設定
1. プロジェクトを作成する
```
$ django-admin startproject プロジェクト名
```

2. 内蔵サーバーを起動させ、サーバーが正常に動いているかを確認
```
1. プロジェクトの1番上まで移動する
2. python manage.py runserver
```

3. settings.pyで言語や時間を編集する
4. デフォルトで存在するモデルをマイグレーションする
```
python manage.py migrate
```

5. アプリケーションを作成する
```
python manage.py startapp アプリケーション名
```

6. プロジェクト > settings.py > INSTALLED_APPSにアプリケーション > apps.py > Configクラスについて追記し、参照できるようにする


7. 

データベースに新しいテーブルやフィールドを追加したいとき
1. アプリ>models.pyに新しいフィールドを追加記載する
2. ターミナルで$ python manage.py makemigrations


アプリケーションのviews.pyに直接htmlを記載せず、templatesフォルダを使う方法。
アプリケーションフォルダ > templates > アプリケーションと同じ名前ファオルダ > index.htmlにhtmlに記載する。views.pyには、
```
return render(request, 'diagnosis/index.html')
```
と記載する
