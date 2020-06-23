# Local Postgres DB 
Running local Postgres DB from Docker on a mac using docker 

## Install client tools
```bash
brew install psql
brew link --force libpq
```
if you use zsh..
```bash
echo 'export PATH="/usr/local/opt/libpq/bin:$PATH"' >> ~/.zshrc
```

## Custom Settings
Edit the 'env.sh' file to set version, user, password etc.  See https://hub.docker.com/_/postgres/ for more detail.
```bash
source ./env.sh
```

## Bring up Postgres Docker Image
```bash
docker-compose up
```

## Connecting to DB
### Access the "Adminer" web based admin tool
http://localhost:8080

### CLI connection to DB
```bash
psql -U postgres -h localhost
```

# Cleanup

## Stop containers
```bash
docker-compose down
```

## Prune local system
> REF: https://docs.docker.com/config/pruning/

```bash
docker container prune
docker network prune
docker image prune
docker volume prune

# or do this....
docker system prune  --volumes
```