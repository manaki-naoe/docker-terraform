# docker-terraform

## Step.1

Modify the variable if you want to change

| variable          | value             |
| :---------------- | :---------------- |
| terraform_version | terraform version |

docker build
```bash
$ docker build -t alpine-terraform
```

## Step.2

docker-compose.yml

Edit [Your terraform project path]
```yml
version: '3'
services:
  web_container:
    image: alpine-terraform
    restart: always
    container_name: terraform_container
    volumes:
      - [Your terraform project path]:/terraform
    tty: true
```

docker-compose
```bash
$ docker-compose up -d
```

## step.3
Access the container

```bash
docker exec -it terraform_container /bin/sh
```

**Get started with terraform**