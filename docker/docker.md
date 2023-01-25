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
$ docker build -t {イメージ名}:latest {Dockerfileが保存してあるディレクトリ}
```

## 2.Dockerコンテナ作成
