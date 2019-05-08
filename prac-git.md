# git 入門

## git コマンド とは

## 概念の話

git を使う際によくある言葉をまとめてみました。

初めのうちは慣れないと思うのでさらっと読んで、使っていくうちに慣れていきましょう。

### ブランチ(branch)

「ブランチとは、履歴の流れを分岐して記録していくためのものです。分岐したブランチは他のブランチの影響を受けないため、同じリポジトリ中で複数の変更を同時に進めていくことができます。」( [サルでもわかるGit入門](<https://backlog.com/ja/git-tutorial/stepup/stepup1_1.html?gclid=CjwKCAjw2cTmBRAVEiwA8YMgzW6Uuaunj8cDnUrdbyCImWQ4F4jWYGG7-rqz0qrFN_6J2SdFiif7ExoCkFMQAvD_BwE>) )

簡単に言うと、変更を加える際に、本流のプロジェクトに影響を与えないために一旦場所を他に移すための機能のことをいいます。

master ブランチから、作業ブランチを作って移動してから作業することを、**ブランチを切る**といいます。

### コミット(commit)

ファイルやディレクトリの追加や変更を、リポジトリに記録する操作のことをコミットと言います。

### マージ(merge)

ブランチを切って作業して、記録されたcommitをmasterなどのブランチに同期させることをマージといいます。

## Let's start

### 前半戦

#### 1. git リポジトリを作ってみよう

まずはgitレポジトリを自分の環境に作ってみましょう！`gittouter` というディレクトリをつくってgitレポジトリとしたいと思います！次のコマンドを実行してください。

```
$ mkdir gittouter
$ cd gitrouter/
```

gittouterというディレクトリができました。

```
$ git init
```

このコマンドを打つと、`.git/` というディレクトリができてるはずです。



#### 2. ファイルをgit で保存をしてみよう

gitにファイルを保存してみましょう。

初めに`emacs` でファイルを開いて名前を書いてみましょう。

```
$ emacs name.txt
$ cat name.txt
Hage Taro
```

ではこのファイルをgit管理してみましょう。

```
$ git add name.txt
$ git commit -m "add name.txt"
```

このように実行してみてください。

`git add [filename]` このコマンドはコミットするファイルは`[filename]` であるとgitに教えています。

`git commit` このコマンドは`add`したファイルをコミットしてリポジトリに保存しています。`-m` はコメントを付け加えるオプションで、`"add name.txt"` という`name.txt`を追加したよというコメントを付け加えています。

ちなみに、`-m`オプションを付け加えずにコミットを実行すると任意のテキストエディタが自動で開かれるので、そこにコメントを付け加えることができます。(コミットメッセージは付け加えないと怒られます)

```
$ git status
On branch develop
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

このコマンドを実行すると、新しく作ったり変更を加えたファイルがあると教えてくれます。上のメッセージと同じものがでれば大丈夫です。

コミット漏れがないように逐次実行していきましょう。



#### 練習1

それでは、ここまでまとめで練習問題をしましょう。

1. 学籍番号を書いたファイル`number.txt` を追加して保存してください。
2. `git status` を実行した時に上記のような表示が出るようにしましょう。



### 後半戦

#### ブランチを切ってみよう

ブランチを切って作業をしてみましょう。次のコマンドを実行してください。

```
$ git branch
* master
```

このコマンドでは、現在gitリポジトリ上に存在しているブランチの一覧と現在どのブランチにいるかがわかります。

前半戦を終了してるならこのような出力があると思います。これで、今現在 `master` というブランチにいることがわかりました。

`name.txt` の変更をしようと思います。

```
$ git branch fix/name.txt
$ git branch
  fix/name.txt
* master
```

`git branch [branch-name]` このコマンドで、`[branch-name]` というブランチが出来上がりました。

```
$ git checkout fix/name.txt
Switched to branch 'fix/name.txt'
```

 `git checkout` コマンドでブランチを移動することができます。(ディレクトリを移動する時の`cd`と似たような機能です。)

```
$ git branch
* fix/name.txt
  master
```

となっていれば大丈夫です。



#### ファイルを変更してcommitしてみよう

このブランチで `name.txt` を変更してみましょう。

ファイルの中身を変更してみてください。

```
$ emacs name.txt
```

この時点で`git status`を実行すると怒られると思います。要は試しなのでやってみましょう。

```
$ git status
On branch fix/name.txt
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   name.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

怒られましたね。ではコミットしていこうと思います。

```
$ git add name.txt
$ git commit -m "fix name.txt"
```

ファイルの変更を教えてコミットしました。ここで`git status`を実行すると大丈夫なはずです。



#### masterに戻ってファイルを確認してみよう

ここで一旦 `master` ブランチに戻り、変更したはずのファイルが元のままなのを確認してみましょう。

```
$ git branch
* fix/name.txt
  master
```

(いま `fix/name.txt` にいる)

```
$ git checkout master
Switched to branch 'master'

$ git branch
  fix/name.txt
* master
```

`master` ブランチに戻ってきました。

ここで一旦ファイルを確認してみましょう。

```
$ emacs name.txt
```

変更を加える前のままでしたか？それなら正解です。

それでは `git status` を実行して怒られなければ次に進みましょう。



#### ブランチに戻ってファイルを確認してみよう

助長かもしれませんがブランチに戻ってファイルを確認してみましょう。

```
$ git checkout fix/name.txt
Switched to branch 'fix/name.txt'
$ emacs name.txt
```

変更したファイルに戻ってました。



#### ファイルをマージしてみよう

`master` ブランチに`fix/name.txt` ブランチで編集した変更を同期させます。

`master` ブランチに戻ってください。

```
$ git branch
* fix/name.txt
  master
  
$ git checkout master
Switched to branch 'master'
```

`fix/name.txt` ブランチを `master` ブランチにマージしましょう。

```
$ git merge fix/name.txt master
Updating 4a7733c..a957630
Fast-forward
 name.txt | 1 +
 1 file changed, 1 insertion(+)
```

この表示がでれば完了です！

`name.txt` が変更したものになってれば成功です。



#### 練習2

それでは練習問題です。

練習1で作った`number.txt` に次のことを守り誕生日を付け加え、マージまでしてください。

1. `fix/number.txt` というブランチで編集作業をすること。 
2. ファイルの編集はコマンドラインから行うこと。



### 練習問題の答え

練習1

```
$ emacs number.txt // emacs が起動されたら学籍番号を書く
$ git add number.txt
$ git commit -m "add number.txt" //コミット完了
```

練習2

```
$ git branch fix/number.txt
$ git checkout fix/number.txt

$ emacs number.txt //ここで編集します
$ git add number.txt
$ git commit -m "fix number.txt"

$ git checkout master
$ git merge fix/number.txt master
```

