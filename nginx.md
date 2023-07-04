# Nginx set up for socket.io

```
server  

{ 
       server_name backend.farmlink.me; 

       location /{ 
             #  proxy_set_header X-Real-IP $remote_addr; 
               proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for; 
               proxy_set_header Host $host; 
             #  proxy_set_header X-NginX-Proxy true; 
                proxy_pass http://localhost:4000/; 
                         proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection "upgrade";
             #  proxy_redirect http://localhost:5000/ https://$server_name/;       
       } 
}
```
