## Build das imagens

```
# autenticar no registry
docker login registry-domain-aqui

# caso precise buildar novamente a imagem e atualizar o registry
docker build -t leidison/php:8.0-postgres ./php/8.0/postgres --no-cache
docker build -t leidison/php:7.4-postgres ./php/7.4/postgres --no-cache
docker build -t leidison/php:7.4-sqlsrv ./php/7.4/sqlsrv --no-cache
docker build -t leidison/php:7.2-sqlsrv ./php/7.2/sqlsrv --no-cache
docker build -t leidison/php:7.2-postgres ./php/7.2/postgres --no-cache

# subir a imagem para registry
docker push leidison/php:8.0-postgres
docker push leidison/php:7.4-postgres
docker push leidison/php:7.4-sqlsrv
docker push leidison/php:7.2-sqlsrv
docker push leidison/php:7.2-postgres

```
