# VSCodeの拡張機能 Dev Container
Dockerを使用する上で便利な機能を提供するVSCodeの拡張機能．

## いいなと感じるポイント
* Githubの連携をしておくと，再ビルドした際に再度Githubの認証をする必要がない．
* Github上のリモートリポジトリがあれば，そのデータをそのままVolumeに持ってくることができる．

## Dev Containerを使うための準備
1. Dev Containerのインストール

2. devcontainer.jsonの作成
Dockerの作業ディレクトリのトップに`.devcontainer`のディレクトリを作成し，その中に`devctontainer.json`を作成する．

``` 
.
├── fuga.py
├── fuga_dir
│   ├── fuga
│   └── fugafuga
├── fugafuga.py
├── Dockerfile
├── docker-compose.yml
└── .devcontainer
    └── devcontainer.json
```
<br>

【devcontainer.json】

``` json:devcontainer.json
{
    "name": "quron_test_devcontainer",
    "dockerComposeFile": "../docker-compose.yml",
    "service": "quron_test",
    "workspaceFolder": "/workspace"
}
```

## Githubとの連携



## Dockerコンテナ構築
※ここでは，名前付きボリュームを使用するようなコンテナを，リモートリポジトリのデータをもとに構築する方法を紹介する．





