## 常用安全工具自动生成仓库

[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/xiecat/sec-docker/Publish%20sec-custom%20to%20Hub)](https://github.com/xiecat/sec-docker/actions)
使用 `github action` 生成 docker 镜像并且自动推送给 `DockerHub`

目前已经支持 `amd64` 、`arm64`、 `arm`平台   

**latest** 是最近一次更新版本   
**nightly** 当天版本   
**yyyy-mm-dd** 某天更新的版本   

## 国内加速构建

国内网络环境太差。为了好构建可以加入国内源测试。测试结束后移除即可

```shell
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories
RUN pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

## 定期更新镜像

每天自动构建

### 基础镜像

| 版本                                                 | 镜像大小                                                                                                                                                                     |
|:--------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| `docker pull becivells/alpine-chromium:latest`     | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/alpine-chromium/latest)](https://hub.docker.com/r/becivells/alpine-chromium/tags)         |
| `docker pull becivells/alpine-chromium-py3:latest` | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/alpine-chromium-py3/latest)](https://hub.docker.com/r/becivells/alpine-chromium-py3/tags) |
| `docker pull becivells/gobase-1.5:latest`          | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/gobase-1.5/latest)](https://hub.docker.com/r/becivells/gobase-1.5/tags)                   |
| `docker pull becivells/gobase-1.6:latest`          | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/gobase-1.6/latest)](https://hub.docker.com/r/becivells/gobase-1.6/tags)                   |
| `docker pull becivells/gobase-1.7:latest`          | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/gobase-1.7/latest)](https://hub.docker.com/r/becivells/gobase-1.7/tags)                   |
| `docker pull becivells/alpine-gcc:latest`          | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/alpine-gcc/latest)](https://hub.docker.com/r/becivells/alpine-gcc/tags)                   |

### 应用镜像

|                    版本                     | 镜像大小                                                                                                                                                   |
|:-----------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `docker pull becivells/anew:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/anew/latest)](https://hub.docker.com/r/becivells/anew/tags)             |
|    `docker pull becivells/nmap:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/nmap/latest)](https://hub.docker.com/r/becivells/nmap/tags)             |
|    `docker pull becivells/zmap:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/zmap/latest)](https://hub.docker.com/r/becivells/zmap/tags)             |
|   `docker pull becivells/chaos:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/chaos/latest)](https://hub.docker.com/r/becivells/chaos/tags)           |
|   `docker pull becivells/dismap:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/dismap/latest)](https://hub.docker.com/r/becivells/dismap/tags)         |
|   `docker pull becivells/vulmap:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/vulmap/latest)](https://hub.docker.com/r/becivells/vulmap/tags)         |
|   `docker pull becivells/fofax:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/fofax/latest)](https://hub.docker.com/r/becivells/fofax/tags)           |
| `docker pull becivells/interactsh:latest` | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/interactsh/latest)](https://hub.docker.com/r/becivells/interactsh/tags) |
|   `docker pull becivells/nabbu:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/nabbu/latest)](https://hub.docker.com/r/becivells/nabbu/tags)           |
|   `docker pull becivells/nuclei:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/nuclei/latest)](https://hub.docker.com/r/becivells/nuclei/tags)         |
| `docker pull becivells/sec-custom:latest` | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/sec-custom/latest)](https://hub.docker.com/r/becivells/sec-custom/tags) |
|    `docker pull becivells/xray:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/xray/latest)](https://hub.docker.com/r/becivells/xray/tags)             |
|   `docker pull becivells/amass:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/amass/latest)](https://hub.docker.com/r/becivells/amass/tags)           |
| `docker pull becivells/crawlergo:latest`  | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/crawlergo/latest)](https://hub.docker.com/r/becivells/crawlergo/tags)   |
|    `docker pull becivells/dnsx:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/dnsx/latest)](https://hub.docker.com/r/becivells/dnsx/tags)             |
|   `docker pull becivells/httpx:latest`    | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/httpx/latest)](https://hub.docker.com/r/becivells/httpx/tags)           |
| `docker pull becivells/ksubdomain:latest` | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/ksubdomain/latest)](https://hub.docker.com/r/becivells/ksubdomain/tags) |
|   `docker pull becivells/notify:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/notify/latest)](https://hub.docker.com/r/becivells/notify/tags)         |
|  `docker pull becivells/proxify:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/proxify/latest)](https://hub.docker.com/r/becivells/proxify/tags)       |
|  `docker pull becivells/dumpall:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/dumpall/latest)](https://hub.docker.com/r/becivells/dumpall/tags)       |
| `docker pull becivells/pocsuite3:latest`  | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/pocsuite3/latest)](https://hub.docker.com/r/becivells/pocsuite3/tags)   |
| `docker pull becivells/dirsearch:latest`  | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/dirsearch/latest)](https://hub.docker.com/r/becivells/dirsearch/tags)   |
|  `docker pull becivells/massdns:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/massdns/latest)](https://hub.docker.com/r/becivells/massdns/tags)       |
| `docker pull becivells/subfinder:latest`  | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/subfinder/latest)](https://hub.docker.com/r/becivells/subfinder/tags)   |
| `docker pull becivells/oneforall:latest`  | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/oneforall/latest)](https://hub.docker.com/r/becivells/oneforall/tags)   |
|  `docker pull becivells/masscan:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/masscan/latest)](https://hub.docker.com/r/becivells/masscan/tags)       |
|  `docker pull becivells/yaklang:latest`   | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/becivells/yaklang/latest)](https://hub.docker.com/r/becivells/yaklang/tags)       |



## FAQ

### ksubdomain 扫描无结果

起一个容器先执行一下，如果无结果。考虑配置文件问题
docker 是一次性容器。内部ip和mac都是随时会变化的。ksubdomain 生成的配置文件ip mac是固定的。运行之前先删除 `ksubdomain.yaml` 可参考我这里的 shell

```shell
#!/usr/bin/env sh

cd /app/
while true;do
  rm -rf ksubdomain.yaml
  for domain in $(cat domains.txt);do
    ksubdomain enum  -d $domain -od -silent --skip-wild|anew subdomains.txt;
  done
  echo "任务完成共计 $(cat subdomains.txt|wc -l) 子域名"|notify
  sleep 7200;
 done
```
