## docker-compose LNMP 使用方法

1. 切换到当前目录
2. 根据当前项目配置docker-compose.yml和docker.env（docker-compose.yml所需环境变量）
   若使用到MySQL服务,MySQL镜像env_file在mysql/config.env文件中配置
3. 启动服务
   - 环境变量生效：source docker.env
   - 启动服务：docker-compose up -d

