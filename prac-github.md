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

Organization にある [prac-pr](https://github.com/sccp2020/prac_pr) というリポジトリを clone します。

> **「clone」** とはリモートリポジトリをローカルにダウンロードすることです。

#### コマンド

```
$ git clone git@github.com:sccp2020/prac_pr.git
```

### ブランチ切って変更を加える

「prac/s12XXXXX」というブランチを作り、そこで

**「`s12XXXXX.txt` というファイルに `Hello, World!` を 1000 行書いて」** push してください。

> s12XXXXX の部分は自分の学籍を書いてください

### プルリク出す

以下の手順で進めてください。  
赤い枠のボタンを押して行ってください。

![](https://i.imgur.com/dAIgdX8.png)
![](https://i.imgur.com/Le2djOI.png)
![](https://i.imgur.com/TzpxF4T.png)

### merge してもらう

TA がマージしていきます。

### 演習 2

さて git/github 入門最後の演習です張り切っていきましょう。

最後の演習は！

1. `id.txt` というファイルに **自分の学籍番号** 追加してください。
2. [prac-pr](https://github.com/sccp2020/prac_pr) にプルリクを出してください。

#### 注意点

1. ブランチ名は、`fix/s12XXXXX` にすること。
2. すでに記入している `id.txt` の中身は変更しないでください。
3. 一番初めの人以外は全員 `git pull` をしないと怒られるでしょう(理由は後で説明します)。

![](https://i.imgur.com/OIlUNld.png)
