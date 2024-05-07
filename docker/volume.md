# Volumeに関して

## データの保存場所
Dockerのコンテナ内のデータは，コンテナ削除時には消失する．そこで，コンテナを削除してもコンテナ内に存在していたデータ（コードなどのファイル）を保存しておく方法が主に2通りある．<br>
それが...

1. Volumes
2. Bind mount

の2種類である．
<br>
これら2つの違いは，**データをどこに保存するのか**である．

※ マウント（mount）とは？<br>
コンテナ内の一部のデータを，別の場所にあるデータと同期すること


### 1. `Volumes`
コンテナ内のデータを，Docker内の「Volumes」というコンテナとは別の領域に保存する仕組み．コンテナとは別の領域であるため，コンテナ自体を削除してもデータはVolumesの中で生き続ける．<br>
* 名前付きボリューム（named volumes） : ボリュームに好きな名前をつけられる
* 匿名ボリューム（anonymous voumes） : ボリュームの名前に適当なハッシュ値が振られる

の2種類がある．

### 2. `Bind mount`
コンテナ内のデータを，ホストマシン（自分のPCのこと）のディレクトリ内に保存する仕組み．

<br><br>

## docker-compose.ymlの書き方
Volumes, Bind mountのどちらを使用したいかによって，docker-compose.ymlの書き方が異なる．

### 1. `Volumesを使用する場合のdocker-compose.ymlの書き方`
※ ここでは名前付きボリュームを使用する場合を説明する．

1. あらかじめボリュームを作成しておく．（Docker DesktopからGUIでも作成できる）
```
docker volume create sample_volume
```
この例の場合，「sample_volume」という名前のvolumeが作成される．
<br>

2. docker-compose.ymlを作成する
```
version: "3"
services:
  app:
    build： .
    volumes:
      - type: volume
        source: sample_volume
        target: /Workspace

volumes:
  sample_volume:
    external: true
```
この例の場合，手順1で作成したsample_volumeと，コンテナ内の/Workspace ディレクトリを同期させている．

### 2. `Bind mountを使用する場合のdocker-compose.ymlの書き方`

1. docker-compose.ymlを作成する
```
version: "3"
services:
  app:
    build： .
    volumes:
      - type: bind
        source: ./local_workspace
        target: /Workspace
```
この例の場合，ホストマシンのlocal_workspaceディレクトリと，コンテナ内の/Workspaceディレクトリを同期させている．



