

### 配置文件



```  
http {
    include       mime.types;
    default_type  application/octet-stream;
    sendfile        on;

    keepalive_timeout  65;
    
    #负载均衡并设置权重
    upstream test {
        #ip_hash;  根据ip做hash，每个ip有固定的机器，解决session问题
        #fair;   根据响应时间作为权重
        server localhost:8080 weight=9;
        server localhost:8081 weight=1;
    }

    server {
        #端口
        listen       8099;
        server_name  localhost;
        
        #设置日志路径
        access_log  e:\wwwroot\proxy.access.log;
        error_log   e:\wwwroot\proxy.error.log;
        
        location / {  
            root   e:\wwwroot;  
            index  index.html;  
        }  

        # 静态请求
        location ~ \.(gif|jpg|jpeg|png|bmp|swf|css|js)$ {  
            root    e:\wwwroot;  
        }  

        # 动态请求
        location ~ \.(jsp|do)$ {  
            proxy_pass  http://test;  
        }  
        
        #请求转发
        location /yum {
            proxy_pass   http://ftp.sjtu.edu.cn/centos;
        }
        #请求转发
        location /yum_extend {
            proxy_pass   https://mirrors.fedoraproject.org;
        }

    }
}
```
