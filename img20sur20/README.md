to deploy the application, run local container:

docker run --rm -p 127.0.0.1:8080:8080 -p 127.0.0.1:8000:8000 -p 127.0.0.1:9000:9000 -e "MODULES=github.com/dbenque/appengine_apps/img20sur20 github.com/dbenque/meteoArchive/moduleMeteoArchive github.com/dbenque/GAE-Image-Server github.com/dbenque/goAppengineToolkit/moduleDefault" dbenque/goappengine

then get into the container:

#to get the container id
docker ps

#shell into the container
docker exec -ti d1ca8373bb91 /bin/bash

#deploy the modules
goapp deploy moduleDefault/default.yaml GAE-Image-Server/app.yaml moduleMeteoArchive/meteoArchive.yaml
