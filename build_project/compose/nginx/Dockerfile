FROM nginx:latest

# 删除原有配置文件
RUN rm /etc/nginx/conf.d/default.conf

# 添加新配置文件
ADD ./nginx.conf /etc/nginx/conf.d/

# 静态文件拷贝容器，并解压
COPY phone.tar.gz /usr/share/nginx/html/phone.tar.gz
COPY admin.tar.gz /usr/share/nginx/html/admin.tar.gz

RUN tar -xzf /usr/share/nginx/html/phone.tar.gz -C /usr/share/nginx/html/ && \
    tar -xzf /usr/share/nginx/html/admin.tar.gz -C /usr/share/nginx/html/ && \
    rm /usr/share/nginx/html/phone.tar.gz /usr/share/nginx/html/admin.tar.gz

# 关闭守护模式
CMD ["nginx", "-g", "daemon off;"]