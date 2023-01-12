# gitとgithub

### 基本
①リモートリポジトリからクローンする方法

1. まず、githubでリモートリポジトリのURLを確認する
2. そのリモートリポジトリをローカルリポジトリにも作成する
```
$ git clone URL
```
3. ファイルを編集したら、addする
```
$ git add sample.html
```

4. いくつかのファイルを編集し、きりがよくなったらcommitする
```
$ git commit -m 'コメント'
```
5. commitを何回かして、きりが良くなったらpushする
```
$ git push origin
```
6. リモートリポジトリから最新の情報を取得する
```
$ git pull origin
```

<br><br>
②ローカルリポジトリとリモートリポジトリを別々に作成し、接続する方法

1. まず、githubでリモートリポジトリのURLを確認
2. ローカルリポジトリを作成する
```
$ git init
```
3. 接続
```
$ git remote add origin 〇〇
```


### SSH鍵の生成と登録(tetsuroabe > .ssh)
1. 鍵を生成する
```
$ ssh-keygen -t rsa -b 4096 -C "メアド"
```
2. パスワードを打つ
3. 公開鍵の情報をコピーする
```
$ pbcopy < ~/.ssh/id_rsa.pub
```
4. それをgithubのsettings > SSH&GPGのところから登録する




### ブランチ(マルチユニバース的なもの)
- 現在のブランチを確認する
```
$ git branch
```

- ブランチを新規作成かつ切り替える
``` 
$ git checout -b {切り替えたいブランチ名}
```

- ブランチを切り替える
```
$ git checkout {切り替えたいブランチ名}
```

### マージ（ブランチを合流させること）
例） devolopをmasterにマージさせる
1. masterブランチにチェックアウトする
2. マージさせる
```
$ git merge develop
```













