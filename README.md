Procfileとは
- Herokuアプリには、起動時にアプリによって実行されるコマンドを指定するProcfileが含まれている
- アプリケーションがどのプロセスを使うのか宣言するためのファイル。Procfileを使用して、以下のようなさまざまなプロセスタイプを宣言できる。
- アプリケーションのルートディレクトリに配置して利用する
- ルートディレクトリ以外の場所に配置すると機能しない

what is Procfile?
- Heroku app includes a Procfile that specifies the command to be executed by the app at startup
- A file to declare which process the application uses. You can use Procfile to declare various process types
- Use it by placing it in the root directory of the application. It does not work if placed in a location other than the root directory

Sample picture
![2019-02-17 3 01 43](https://user-images.githubusercontent.com/35171408/52903457-19592580-3261-11e9-9810-82883d45d5a8.png)


See the logs in the red frame
![スクリーンショット 2019-10-26 22 47 33](https://user-images.githubusercontent.com/35171408/67632375-c94d5b00-f8e5-11e9-8ce3-b3dc0f34fdae.png)

procedure  
1  craete an application(whatever)  
2  heroku create  
3  git add .  
4  git commit -m "Create app for nginx"  
5  git push heroku master  
　
6  heroku buildpacks:add heroku-community/nginx  
7  Creaet a Procfile file  
8  write web: bin/start-nginx bundle exec unicorn -c config/unicorn.rb in Procfile  
9  git add Procfile  
10  git commit -m 'Update procfile for NGINX buildpack'  
11  Create config/unicorn.rb  
12  Edit unicorn.rb according to this refference below  
https://github.com/heroku/heroku-buildpack-nginx/blob/master/readme.md
12  git add config/unicorn.rb  
13  git commit -m 'Update unicorn config to listen on NGINX socket.'  
14  git push heroku master  
15  heroku open  
16  heroku logs -t  
