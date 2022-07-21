Run using the dockerfile, no parameters required, just expose port 80. Or use testing/docker-compose.yml and head to port 8080

### edit: location / will proxy pass to DVWA
Creds: admin:password

```
Current error:
testing-coraza-1       | New transaction request
testing-nginx-1        | 2022/07/21 09:47:55 [info] 24#24: *1 client timed out (110: Connection timed out) while waiting for request, client: 172.24.0.1, server: 0.0.0.0:80
testing-coraza-1       | Request error: unexpected EOF
testing-coraza-1       | Transaction 7c1eef8a79fbbe557e60e90fb3bb041e ok
testing-nginx-1        | 2022/07/21 09:48:08 [error] 24#24: *2 upstream timed out (110: Connection timed out) while reading response header from upstream, client: 172.24.0.1, server: , request: "POST /login.php HTTP/1.1", subrequest: "/auth", upstream: "http://172.24.0.4:8080/auth", host: "localhost:8080", referrer: "http://localhost:8080/login.php"
testing-nginx-1        | 2022/07/21 09:48:08 [error] 24#24: *2 auth request unexpected status: 504 while sending to client, client: 172.24.0.1, server: , request: "POST /login.php HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/login.php"
```

Error happens when type is POST and mime-type is muiltipart-form or x-www-form
