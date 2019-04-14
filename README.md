# Docker Commands for development

As preparation, you need to create a folder to store mysql shared data.
```
mkdir -p ~/shared_docker/mysql/5.7
```

Then let's run docker commands.
```
$ docker-compose up
$ docker-compose run rails rake db:create
$ docker-compose run rails bundle exec rails db:migrate
$ docker-compose exec rails bundle exec rails c
$ docker-compose logs -f # see logs
```

# Trouble Shooting

```
$ docker-compose run rails bundle exec bin/rails c
Could not find rake-12.3.2 in any of the sources
Run `bundle install` to install missing gems.
```
In this case, the bundle files are not installed in a correct place. Let's run with "--path" option.

```
$ bundle install --path vendor/bundle
```


```
$ docker-compose up
/bin/sh: 1: [: missing ]
```

In this case, you have a wrong syntax in Dockerfile.dev. Please check it and re-run the command.
