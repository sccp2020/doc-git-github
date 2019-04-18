# Git / GitHub 使い方

この記事では、個人開発でGitHubリポジトリをつくってバージョン管理ができるようになるまでを扱います。

![image](https://github.githubassets.com/images/modules/logos_page/Octocat.png)



## Git

世界で最もポピュラーなVCS(Version Control System, バージョン管理システム)の一つです。ソースコードの変更内容 **「いつ・誰が・何の・どこを・どのように変更したのか」** を管理することができます。

## GitHub

 GitHubはその名の通り **「Git」の「ハブ：拠点・中心・集まり」** です。

GitHubはGitの仕組みを利用して、世界中の人々が自分の作品（プログラミングコードやデザインデータなど）を保存、公開できるようにしたWebサービスの名称です。

GitHubはGitHub, inc. という会社によって運営されており、個人・企業問わず無料で利用することができます。

## アカウントを作る

Githubのユーザー登録の仕方について説明します。日本語ページは用意されていませんが躓いた時でも注意深く指示を読めばトラブルシューティングも難しくありません。

もうすでに自分のアカウントを持っている人はそのアカウントをそのまま使っても大丈夫です。



1. https://github.com/ を開いてください。GitHubのトップページです。

2. アカウントを作るために左上の `Sign up` をおしてください。![](https://github.com/sccp2020/doc-git-github/blob/master/img/pushSignup.png)

3. ユーザー情報の登録画面が表示されます。この課外プロジェクトで作成するアカウントには、ac.jpのメールアドレスを使用してください。

   | **items** |        **content**        |
   | :-------: | :-----------------------: |
   | Username  | sXXXXXXX-苗字 |
   |   Email   |   sXXXXXXX@u-aizu.ac.jp   |
   | Password  |           任意            |

   ![](https://github.com/sccp2020/doc-git-github/blob/master/img/pushSignup.png)

4. Githubの契約プランを選択する画面です。**free plan**にチェックをいれたまま次に行きましょう。 ![](https://github.com/sccp2020/doc-git-github/blob/master/img/selectCourse.png)

5. アンケート画面です。スキップすることもできますが、該当する箇所をチェックして送信しましょう。![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-qestion.png)

6. 仮登録が終わると、GitHubからメールが届きます。届いたメールを確認して、**Verify email address** をクリックして、メールアドレスの認証を完了させましょう。(tips: メールアプリを開くにはterminalで`sylpheed &`と打つとひらけます) ![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-mail-verify.png)

7. 認証に成功すると、`Your email was verufied` と表示され、アカウントの登録が無事完了します。![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-start.png)

8. 右上のアイコンをクリックして、`Your profile` に飛びます。ユーザープロフィールページです。作成したリポジトリや、その他ユーザー情報、コントリビューションはここに表示されます。![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-home.png)

## SSH key 登録

GitHubとのデータのやり取りでSSH公開鍵認証を使うために、GitHubにSSH公開鍵を登録します。
1. ユーザー情報の**setting**をクリックしてください。
![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-sshkey.png)

2. **SSH and GCP Key** 項目をクリックすると鍵登録の項目が出てくるので**New SSH Key**をクリックしてください。
![](https://github.com/sccp2020/doc-git-github/blob/master/img/github-addssh.png)

3. ローカルでSSH公開鍵を作ります。
```
$ ssh-keygen -t rsa

<< 空Returnを押しまくる >>

$ cd ~/.ssh

$ cat id_rsa.pub
ssh-rsa hkuhycdrkwAX49XkKVJg6wtZfERHCsrMjDHGUdCtdEF6kjHb8JyXyHPbRR6VzggBaK8AwT
JKjQP2MhaWCBgZCciVXH2Lhfjz5rXXRf29JDt3JFPzzxSNuntYLp7YCCPUYMEhMuFfpesyQ3jdZxCZ
SY6pfA5cXpwAYGC7GxZSrYRarwjWRYHfYFL2MUrcG2M3zjuPT3mDYHu4MR4u9rhFsBaXDXCCmCVTSJ
WrfBi4JxQwGKf5GZfxSW4Hkkap6SVwZ8KRQRheadyTiJ7JNLsGnB77e3pLBBnnemi5rpJTf3s775ic
wtX9Qtd6dieFnH9Ej9DJurL7Wj95WzaCLaEmUeN6bCk2T8K8QdHKPLFfAk== s1250XXX@sshsv171
# ssh-rsaから後ろをコピーする
```
これを**key**にペーストします。

## git config
Gitを使った操作には全てユーザー自身の責任が伴います。Gitに今コマンド操作やファイルの編集をしているユーザーが誰なのかを教えるために、ユーザー情報をgit configコマンドを使って設定しましょう。`user.name`と`user.email`はさっきGitHubに登録したものです！

|item|content|
|user.name| sXXXXXXX-苗字 |
|user.email| sXXXXXXX@u-aizu.ac.jp|
|core.editor|emacs|

```
$ git config --global user.name "sXXXXXXX-◯◯"

$ git config --global user.email "sXXXXXXX@u-aizu.ac.jp"

$ git config --global core.editor "emacs"
```

## お疲れ様でした。これであなたの環境でGitHubが使えるようになりました！

