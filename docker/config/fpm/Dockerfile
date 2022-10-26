FROM php:8.1-fpm-buster

RUN apt update && apt install -y mariadb-client vim procps curl libcurl4-openssl-dev libonig-dev zlib1g-dev libpng-dev git zip libxml2 libxml2-dev libjpeg-dev libpng-dev

RUN docker-php-ext-configure gd --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install pdo_mysql curl mbstring xml

#RUN yes | pecl install xdebug

RUN php -r "copy('https://getcomposer.org/composer-1.phar', '/usr/bin/composer');" && chmod +x /usr/bin/composer

ARG DEV_UID
ARG DEV_GID
RUN groupadd site -g ${DEV_GID}
RUN useradd site -u ${DEV_UID} -g ${DEV_GID} -m

USER site
RUN curl -L https://raw.github.com/git/git/master/contrib/completion/git-prompt.sh > ~/.bash_git
RUN curl -L https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash > ~/.completion_git
RUN mkdir ~/homekeep && touch ~/homekeep/.bash_history && ln -s ~/homekeep/.bash_history ~/
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash && export NVM_DIR="$HOME/.nvm" && [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" && nvm install v14.15.3 --default && npm install -g yarn
