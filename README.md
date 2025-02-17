```shell
├── docker-compose.yml      # 部署编排文件
├── compose                 # 存放各容器服务Dockerfile配置文件
│   ├── mysql
│   │   ├── conf
│   │   │   └── my.cnf      # mysql配置文件
│   │   ├── init
│   │   │   └── init.sql    # mysql初始化启动脚本
│   │   └── sqldata 
│   │       └── import.sql  # sql数据
│   ├── nginx
│   │   ├── Dockerfile      # 构建nginx镜像的dockerfile
│   │   ├── log             # 挂载保存nginx容器内日志文件夹
│   │   │   ├── access.log
│   │   │   └── error.log
│   │   ├── nginx.conf      # nginx配置文件
│   │   ├── phone.tar.gz    # vue静态打包文件手机端
│   │   └── admin.tar.gz    # react静态打包文件后台管理系统
│   ├── redis
│   │   └── redis.conf      # redis配置文件
│   └── uwsgi               # 挂载保存flask+uwsgi容器内uwsgi日志
└── backend_project # 项目目录
    ├── app         # 存在项目app
    ├── Dockerfile  # 构建flask+Uwsgi镜像的dockerfile
    ├── logs        # 项目日志
    ├── manage.py
    ├── requirements.txt    #项目依赖
    ├── static      # 静态文件
    ├── uwsgi.ini   # uwsgi配置
    └── uwsgi.log
```


vim /etc/docker/daemon.json

{
    "registry-mirrors": [
        "https://do.nark.eu.org",
        "https://dc.j8.work",
        "https://docker.m.daocloud.io",
        "https://dockerproxy.com",
        "https://docker.mirrors.ustc.edu.cn",
        "https://docker.nju.edu.cn"
    ]
}

sudo systemctl daemon-reload
sudo systemctl restart docker
