# Docker image: Node 10.15

## Build image
```bash
docker build -f Dockerfile --build-arg ENV_USER=$(whoami) -t david/node10.25 .
```

## Create volume
```bash
VOLUME_NAME="my-volume"
VOLUME_PATH="path/in/host"
docker volume create --driver local --opt type=none --opt device=${VOLUME_PATH} --opt o=bind ${VOLUME_NAME}
```

## Verify volume
```bash
docker volume inspect ${VOLUME_NAME}
```

## Run container
```bash
docker run -it --rm --name my-node10 -p 1234:1234 -v ${VOLUME_NAME}:/home/$(whoami)/vol david/node10.15 /bin/sh
```

## Uninstall
```bash
docker image rm david/node10.15
docker volume rm ${VOLUME_NAME}
```