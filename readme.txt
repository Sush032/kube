Vote: dipesh017/demo:vote
Redis: redis:5.0-alpine3.10
Worker: dipesh017/demo:worker
Db: postgres:9.4
POSTGRES_USER : postgres
POSTGRES_PASSWORD : postgres
Result: dipesh017/demo:result


Use namespace name "local"  namespace:local
  
sed -i 's/  namespace: vote/  namespace: local/g' * //replace namespace name from "vote" to "local"
