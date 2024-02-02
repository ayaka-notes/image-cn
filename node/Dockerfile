# 使用方法: docker build -t node:latest --build-arg nodetag=18.18.2 .

ARG nodetag=latest

FROM node:${nodetag}

# 此步骤必须在海外机器构件
RUN apt-get update && apt-get install lsb-release

# 换源apt
RUN curl -sSL https://linuxmirrors.cn/main.sh -o main.sh \
 && chmod 755 ./main.sh \
 && bash main.sh --source mirrors.aliyun.com \
 && rm -rf ./main.sh \
 && apt-get update

# 换源npm
RUN npm config set registry https://registry.npmmirror.com