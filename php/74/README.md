Fork from https://gitlab.com/ric_harvey/nginx-php-fpm

## Quick Start
To pull from docker hub:
```
docker pull jpratama/php-fpm-nginx:latest
```
### Running
To simply run the container:
```
sudo docker run -d jpratama/php-fpm-nginx
```
To dynamically pull code from git when starting:
```
docker run -d -e 'GIT_EMAIL=email_address' -e 'GIT_NAME=full_name' -e 'GIT_USERNAME=git_username' -e 'GIT_REPO=github.com/project' -e 'GIT_PERSONAL_TOKEN=<long_token_string_here>' jpratama/php-fpm-nginx:latest
```

You can then browse to ```http://<DOCKER_HOST>``` to view the default install files. To find your ```DOCKER_HOST``` use the ```docker inspect``` to get the IP address (normally 172.17.0.2)

For more detailed examples and explanations please refer to the documentation.
