# GitHub 入門

## 前半戦

リモートレポジトリの作成からコンテンツのアップロードまでの流れを勉強します。

### レポジトリ作る

GitHub 上にレポジトリを作りましょう

![](https://i.imgur.com/lw8pYFl.png)

![](https://i.imgur.com/t96IWsd.png)

### リモートリポジトリを設定する

さっき GitHub に作ったレポジトリをリモートレポジトリに設定しましょう。

前回 Git の練習で使っていたディレクトリに移動してください。

#### コマンド

```
$ git remote add origin {URL}
```

![](https://i.imgur.com/iA9viZ4.png)

URL の部分は、**自分のレポジトリ** の画像の赤で囲っている部分のものを使ってください。

### ローカルレポジトリをリモートにあげる

前回の演習で使っていたものをリモートレポジトリに Push（リモートレポジトリにアップロードすること）してみましょう。

#### コマンド

```
$ git push origin master
```

このコマンドに意味は、「**origin** という **リモートレポジトリ** に **ローカル** の **master** という **ブランチ** を Push します」という意味です。

### 演習 1

適当なファイルを追加してからリモートレポジトリに Push して見ましょう。

できるだけ、CUI だけで操作してみましょう。

#### 答え

##### ファイルを追加する

- emacs でファイルを新規作成する

```
$ emacs hoge.txt
```

- echo コマンドとリダイレクトでファイルに書き込む

```
$ echo hoge > hoge.txt
```

- touch コマンドで空のファイルを作成する

```
$ touch hoge.txt
```

##### Commit する

```
$ git add hoge.txt
$ git commit -m "Add hoge.txt"
```

##### リモートに Push する

```
$ git push origin master
```

## 後半戦

複数人で開発する際の GitHub の使い方を勉強します。

### clone する

### ブランチ切って変更を加える

### プルリク出す

### (merge してもらう)

### 演習 2

さて git/github 入門最後の演習です張り切っていきましょう。

最後の演習は！

`helloworld.txt` というファイルに `Hello, World!` を 1000 行出力して、

[url] のリポジトリにプルリクを出してください。

注意点

1. ブランチ名は、`s12XXXXX/hello` にすること。
2. `helloworld.txt` を作る方法は何を使っても構わない。
3. 一番初めの人以外は全員 `git pull` をしないと怒られるでしょう(理由は後で説明します)。

![](https://i.imgur.com/OIlUNld.png)
