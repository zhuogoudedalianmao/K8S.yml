FROM nginx:1.12
# set timezone
COPY ./Shanghai /etc/localtime
COPY ./Shanghai /usr/share/zoneinfo/Asia/Shanghai
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

COPY ./proxy_params /etc/nginx/proxy_params
COPY ./nginx.conf /etc/nginx/nginx.conf
