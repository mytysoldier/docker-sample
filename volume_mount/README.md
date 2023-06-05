### Docker Engineの領域をマウントするやり方（ボリュームマウント）
- httpdイメージを使ったやり方例
- `docker volume create`コマンドであらかじめボリュームを作成する。
```
docker volume create mysqlvolume
```
- mysqlコンテナを起動
```
docker run --name db01 -dit -v mysqlvolume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=mypassword mysql:5.7
```

### バインドマウントよりボリュームマウントを選ぶ場面
- Dockerコンテナが扱うデータをブラックボックスとして扱い、コンテナを破棄してもデータが残るようにしたい場合(例：データベースのデータ)