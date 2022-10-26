FROM httpd:2.4

ARG DEV_UID
ARG DEV_GID
RUN groupadd site -g ${DEV_GID}
RUN useradd site -u ${DEV_UID} -g ${DEV_GID} -m