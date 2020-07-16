
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

[Dcoker環境でコントローラーファイルを作成する]
$ docker-compose exec workspace php artisan make:controller LineBotController

[LineのAPIの設定]
Provider : Laravel_Taichi's_App
Channel name : Laravel_Test_App
Channel description : Laravelでアプリケーションを作成してみました。

[LineのSDKのインストール]
$ docker-compose exec workspace composer require linecorp/line-bot-sdk 4.2.*
