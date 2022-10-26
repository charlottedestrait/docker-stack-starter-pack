# Docker stack starter pack

## Installation

### 1. Rename the cloned directory from "docker-stack-starter-pack" to your project name

### 2. Remove the .git folder
```shell
cd {your_project_name}
rm -rf .git
```

### 3. Replace all "docker-stack-starter-pack" words by your project name

### 4. Generate your .env file by running this command
```shell
cd {your_project_name}
echo "DEV_UID=$(id -u)" >> .env && echo "DEV_GID=$(id -g)" >> .env
```

### 5. Add the host name to your vhost file
```shell
127.0.0.1 www.{your_project_name}.dpdev
```

## Stack usage
### Start
```shell
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
```
### Stop
```shell
docker-compose -f docker-compose.yml -f docker-compose.dev.yml down
```
### Enter the cli
```shell
docker exec -ti {your_project_name}_php_fpm bash
```
