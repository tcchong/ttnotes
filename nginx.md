# Nginx

### root vs alias

```
# root
location /s/ {
    root /data/static/;
}
# http://example.com/s/main.js => /data/static/s/main.js
# http://example.com/s/i/not_found.png => /data/static/s/i/not_found.png

# alias
location /s/ {
    alias /data/static/;
}
# http://example.com/s/main.js => /data/static/main.js
# http://example.com/s/i/not_found.png => /data/static/i/not_found.png
```

### error\_page

internal redirect to specific uri

```
error_page 500 502 503 503 /50x.html;
```

change the response code

```
error_page 404 =200 /not_found.png;
```

named location

```
location / {
    error_page 404 = @not_found;
}

location @not_found {
    // do some stuff
}
```



## Ref

* http://nginx.org/en/docs/http/ngx\_http\_core\_module.html



