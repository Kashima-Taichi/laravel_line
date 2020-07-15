
[install laradock]
$ git clone https://github.com/Laradock/laradock.git -b v9.6

[laradock envの作成]
$ cd laradock
$ cp env-example .env

[laradock .envの編集]
$ APP_CODE_PATH_HOST=../laravel
$ DATA_PATH_HOST=../data
$ cd ~/laravel-linebot/laradock
$ docker-compose up -d workspace php-fpm nginx
$ docker-compose exec workspace composer create-project --prefer-dist laravel/laravel . "6.8.*"
ここで localhost にアクセスをしてLaravelの画面が表示されればOK