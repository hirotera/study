# 鉄則
とにかく細かくコミットしよう
コミット→マージを細かくすることでセーブポイントを増やし､コンフリクト解消に繋がる｡

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