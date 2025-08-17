# 编译前端文件
```shell
cd ui
npm build
```

# 打包jar文件
```shell
& "D:\dev\apache-maven-3.8.6\bin\mvn.cmd" -B package -DskipTests --file pom.xml
```

# 构建docker镜像
```shell
docker build -t anirss1:test . -f docker/Dockerfile
```

# 镜像导出
```shell
docker save -o anirss1.tar anirss1:test
```