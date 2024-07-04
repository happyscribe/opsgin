# Opsgin
To build and redeploy this application follow the steps below:
1. `docker build --rm --platform linux/amd64 -f docker/Dockerfile.linux.amd64 -t opsgin .`
2. `docker tag opsgin registry.heroku.com/opsgin/web`
3. `docker push registry.heroku.com/opsgin/web`
4. `heroku container:release web --app opsgin`

The opsgin Heroku app has a scheduler task that will run the sync command every 10 minutes.