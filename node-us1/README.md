# Server & Client
This node contains the server and the client and a proxy server, to set this up just use the `docker-compose.yml` file when creating a new stack.

## Volumes
Three volumes need to be created before set-up, no actual data will be written to these volumes and they are purely for configuration.

 1. `waifu_config`
This volume must contain the server config file, an example of this file would be [here](https://github.com/Waifu-pics/api/blob/master/config.example.yml). This file should be named `config.yml`
 
 2. `nginx_config`
This volume has the NGINX config file, this file must be named `default.conf`. The config in this folder named `default.conf` has the configuration that should be used when deploying the service.

3. `nginx_cert`
This volume contains certificates for SSL, if you do not need SSL just remove the volume from the compose file and be sure to change the `default.conf` file. If you use the default configuration, make sure the file names are `waifu.pem` and `waifu.key` and located at the root of this volume.

## Important notes
The client image is prebuilt on docker and uses the official API url by default, if you want to selfhost your own backend, you need to create your own docker image and change the compose file accordingly. Sorry self hosters 🥴