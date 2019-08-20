#	redis
### 一、說明
#### 此伺服器皆由 https://github.com/MicrosoftArchive/redis/releases 下載對應的版本解壓縮後進行調整

###	二、於Windows下的安裝教學
####	step1.使用cmd cd到各自的六個目錄下(ex.cd 開發DB\redis\RedisSentinel26377)
####	step2.輸入以下各自的指令分別安裝一台主伺服器、二台從伺服器、三台哨兵伺服器(安裝後，以後就可以從「服務」內直接啟動)
*	(1).安裝主伺服 : redis-server.exe --service-install redis.windows6379.conf --loglevel verbose  --service-name RedisService6379
*	(2).安裝從1伺服: redis-server.exe --service-install redis.windows6380.conf --loglevel verbose  --service-name RedisService6380
*	(3).安裝從2伺服: redis-server.exe --service-install redis.windows6381.conf --loglevel verbose  --service-name RedisService6381
*	(4).安裝哨1伺服: redis-server.exe --service-install redis.windows26377.sentinel.conf --service-name RedisService26377 --sentinel
*	(5).安裝哨2伺服: redis-server.exe --service-install redis.windows26378.sentinel.conf --service-name RedisService26378 --sentinel
*	(6).安裝哨3伺服: redis-server.exe --service-install redis.windows26379.sentinel.conf --service-name RedisService26379 --sentinel
####	step3.啟動各自一台主伺服器、二台從伺服器、三台哨兵伺服器(也可以從「服務」內直接啟動，但此法可以方便看到即時console)
*	(1).主伺服 : redis-server.exe redis.windows6379.conf
*	(2).從1伺服: redis-server.exe redis.windows6380.conf
*	(3).從2伺服: redis-server.exe redis.windows6381.conf
*	(4).哨1伺服: redis-server.exe redis.windows26377.sentinel.conf --sentinel
*	(5).哨2伺服: redis-server.exe redis.windows26378.sentinel.conf --sentinel
*	(6).哨3伺服: redis-server.exe redis.windows26379.sentinel.conf --sentinel




 
