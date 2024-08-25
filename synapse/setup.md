# Setup

Before you run docker compose, you need do following operation:

1. Create `synapse-data` volume

    ```shell
    docker volume create synapse-data
    ```

2. Generate config file in `synapse-data`

    ```shell
    docker run -it --rm \
        --mount type=volume,src=synapse-data,dst=/data \
        -e SYNAPSE_SERVER_NAME=<YOUR SERVER NAME>.com \
        -e SYNAPSE_REPORT_STATS=no \
        matrixdotorg/synapse:v1.113.0 generate
    ```

3. Modifiy the config file

    ```shell
    vim /var/lib/docker/volumes/synapse-data/_data/homeserver.yaml
    ```
