# Git Practice - Git コマンド覚書

Git の練習も兼ねた Git コマンド覚書

## Git Setting

### git config

Git の設定を表示・変更する。

`git config --list` or `git config -l` 現在の設定値を表示する

`git config --global [value]` ユーザーの Git の設定

`git config --system [value]` システム全体の Git の設定

`git config [value]` リポジトリの Git の設定

---

## Git Basics: Ground level

よく使う Git 基本コマンド

### git init

リポジトリを初期化します。リポジトリを作成する

### git add

変更ファイルを***ステージングエリア***に追加する  
***インデックス***とも言う

ステージングリアは**コミット対象ファイルを管理するところ**

### git commit

変更ファイルをステージングエリアからローカルリポジトリに登録する

### git status

現在のファイルの状態を表示する

`git status`

`git status -s` 短いフォーマットで出力する。ファイルが多い時に便利

アルファベットの状態表示の意味

| 記号 | 意味 |
|-----|-----|
| なし | 変更なし |
|  M  |  変更 |
|  A  |  追加 |
|  D  |  削除 |
|  R  | 名前変更 |
|  C  |  複製 |
|  U  | 競合中 |


### git log

コミット履歴を見る

`git log`

`git log --oneline` コミットメッセージの1行目だけ表示する

`git log --patch` or `git log -p` コミット変更内容をパッチ形式で表示する

`git log --graph` コミットの履歴をグラフ表示する。ブランチの分岐やマージを確認するときに使う

`git log --stat` コミットの変更内容の統計情報を表示する

`git log --decorate` HEAD、タグ、リモートブランチのHEADの情報を合わせて表示する

`git log --all` すべてのブランチのコミットメッセージを表示する

### git rm

ファイルをバージョン管理から外す

### git mv

ファイルの名前変更・ファイルの移動

* `-f` 移動先のファイルが存在する場合でも上書きして強制的に移動
* `-n` `mv` コマンドは実行せず、結果だけ確認

### git tag

コミットにタグを設定する

`git tag <tagname> <commit>`

* `<tagname>` で指定した名前のタグを作成。  
`<commit>` で指定したコミットに付与される。 `<commit>` を省略すると HEAD にタグが付与

`git tag -l` 一覧表示する

`git tag -d <tagname>` 既存のタグを削除



---

## Git Basics: Branch, checkout, merge...etc

Git に慣れてきたら使うコマンド

### git branch

`git branch [branch name]` ブランチ（分岐）を作る

`git branch -d [branch name]` ブランチ（分岐）を削除する

`git branch -v` or `git branch --verbose`

`git branch -vv`

`git branch -a` or `git branch --all`

### git checkout

`git checkout [branch name]` ブランチを切り替える

`git checkout -b [branch name]` ブランチを作って作ったブランチに切り替える

### git show-branch

ブランチの状態を把握する

### git merge

他のブランチの変更内容をマージする

### git reset

ファイルの変更やコミットをリセットする

`git reset --mixed` or `git reset` 変更ファイルをインデックスから作業ツリーにもどす。`git add` の反対

* `--mixed` は省略可

`git reset --hard <commit>` 作業ツリーもインデックスも破棄して、指定したコミットの状態にする

`git reset --soft <commit>` 作業ツリーもインデックスも現在の状態のままになる。コミットをやり直したいときに使う

### git stash

作業を一時的に保存する

### git reflog

内部のログを見る

### git rebase

コミット履歴を変更する

---

## Git'in GitHub

リモートリポジトリがあるときに使う主なコマンド

### git clone

リポジトリをローカルにコピーする

### git push

リモートリポジトリにローカルリポジトリの内容を送信する

* `-u(--set-upstream)` 新規作成したリポジトリやブランチをプッシュする際、ローカルリポジトリのブランチとプッシュ先リポジトリのブランチの対応付けを行う。対応付けを行うとプッシュ時にブランチ名を省略することが出来る
* `--all` すべてのブランチをプッシュする

`git push -f origin [commit]:[branch name]` **リモートリポジトリを巻き戻す**  
Example) `git push -f origin HEAD^:master` HEAD^ でもいい。

### git pull

リモートリポジトリの変更を取得してマージする。

### git fetch

リモートリポジトリの変更を取得する。**変更取得後にマージは行わない**  
`fetch` コマンド `merge` コマンドを分けて実行するメリットは、マージされる前に変更点を確認できるところです

### git remote

リモートリポジトリを設定する

`git remote` 登録されているリポジトリの名前を表示

`git remote [-v(--verbose)]` 登録されているリポジトリの名前とURLを表示

* `-v(--verbose)` リモートリポジトリの名前の後に、リモートリポジトリのURLを表示する

`git remote set-url <name> <newurl>` リモートリポジトリのアドレスの変更

---

## Other

### .gitignore

git で管理しない（変更履歴を取らない）ファイルをこのファイルに記述する

* [gitignore.io - Create useful .gitignore files for your project](http://www.gitignore.io/)

### .gitattributes

パスごとの属性を定義する

---

## ADDITIONAL: Git GUI Tools for Windows

* GitHub for Windows
* Source Tree
* Visual Studio Tools for Git

---

## ADDITIONAL: Git GUI Tools for Macintosh

* GitHub for Mac
* Source Tree
* Tower

---

## ADDITIONAL: Git Repository Hosting Services

* [GitHub](https://github.com/)
* [Bitbucket](https://bitbucket.org/)
* [Visual Studio Online (旧 Team Foundation Service) ](https://tfs.visualstudio.com/)
* [Beanstalk](http://beanstalkapp.com/)
* [Backlog](http://www.backlog.jp/)
