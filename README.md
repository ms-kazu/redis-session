# redis-session

## コンテナ起動
```
docker-compose up -d
```

##パッケージインストール
```
npm install --save express \
express-session \
cookie-parser \
redis \
connect-redis
```

##セッション確認
```
node app.js 
// セッション指定なし
curl -v http://localhost:5000 | jq
// セッション指定
curl -b connect.sid=[Set-Cookieを指定] -v http://localhost:5000 | jq
```


## Redisの起動しているコンテナに入る
```
docker-compose ps 
docker exec -i -t [コンテナ名] /bin/bash 
redis-cli
keys *
```
