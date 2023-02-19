
# What it is

Basic example of a docker container / docker-compose service that receives an username as argument. It creates the same user during container build and switches to that user.

# How to use

## As a container
1. Build
```bash
ENV_USER=$(whoami) ENV_PWD=example docker build -t myimage --build-arg ENV_USER=${ENV_USER} --build-arg=${ENV_PWD} .
```

2. Run
```bash
docker run -it --rm myimage
```

4. Test
```bash
whoami
pwd
```

3. Clean-up
```bash
docker image rm myimage
```

## As a compose service
1. Build + run
```bash
ENV_USER=$(whoami) ENV_PWD=example docker compose up
```

2. Test
```bash
docker exec -it user-arg-test-1 /bin/sh
```

3. Clean-up
```bash
docker compose down
docker image rm user-arg-test
```
