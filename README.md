## Build das imagens

```
# autenticar no registry
docker login registry-domain-aqui

# caso precise buildar novamente a imagem e atualizar o registry
docker build -t leidison/php:8.0-postgres ./php/8.0/postgres --no-cache

# subir a imagem para registry
docker push leidison/php:8.0-postgres

```
