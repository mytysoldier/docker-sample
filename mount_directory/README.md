### ホストOSのディレクトリをマウントするやり方（バインドマウント）
- httpdイメージを使ったやり方例


```
docker run -dit --name web01 -p 8080:80 -v "$PWD"/web01data:/usr/local/apache2/htdocs/ httpd:2.4
```