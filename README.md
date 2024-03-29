# image-cn

众所周知，在下载Dockerhub、ghcr、的镜像，对于各显神通的开发者已经不是大问题(各路镜像仓库等)，但是问题最多的往往出现在`Docker Build`这个步骤。`Docker Build`本身是可以支持`Proxy`等各种代理，但是问题很多。对于`apt-get`等命令，使用`Proxy`可能导致各种崩溃，不使用又可能导致速度爆炸慢。更何况`Proxy`的还只有Linux支持连接到本地的代理服务，总之问题往往很多，很难搞定。

至于换源？一般来说Dockerhub下载的镜像都是原版的镜像，加上又没有合适的换源脚本，开发者要目手动开启编辑器换源的，要目自己写脚本去换源。

假设有人愿意换源，然后下载了一个换源脚本，发现又需要安装`lsb-release`，然后一搜安装方法，竟然又是`apt-get install lsb-release`，这下闭环了。我当场就是为了`apt`速度慢换源，结果换源又需要依赖`apt`。

综上所述，唯一的解决方法就是类似阿里云提供的**海外构建**的方案，把换源的步骤放在海外做，然后把构建好的镜像同步回来，这也是本仓库：适合在国区使用的Docker镜像（已完成换源操作）的目的所在。


