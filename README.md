# docker.alpine.nginx.hugo.livereload #

 > Docker: 17.12.0-ce, build c97c6d6

 > Alpine: 3.6.0

 > Hugo: 0.32.4

 > Nginx: 1.13.8

 > LiveReload: 0.4.0 | build from node: 8.5.0 


## debug | WIP ##


hugo server \
--watch=true \
--cleanDestinationDir \
--renderToDisk \
--port=1313 \
--liveReloadPort=1313 \
--disableFastRender \
--bind="0.0.0.0" \
--buildDrafts \
--ignoreCache \
--navigateToChanged \
--noHTTPCache \
--verbose



hugo server \
--source="blog" \
--watch=true \
--cleanDestinationDir \
--renderToDisk \
--port=80 \
--liveReloadPort=80 \
--disableFastRender \
--bind="0.0.0.0" \
--buildDrafts \
--ignoreCache \
--navigateToChanged \
--noHTTPCache \
--verbose








### Setup: ###
 - folder structure for docker.alpine:
    - ``var/www/app/``

 - folder structure for the lite-server:
    -  ``var/www/app/public/index.html``


# debug nginx #

```
docker run \
-p 80:80 \
--name debug.dev \
-it --rm researchranks/debug:latest /bin/ash
```




### Example: ###

 - ``Docker run wants absolute paths``
 - ``docker-compose is just a stand-in for the docker-engine client``
 - Start with ``docker-compose up``
 - Otherwise use our custom bash command ``dockr`` for complex docker shortcuts

```bash
docker run \
-v $PWD/app:/var/www/app \
-p 80:1313 \
--name alpine.hugo.dev \
-it --rm researchranks/alpine.hugo:latest /bin/ash
```

```bash
docker run \
-v $PWD/app:/var/www/app \
-p 80:1313 \
--name alpine.hugo.dev \
-it --rm researchranks/alpine.hugo /bin/ash
```

### Starting Hugo Inside Of A Docker Container ###

```
hugo server \
--bind="0.0.0.0" \
--disableFastRender \
--watch=true \
--verbose \
--port=1313 \
--disableLiveReload=false
```
```
docker run \
-v $PWD/app:/var/www/app \
--name alpine.hugo.dev \
--net=host \ 
-it --rm researchranks/alpine.hugo /bin/ash
```

## -- livereload working -- ##

docker run \
-v $PWD/app:/var/www/app:rw \
-p 80:80 \
--name alpine.hugo.dev \
-it --rm researchranks/alpine.hugo /bin/ash

hugo server \
--bind="0.0.0.0" \
--port=80 \
--buildDrafts \
--watch=true \
--disableFastRender \
--ignoreCache \
--liveReloadPort=80 \
--navigateToChanged \
--noHTTPCache

## ---------------- ##



