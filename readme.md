# Opsgin
To build and redeploy this application:
```bash
heroku container:login
docker build --rm --platform linux/amd64 -f docker/Dockerfile.linux.amd64 -t opsgin .
docker tag opsgin registry.heroku.com/opsgin/web
docker push registry.heroku.com/opsgin/web
heroku container:release web --app opsgin
```

The opsgin Heroku app has a scheduler task that will run the sync command every 10 minutes.