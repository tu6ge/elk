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

## 感谢

[Hukey's Blog](https://www.cnblogs.com/hukey/p/11519612.html)
