```
#!/usr/bin/env bash

src_redis="10.8.163.1"
src_port="6379"
dest_redis="10.8.132.13"
dest_port="6379"

for y in $(redis-cli -h ${src_redis} -p ${src_port} keys "*"); do
   redis-cli -h ${src_redis} -p ${src_port} migrate ${dest_redis} ${dest_port} ${y} 0 1000 copy replace
   echo "$(date +%F\ %T) Copy key ${y} to new redis...."
done
```

