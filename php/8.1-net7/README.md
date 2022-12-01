Fork from https://gitlab.com/ric_harvey/nginx-php-fpm


## Overview
This is a Dockerfile/image to build a container for nginx and php-fpm, with the ability to pull website code from git when the container is created, as well as allowing the container to push and pull changes to the code to and from git. The container also has the ability to update templated files with variables passed to docker in order to update your code and settings. There is support for lets encrypt SSL configurations, custom nginx configs, core nginx/PHP variable overrides for running preferences, X-Forwarded-For headers and UID mapping for local volume support.

If you have improvements or suggestions please open an issue or pull request on the GitHub project page.

### Versioning
| Docker Tag | Git Release | Nginx Version | PHP Version | Alpine Version |
|-----|-------|-----|--------|--------|
| latest/2.1.4 | Master Branch |1.21.6 | 8.1.9 | 3.16 |

For other tags please see: [versioning](https://github.com/richarvey/nginx-php-fpm/blob/master/docs/versioning.md)

__NOTE:__ From 2.0.5 onwards there are x86 and arm64 builds available


## Quick Start
To pull from docker hub:
```
docker pull jpratama7/php-fpm-nginx:latest
```
### Running
To simply run the container:
```
sudo docker run -d jpratama7/php-fpm-nginx
```
To dynamically pull code from git when starting:
```
docker run -d -e 'GIT_EMAIL=email_address' -e 'GIT_NAME=full_name' -e 'GIT_USERNAME=git_username' -e 'GIT_REPO=github.com/project' -e 'GIT_PERSONAL_TOKEN=<long_token_string_here>' jpratama7/php-fpm-nginx:latest
```

You can then browse to ```http://<DOCKER_HOST>``` to view the default install files. To find your ```DOCKER_HOST``` use the ```docker inspect``` to get the IP address (normally 172.17.0.2)