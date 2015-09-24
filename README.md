# docker-mailcatcher

A [Docker](https://docker.com/) container for [MailCatcher](http://mailcatcher.me/).

## Run the container

    CONTAINER="mailcatcher" && sudo docker run \
      --name "${CONTAINER}" \
      -h "${CONTAINER}" \
      -p 80:80 \
      -p 443:443 \
      -p 25:25 \
      -e SERVER_NAME="localhost" \
      -e TIMEZONE="Etc/UTC" \
      -e TIMEOUT="300" \
      -e PROTOCOLS="https,http" \
      -e HTTP_BASIC_AUTH_USERNAME="container" \
      -e HTTP_BASIC_AUTH_PASSWORD="" \
      -d \
      dockerizedrupal/mailcatcher:1.0.7

## Build the image

    TMP="$(mktemp -d)" \
      && git clone https://github.com/dockerizedrupal/docker-mailcatcher.git "${TMP}" \
      && cd "${TMP}" \
      && git checkout 1.0.7 \
      && sudo docker build -t dockerizedrupal/mailcatcher:1.0.7 . \
      && cd -

## Changing the container behaviour on runtime through environment variables

    // TODO

## License

**MIT**
