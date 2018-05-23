# dokku



**multiple buildpacks**

```
# .buildpacks
https://github.com/heroku/heroku-buildpack-nodejs.git#v123
https://github.com/heroku/heroku-buildpack-python.git#v134
```

```
# Procfile
web: npm start
cron: python3 -m cronjob
```



**subdirectory**

```
# root package.json
{
    "name": "root",
    "version": "0.0.1",
    "scripts": {
        "postinstall": "npm install --prefix server"
    }
}
```

```
Procfile
web: npm start --perfix server
```



run cron tasks

```
dokku ps:scale my-web-app cron=1
dokku enter my-web-app cron <COMMAND> # dokku enter my-web-app cron python3 -m cronjob
```



