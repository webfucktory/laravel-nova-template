```shell
export BASE_IMAGE=ghcr.io/{owner}/{repository}
```

### Base

> Note: replace `NOVA_EMAIL`, `NOVA_PASSWORD` with correct values.
```shell
docker build \
  --build-arg nova_email=NOVA_EMAIL \
  --build-arg nova_password=NOVA_PASSWORD \
  -f Dockerfile \
  -t $BASE_IMAGE \
  ../..
```

### App

```shell
docker build \
  -f app.Dockerfile \
  -t $BASE_IMAGE/app \
  ../..
```

### Webserver

```shell
docker build \
  -f webserver.Dockerfile \
  -t $BASE_IMAGE/webserver \
  ../..
```

### Queue Worker

```shell
docker build \
  -f queue.Dockerfile \
  -t $BASE_IMAGE/queue \
  ../..
```

### Schedule Runner

```shell
docker build \
  -f schedule.Dockerfile \
  -t $BASE_IMAGE/schedule \
  ../..
```
