
### 问题
docker有两种类型 ：arm64 和 amd64
死活拉不下jdk 17的amd64架构的镜像，只能拉arm64架构的镜像，但是arm64架构的镜像中没有jdk 17的镜像

### docker_jdk17_amd_arm

创建一个临时目录，新建一个 Dockerfile：
FROM --platform=linux/amd64 eclipse-temurin:17-jre
CMD ["java", "-version"]
然后构建：
docker build --platform linux/amd64 -t eclipse-temurin:17-jre-amd64 .

这样构建出来的镜像就是单一 amd64 架构的，而且不会受到本地 manifest 缓存的影响。

### 验证新镜像架构
docker inspect eclipse-temurin:17-jre-amd64 --format='{{.Architecture}}'
现在应该输出 amd64。

### 或者配置代理
- export https_proxy=http://127.0.0.1:6738
- export http_proxy=http://127.0.0.1:6738