FROM alpine:3.17

ARG ENV_USER
ARG ENV_PWD
RUN adduser $ENV_USER; echo $ENV_USER':'$ENV_PWD | chpasswd
USER $ENV_USER

WORKDIR /home/$ENV_USER