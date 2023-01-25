# Dockerの基本的な使い方

## 1.Dockerイメージ作成
### Docker Hubからダウンロードする方法（例: ubuntu）
```
$ docker image pull ubuntu:18.04
```

### 自分でDockerfileから作成する方法
1. 任意のディレクトリを作成し、その中にDockerfileを作成する
2. ビルドする（Dockerfileからイメージを作ること）
```
$ docker build -t {イメージ名}:latest {Dockerfileが保存してあるディレクトリのpath}
```

## 2.Dockerコンテナ作成
### 基本コマンド
```
$ docker run -d -it -p {ローカル側のポート番号}:｛コンテナ側のポート番号｝ -v {同期させたいローカル側のディレクトリのpath}:{同期させたいコンテナ側のディレクトリのpath} --name {コンテナ名} {イメージID}

（例）
$ docker run -d -it -p 8888:8888 -v /Users/yourpc/ProgramingStudy/FixstarsAmplify_Docker:/workspace --name FixstarsAmplify 4ka88cc8833
```

### オプション
| オプション    | 説明                       | 例                                              |
|---------------|----------------------------|-------------------------------------------------------|
| --name         | コンテナ名を指定           | docker run --name "test" centos                       |
| -d            | バッググラウンド実行       | docker run -d centos                                  |
| -it           | コンソールに結果を出力     | docker run -it --name "test" centos /bin/cal          |
| -p host:cont  | ポートフォワーディング     | docker run -d -p 8080:80 httpd                        |
| --add-host    | ホスト名とIPを指定         | docker run -it --add-host=test.com:192.168.1.1 centos |
| --dns         | DNSサーバを指定            | docker run --dns=192.168.1.1 httpd |
| --mac-address | MACアドレスを指定          | docker run -it --mac-address="92:d0..." centos |
| --cpu-shares  | CPU配分 (全体で1024)       | docker run --cpu-shares=512 centos                    |
| --memory      | メモリの上限               | docker run --memory=512m centos                       |
| -v            | ディレクトリの共有         | docker run -v /c/Users/src:/var/www/html httpd        |
| -e            | 環境変数を設定             | docker run -it -e foo=bar centos /bin/bash            |
| --env-file    | 環境変数リストから設定 | docker run -it --env-file=env_list centos /bin/bash   |
| -w            | 作業ディレクトリを指定     | docker run -it -w=/tmp/work centos /bin/bash          |
