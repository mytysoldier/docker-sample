### ホストOSのディレクトリをマウントするやり方（バインドマウント）
- httpdイメージを使ったやり方例


```
docker run -dit --name web01 -p 8080:80 -v "$PWD"/web01data:/usr/local/apache2/htdocs/ httpd:2.4
```

- `--mount`オプションを使った書き方。（こちらが推奨されている）
```
docker run -dit --name web01 -p 8080:80 --mount type=bind,src="$PWD"/web01data,dst=/usr/local/apache2/htdocs/ httpd:2.4
```

### ボリュームマウントよりバインドマウントを選ぶ場面
- Dockerホストの設定ファイルをコンテナに渡したい場合
- 作業ディレクトリの変更を即座にコンテナから参照したい場合