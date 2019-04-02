Procfileとは
- Herokuアプリには、起動時にアプリによって実行されるコマンドを指定するProcfileが含まれている
- アプリケーションがどのプロセスを使うのか宣言するためのファイル。Procfileを使用して、以下のようなさまざまなプロセスタイプを宣言できる。
- アプリケーションのルートディレクトリに配置して利用する
- ルートディレクトリ以外の場所に配置すると機能しない

![2019-02-17 3 01 43](https://user-images.githubusercontent.com/35171408/52903457-19592580-3261-11e9-9810-82883d45d5a8.png)

1  app作成
2  heroku create
3  git push heroku master
4  heroku buildpacks:add heroku-community/nginx
5  vi Procfile web: bin/start-nginx bundle exec unicorn -c config/unicorn.rb
6  git add Procfile
7  git commit -m 'Update procfile for NGINX buildpack'
8  vi config/unicorn.rb
9  git add config/unicorn.rb
10  git commit -m 'Update unicorn config to listen on NGINX socket.'
11  git push heroku master
