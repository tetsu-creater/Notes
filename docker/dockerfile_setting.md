# Dockerfileとdocker-compose.ymlについて

## 用途
* **Dockerfile** <br>
→ Dockerイメージを作成するための設定を記述したテキストファイル．

* **docker-compose.yml** <br>
→ 複数のDockerイメージを組み合わせてアプリケーションを実行するための設定を記述したファイル．

## どちらを使った方がよいか
のちのち別のコンテナも作成して組み合わせる可能性があるため，docker-compose.ymlを使う方が個人的にはいいと思う．

## 記法

### `Dockerfile`
```
FROM python:3.10

RUN apt-get update &&\
    apt-get -y install locales &&\
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm

RUN pip install --upgrade pip

# Poetryのインストール
RUN curl -sSL https://install.python-poetry.org | python -

# Poetryのパスの設定
ENV PATH /root/.local/bin:$PATH

# Poetryが仮想環境を生成しないようにする
RUN poetry config virtualenvs.create false
```

https://qiita.com/daisuke30x/items/a3ea62ff8fa582b2b065

**FROM** <br>
ベースとなるイメージを決定するための項目．基本的にはOSを記述する．

**RUN** <br>
コンテナをビルドするときに実行してほしいコマンドを記述するための項目．

**ENV** <br>
環境変数を設定するための項目．


### `docker-compose.yml`
```
version: '3'
services:
  docker_compose_sample:
    restart: always
    build: .
    container_name: 'docker_compose_sample_container'
    working_dir: '/Workspace'
    tty: true
    volumes:
      - .:/myapp
```

https://qiita.com/yuta-ushijima/items/d3d98177e1b28f736f04

**version** <br>
docker-composeで使用するバージョンを定義している．指定すべきversionは公式サイトを参照．

**services** <br>
Docker Composeでは，アプリケーションを動かすための各要素をServiceと読んでいる．上記の例の場合，「docker_compose_sample」がサービス名．

**volumes** <br>
volume.mdで詳しく説明する．





