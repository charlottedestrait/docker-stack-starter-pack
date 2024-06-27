# Docker stack starter pack

## Installation


### 1. Rename the cloned directory from "docker-stack-starter-pack" to your project name

```shell
mv docker-stack-starter-pack {your_project_name}
```

Then, remove the `.git` folder :

```shell
cd {your_project_name}
rm -rf .git
```

### 2. Create the .env file

```shell
cd {your_project_name}
mv .env.example .env
```

#### 2.1 Add your `DEV_UID` and `DEV_GID`
```shell
cd {your_project_name}
echo "DEV_UID=$(id -u)" >> .env && echo "DEV_GID=$(id -g)" >> .env
```

#### 2.2 Set your project name

Fill the `PROJECT_NAME` value in the .env file :
```shell
PROJECT_NAME={your_project_name}
```

### 3. Add the host name to your vhost file
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
