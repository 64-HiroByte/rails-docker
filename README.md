# README

こちらは、既存のRailsプロジェクトをdocker化したものです。
ローカル環境にクローンすることでタスク管理アプリケーションを実行することができます。

Dockerが未インストールの方は [こちらから](https://www.docker.com/ja-jp/products/docker-desktop/) インストールしてください。
使用したDockerのバージョンは以下の通りです。
* Docker version: 26.1.1
* Docker Compose version: v2.27.0

また、使用したRuby, Postgresqlのバージョンは次の通りです。
* Ruby version: 3.2.2
* Postgresql version: 12

## アプリケーションの実行手順(初回起動時)
1. ターミナルを開いて、任意の場所に `git clone` コマンドでクローンしてください<br>例）HTTPS接続の場合<br>`$ git clone https://github.com/64-HiroByte/rails-docker.git`
2. 作業ディレクトリ（rails-dockerディレクトリ）に移動します
3. 次のコマンドを実行すると、アプリケーションが起動します<br>`$ docker-compose up -d`
4. アプリケーションが起動したのを確認した後、次のコマンドを入力してデータベースの初期設定を行います<br>`$ docker-compose exec app bash`
5. データベースの作成をします<br>`$ rails db:create`
6. データベースのマイグレーションを実行します<br>`$ rails db:migrate`
7. 初期設定後、お使いのWebブラウザを起動し、アドレスバーに `localhost:3000` と入力します
8. タスク管理アプリが起動します

## アプリケーションの実行手順（２回目以降の起動）
1. 作業ディレクトリに移動します
2. 次のコマンドを入力すると、アプリケーションが起動します<br>`$ docker-compose up` or`$ docker-compose up -d` 
3. サーバーが起動したのを確認した後、お使いのWebブラウザを起動し、アドレスバーに `localhost:3000` と入力します
4. タスク管理アプリが起動します

## アプリケーションの終了
`$ docker-compose up -d` コマンドでアプリケーションを起動した場合は、以下の手順1. は省略してください
1. アプリケーションを終了するには、ターミナルで `Ctrl` + `C` を押してサーバーを停止します（`$ docker-compose up`コマンド使用時）
2. `$ docker-compose down`を実行して、使用したコンテナを削除します

## 設定した環境変数について
使用した環境変数とデフォルト値は次の通りです。
|環境変数 | デフォルト値 |
| :----- | :--------- |
| DATABASE_PASSWORD | postgres |
| POSTGRES_USER | postgres |
| POSTGRES_PASSWORD | postgres |

## その他
* docker-compose.ymlの1行目`version: '3'`は現行のDocker Composeのバージョンでは記述不要となりました。記述した状態では、警告（WARN）が表示されるためコメントアウトしています。<br>お使いのDocker Composeのバージョンによりますが、必要に応じてコメントアウトを外してください。
* 使用にあたり不明な点がありましたらお気軽にお問い合わせください。