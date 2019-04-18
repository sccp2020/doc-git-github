## 使い方

ここからは実際にリポジトリを作って作業してみましょう。

### ローカルリポジトリを用意する

githubに最初にあげるためのリポジトリを用意しましょう。terminalを用意して

```
$ mkdir hogehoge
$ cd hogehoge
```

と打ってみましょう。hogehogeというディレクトリ(フォルダ) ができあがり、hogehogeディレクトリに移動したはずです。

```
$ touch test
```

testというファイルができあがりました。

```
$ git init
```

これで、このローカルリポジトリが**Gitレポジトリ**に変換されました。(tips : `ls -a`というコマンドを打てば、`.git`というファイルができているはずです。)



### GitHubにリモートレポジトリを用意する

先ほどのGitHubのユーサープロフィールページから今回あげるようのリポートリポジトリを作りましょう。

左上のアイコンをクリックして、`Your repositories` をクリックします。次のような画面になるので、`New`のボタンをクリックしましょう。

![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-makeripo.png)



レポジトリの設定画面が出てきます。`Repository name` と `Description` を埋めて、`Create respository` をクリックしましょう。

`Repository name` はリポジトリの名前。今回は`hogehoge` にしましょう。

`DEscription` はこのリポジトリの簡単な説明です。空白でも大丈夫です。

![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-copyURL.png)



ボタンを押すと、セットアップの画面が出るのでそのままにしていてください。
