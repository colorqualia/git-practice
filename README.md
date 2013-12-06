# Git Practice

Git の練習も兼ねた Git コマンド覚書

# Git コマンド覚書

## Git Setting

### git config

Git の設定を表示・変更する。

``git config --list`` or ``git config -l`` 現在の設定値を表示する

``git config --global [value]`` ユーザーの Git の設定

``git config --system [value]`` システム全体の Git の設定

``git config [value]`` リポジトリの Git の設定



## Git Basics: Ground level

よく使う Git 基本コマンド

### git init

リポジトリを初期化します。リポジトリを作成する

### git add

変更ファイルを***ステージングエリア***に追加する  
インデックスとも言う

ステージングリアは**コミット対象ファイルを管理するところ**

### git commit

変更ファイルをステージングエリアからローカルリポジトリに登録する

### git status

現在のファイルの状態を表示する

``git status``

``git status -s``　短いフォーマットで出力する。ファイルが多い時に便利。

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

``git log``

``git log --oneline`` コミットメッセージの1行目だけ表示する

``git log --patch`` or ``git log -p`` コミット変更内容をパッチ形式で表示する

``git log --graph`` コミットの履歴をグラフ表示する。ブランチの分岐やマージを確認するときに使う

``git log --stat`` コミットの変更内容の統計情報を表示する

``git log --decorate`` HEAD、タグ、リモートブランチのHEADの情報を合わせて表示する

``git log --all`` すべてのブランチのコミットメッセージを表示する


## Git Basics: Branch, checkout, merge...etc

Git に慣れてきたら使うコマンド

### git branch

ブランチ（分岐）を作る

``git branch [branch name]``

ブランチ（分岐）を削除する

``git branch -d [branch name]``

### git checkout

ブランチを切り替える

``git checkout [branch name]``

ブランチを作って作ったブランチに切り替える

``git checkout -b [branch name]``

### git show-branch

ブランチの状態を把握する

### git merge

他のブランチの変更内容をマージする

### git reset

ファイルの変更やコミットをリセットする

### git stash

### git rebase





## Git'in GitHub

リモートリポジトリがあるときに使う主なコマンド

### git clone

リポジトリをローカルにコピーする

### git push

リモートリポジトリにローカルリポジトリの内容を反映する

### git remote



### git tag



## Other

### .gitignore

git で管理しない（変更履歴を取らない）ファイルをこのファイルに記述する

### .gitattributes

パスごとの属性を定義する


## ADDITIONAL: Git GUI Tools for Windows

* GitHub for Windows
* Source Tree
* Visual Studio Tools for Git

## ADDITIONAL: Git Repository Hosting Services

* [GitHub](https://github.com/)
* [Bitbucket](https://bitbucket.org/)
* [Visual Studio Online (旧 Team Foundation Service) ](https://tfs.visualstudio.com/)
