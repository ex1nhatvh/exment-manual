# 不具合修正 API実行時のリビジョン修正
### 不具合発生条件
- v3.0.9以下の時点で、API経由でデータを新規追加・更新を行った
- リビジョンが正常に表示されない

### 不具合発生バージョン
v3.0.9以下

### 修正方法
- Exmentのバージョンを、v3.0.10以上に[アップデート](/ja/update)する。
- 以下のコマンドを実行する。

~~~
php artisan exment:patchdata revisionable_type
~~~

- これで、過去にAPIから新規追加・登録を行ったデータの履歴が表示されます。