# recipe-app-api-django
Recipe API by Django

# Coding path
- 1: 创建 requirements.txt， 指定所需要的各种软件的版本
- 2: 创建 Dockerfile， 用来创建自己适用的docker
- 3: 创建 .dockerignore 文件，告诉docker有哪些本地文件需要在创建 image 的时候忽略
- 4: 创建 app/ 文件夹
- 5: 运行 “docker build .” 命令，来创建image

- 6: 创建 docker-compose.yml 文件
- 7: 运行 “docker-compose build” 命令来创建虚拟机

# 添加 Linting 工具 flake8
- 创建配置文件 requirements.dev.txt, 这是只有在dev模式下才安装的软件包
- 在app目录下创建 .flake8 配置文件
- 运行 `docker compose run --rm app sh -c "flake8" ` 命令即可进行linting的检查

# 创建 Django 项目
`docker compose run --rm app sh -c "django-admin startproject app ."`

# 启动Docker 服务器
`docker compose up`

# 使用 Github Actions 作为自动化测试/部署工具
- 1: 创建配置文件 .github/workflows/checks.yml
    - 1.1: 设置 Trigger
    - 1.2: 添加Steps，以便执行testing和linting
    - 1.3: 可以在 .github/workflows/ 目录下创建其他文件，例如 deployments.yml 等， 来表示不同的自动化流程。文件名可以任意指定
