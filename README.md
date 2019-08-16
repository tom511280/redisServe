#redis

##安裝教學
###step1.到https://github.com/MicrosoftArchive/redis/releases下載對應的版本
###step2.輸入以下指令安裝一台主伺服器和二台從伺服器(安裝後以後就可以從「服務」內直接啟動)
>(1).安裝主伺服 : redis-server.exe --service-install redis.windows6379.conf --loglevel verbose  --service-name RedisService6379
>(2).安裝從1伺服: redis-server.exe --service-install redis.windows6380.conf --loglevel verbose  --service-name RedisService6380
>(3).安裝從2伺服: redis-server.exe --service-install redis.windows6381.conf --loglevel verbose  --service-name RedisService6381
###step3.啟動一台主伺服器、二台從伺服器、三台哨兵伺服器
>(1).主伺服 : redis-server.exe redis.windows6379.conf
>(2).從1伺服: redis-server.exe redis.windows6380.conf
>(3).從2伺服: redis-server.exe redis.windows6381.conf
>(4).哨1伺服: redis-server.exe redis.windows26377.sentinel.conf
>(5).哨2伺服: redis-server.exe redis.windows26378.sentinel.conf
>(6).哨3伺服: redis-server.exe redis.windows26379.sentinel.conf

##檔案介紹
> redis.windows-service.conf 主伺服器配置
> redis.windows-service6380.conf 從A伺服器配置
> redis.windows-service6381.conf 從B伺服器配置
> sentinelR1.conf 哨兵1伺服器配置
> sentinel23677R1.conf 哨兵2伺服器配置
> sentinel23678R1.conf 哨兵3伺服器配置

##啟動相關
###使用cd指令進到redis資料夾內
###如啟動後無反應，可以到「服務」內確認伺服器是否有打開
> redis-server sentinelR1.conf --sentinel : 啟動哨兵1伺服器
> redis-server sentinel23677R1.conf --sentinel: 啟動哨兵2伺服器
> redis-server sentinel23678R1.conf --sentinel: 啟動哨兵3伺服器



redis-server.exe redis.windows-service.conf
redis-server.exe redis.windows-service6380.conf
redis-server.exe redis.windows-service6381.conf




 