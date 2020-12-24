# 基礎知識
### gitの構成

Gitにはファイルを保存するための場所がいくつかあり,
その構成は以下のようになっている｡

1. ワーキングツリー（今作業しているファイルのある場所）
2. インデックス（コミットするためのファイルを登録する場所）
3. ローカルリポジトリ（リモートリポジトリに変更内容を送信するための場所）
4. リモートリポジトリ（複数人でファイルを共有するための場所）


# 鉄則
- とにかく細かくコミットしよう  
- コミット→マージを細かくすることでセーブポイントを増やし､コンフリクト解消に繋がる｡

# まずはじめにやること
gitのバージョン管理を開始する
```
git init
```
# 流れ 
add .してコミットしてプッシュ
```php
git add . //インデックスに上げる
git commit -m "コミットメッセージ" //変更履歴を保存
git push origin ○○ (基本的にmasterにプッシュはしない)
```

# addを取り消す
```
git reset HEAD config/database.yml
```

#  コミット履歴確認
```
git log 
```

# 変更履歴のメッセージを修正する
```php
// bashの場合
git rebase -i HEAD^
// zshの場合
git rebase -i HEAD~
// bash か zsh か分からない場合は echo $SHELL を実行
```

# 変更内容を一時退避(コミット前の変更内容)
```
git stash
```

# 退避した変更を復元する
```
git push origin remote_url
```

# リモートリポジトリの状態を無視して強制プッシュ
```
git push -f orijgin remote_url
```

# ブランチの確認
```
git branch
```

# ブランチの切り替え
```
git checkout ○○
```
# ブランチを新規作成して切り替えまで一気にやる
```
git checkout -b ○○
```
# ブランチ名の変更
```
git branch -m ○○
```

# 過去のコミットの状態にファイルを戻す｡
```php
git checkout HEAD^//1つ前
git checkout HEAD^^^//3つ前
```

# リポジトリをクローンする
```
git clone github_url
```

# 前回のコミットとの差分を確認する｡
```
git diff HEAD^ //1つ前
git diff HEAD^^ //2つ前
```

# リモートリポジトリの変更内容をローカルリポジトリに反映させる(リモートリポジトリにあるブランチがローカルリポジトリに反映される)
```
git fetch
```

# リモートリポジトリのブランチを確認する
```
git branch -a 
```

# HEADにマージしたローカルリポジトリのブランチを消す
```
git branch -delete ○○
```

# マージの有無に関わらずローカルリポジトリのブランチを消す
```
git branch -D ○○
```

# 過去のコミットをまとめる
```php
git rebase -i HEAD^^//2つ分
git rebase -i HEAD^^^//3つ分
```

# ローカルの変更内容を取り消す
```
git checkout .
```

# リモートリポジトリをクローンする
リモートリポジトリを自分のパソコンにコピーしてくること
```php
git clone ○○ // ○○はgithubのurl
```


# リモートリポジトリの変更内容をローカルリポジトリに反映

```php
git checkout master //masterブランチに戻ってくる
git pull //リモートリポジトリの内容をローカルリポジトリに反映

git checkout ○○ //自分が作業したいブランチに切り替える

git merge master //変更をpullしたmasterをmerge
```

# コンフリクト
コンフリクトとは同じ箇所に対して2人以上が違う内容の変更を行う場合に発生する現象のこと｡
発生すると
```
<<<<<<< branch_a
puts "こんにちは！"
=======
puts "おはよう!!"
>>>>>>> master
```
こんな感じで表示される｡

## 解消するにはリモートリポジトリの
ローカルリポジトリでmasterに切り替え､リモートリポジトリのmasterをpullする
```
git pull origin master
```
その後ブランチをどちらかに切り替える
```
git checkout ○○
```
ブランチを切り替えたら変更を反映させたmasterを○○にマージする｡
```
git merge master 
```

その後､改めて自分が行いたい変更をする｡

完成したらリモートリポジトリにpushしてプルリクを送ると､コンフリクトが発生せずに変更内容をマージすることができる｡

