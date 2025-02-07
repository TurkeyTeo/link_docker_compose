FROM nginx:latest
# 删除原有配置文件
RUN rm /etc/nginx/conf.d/default.conf
# 静态文件拷贝容器，并解压
#ADD phone.tar.gz /opt/
#ADD web.tar.gz /opt/
# 添加新配置文件
ADD ./nginx.conf /etc/nginx/conf.d/
# 关闭守护模式
CMD ["nginx","-g","daemon off;"]


