## Configuring NGINX
nginx already installed  
darina@MacBook-Pro ~ % nano /opt/homebrew/var/www/my_site.html  
darina@MacBook-Pro ~ % nginx -t

<details>
nginx: the configuration file /opt/homebrew/etc/nginx/nginx.conf syntax is ok
nginx: configuration file /opt/homebrew/etc/nginx/nginx.conf test is successful
darina@MacBook-Pro ~ % brew services start nginx
==> Successfully started `nginx` (label: sh.brew.nginx)
darina@MacBook-Pro ~ % brew services list | grep nginx
nginx         started         darina ~/Library/LaunchAgents/sh.brew.nginx.plist
</details>

darina@MacBook-Pro ~ % nano /opt/homebrew/etc/nginx/servers/my_site  
darina@MacBook-Pro ~ % nginx -t  
darina@MacBook-Pro ~ % brew services reload nginx

<details>
nginx: [warn] conflicting server name "localhost" on 0.0.0.0:8080, ignored
nginx: the configuration file /opt/homebrew/etc/nginx/nginx.conf syntax is ok
nginx: configuration file /opt/homebrew/etc/nginx/nginx.conf test is successful
Stopping `nginx`... (might take a while)
==> Successfully stopped `nginx` (label: sh.brew.nginx)
==> Successfully started `nginx` (label: sh.brew.nginx)
</details>

Check: 
```bash
darina@MacBook-Pro ~ % tail -f /opt/homebrew/var/log/nginx/access.log
127.0.0.1 - - [06/Oct/2026:13:22:00 +0600] "GET / HTTP/1.1" 200 896 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.6.2 Safari/605.1.15"
127.0.0.1 - - [06/Oct/2026:13:22:00 +0600] "GET /favicon.ico HTTP/1.1" 404 153 "http://localhost:8080/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.6.2 Safari/605.1.15"
127.0.0.1 - - [06/Oct/2026:13:28:24 +0600] "GET /api/test HTTP/1.1" 404 153 "-" "curl/8.7.1"
127.0.0.1 - - [06/Oct/2026:13:29:16 +0600] "GET /api/test HTTP/1.1" 404 153 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.6.2 Safari/605.1.15" #mine
```