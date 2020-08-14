# elk

## nginx配置方式

```
http{
  log_format json '{"domain":"$server_name",'
    '"http_x_forwarded_for":"$http_x_forwarded_for",'
    '"time_local":"$time_iso8601",'
    '"request":"$request",'
    '"request_body":"$request_body",'
    '"status":$status,'
    '"body_bytes_sent":"$body_bytes_sent",'
    '"http_referer":"$http_referer",'
    '"upstream_response_time":"$upstream_response_time",'
    '"request_time":"$request_time",'
    '"http_user_agent":"$http_user_agent",'
    '"upstream_addr":"$upstream_addr",'
    '"upstream_status":"$upstream_status"}';
}
```

## 前提条件

电脑需要安装docker和docker-compose

因为elasticsearch最低需要2G内存，由于docker默认分配给容器的内存很小，所以需要设置一下虚拟内存大小

```
sudo sysctl -w vm.max_map_count=262144
```

## 运行

克隆代码后，运行
```
docker-compose up -d
```

查看日志，运行
```
docker-compose logs -f [elasticsearch,logstash,kibana]
```

## 感谢

[Hukey's Blog](https://www.cnblogs.com/hukey/p/11519612.html)
