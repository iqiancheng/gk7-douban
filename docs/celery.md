## celery 任务调度服务说明

celery下载图片、发送邮件
在`gk7-douban`项目中需要以`root`用户运行，设置环境变量：

```bash
export C_FORCE_ROOT='root'
```


### 启动 ###

```bash
celery -A helper.tasks worker -l info -D -f /var/log/celery/gk7-douban.log --pidfile=/var/run/celery.pid
```

+ `-D` 守护进程
+ `-f` 日志文件路径
+ `--pidfile` 运行id文件

### 停止 ###

```bash
ps auxww | grep celery | awk '{print $2}' | xargs kill -9
```