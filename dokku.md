# dokku

**simple web app**

```
$ dokku create:apps my-web-app
```

Procfile

```
web: python3 -m server
```

ssl

```
$ dokku plugins:install https://github.com/dokku/dokku-letsencrypt.git
$ dokku config:set --no-restart my-web-app DOKKU_LETSENCRYPT_EMAIL=your@email.com
$ dokku letsencrypt my-web-app
```

deploy from local machine

```
$ git remote add dokku dokku@domain.com:my-web-app
$ git push dokku master
```

**backing services**

install the plugin

```
$ dokku plugin:install https://github.com/dokku/dokku-mongo.git
```

create service

```
$ dokku mongo:create mongodb
```

linking service

```
$ dokku mongo:link mongodb my-web-app
```

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
# Procfile
web: npm start --perfix server
```

**run cron tasks**

```
$ dokku ps:scale my-web-app cron=1
$ dokku enter my-web-app cron <COMMAND> # $ dokku enter my-web-app cron python3 -m cronjob
```



