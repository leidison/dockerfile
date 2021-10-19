FROM php:7.4-apache

# MSSQL drivers version
ARG MSSQL_DRIVER_VER=5.8.0

RUN apt-get update -y \
    && a2enmod rewrite \
    && apt-get install -y --no-install-recommends libpq-dev libicu-dev libzip-dev \
    # 
    && apt-get install -y \
        apt-transport-https \
        gnupg \
        unixodbc \
        unixodbc-dev \
        libgss3 \
        odbcinst \
    && curl -s https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
    && curl -s https://packages.microsoft.com/config/debian/9/prod.list > /etc/apt/sources.list.d/mssql-release.list \
    && apt-get update -y \
    && ACCEPT_EULA=Y apt-get install -y \
        msodbcsql17 \
        locales \
    && echo "en_US.UTF-8 zh_CN.UTF-8 UTF-8" > /etc/locale.gen \
    && locale-gen \
    && pecl install -f pdo_sqlsrv-${MSSQL_DRIVER_VER} sqlsrv-${MSSQL_DRIVER_VER} \
    && docker-php-ext-enable pdo_sqlsrv sqlsrv \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*