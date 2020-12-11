# コマンド一覧
Exmentで利用可能なコマンド一覧です。  
システム内で利用しているコマンド、開発用のコマンドを含みます。

## インストール・アップデート

### インストール

Exmentを手動でインストールするためのコマンドです。  
詳細は[こちら](/ja/quickstart_manual)をご確認ください。   
※インストールは、下記のコマンド以外にも必要な作業がございます。インストール実行時には、基本的に上記のリンク先の内容に従い、実行してください。

```
php artisan exment:install
```

### アップデート
Exmentを手動でアップデートするためのコマンドです。  
詳細は[こちら](/ja/update)をご確認ください。  
※アップデートは、下記のコマンド以外にも必要な作業がございます。アップデート実行時には、基本的に上記のリンク先の内容に従い、実行してください。

```
php artisan exment:publish
```

### css・jsファイルなど発行
パッケージ内のcss、js、画像ファイルや、設定ファイルなどの一式を、laravelの既定のパスへ発行します。

```
php artisan exment:publish
```



## データインポート・エクスポート・データ削除

### データエクスポート
データのエクスポートをコマンドから実行します。  
詳細は[こちら](/ja/data_cmd_import_export#データエクスポート)をご確認ください。

~~~
php artisan exment:export (テーブル名)
~~~

### データエクスポート(chunkモード)
データのエクスポート(chunkモード、分割出力)をコマンドから実行します。  
詳細は[こちら](/ja/data_cmd_import_export#export_chunk)をご確認ください。

~~~
php artisan exment:chunkexport (テーブル名)
~~~


### データインポート
データのインポートをコマンドから実行します。  
詳細は[こちら](/ja/data_cmd_import_export#データインポート)をご確認ください。

~~~
php artisan exment:import {フォルダ名}
~~~


### 大量データ一括投入
大量データ一括投入を、コマンドから行います。  
詳細は[こちら](/ja/data_bulk_insert)をご確認ください。

~~~
php artisan exment:bulkinsert {フォルダ名}
~~~


### カスタムデータのリフレッシュ
Exmentに登録している、カスタムデータを、リフレッシュ(一括削除)します。  
テーブル定義のみ残し、テストデータを削除する場合などにご利用ください。  
詳細は[こちら](/ja/refresh_data)をご確認ください。

~~~
php artisan exment:refreshdata
~~~


### カスタムデータのリフレッシュ(指定のテーブル)
Exmentに登録している、カスタムデータのうち、指定のテーブルのデータを、リフレッシュ(一括削除)します。  
テーブル定義のみ残し、テストデータを削除する場合などにご利用ください。  
詳細は[こちら](/ja/refresh_data)をご確認ください。

~~~
php artisan exment:refreshtable (テーブル名)
~~~







## バックアップ・リストア

### バックアップ
Exmentのバックアップを実行します。画面から実行する、バックアップ機能と同等の機能となります。  
詳細は[こちら](/ja/backup#backup_command)をご確認ください。  

```
php artisan exment:backup
```

### リストア
Exmentのリストアを実行します。画面から実行する、リストア機能と同等の機能となります。  
詳細は[こちら](/ja/backup#restore_command)をご確認ください。  

```
php artisan exment:restore (zipファイル名)
```


## バッチ・スケジュール
### プラグインバッチ実行
Exmentに登録しているバッチを実行します。  
詳細は[こちら](/ja/plugin_quickstart_batch)をご確認ください。

~~~
php artisan exment:batch 1
~~~


### スケジュール実行
Exmentに登録しているスケジューラに従い、ジョブを実行します。  
詳細は[こちら](/ja/additional_task_schedule)をご確認ください。

~~~
php artisan exment:schedule
~~~




## その他、開発用

### パスワードリセット
Exmentのログインパスワードリセットを、コマンドから実行します。  
詳細は[こちら](/ja/login_setting#パスワードリセットコマンド)をご確認ください。

```
php artisan exment:resetpassword --email=(対象ユーザーのメールアドレス) --password=(変更後パスワード)
```


### テストデータ作成
Exmentのテストデータ一式を作成します。  
<span class="red">※登録済みの全データが削除されますので、ご注意ください。</span>

```
php artisan exment:inittest
```


### メール送信テスト
Exmentに設定されたメール設定に従い、メール送信テストを行います。  
詳細は[こちら](/ja/mailsend_setting#コマンドから実行)をご確認ください。

```
php artisan exment:notifytest --to=(メール送信先)
```

### 言語ファイル対応漏れ確認
Laravelの言語ファイルで、パッケージに反映が漏れている言語・単語を確認します。

```
php artisan exment:checklang
```


### データパッチ
データベースに登録されているデータの補正が必要になった場合に実行するコマンドです。  
※基本的には、データのアップデート実施時に自動的に実行されます。  
※実施アクションは、ソース"src/Console/PatchDataCommand.php"を直接ご確認ください。

```
php artisan exment:patchdata {実施アクション}
```

