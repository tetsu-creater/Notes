＊anacondaのWebScraping1という環境でやる

Seleniumのインストール
```
$ conda install -c conda-forge selenium
```

chromedriverのインストール
```
$ conda install python-chromedriver-binary
```

pillowのインストールは、Anaconda Navigatorからインストールした

jupyter notebookの起動
```
$ jupyter notebook
```

## ここからはJupyter notebookの話
### 単純なテキスト情報収集
```py
# webdriver をインポート
from selenium import webdriver
```

```py
# Chromeを起動
broswer = webdriver.Chrome()
```

```py
# 特定のページに移動　
broswer.get('URL')
```

```py
# 指定した要素に値を入力する(例えばユーザー名をidで指定する)   
elem_username = broswer.find_element_by_id('username')
elem_username.send_keys('abe')
```

```py
# ページのボタンをクリックする  
elem_login_btn = broswer.find_element_by_id('login-btn')  
elem_login_btn.click()
```

```py
# テキストデータを抽出し、表示  
elem = broswer.find_element_by_id('name')  
elem.text
```

```py
# 一括で取得
elems_th = broswer.find_elements_by_tag_name('th')
```

CSVファイルに出力




### Pillow（画像に関するライブラリ）の使い方
```
# pillowというライブラリからImageパッケージを読み込む
from PIL import Image
```

```
# 同じ階層の写真を読み込む
img = Image.open('sample.jpeg')
```

```
# 写真のサイズ確認
img.size
```

```
# 写真をリサイズ
img.resize((1024, 768))
```

```
# 編集した写真を保存する
img.save('sample_resize.jpeg')
```

### PillowとSeleniumを用いて画像を収集
```
# 一枚の画像を収集

## まず、画像のあるところまで絞り込む
elem = broswer.find_element_by_class_name('material-placeholder')
elem = elem.find_element_by_tag_name('img')

## その画像のsource情報を取得し、urlに代入
url = elem.get_attribute('src')

##画像を取得するために必要なパッケージをインポートする
import io
from urllib import request

## 写真を読み込む
f = io.BytesIO(request.urlopen(url).read())
img = Image.open(f)
```

```
# 複数の写真を読み込む
elems = broswer.find_elements_by_class_name('material-placeholder')

for index, elem in enumerate(elems):
    elem = elem.find_element_by_tag_name('img')
    url = elem.get_attribute('src')
    
    f = io.BytesIO(request.urlopen(url).read())
    img = Image.open(f)
    
    ## 同じ階層のimageフォルダに写真たちを保存する
    img.save('image/img{}.jpg'.format(index))
```


