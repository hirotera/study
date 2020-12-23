# コマンド一覧
```php
php artisan list
```
どんなコマンドがあるか調べる時に使うらしい｡
バージョンアップ時に使用が変わることがあるので｡


# ヘルプを表示
```php
php artisan make:controller -h
```
---

# ルートの確認
```php
php artisan route:list
```
超大事｡エラーが出た時にルートを疑う際に使用｡

# モデル作成
```php
php artisan make:model ○○
```
モデル作成の雛形

# マイグレーションの作成
```php
php artisna make:migration ○○○ --create= ○○
```
作成するときはだいたいテーブルを作成するときなので､ --create=オプションを使う｡ファイル名の頭文字には日時が付与される｡

# マイグレーション実行
```php
php artisan migrate
```
作成したマイグレーションファイルを実行したいとき｡

# マイグレーションの再実行
```php
php artisan reset
php artisan migration:refresh
```
一度実行されたmigrateファイルは基本実行されないので､再度実行する際は､resetやrefresh等を組み合わせて使う｡他にもrollbackがある｡

# Seederの作成
```php
php artisan make:seeder ○○
```
DBに流し込みたいデータを作る時に

# Seederの実行
```php
php artisan db:seed
```
完成したseedファイルを実際にDBに流し込む｡基本は作成とセット｡

# コントローラー作成
```php
php artisan make:controller ○○
```
コントローラーを生成｡よく使う｡

# 最適化
```php
php artisan optimize
```
手動でコントローラを生成したりリネームするときに

# サーバー起動
```php
php artisan serve
```
サーバー起動

# 対話型コンソール起動
```php
php artisan tinker
```
ちょっとしたデバッグなど､DBにデータを入れたい時に