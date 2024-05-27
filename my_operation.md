- 任意の場所に移動し、git　cloneを実行  
  `$ git clone https://github.com/64-HiroByte/rails-docker.git` 
- コンテナの起動  
  `$ docker-compose up -d`
- コンテナからbashを起動
  `$ docker-compose exec web bash`
- データベース作成  
  `$ rails db:create`
- マイグレーション  
  `$ rails db:migrate`
- Rails起動  
  `$ rails s -b 0.0.0.0`
