# 《Linux 性能优化实战》案例

## 部分案例列表

* [应用程序 CPU 使用率过高案例](nginx-high-cpu/README.md)
* [用户 CPU 使用率过高案例](nginx-short-process/README.md)
* [iowait 使用率过高案例](high-iowait-process/README.md)
* [未利用系统缓存导致 I/O 缓慢案例](io-cached/README.md)
* [内存泄漏案例](mem-leak/README.md)
* [狂打日志案例](logging-app/README.md)
* [I/O延迟案例](io-latency/README.md)
* [MySQL 案例](mysql-slow/README.md)
* [Redis 延迟案例](redis-slow/README.md)

## 依赖环境

所有案例的编译运行都需要预先安装 Docker 以及必要的编译工具。以 CentOS7.5 为例，可以运行以下命令来安装它们：

```sh
sudo yum install -y docker-ce
```
