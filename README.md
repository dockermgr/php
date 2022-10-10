## 👋 Welcome to php 🚀  

php README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update php
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/php/dataDir"
git clone "https://github.com/dockermgr/php" "$HOME/.local/share/CasjaysDev/dockermgr/php"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/php/dataDir/." "$HOME/.local/share/srv/docker/php/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/php:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-php \
--hostname casjaysdev-php \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/php/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/php/dataDir/config:/config:z \
-p 19001:19001 \
casjaysdevdocker/php:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  php:
    image: casjaysdevdocker/php
    container_name: php
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-php
    volumes:
      - $HOME/.local/share/srv/docker/php/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/php/dataDir/config:/config:z
    ports:
      - 19001:19001
    restart: always
```

## Author  

🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ dockermgr: [Github](https://github.com/dockermgr) ⛵  
