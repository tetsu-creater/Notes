# anacondaに関する知識

## Anacondaに関するコマンド

Anacondaにある全ての環境を一覧表示する
```
$ conda info -e
```

Anacondaで仮想環境を作成する
```
$ conda create -n 環境名
```

作成した仮想環境を起動させる
```
$ conda activate 環境名
```

起動した仮想環境を終了させる
```
$ conda deactivate
```

インストールしたライブラリにcondaが対応しているかの確認　
```
$ conda search ライブラリ名
```

ライブラリのインストール
```
$ conda install ライブラリ名
```
