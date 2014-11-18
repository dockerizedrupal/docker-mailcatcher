# docker-mailcatcher

A [Docker](https://docker.com/) container for [MailCatcher](http://mailcatcher.me/).

## MailCatcher (DEVELOPMENT BRANCH)

### Run the container

Using the `docker` command:

    CONTAINER="mailcatcher" && sudo docker run \
      --name "${CONTAINER}" \
      -h "${CONTAINER}" \
      -p 1080:1080 \
      -p 1025:1025 \
      -d \
      simpledrupalcloud/mailcatcher:dev
      
Using the `fig` command

    TMP="$(mktemp -d)" \
      && git clone http://git.simpledrupalcloud.com/simpledrupalcloud/docker-mailcatcher.git "${TMP}" \
      && cd "${TMP}" \
      && git checkout dev \
      && fig up

### Build the image

    TMP="$(mktemp -d)" \
      && git clone http://git.simpledrupalcloud.com/simpledrupalcloud/docker-mailcatcher.git "${TMP}" \
      && cd "${TMP}" \
      && git checkout dev \
      && sudo docker build -t simpledrupalcloud/mailcatcher:dev . \
      && cd -

## License

**MIT**
