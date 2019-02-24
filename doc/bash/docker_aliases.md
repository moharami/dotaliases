# Docker alias and function #


### Get latest container ID ###
- **dl** : `docker ps -l -q`


### Get container process ###
- **dps** :`docker ps`

### Get process included stop container ###
- **dpa** : `docker ps -a`

#### Get images ###
- **di** :`docker images`

### Get container IP ###
- **dip** :`docker inspect --format '{{ .NetworkSettings.IPAddress }}'`

### Run deamonized container ###
    e.g., $dkd base /bin/echo hello
- **dkd** :`docker run -d -P`

#### Run interactive container ###
    e.g., $dki base /bin/bash
- **dki** :`docker run -i -t -P`

#### Execute interactive container ### 
    e.g., $dex base /bin/bash
- **dex** :`docker exec -i -t`

#### Stop all containers ###
- **dstop()** ‍‍‍`docker stop $(docker ps -a -q);`

#### Remove all containers ###
- **drm()** `{ docker rm $(docker ps -a -q); }`

#### Stop and Remove all containers ###
- **drmf** :`docker stop \$(docker ps -a -q) && docker rm $(docker ps -a -q)`

#### Remove all images ###
- **dri()** `{ docker rmi $(docker images -q); }`

#### Dockerfile build ### 
    e.g., $dbu tcnksm/test 
- **dbu()** `{ docker build -t=$1 .; }`

#### Show all alias related docker ###
- **dalias()** `{ alias | grep 'docker' | sed "s/^\([^=]*\)=\(.*\)/\1 => \2/"| sed "s/['|\']//g" | sort; }`

#### Bash into running container ###
- **dbash()** `{ docker exec -it $(docker ps -aqf "name=$1") bash; }`